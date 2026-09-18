# 印刷品管线（实证版）

来源：两个已交付 session——108 页 B5《生物化学简明讲义》（Paged.js 书籍管线，全部页面经 judge 并行验收）与 A4 人物海报（HTML@96dpi 直排，见 `assets/poster-template.html`）。以下规则都踩过坑。

## 1. 两条管线怎么选

| 交付物 | 管线 | 工具链 |
|---|---|---|
| 书籍 / 讲义 / 长报告（多页、页码、目录、公式） | **Paged.js 书籍管线** | markdown → 生成 HTML → Paged.js 分页 → headless Chrome 打 PDF → pymupdf 合并 |
| 海报 / 单页 / 封面 / 证书（一页定稿） | **固定尺寸 HTML 管线** | 单文件 HTML（A4@96dpi=794×1123px）→ Chrome `--print-to-pdf` |

共同底座：**一切印刷品先写 HTML/CSS 再渲染 PDF**，不直接操作 PDF。字体必须本地字体文件 `@font-face`（不依赖 Google Fonts CDN），否则渲染机取不到字。

## 2. 书籍/讲义管线（实证细节）

### 2.1 流程

```text
build.py body     → 生成正文 HTML（含 CSS、KaTeX 预渲染结果、图片锚点）
render.js         → Paged.js 分页 + Chrome 打 body.pdf + 每页 PNG（scale 2）
pymupdf 扫描      → 从 body.pdf 提取各章起始页 → toc_pages.json
build.py front    → 生成前辅文（封面/扉页/目录/前言），目录页码来自 toc_pages.json
render.js         → front.pdf
pymupdf 合并      → 成书 + 元数据
```

KaTeX 公式用 node 预渲染成 HTML/CSS（`mathrender.js`），不要指望 Paged.js 里跑 JS 渲染公式；`.katex { font-size: 1.04em }` 与正文光学匹配。

### 2.2 实证设计 token（学术印刷系直接可用）

```css
:root {
  --ink: #1c1c1c; --red: #BF3126; --gray: #8a8a8a;      /* 墨 / 朱红(红笔) / 次要灰 */
  --rule: #d8d4cd; --wash: #f4f2ee;                      /* 规则线 / 淡底 */
  --sans: "Noto Sans SC", "Helvetica Neue", sans-serif;  /* 标题/标签/UI */
  --serif: "Noto Serif SC", "Songti SC", Georgia, serif; /* 正文 */
}
@page { size: 176mm 250mm; margin: 21mm 16mm 19mm 18mm; }  /* B5，上21/外16/下19/内18，非对称版心 */
body { font: 9.5pt/1.78 var(--serif); }                    /* 正文 9.5pt 行距 1.78 */
p { text-indent: 2em; }                                    /* CJK 段首缩进 */
```

组件语法（全部有实证通过版本，照抄结构改内容）：
- **章首**：54pt Helvetica 章号 + kicker（小字 · 红点 · 小标题）+ 大写宽字距英文 + 21pt 中文标题 + 4mm 红方块 + 导语（62% 宽）+ OBJECTIVES 边框盒
- **节标题 h2**：上边框 0.8pt 墨线 + 红色节号（`4.1` 红色，标题黑）
- **h3**：红色 6pt 实心方■前缀
- **列表**：`—` 长划线 bullet（灰），非默认圆点
- **callout**：左粗线 2.2pt（墨=普通，红=KEY/易错）+ sans 标签
- **表格**：th 上边 1pt 墨线 + 下 0.6pt + wash 底 + 无竖线；末行下 0.8pt 收底
- **图版**：0.5pt rule 边框盒 + 内 3mm padding；figcaption 上边线 + 红图号（图 4.2）+ 灰来源行右对齐
- **页眉页脚**：6.5pt sans 灰字距 0.1em（左=书名，右=章名 string-set）；页码 8pt；角上 2.6mm 红方块（品牌动作，全书写实重复）

### 2.3 Paged.js 踩坑记录（直接继承，勿重蹈）

1. **镜像页码只能注入正文文档**：`@page :left/:right` 翻转规则（左页页码外侧、红方块换内角、页眉只留对侧文字）写进 body 文档的独立 CSS 块，**不要放共享 CSS**——Paged.js 不认 `@page front:left` 组合选择器，泛 `:left` 会把方块漏进前辅文。
2. **前辅文必须偶数页**：前辅（封面/扉页/目录/前言）页数为偶，正文渲染奇偶才=成书奇偶；前辅变奇数页时全书镜像整体翻转，需在 front 末尾补空白页。
3. **`text-align-last` 会拉伸 CJK**：两端对齐的最后一行慎用，会拉出难看字距。
4. **大表跨页**：Paged.js 切表后 `<thead>` 丢失，需注册 Handler 在 `afterPageLayout` 里对 `table[data-split-from]` 克隆源表头回去。
5. **figcaption 防断词**：caption 用 `display:flex; flex-wrap:wrap`，图号/标题/来源三段各自 `white-space:nowrap`——来源行放不下时整体落第二行，不会出现「图/11.4」式断词或标题被挤成竖排。
6. **page counter / string-set**：章名用 `h1 { string-set: chaptitle content(text) }`，页眉 `@top-right { content: string(chaptitle) }`。
7. **Unicode 上下标**（H₂O、Ca²⁺）优先用 Unicode 字符 + 字体确认覆盖，不叠 `vertical-align` span（行高会跳）。

### 2.4 渲染参数（render.js 实证）

```js
puppeteer.launch({ headless: true, args: [
  "--allow-file-access-from-files", "--no-sandbox",
  "--font-render-hinting=none", "--disable-lcd-text" ] });  // 排版软件级渲染，无 LCD/暗示
page.setViewport({ width: 1100, height: 1500, deviceScaleFactor: 2 });  // PNG 验收图 2x
// 等 Paged.js 完成：轮询 .pagedjs_page 数量连续 5 次稳定才截图（不是 networkidle 就完事）
```

Chrome for Testing 独立二进制（免装浏览器、版本固定）；`waitUntil: "networkidle0"` + 稳定页数双条件，timeout 240s。

### 2.5 文字转曲（对外分发/印刷厂要求字体全嵌入时）

```bash
gs -o 输出.pdf -sDEVICE=pdfwrite -dNoOutputFonts \
   -dCompatibilityLevel=1.7 -dSAFER 输入.pdf
```

ghostscript 10.08；转曲后内嵌字体归零、文字不可选取、页数元数据保留；**勿加 `-dPDFSETTINGS`**（会降采样图片）。

## 3. 海报/单页管线（固定尺寸 HTML）

### 3.1 尺寸换算（96dpi 直接写 px）

A4 794×1123 · A3 1123×1587 · A2 1587×2245（横向交换）。`@page { size: A4; margin: 0 }`，容器 `width:794px; height:1123px; overflow:hidden`。

### 3.2 浏览器预览自适应（实证技巧）

```css
@media screen {
  html { display:flex; justify-content:center; }
  body { transform-origin: top center; scale: min(1, calc(100vw / 794)); }
}
@media print { .bg-grid { -webkit-print-color-adjust: exact; print-color-adjust: exact; } }
```

打印时背景色/图必须加 `print-color-adjust: exact`，否则 Chrome 丢底色。

### 3.3 海报组件语法（Swiss editorial 实证版，模板在 assets/）

顶行 meta（左红点+栏目 · 右大写拉丁标签）→ hero 衬线巨字（Noto Serif SC 900，138px 级）+ 拉丁名字（Inter 宽字距 13px）→ 发丝线 + 96px 红段覆盖 → hero 行（kicker 红大写 / 标题 48px / lead 24px + 档案照框：1px 墨边 + 10px 白衬 + 小图注）→ 印章块（4px 红框竖排字）→ 数据行（64px Inter Black 数字 + 分隔细线）→ 底部 pinned footer（细线 + 左右 meta）。背景可加 40px 坐标纸网格（8–10% 不透明度）+ 1–3 个 7% 不透明度公式水印（**公式必须与主题真实相关**）。

照片内嵌用 base64（`data:image/jpeg;base64,...`）保证单文件分发；PNG 导出用 Chrome screenshot deviceScaleFactor 2。

## 4. 图片素材合规（Wikimedia Commons 实证）

- 检索 Commons API；**缩略图 URL 带 `?utm_…` 参数直接 404**，必须 `url.split("?")[0]`；少数原图 403/404 时用 1000px 缩略图 URL 渲染替代
- 每张图记录作者/来源/授权到 `img/MANIFEST.md`，figcaption 来源行同步展示（PD/CC 标注）
- 多图拼合时中文标签用 NotoSansSC；**注释文字放在面板高度之外的独立区域**（`lab_h + panel_h + gap`），否则与键线交叠

## 5. 科学图版语言（自绘 diagrams）

matplotlib 自绘遵循 specimen 风格：细测量线（0.8–1.2pt）、编号坐标轴、区域标注、标本签式注释（Helvetica 15px 灰 #8a8a8a、字距 4、可旋转 −90°）、数据系列强调用唯一红 #BF3126；同书所有图同一 stroke 权重与标签语法——「一百张图读起来像一个人画的」。对照组必须有（无对照的实验图会被验收打回）。

## 6. 验收（judge 并行视觉验收，实证流程）

1. 每页导出 2x PNG
2. 分批交 judge（渲染类验收 agent）逐页审：空白页、元素交叠、断词、图文错位、镜像页码方向、图内容正确性（曾有双倒数图缺对照线被指出）
3. 返工后**必须复验**该页
4. 内容存疑（术语/数据）不擅改，列清单交用户定夺

## 7. 印刷自查清单

- [ ] 版心非对称 + 镜像（左页右页页码在外侧）
- [ ] 前辅文偶数页
- [ ] 跨页表格表头重复、图片 caption 不断裂
- [ ] 字体全部本地 @font-face；分发版转曲（§2.5）
- [ ] 位图 ≥300dpi；线条图用 PDF/SVG 矢量
- [ ] 出血：满版元素外扩 3mm；海报字溢出方向 5mm+
- [ ] 双色/黑白工艺下设计仍成立（Swiss 系天然成立；荧光/渐变风格须先问工艺）
- [ ] print-color-adjust: exact 已加
