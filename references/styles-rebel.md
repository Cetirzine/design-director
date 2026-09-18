# 叛逆谱系风格卡（R01–R12）

叛逆档位 ★★★–★★★★★。共同前提（SKILL.md §1.2）：**视觉叛逆，功能保守**（除非纯艺术海报）；好的叛逆是懂规则后破规则——先有网格，才谈打破网格。
字段同 styles-calm.md。

---

## R01 · Experimental Swiss / Swiss Punk ★★★

**本质**：Swiss 的全部基因（黑白红、grotesk、网格）+ 一处系统性破坏。既先锋，又不像廉价潮流海报。
**签名**：色板仍是黑/白/单红；Helvetica 类；但字会旋转、切割、溢出画布（DES / 换行缩进错位 / IGN 跑到版心外）；字号对比极端（300pt 对 8pt）；基线故意不齐一处。
**版式**：先严格网格，再选**一处**打破（一个词溢出、一行旋转 4–8°、一列下沉）；其余全部对齐——破坏才有力量。
**网页**：break 用 CSS transform，溢出记得 `overflow-x: hidden` 防滚动条；移动端收回规整（<768px 回网格）。
**印刷**：海报/展册主场；出血留足（字溢出方向 5mm+）。
**生图关键词**：`experimental Swiss typography poster, black white and red, rotated and clipped oversized grotesk letters, broken grid but disciplined, Zurich design school`
**走样**：到处破坏=没有破坏；颜色超出黑白红；变成普通排版加个旋转贴纸。
**混搭**：✓ Kinetic（字的运动延续破坏）；✗ Texture、Scrapbook（脏化即失格）。

## R02 · Maximalism 极繁主义 ★★★

**本质**：More is more——但层级仍在，复杂不等于乱。
**签名**：插画+3D+图案+贴纸+渐变同屏共存；高饱和撞色（3–5 色成体系）；展示字体可装饰（display serif 变体 / Syne / 花体）；每屏都满，视线有明确路径（大→中→小三级入口）。
**版式**：密但有骨架——网格仍在，元素叠网格而非散放；每屏一个主视觉锚点；重复母题（同款星星/波浪线）制造统一。
**网页**：性能预算严（图多）；动效分层（背景慢前景快）；确保正文区有「静区」保可读。
**印刷**：四色满版；riso 多色套印绝配（套印错位是加分）。
**生图关键词**：`maximalist collage layout, saturated clashing palette, layered illustrations stickers and patterns, dense but hierarchical, repeating motifs`
**走样**：无层级的垃圾场（什么都大=什么都不大）；正文淹没在纹理里；没有重复母题导致散架。
**混搭**：✓ Scrapbook、Y2K；✗ Swiss、Luxury（互斥）。

## R03 · Neo-Brutalism 新粗野主义 ★★★★

**本质**：粗黑描边 + 硬阴影 + 原色块 + 超大字。看起来反设计，UX 仍然正常——**视觉叛逆，功能保守**。
**签名**：边框 2–3px 纯黑；硬阴影 `box-shadow: 6px 6px 0 #000`（无模糊无透明）；底色高饱和原色（黄 #FFDE59 / 粉 #FFB3D9 / 蓝 #A6FAFF / 薄荷 #B1F3B1）；字体粗壮（Archivo Black / Space Grotesk Bold / Lexend Mega；CJK：站酷庆科黄油体）；按钮 hover 位移 2px 阴影缩短（物理感）。
**版式**：明显网格、粗分割线；卡片方角 0px；模块大而少；超大标语左对齐。
**网页**：状态齐全（hover/active/disabled 都做位移或反色）；表单同样粗边；a11y 注意黄底黑字过关、原色上文字对比度。
**印刷**：黑白复印后描边仍在=天生耐复印；活动海报强。
**生图关键词**：`neo-brutalist web poster, thick black outlines, hard offset shadows, saturated primary color blocks, oversized bold type, visible grid`
**走样**：圆角残留（哪怕 4px 就破功）；柔和阴影混入；颜色超过 4 种；做成真丑（按钮不可辨认）。
**混搭**：✓ Notes Chic、Bento（粗化版）；✗ Glass、Luxury。

## R04 · Brutalism 粗野主义 ★★★★★

**本质**：为什么网页一定要长得像网页模板？HTML 原生感即立场。
**签名**：系统字（Times New Roman / Arial / monospace）；默认蓝链接可保留；原生 button/checkbox 直出；无圆角无阴影无动画无 max-width 仁慈；巨大文字（viewport 宽）或故意极空；背景可故意只有 #FFF 或 #F0F0F0。
**版式**：单栏 brutal 直排，或故意挤/故意空到极端；无 hero 概念，顶部就是 MY WEBSITE 级标题 + 裸列表导航。
**网页**：真做交互（链接都通）；非对称排版可选；**功能完备**是底线——brutalism 丑得诚实，不是坏。
**印刷**：裸排讲义/传单，Times 12pt 直出反而有力量。
**生图关键词**：`pure brutalist webpage, system fonts, default blue hyperlinks, raw HTML aesthetics, huge plain text, no styling, honest structure`
**走样**：把「没做完」当风格（死链、错位 bug）；加任何美化（渐变按钮、圆角）即背叛；写 "BRUTAL" 字样点题（§1.2）。
**混搭**：✓ 几乎不混（独占）；最多 Notes Chic。

## R05 · Anti-Design 反设计 ★★★★★

**本质**：规则全懂，所以知道怎么故意破。对齐/统一/留白/网格/配色，逐条选一破。
**签名**：多字体并存（Helvetica + Times + 手写体同屏，**各司其职**：标题/引文/批注）；文字故意错位跳行（DON'T / LOOK / HERE 三级缩进）；低清压缩图；元素互相遮挡；字号溢出画面；按钮不像按钮（但可点）。
**版式**：每一处「错」都是决策：列三列故意基线差 12px、图压字 30%、一行字顶出画布右缘。**记下每个破格的理由**，答不出=删。
**网页**：破格仍可读可点（可读性牺牲 ≤30%）；真内容真数据（Anti-Design 配假内容=灾难）。
**印刷**：展览海报、艺术书；印刷错位（套印错版）可用。
**生图关键词**：`anti-design poster, intentionally misaligned mixed typefaces, overlapping elements, low-res imagery, broken layout conventions but clearly deliberate`
**走样**：随机乱=不会设计；破坏无理由；破坏均匀撒满（=假叛逆 §1.2.2）。
**混搭**：✓ Experimental Type；✗ Bento、Glass（结构语法不相容）。

## R06 · Ugly Minimalism 丑极简 ★★★★

**本质**：Minimalism × Anti-Design。极少元素，但每处都「不对」得刚刚好。做得不好是 PPT 没做完，做得好是艺术总监。
**签名**：全画布 ≤5 个元素；背景一个突兀纯色（BRAT 绿 #8ACE00 级）；字体普通到廉价（Arial / 默认宋体），可压扁 (`transform: scaleX(1.2)`) 或系统渲染感；文案全小写、无标点；日期裸排。
**版式**：一个元素一种「错」：标题压扁、日期贴边、词间距不均（`word-spacing: 20px`）；其余大量空白。
**网页**：静态即完成；hover 可无。
**印刷**：单曲封面式海报；专色一色印。
**生图关键词**：`ugly minimalism poster, single garish background color, few elements, cheap default font slightly distorted, all lowercase, awkward but confident`
**走样**：元素超过 6 个；「丑」元素之间互相抢（只许一个丑动作）；做成真懒（默认行高默认边距的裸 HTML ≠ 丑极简）。
**混搭**：✓ Notes Chic；✗ 一切加法风格。

## R07 · Zine / Punk ★★★★★

**本质**：复印机美学——地下杂志、撕纸、胶带、马克笔。给海报用人味第一。
**签名**：黑白高对比照片（复印 3 次的灰阶）；撕纸边缘（实拍素材或 mask）；胶带贴角（半透明矩形 + 轻旋转）；手写批注（圆珠笔蓝或马克笔）；报纸剪贴字（不同字号的铅字拼句）；错位印刷（双层文字 offset 1–2px 品红/青分色）；FPS 感纸纹。字体：打字机体 Space Mono / 手写 LXGW 文楷 / 剪贴铅字混排。
**版式**：拼贴网格——元素带 1–3° 微旋转、层叠遮挡、钉书钉/胶带锚点；关键信息（日期地点）反而用最大最清楚的字。
**网页**：扫描素材做 img；旋转用 transform；hover 让胶带「揭起」可做彩蛋。
**印刷**：黑白复印即原汁原味；riso 红黑双色更佳；A3 对折成 zine 小册。
**生图关键词**：`punk zine collage poster, photocopied black and white photos, torn paper edges, masking tape, marker handwriting, cut-out newspaper letters, misaligned duotone print`
**走样**：脏污均匀满铺（§1.2.3 人味不可伪造）；关键信息也做旧到看不清；彩色照片直接贴（必须黑白/双色调处理）。
**混搭**：✓ Analog×Digital、Grunge（二选一）；✗ Swiss、Luxury。

## R08 · Grunge ★★★★

**本质**：使用痕迹本身——脏污、颗粒、划痕、破损。地下文化质感。
**签名**：深灰/炭黑/做旧米色底；整体颗粒 overlay（noise 3–6%）；划痕/折痕/咖啡渍素材稀疏点缀；字体磨损感（Tungsten / 旧打字体；或正常字体 + mask 破损边缘）；图像降饱和 + 边缘暗角。
**版式**：正常排版骨架上**局部**做旧——角落污渍、一道划痕穿过标题、一张图的折痕；不是每处都脏。
**网页**：颗粒用 fixed 伪元素 + pointer-events:none（性能，见 design-taste-frontend §6.E）。
**印刷**：牛皮纸/再生纸印刷；专色黑做旧。
**生图关键词**：`grunge texture design, distressed overlays, scratches and stains used sparingly, worn surface, desaturated imagery, underground band poster mood`
**走样**：全画面平均加噪（=滤镜不是设计）；文字脏到不可读；grunge 素材盖住信息层级。
**混搭**：✓ Zine（轻度）、Cyberpunk（反乌托邦脏化）；✗ Luxury、Bento。

## R09 · Y2K / Cyber Y2K ★★★

**本质**：1998–2005 的人想象的未来。Chrome、泡泡、像素窗、蓝色下划线链接。
**签名**：chrome 金属字（CSS: 银灰渐变填充 + 高光扫过）；泡泡/蝴蝶/星星贴片；像素 UI 窗（Win98 灰 #C0C0C0 + 蓝标题栏 #000080）；Marquee 式滚动字幕；蓝紫粉渐变（此处渐变合法——它是主题本体）；字体 VAG Rounded 类圆体 / VT323 像素；CD 光盘虹彩。
**版式**：贴纸式散布 + 中央 chrome 大字；小元素环绕（像素星、闪图 gif 感）；信息窗用「系统对话框」样式装。
**网页**：cursor 可用系统指针（反定制）；`<marquee>` 语义已废，用 CSS animation 复刻；闪烁克制（光敏性癫痫风险，<3 次/秒）。
**印刷**：派对传单、专辑周边；虹彩镭射贴纸工艺绝配。
**生图关键词**：`Y2K cyber aesthetic, chrome metallic typography, bubble and butterfly stickers, pixel windows, iridescent gradients, early internet optimism`
**走样**：与 Cyberpunk 混淆（Y2K 是甜的、未来乐观；Cyberpunk 是暗的、反乌托邦）；chrome 字配现代扁平 UI；贴纸满铺无重心。
**混搭**：✓ Maximalism、Scrapbook；✗ Swiss、Luxury。

## R10 · Acid Graphics ★★★★★

**本质**：地下电音视觉——荧光色 × 怪字体 × 密码化信息，刺眼是功能。
**签名**：荧光绿 #B6FF00 / 荧光黄 #EFFF00 / 紫 #A020F0 / 银 chrome / 纯黑底；字体极窄（Anton 斜排）/ 极宽 / warp 拉伸变形；条形码、二维码、编号、十字准星、WARNING、箭头、坐标（**必须承载真实信息**：日期、场地、阵容，§1.1）；液态金属/融滴 3D 素材。
**版式**：信息密集但分区明确——荧光大字（艺人名）压一切，参数小字网格排（真实 tech rider 数据感）；边缘可出血裁切。
**网页**：hover 荧光溢出（drop-shadow 荧光色，此处合法）；自动播放克制。
**印刷**：UV 荧光墨专色印刷是真 acid；黑底 + 荧光绿二色即成。
**生图关键词**：`acid graphics rave flyer, neon lime and purple on black, warped stretched typography, barcodes and crosshairs with real data, liquid chrome 3D, underground club energy`
**走样**：装饰性假条码假坐标（无信息= §1.1 回声重灾区）；荧光色用在正文长文；与 Y2K 甜味混淆。
**混搭**：✓ Kinetic、Retro-Futurism；✗ Notes Chic、Luxury。

## R11 · Cyberpunk ★★★

**本质**：高科技，低生活。黑色 + 霓虹 + 终端 + 巨企压迫感。
**签名**：近黑底 #0D0D14；霓虹青 #00F0FF + 品红 #FF2A6D + 琥珀警 #F9F002（≤2 主）；等宽字全文（JetBrains Mono / Share Tech Mono）；扫描线 overlay（2px 横纹 8% 透明度）；终端窗口（真实日志/真命令输出）；故障 glitch（RGB 分离 1–2px，hover 触发）；CJK 配思源黑体 + 少量像素字点缀。
**版式**：信息密集 HUD 式；主区 + 侧栏数据流；边角真实系统状态（uptime、版本）。
**网页**：glitch 动画 ≤400ms 且 reduced-motion 降级；终端可用真实 API 日志。
**印刷**：展板/专辑；黑底霓虹专色。
**生图关键词**：`cyberpunk interface, dark terminal aesthetics, neon cyan and magenta on black, scanline texture, glitch typography, dense HUD layout`
**走样**：假终端假日志（必须真数据或明确 mock 标注）；霓虹三色全上（限 2）；Acid 化（酸是派对，赛博是压迫）。
**混搭**：✓ Grunge（脏化反乌托邦）；✗ Y2K、Notes Chic。

## R12 · Retro-Futurism ★★★

**本质**：过去的人想象的未来——50s 太空时代 / 80s 蒸汽波 / 苏式控制论。
**签名**：50s：豆形椅橙 + 蛋壳白 + 细腿字（Googie 式星爆）；80s：蒸气波粉紫青渐变 + 网格地平线 + 罗马雕像 + 日文片假名点缀；苏式：构成主义红黑 + 几何宣传画。选**一个年代**做纯。
**版式**：年代构图复刻——50s 海报的星爆放射、80s 的居中对称 + 地平线网格、苏式的对角线块面。
**网页**：80s 网格可用 CSS perspective 做 3D 地面；雕像图必配真实内容区块。
**印刷**：复古旅行社传单、黑胶封面；专色 + 纸纹。
**生图关键词**：`retro-futurism poster, 1950s space age optimism, atomic era starburst layout, OR vaporwave 80s grid horizon pastel, OR Soviet constructivist geometry`（三选一，勿混）
**走样**：三个年代混做一锅（选一个！）；现代 UI 元素直接混入；「复古未来」写成文案点题。
**混搭**：✓ Acid（80s 支线）、Texture；✗ Notes Chic。
