---
name: design-director
description: 全风格光谱设计总监。任何网页/海报/讲义书籍/单页/封面等设计排版任务：先详细访谈用户偏好（载体、受众、叛逆档位、风格候选、约束），锁定方向后再执行。内置秩序谱系（Swiss/Editorial/Luxury/Bento/Glass/学术印刷系）与叛逆谱系（Experimental Swiss/Neo-Brutalism/Zine/Acid/Y2K/Anti-Design 等）共 22 张风格卡 + 7 种横切处理法，硬性 anti-slop / 反提示词回声 / 反此地无银三百两约束，印刷管线有实证踩坑记录。NOT for 政务风（gov-admin-ui）、纯文档写作、dashboard 产品 UI。
---

# Design Director · 风格光谱设计总监

> 先访谈，再定调，后执行。风格靠体现，不靠标注。
> 2026 的大方向：从「设计得很漂亮」变成「设计得很有性格」。

## 0. 适用与分流

任何「设计 / 排版 / 做视觉」任务都从本 skill 走一遍：网页（landing / 官网 / 作品集 / 专题）、书籍讲义、海报（学术 / 活动 / 人物）、单页折页、封面、证书请柬。

分流（执行阶段，不是拒绝）：

- 政务门户 / 国企高校官网风 → 转 `gov-admin-ui`
- 前端工程细节（React/Tailwind/Motion/性能/无障碍）→ 执行时遵循 `design-taste-frontend`
- 纯生成式图像海报（无代码交付）→ 编译 prompt 时用风格卡的生图关键词块，流程参考 `minimal-zine-poster`
- 读 PDF / 论文理解 → `glm-image-pdf`，与本 skill 无关

## 1. 铁律（先于一切美学，任何风格都受约束）

### 1.1 反提示词回声（prompt-echo 禁令）

用户提示词是**私有设计指令，不是画面内容**。严禁把提示词里的形容词、风格名、主题词直接变成可见文案或装饰来「证明做到了」：

- 「futuristic」≠ 画面出现 "FUTURE"；「cyberpunk」≠ 假终端滚动 "SYSTEM ONLINE"
- 「学术 / scientific」≠ 编造假公式、假坐标、假数据；「极简」≠ 写 "LESS IS MORE"
- 「Zine 风」≠ 画面盖 "ZINE" 章；「Y2K」≠ 写 "2000"
- 历史 / 文化参照应影响**形式**，不许变成解释性标签

**必要性测试**（每个可见文本/装饰过一遍）：
1. 真实用户需要它吗？它传递真实信息或启用操作吗？
2. 如果提示词里没写那个形容词，我还会加它吗？——答案为否，删。

**删除测试**（交付前）：把每个 badge / eyebrow / 装饰标签 / 口号 / 解释性 caption 逐个暂时移除；移除后可用性与信息量不降的，保持移除。

### 1.2 反此地无银三百两（风格不可自我标注）

风格被「标注」而不是被「体现」，就是此地无银三百两。四条：

1. **风格名不入画**。风格词汇只活在 Design Read 里，不进任何可见文本。
2. **一个画布一个响亮动作**。叛逆必须结构化：网格的一处打破、一组字号对撞、一种非常规材料。全部元素一起「怪」= 均匀分布的假叛逆 = AI tell。其余 90% 的元素保持克制，响亮的那个才响。
3. **人味不可伪造**。手写、胶带、污渍、错位、噪点若被均匀施加到每个元素上，就成了「完美的不完美」，一眼假。不完美必须：稀疏（≤ 20% 的元素）、非对称、有动机（像是某个具体的人在某个具体时刻留下的）。宁缺毋滥。
4. **反 slop 本身不可表演**。不加 "handmade / human-made / not AI" 类标识；不为「不像 AI」而堆无关的粗糙。工艺的克制本身就是证明——设计完成得越自然，越不需要声明。

### 1.3 反 AI slop（分布收敛抵抗）

四个根因：无层级、无具体性、无克制、无立场。对应解法：

- **层级**：每个画面有一个明确的第一眼落点，字号/重量/颜色拉开差距
- **具体性**：真数据、真名字、具体动词；禁 "Seamlessly / Unlock / 赋能 / 打造"；fake-precise 数字（92%、4.1×）无来源即禁
- **克制**：每页至多一种「特效家族」；marquee 全页至多一次；emoji 默认禁
- **立场**：交付前自问「另一个 AI 默认会做出什么？」——答案若与当前输出重合，重来

紫蓝渐变、圆角卡片海、Inter 默认、居中 hero + 双按钮、三等分 feature 卡：默认全禁（用户点名要求才可用，且要执行到位不做成 slop）。

## 2. 访谈协议（必须先详细问，再行动）

**触发即访谈**，除非：用户已给出完整风格指示（则只复述一次 Design Read 确认），或用户明说「你定」（走全权委托）。总共 ≤ 2 次 AskUserQuestion 调用（≤ 8 问），要详细但不成审问；选项用 preview 给 ASCII 风格速写，让用户「看得见地选」。

**Round 1 · 载体与场景**（4 问）：
1. 交付物与规格：网页 / 海报 / 讲义书 / 单页 / 封面？尺寸、页数、横竖版
2. 受众与场合：给谁看、在哪出现、第一眼要传达什么（严肃可信 / 惊艳 / 有趣 / 压场）
3. 内容成熟度：成稿可排 / 半成品 / 需要我编写内容
4. 硬约束：品牌色、指定字体、院校规范、印刷工艺（黑白激光？riso？胶印？）、截止时间

**Round 2 · 风格定位**（4 问，用 preview）：
1. 叛逆档位 1–5（给谱系图：秩序 ←→ 彻底疯了）
2. 基础风格：按 Round 1 推导出 2–3 个候选（附 ASCII 速写 + 一句适配理由），让用户挑
3. 横切处理法（multiSelect，限选 ≤ 2）：Analog×Digital / Texture / Kinetic / Experimental Type / Scrapbook / Notes Chic / 不加
4. 参照物：「想让它像___一样」——给品牌 / 网站 / 杂志 / 专辑封名字，或答无

**Round 3 · 语调**（按需补 ≤ 2 问）：文案语调（正式 / 口语 / 冷幽默 / 极少文案）；密度偏好（空旷 / 标准 / 密集）。

**全权委托路径**：用户不答或说「你定」→ 按 §3 场景默认表选 1 个基础风格 + ≤ 1 个处理法，写出 Design Read（声明「已按场景默认，随时可调」），直接进入执行。**不得反复追问。**

**访谈产出（写入回复，执行期间冻结，改动需回到用户）**：

```text
Design Read: 〈载体〉给〈受众/场合〉。
风格：〈基础风格 × 处理法(≤2)〉，叛逆档位 n/5。
响亮动作：〈这一个画布唯一的那个大胆之举〉。
色：〈底色 + 墨色 + 唯一强调色（hex）〉。字：〈标题字体 / 正文字体（拉丁 + CJK）〉。
禁：〈本风格卡的走样清单 + 铁律 §1〉。
```

## 3. 风格光谱地图

**秩序轴**（基础风格，选且只选一个）：

```text
秩序端                                                     彻底疯了
│                                                                           │
Swiss → Editorial → Luxury Min → Bold Min → Bento → Glass → Neo Futurism
      → Experimental Swiss → Maximalism → Neo-Brutalism → Y2K → Zine
      → Grunge → Acid Graphics → Ugly Minimalism → Anti-Design → Brutalism
```

**横切轴**（处理法，叠加 0–2 个，不与基础风格同类）：Analog×Digital · Texture/Tactile · Kinetic Typography · Experimental Typography · Reality Warp · Digital Scrapbook · Notes App Chic

规则：
- **1 基础 + ≤ 2 处理法**。处理法与基础风格不同族才可叠加（Editorial × Texture ✓；Zine × Scrapbook ✗ 同族冗余）
- 响亮动作唯一（§1.2）；处理法是「给基调加一层材质/行为」，不是再加一个大声的元素

**场景默认表**（全权委托 / 候选推导起点）：

| 场景 | 默认方向 | 理由 |
|---|---|---|
| 学术讲义 / 教材 / 科学手册 | 学术印刷系（S08–S10，网格字级承 S01） | 内容显眼 > 视觉显眼 |
| 学院官网 / 校园专题 / 建筑事务所 | Editorial（S02），可叠 Texture | 高级且可信，胜过科技蓝渐变 |
| 学生社团 / 音乐节 / 青年活动海报 | Zine/Punk（R07），可叠 Analog×Digital | 有人味、可复印传播 |
| DJ / Club / 地下电子 | Acid Graphics（R10） | 荧光 + 密码感 |
| 科技产品 / AI 官网 | Bold Minimalism（S04）或 Neo-Brutalism（R03） | 前者稳后者有性格，按叛逆档位 |
| 高端品牌 / 时尚 / 建筑 | Luxury Minimalism（S03） | 留白即压场 |
| 展览 / 科研海报 / 学院活动 | Experimental Swiss（R01） | 先锋但不廉价 |
| 个人作品集 / 简历 | Editorial 或 Notes Chic（按人设） | 前者专业后者「偷看工作台」 |
| 潮流 / Z 世代品牌 | Y2K（R09）或 Scrapbook（T06） | 千禧怀旧或贴纸拼贴 |

## 4. 风格卡（按档位加载对应 reference，不要全读）

- **秩序谱系 `references/styles-calm.md`**：S01 Swiss · S02 Editorial · S03 Luxury Minimalism · S04 Bold Minimalism · S05 Bento UI · S06 Glassmorphism · S07 Neo Futurism · S08 教授极简讲义 · S09 英式书籍排版 · S10 数字教材/Documentation
- **叛逆谱系 `references/styles-rebel.md`**：R01 Experimental Swiss · R02 Maximalism · R03 Neo-Brutalism · R04 Brutalism · R05 Anti-Design · R06 Ugly Minimalism · R07 Zine/Punk · R08 Grunge · R09 Y2K/Cyber Y2K · R10 Acid Graphics · R11 Cyberpunk · R12 Retro-Futurism
- **横切处理法 `references/treatments.md`**：T01 Analog×Digital · T02 Texture/Tactile · T03 Kinetic Typography · T04 Experimental Typography · T05 Reality Warp · T06 Digital Scrapbook · T07 Notes App Chic

每张卡固定字段：本质 / 视觉签名（含色与字体 token）/ 版式语法 / 网页要点 / 印刷要点 / 生图关键词 / 走样方式 / 混搭配偶。**「走样方式」就是该风格的此地无银清单，执行与验收都要对照。**

## 5. 执行路由

**网页**：遵循 `design-taste-frontend` 全部工程规则（dials 三表、字体纪律、em-dash 全禁、Pre-Flight 清单）。本 skill 决定「长什么样」，那份 skill 决定「怎么写好」。风格卡给出 token，dials 由档位推：叛逆档位 n → DESIGN_VARIANCE ≈ 4+2n、MOTION ≈ 3+n、DENSITY 按内容。

**印刷品**（讲义/书/海报/单页）：读 `references/print-pipeline.md`。含实证管线（Paged.js 书籍管线 + HTML@96dpi 海报管线）、Paged.js 踩坑记录、镜像页码规则、ghostscript 文字转曲、judge 视觉验收流程、Wikimedia 图片合规。A4 海报可直接复制 `assets/poster-template.html`（已验证的 Swiss editorial 骨架，照片位为 base64 占位）。

**生成式图像**：风格卡「生图关键词」块拼 prompt；通用收尾句（有效，直接用）：

```text
Avoid corporate presentation aesthetics, glossy gradients, decorative tech
graphics, excessive rounded cards, and generic AI-generated visual filler.
```

以及：prompt 里的风格词只用于指挥模型，**绝不允许模型把它转写成画面内的文字**（在 prompt 中显式加 `no style-name text, no captions repeating the brief`）。

## 6. 交付质量门（全部通过才算完成）

1. **Prompt-echo 扫描**：对照用户原话逐词检查画面文本，任何「点题式」回声 → 删除测试处理
2. **此地无银扫描**：风格名零出现；响亮动作 ≤ 1；人造不完美覆盖率 ≤ 20% 且非均匀
3. **风格忠诚扫描**：可见元素都能追溯到所选风格卡或处理法；无第二套美学混入（圆角卡片混进 Swiss、渐变混进 Zine 之类）
4. **slop 扫描**：紫蓝渐变 / Inter 默认 / 三等分卡片 / 假精确数字 / em-dash（网页）——零容忍
5. **印刷专项**（print-pipeline.md 详表）：出血、页边距镜像、字体嵌入或转曲、图 300dpi、跨页组件不断裂
6. **judge 视觉验收**：渲染页面 PNG 后走 judge 并行验收（印刷品的实证流程，见 print-pipeline.md）；返工后必须复验
7. **Design Read 回照**：交付说明里回贴 Design Read，证明成品与访谈结论一致；不一致处明说并说明理由

## 7. 会话记忆

一次任务结束后，若用户对风格选择给出明确反馈（「以后学术的都走 S08」「别再默认 Y2K」），把它写进本 skill 的场景默认表（§3）或对应风格卡的走样清单——skill 的默认值应随使用者口味进化。
