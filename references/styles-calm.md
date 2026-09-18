# 秩序谱系风格卡（S01–S10）

叛逆档位 ★–★★★。共同底色：网格、层级、留白、克制、内容显眼 > 视觉显眼。
字段：本质 / 签名 / 版式 / 网页 / 印刷 / 生图关键词 / 走样（= 此地无银清单）/ 混搭。

---

## S01 · Swiss / 国际主义 ★

**本质**：版面是测量仪器。网格先行，左对齐，无装饰，字体即图形。
**签名**：白/纸底 + 近黑墨（#1c1c1c 级）+ 唯一强调色（朱红 #BF3126 或学术蓝 #0F4C81）；Helvetica Neue / Neue Haas / Inter（拉丁），Noto Sans SC（CJK）；巨型章节数字（54pt+）配克制的正文标题；发丝线 0.5–0.8pt；小型大写 + 宽字距做标签。
**版式**：严格网格（12 栏或 6mm 基线）；一切左对齐，居中须有理由；留白是最大的声部；信息密度可高但层级分明。
**网页**：无圆角或 ≤2px；无阴影无渐变；motion 仅 hover 变色与 1px 位移；导航文字化。
**印刷**：双色印刷天然友好（黑 + 红）；网格纸/坐标纸底纹可用但要淡（≤8% 不透明度）；参照实证：B5 书 margins 21/16/19/18mm 镜像。
**生图关键词**：`Swiss international typographic style, strict typographic grid, Helvetica, oversized numerals, black on white with single vermilion accent, hairline rules, generous whitespace, flush-left ragged-right`
**走样**：居中上瘾；给网格线描边当装饰（线只许组织真实内容）；强调色用到第三处；往留白里塞东西。
**混搭**：✓ Texture、Experimental Type（少量）；✗ Glass、Neo Futurism。

## S02 · Editorial 编辑风 ★★

**本质**：把网页当杂志做——图片是主角，文字成栏，编号做导航。
**签名**：Serif 大标题 + Sans 正文（或反向）；黑白灰 + 1 强调色；满栏巨图（首图 ≥ 60% 视口高）；发丝线分隔；章节编号（01/02…）做导航；首字下沉可选。拉丁：PP Editorial New / GT Sectra / Tiempos / Playfair（轮换，勿连用同款）；CJK：Noto Serif SC 标题 + Noto Sans SC 正文。
**版式**：12 栏复杂网格、非对称；正文栏宽 55–65ch；图片与文字 6:4 呼吸节奏；跨页大图 + 小注图交替。
**网页**：大图 lazy-load + 占位防 CLS；scroll-reveal 克制（fade 12px 即可）；可叠 Kinetic 做标题入场。
**印刷**：杂志开本（A4/210×275）；双色或四色；图 300dpi 出血 3mm。
**生图关键词**：`editorial magazine spread, asymmetric grid, oversized serif headline, full-bleed photography, hairline rules, numbered sections, single accent color, Monocle-style layout`
**走样**：编号泛滥成 eyebrow 装饰（每节一个 01/02）；图不够大字来凑的「伪杂志感」；serif 用到 Fraunces/Instrument Serif（AI 默认脸）。
**混搭**：✓ Texture、Analog×Digital；✗ Glass、Acid。

## S03 · Luxury Minimalism ★

**本质**：留白即压场。越贵的东西越安静。
**签名**：巨大留白（正片区域 ≤ 40%）；细 serif（Cormorant / Saol / Canela；CJK：Noto Serif SC Light）；高质摄影（实物、材质、光影）；charcoal/off-white，强调色至多一枚细线或小字；字距略开。
**版式**：近乎对称的稳定构图；一屏一物；产品图居中或黄金位；文字极少且每句都值钱。
**网页**：motion 极缓（0.6–1s ease）；hover 只做 opacity；字体必须 self-host 高字重质量。
**印刷**：特种纸（亚粉/艺术纸）、烫金或单色压印可选、大出血留白。
**生图关键词**：`luxury minimal editorial, vast negative space, thin elegant serif, single object studio photography, muted sophisticated palette, architectural composition`
**走样**：米色+黄铜+深棕 AI 默认奢华色（禁用色族见 design-taste-frontend §4.2，轮换 Cold Luxury / Forest / Cobalt+Cream）；文案煽情；留白里偷偷加装饰线。
**混搭**：✓ Texture、Kinetic（极缓）；✗ Maximalism、Acid、Scrapbook。

## S04 · Bold Minimalism ★★

**本质**：极简结构 + 超大字体/强色块。少即是吼。
**签名**：结构极简（几乎无卡片无线条）但标题 96–200px、色块整幅（电光蓝/亮绿/黑）；Sans 强字重（Archivo Black / Anton / Space Grotesk；CJK：Noto Sans SC Black 或站酷庆科黄油体）；一句话 hero。
**版式**：大留白 + 巨型字对撞；一屏一主张；色块整幅切换分区。
**网页**：scroll-driven 字号变化；色块分区滚动；prefers-reduced-motion 必须降级。
**印刷**：大面积专色（注意成本与覆盖）；海报首选；黑白激光下靠字号仍成立。
**生图关键词**：`bold minimalism poster, massive typography, single saturated color field, minimal structure, huge sans-serif display type, high contrast`
**走样**：大字 + 渐变 + 发光三连；一句话标语写成口号空话；色块超过三种色。
**混搭**：✓ Kinetic、Notes Chic（反差萌）；✗ Texture（互相抵消）、Grunge。

## S05 · Bento UI ★

**本质**：便当盒信息架构——卡片即网格，模块即语义。
**签名**：圆角卡片（统一 12–16px）浅底 #FAFAFA/#F5F5F3 + 1px 边 #E5E5E5；卡片尺寸不等（2×2、1×2、2×1 有节奏）；Inter/Geist + JetBrains Mono 数字；图标单色线性。
**版式**：6–12 栏 bento 网格；N 内容 = N 格，禁止空格与凑数格；≥2–3 格要有真实视觉差（图/渐变/图表，非纯字卡）。
**网页**：hover 微抬 2px + 边加深；stagger 入场一次即可。
**印刷**：产品单页/白皮书摘要页可用；卡片间距体系 8/16/24pt。
**生图关键词**：`bento grid layout, modular cards, soft rounded tiles, light neutral background, varied cell sizes, clean sans typography`
**走样**：六张白上白纯文字卡；每格一个 emoji；圆角与直线元素混用无规则。
**混搭**：✓ Notes Chic（弱化圆角后）；✗ Zine、Brutalism（语法冲突）。

## S06 · Glassmorphism ★

**本质**：材质为信息分层——毛玻璃是层级，不是滤镜。
**签名**：backdrop-filter blur(20–28px) saturate(180%)；半透明白 8–16% 叠加；1px 内描边 rgba(255,255,255,.3)；内侧高光 inset 0 1px 0 rgba(255,255,255,.4)；背景必须有可模糊的彩色内容（渐变斑块/图片），否则玻璃无意义。
**版式**：悬浮层与底层明确两层叙事；玻璃面板承载关键操作；`prefers-reduced-transparency` 必须给实底降级。
**网页**：Apple Liquid Glass 无官方 web 版，一切实现都是近似，代码注释要写明；性能敏感（移动端帧率），面板数量 ≤3。
**印刷**：**不适用**（材质依赖屏幕光）；印刷需求转 S03 或 S07。
**生图关键词**：`frosted glass panels over vivid gradient background, translucent layered UI, subtle inner glow edges, depth of layers`
**走样**：纯白底上糊玻璃（无东西可模糊）；处处玻璃；紫蓝渐变 AI 默认底；真当 Apple 官方组件。
**混搭**：✓ Neo Futurism；✗ Swiss、Zine、Print 一切。

## S07 · Neo Futurism ★★★

**本质**：未来界面——3D、流体、光效，但服务于「可信的先进感」。
**签名**：深底 #0A0A12 + 一到两束冷光（青/紫罗兰/橙）；玻璃+流体形状；等宽字做数据层（IBM Plex Mono / Space Mono）；微粒子/线框网格背景；3D 物体单件居中。
**版式**：中心舞台式——一件 3D/流体主角，文字环绕辅助；数据 HUD 感点缀（小坐标、细十字线，须有真实语义）。
**网页**：Three.js/WebGL 隔离在 client 叶子组件；LCP 保护（3D 延迟加载）；reduced-motion 全降级。
**印刷**：仅封面/展板适用，深底专色 + 局部 UV。
**生图关键词**：`neo-futuristic interface, dark scene with cold volumetric light, single 3D chrome object, wireframe grid, HUD annotations, cinematic but restrained`
**走样**：霓虹乱洒；假 HUD 满屏（无语义的坐标/十字准星= §1.1 回声）；紫蓝渐变 slop 底。
**混搭**：✓ Reality Warp、Kinetic；✗ Zine、Texture。

## S08 · 教授极简讲义（University Lecture Notes）★

**本质**：内容必须比视觉显眼。公式占据核心视觉，白底黑字一个学院色结束。
**签名**：白底 #FFF；黑字 #111；至多一个主题色（MIT 红 / 斯坦福红 / 学院蓝）；Helvetica/Arial/Source Sans/Computer Modern；Lecture 07 + 课程号 + 日期的题头块；编号大纲（1. Motivation 2. Least Squares…）；图表极干净（细轴、少墨）。
**版式**：单栏 A4/US Letter；1in 边距；公式块居中独立行；定理/引理用斜体或小型大写标签；页脚页码足矣。
**网页**：即文档页——左目录右正文，锚点导航，print CSS 友好；KaTeX/MathJax 公式渲染。
**印刷**：黑白激光完美成立；图线条 ≥0.5pt 防打印消失；实证细节见 print-pipeline.md。
**生图关键词**：`minimal academic lecture notes, white background black text, single university accent color, clean numbered outline, centered display equations, scientific line figures`
**走样**：加任何「美化」（花标题、彩色框、装饰图）；假公式装饰（§1.1）；图标 emoji 化。
**混搭**：✓ Documentation 化（=S10）；✗ 一切叛逆处理法。

## S09 · 英式书籍排版（Oxford/Cambridge/Penguin）★

**本质**：像书的书。Book typography 而非 slides。
**签名**：Serif 正文（EB Garamond / Tiempos / CJK 思源宋体）+ Sans 或小型大写标题；大量页边距（外白 20–25mm）；漂亮脚注（字号 7.5–8pt，高挂注码）；Small Caps 人名术语；章首页克制（CHAPTER FIVE + 标题 + 一段引文，其余留白）；图注字号很小且离图远；黑白 + 单强调色。
**版式**：稳定版心，偶数章起新页；页码外侧；目录三级即止；权威感来自节奏一致而非任何单页惊艳。
**网页**：长文阅读页（65–70ch 栏宽、1.7 行距、脚注悬浮）。
**印刷**：这是它主场——轻量纸、锁线胶装、章首可做辑页；页边注(margin notes)是加分项。
**生图关键词**：`classic British book typography, generous margins, small caps, footnotes, restrained chapter opener, serif body with sans headings, single ink accent, Penguin-style restraint`
**走样**：章首堆装饰纹样；正文无衬线化；页边距被图吃掉；脚注做成框。
**混搭**：✓ Texture（纸感）；✗ Kinetic、Scrapbook。

## S10 · 数字教材 / Documentation ★

**本质**：SaaS UI × 学术笔记——Notion/Linear/mdn 时代的讲义。
**签名**：浅灰底 #F8F8F7 / 纯白卡；极细边 1px #E5E5E5；小圆角 6–8px；Inter/Geist + SF Pro 图标；8/16/24px 间距体系；callout 色条（info 蓝/warn 黄灰）；code block 深底浅字 + 语法高亮；`→` 导航列表。
**版式**：左侧栏（目录/章节树）+ 主栏内容 + 可选右侧「本页要点」；模块化概念卡（Concept / Example / Note）；面包屑 + 阅读进度。
**网页**：SSR/SSG 优先；锚点滚动 spy；暗色模式成对设计；搜索 (⌘K)。
**印刷**：导出 PDF 时卡底转白、边转灰线、code block 浅灰底（深底费墨）。
**生图关键词**：`modern documentation site, Notion-like clean interface, light gray background, hairline borders, small radius cards, callout blocks, monospace code, 8px spacing system`
**走样**：卡片套卡片；每段一个 callout；图标代替小标题；渐变按钮。
**混搭**：✓ Notes Chic（反向污染成草稿感）；✗ Texture、Grunge。
