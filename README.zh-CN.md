# Design Director · 风格光谱设计总监

**[English](README.md) | [中文](README.zh-CN.md)**

一个访谈先行的全风格光谱设计总监 skill，面向 AI 编程代理。在任何像素落地之前，先详细询问你的偏好（交付物、受众、叛逆档位、参照物、约束），锁定一份 **Design Read**，再在 **22 张风格卡** 与 **7 种横切处理法** 中路由执行——覆盖网页与一切印刷品（讲义、书籍、海报、单页、封面、证书）。

> 2026 的大方向：从「设计得很漂亮」变成「设计得很有性格」。
> 风格靠**体现**，从不靠**标注**。

---

## 为什么需要它

AI 生成的设计大多收敛到同一个均值：紫蓝渐变、圆角卡片、居中 hero、emoji 图标。而 2025–2026 的真实设计正在主动反抗精致的 SaaS 模板——粗野主义、Zine、Acid Graphics、模拟纹理、备忘录风。

这个 skill 给代理两样它通常缺的东西：

1. **真正的风格词汇表**——从 Swiss 克制到纯粗野主义的整个光谱，每张卡都有具体 token（hex、字体搭配、版式语法、印刷规格），而不是「极简」一个形容词。
2. **纪律**——三条铁律先于一切美学，堵住下面三个经典失败模式。

## 三条铁律（先于一切美学）

1. **反提示词回声。** 你的提示词是*私有设计指令，不是画面内容*。「futuristic」不等于把 "FUTURE" 印在页面上；「学术」不等于编造假公式。每个可见字符串都要过必要性测试与删除测试。
2. **反此地无银三百两。** 风格名永不入画。一个画布一个响亮动作——其余 90% 保持克制。人味痕迹（手写、胶带、污渍）必须稀疏（≤20% 元素）、非对称、有动机；均匀施加的不完美一眼假。反 slop 本身也不可表演。
3. **反 AI slop。** 无层级、无具体性、无克制、无立场——四个根因各有对策。紫蓝渐变、Inter 默认、三等分卡片：默认全禁。

## 工作方式

```text
访谈（≤2 轮 AskUserQuestion，选项带 ASCII 风格速写）
   │  或：全权委托路径（「你定」）→ 按场景默认表定向
   ▼
Design Read —— 冻结的一段话规格：
   风格 × 处理法(≤2) · 叛逆档位 · 唯一的响亮动作 · 色/字 token
   ▼
执行路由：
   网页     → 工程规则委托给前端品味 skill
   印刷品   → 实证管线（本仓库 references/print-pipeline.md）
   生图     → 每张卡的英文关键词块
   ▼
质量门：回声扫描 · 此地无银扫描 · 风格忠诚扫描 ·
        slop 扫描 · 印刷专项 · judge 视觉验收
```

## 风格光谱

**秩序轴（基础风格——选且只选一个）：**

| 卡号 | 风格 | 叛逆度 |
|---|---|---|
| S01 | Swiss / 国际主义 | ★ |
| S02 | Editorial 编辑风 | ★★ |
| S03 | Luxury Minimalism | ★ |
| S04 | Bold Minimalism | ★★ |
| S05 | Bento UI | ★ |
| S06 | Glassmorphism | ★ |
| S07 | Neo Futurism | ★★★ |
| S08 | 教授极简讲义 | ★ |
| S09 | 英式书籍排版（Oxford/Penguin） | ★ |
| S10 | 数字教材 / Documentation | ★ |
| R01 | Experimental Swiss / Swiss Punk | ★★★ |
| R02 | Maximalism 极繁主义 | ★★★ |
| R03 | Neo-Brutalism 新粗野主义 | ★★★★ |
| R04 | Brutalism 粗野主义 | ★★★★★ |
| R05 | Anti-Design 反设计 | ★★★★★ |
| R06 | Ugly Minimalism 丑极简 | ★★★★ |
| R07 | Zine / Punk | ★★★★★ |
| R08 | Grunge | ★★★★ |
| R09 | Y2K / Cyber Y2K | ★★★ |
| R10 | Acid Graphics | ★★★★★ |
| R11 | Cyberpunk | ★★★ |
| R12 | Retro-Futurism | ★★★ |

**横切处理法（叠加 0–2 个，须与基础风格不同族）：**

T01 Analog × Digital · T02 Texture/Tactile · T03 Kinetic Typography · T04 Experimental Typography · T05 Reality Warp · T06 Digital Scrapbook · T07 Notes App Chic

每张卡固定包含：本质 / 视觉签名（hex + 字体 token，拉丁与 CJK）/ 版式语法 / 网页要点 / 印刷要点 / 生图关键词 / **走样方式（该风格的此地无银清单）** / 混搭配偶。

## 实证印刷管线

`references/print-pipeline.md` 从两个已交付项目蒸馏而来，不是理论：

- 一本 **108 页 B5 讲义**：markdown → HTML → Paged.js → headless Chrome → pymupdf 合并 → ghostscript 文字转曲（全部页面经并行视觉验收通过）；
- 一张 **A4 Swiss editorial 海报**：单文件 HTML @96dpi（`assets/poster-template.html`——已验证的骨架，复制后改三个 CSS 变量即可换色换风格）。

内含踩坑记录：镜像页码只能注入正文文档、前辅文必须占偶数页、跨页表头需注册 Paged.js Handler、figcaption 用 flex-wrap 防断词、`print-color-adjust: exact`、Wikimedia Commons URL 陷阱与授权清单、ghostscript `-dNoOutputFonts` 命令（切勿加 `-dPDFSETTINGS`）。

## 仓库结构

```text
design-director/
├── SKILL.md                     # 协议：铁律、访谈、路由、质量门
├── README.md / README.zh-CN.md  # 你在这里
├── references/
│   ├── styles-calm.md           # S01–S10 秩序谱系风格卡
│   ├── styles-rebel.md          # R01–R12 叛逆谱系风格卡
│   ├── treatments.md            # T01–T07 横切处理法 + 冲突速查表
│   └── print-pipeline.md        # 实证印刷工程
└── assets/
    └── poster-template.html     # 已验证 A4 Swiss editorial 海报骨架
```

## 依赖（必读）

本 skill 是总监不是巨石——刻意委托而非重复。**必须同步安装三个 skill**（放在同一 skills 目录），缺装则对应能力缺失：

| Skill | 级别 | 承担什么 | 缺了会怎样 |
|---|---|---|---|
| `design-taste-frontend` | **必装** | 网页执行阶段全部工程规则：dials 三表、字体纪律、Pre-Flight 清单、性能与无障碍 | 网页项目只有风格 token，没有工程护栏 |
| `anti-ai-slop` | **必装** | 铁律三的完整检查清单与逐项对策、slop 评分表 | 反 slop 只剩摘要，缺判定细则 |
| `anti-prompt-echo` | **必装** | 铁律一的完整测试流程（必要性测试、删除测试） | 回声扫描凭感觉，易漏判 |
| `gov-admin-ui` | 按需 | 政务门户项目的分流目标 | 仅影响该类项目 |
| `minimal-zine-poster` | 按需 | 纯生图海报的 prompt 编译器 | 仅影响该类交付物 |

本仓库的访谈协议、风格卡、印刷管线自身完备；必装三件套驱动网页执行路线与完整质量门。缺装时先安装再跑对应路线——**绝不要凭记忆复述依赖 skill 的规则**，记忆版规则是 AI slop 的入口。

## 安装

任何加载 markdown skill 的代理（Claude Code、ZCode 及同类）：

```bash
git clone https://github.com/Cetirzine/design-director.git \
  ~/.zcode/skills/design-director        # 或你的代理的 skills 目录
```

然后从各自来源获取三个必装 skill（`design-taste-frontend`、`anti-ai-slop`、`anti-prompt-echo`），作为兄弟目录放入。最终布局：

```text
~/.zcode/skills/
├── design-director/          # 本仓库
├── design-taste-frontend/    # 必装
├── anti-ai-slop/             # 必装
└── anti-prompt-echo/         # 必装
```

## 致谢

运行在 `design-taste-frontend`、`anti-ai-slop`、`anti-prompt-echo`、`gov-admin-ui`、`minimal-zine-poster` 的工作安装之上（见「依赖」）——本 skill 负责定向与路由，刻意委托而非重复它们。
