# 视觉创作 Skill 深度目录

> 本目录基于作者 `dacnay816y62-hub` 的 15 个公开仓库，以及本地的 `zy-cinematic-realism`。  
> `cinema-dna-21x9x3` 已属于作者的 15 个仓库，因此按唯一项目计数为 16 个。  
> 这里分析的是仓库中的 README、SKILL、references、scripts、templates、examples 和测试结构，不只是 GitHub 简介。

## 快速选择

| 需求 | 首选 |
|---|---|
| 单张电影感图 / 跨模型提示词 | zy-cinematic-realism |
| 21:9 三联或九镜故事板 | cinema-dna-21x9x3 |
| 写实角色、服装和连续性 | character-casting-studio-skill |
| 写实人像 | fantasy-life-force-portrait-photography |
| 任意地点的摄影模拟 | fantasy-photography-simulation-github |
| 电影海报 | fantasy-movie-poster-skill |
| 东方文化海报 | chinese-poster-skill / fantasy-dongfang-jianyuehaibao |
| 地域文化视觉 | regional-culture-poster |
| 文化 KV 主视觉 | culture-fragment-poster-engine |
| 极简杂志海报 | FANTASY-Minimal-Magazine |
| 照片转手绘 | photo-revival |
| 只改照片中的人物 | street-photo-illustration-skill |
| 车窗旅行风景 | window-scenery-skill |
| 趣味社交媒体内容 | fantasy-qiqiguaiguai-skill |
| Logo 方向探索 | minimal-logo-design |

## 1. zy-cinematic-realism

[仓库](https://github.com/popopo-99/zy-cinematic-realism)

**具体作用：**  
它不是单纯的“电影感 prompt 模板”，而是一套从场景理解到模型表达、再到结果修复的提示词编译系统。核心链路是：

`Scene Master → Creative Grammar → Model Compiler → Result Repair`

先固定人物、空间、动作、机位、光源、色彩和限制条件，再根据导演方法、摄影语法和目标模型生成 prompt。一个 Scene Master 可以编译为多个模型版本。

**关键特点：**

- 支持 Create、Model Router、Transcode、Multi-model Pack、Continuity、Repair、Prompt Check、Director、Style、Cinematography、Remix、Creative Shuffle 等模式。
- 有 GPT Image 2、Midjourney、Seedream 5.0 Pro、Nano Banana 专用 adapter，不把同一条 prompt 粗暴复制到不同模型。
- 通过导演 Four-Axis、相机和灯光参考、反 AI cleanup、negative prompts、quality checklist 约束输出。
- 强调光源必须有物理原因，避免无来源轮廓光、雾、霓虹、胶片词堆叠和广告式调度。
- 有 Continuity Bible、Shot Deltas、结果诊断和“一次只改一个变量”的 Remix 机制。

**什么时候用：**  
要做单帧电影图、已有 prompt 检查、跨模型转换、导演风格翻译、连续性设定或失败结果修复时使用。它是 16 个项目里最通用、最像“提示词工程基础设施”的一个。

**不适合：**  
如果目标只是直接生成三张组成的视觉故事板，`cinema-dna-21x9x3` 的默认工作流更直接。

## 2. cinema-dna-21x9x3

[仓库](https://github.com/dacnay816y62-hub/cinema-dna-21x9x3)

**具体作用：**  
把一句故事、人物、建筑、体育或科幻设定转为真人电影式的 21:9 单帧、三联镜头或九镜故事板。默认偏向 3 张独立镜头，再纵向拼接；完整故事可切换为 9 张并拼成 3×3。

**关键特点：**

- 先判断关系压力：谁看谁、谁知道更多、谁受空间或制度限制。
- 每镜只保留一个主要动作、一个次要线索、一个构图决定和一个主光源。
- 每镜要求写清“视线从哪里进入，被什么阻挡，落到什么信息，最后由什么带走”。
- 先建立 Continuity Bible，再建立 Shot Ledger，记录剧情功能、动作、观众位置、景别、构图压力和镜头变化。
- 9 镜协议包含节拍、镜头变化矩阵、空间轴、漂移修复、分批生成和九宫格验收。
- 自带 PowerShell 拼版脚本，保留 9 张源图，只补跑失败镜头，不因一张失败而重做整组。
- 明确禁止把三联或九宫格交给模型在一张画布中绘制。

**什么时候用：**  
要做电影分镜、三联图、九宫格、镜头测试、连续叙事或 21:9 视觉系列时使用。

**不适合：**  
只想要一条极短 prompt、模型参数转译或对单张生成结果做技术修复时，使用 `zy-cinematic-realism`。

## 3. character-casting-studio-skill

[仓库](https://github.com/dacnay816y62-hub/character-casting-studio-skill)

**具体作用：**  
以材质和视觉参考为依据，完成写实角色的“选角工作室”：不是只生成一个漂亮头像，而是判断演员/角色气质、年龄层、体态、肤质、发型、服装材质和镜头适配性，并形成可供后续分镜使用的角色锚点。

**关键特点：**

- 以 material reference 为输入核心，把面料、织法、磨损、反光、垂坠和颜色作为角色身份的一部分。
- 仓库包含较大的 SKILL 与 references 体系，说明它强调流程化判断，而非单一模板。
- 角色通常需要保留稳定的年龄段、脸型/发型、体态、服装主色、材质和识别物，便于跨场景复用。
- 适合作为 `cinema-dna` 前置环节：先锁角色，再锁空间和镜头。
- 关注写实演员感，避免把角色做成游戏立绘或过度修饰的时尚广告模特。

**什么时候用：**  
做短剧/电影角色设定、演员气质探索、服装材质参考、系列人物一致性或角色定妆图时使用。

**不适合：**  
只需要一张无连续性要求的人像海报时，`fantasy-life-force-portrait-photography` 更轻量。

## 4. fantasy-life-force-portrait-photography

[仓库](https://github.com/dacnay816y62-hub/fantasy-life-force-portrait-photography)

**具体作用：**  
生成强调“生命感”的人像摄影。核心不只是脸部清晰，而是通过呼吸、肌肉张力、眼神、皮肤纹理、姿态、服装触感和光线方向让人物像真实的人在镜头前存在。

**关键特点：**

- 重点处理人物状态，而不是标准证件式摆拍。
- 倾向真实皮肤、自然不对称、身体重量和合理手部姿态。
- 可用于人物写真、情绪肖像、艺术人像和角色气质测试。
- 与角色 casting skill 的区别是：前者偏“角色身份与连续性”，本项目偏“单张人像的生命力和摄影表现”。

**什么时候用：**  
用户说“生命感人像”“真实肖像”“不要塑料皮肤”“像摄影师拍的”时使用。

**不适合：**  
需要多人关系、复杂场面调度或 21:9 故事时，使用电影或摄影模拟 skill。

## 5. fantasy-photography-simulation-github

[仓库](https://github.com/dacnay816y62-hub/fantasy-photography-simulation-github)

**具体作用：**  
模拟“摄影师在任何地方完成摄影”，把幻想地点、异世界、极端环境或不可能场景按真实摄影任务来处理。

**关键特点：**

- 把地点想象转成可拍摄的机位、镜头距离、视线高度、前中后景和光源关系。
- 重视摄影味道：曝光、景深、反射、空气透视、材质、动态范围和有限光学缺陷。
- 与一般概念艺术 prompt 的区别是，它要求画面像“被相机记录”，而不是像世界观设定图。
- 可作为 `cinema-dna` 的单帧摄影分支，但叙事连续性不如后者完整。

**什么时候用：**  
做“在月球/异星/幻想建筑中拍一张真实照片”、旅行摄影模拟、地点视觉勘景时使用。

## 6. fantasy-movie-poster-skill

[仓库](https://github.com/dacnay816y62-hub/fantasy-movie-poster-skill)

**具体作用：**  
把电影故事、类型、剧照或三联分镜转成海报方向与分层生产流程。它先判断这是什么电影，再决定视觉母题、标题承载面和排版层级，不是简单给剧照加片名。

**关键特点：**

- 先分析类型、受众、情绪温度、核心冲突和视觉母题。
- 分为 Base Layer、Typography Layer、Grid Composite：底图、标题图层、最终合成分别处理。
- 强调标题要附着在真实物理表面上，如墙、玻璃、幕布、天空、桌面或道具。
- 有 genre presets、typography system、composition models、quality control 和可执行脚本。
- 约束虚构署名、避免真实电影节桂冠、片商标志、随机媒体引语和无意义小字。
- 适合 9:16 中文电影海报及多尺寸扩展。

**什么时候用：**  
已经有电影故事/剧照/分镜，需要片名、海报、底图与文字层、可发布封面时使用。

**不适合：**  
只做东方文化活动海报时，`chinese-poster-skill` 或 `regional-culture-poster` 更精准。

## 7. FANTASY-Minimal-Magazine

[仓库](https://github.com/dacnay816y62-hub/FANTASY-Minimal-Magazine)

**具体作用：**  
制作 3:4 的安静、留白、编辑出版感海报或杂志页。它把画面当作 editorial layout，而不是商业广告或电影海报。

**关键特点：**

- 重点是留白、图文比例、标题层级、材料质感和克制的视觉节奏。
- 适合室内、家具、艺术、生活方式、文化选题和品牌杂志内容。
- 仓库有 examples、references 和独立 SKILL，说明它更偏可复用的编辑设计规范。
- 与电影海报 skill 的差异是：这里不需要强叙事冲突，重点是稳定、安静和出版物秩序。

**什么时候用：**  
做杂志封面、编辑海报、艺术展页、空间/家具内容或高端生活方式视觉时使用。

## 8. chinese-poster-skill

[仓库](https://github.com/dacnay816y62-hub/chinese-poster-skill)

**具体作用：**  
把主题、中文标题、文化对象、品牌文案或活动信息转换成 refined contemporary Chinese / Oriental poster 方向和 prompt，并支持 Image 2 批量任务。

**关键特点：**

- 反对“宣纸、毛笔字、红印章”的单一东方模板。
- 使用“主题 → 文化关键词 → 物理结构 → 视觉形状 → 海报构图”的转译链。
- 内置 Museum Archive、Architectural System、Material Macro、Typography Campaign、Route/Map/Data、Textile/Pattern 等视觉原型。
- 标题被当成构图结构，而不是最后贴上的文字。
- 仓库有 Python 批量生成脚本、JSONL job 文件和 manifest，适合多方向测试和批处理。
- 默认 3:4 竖版，中文为主文字，适用于展览、博物馆、工艺、茶、香、时尚和文化品牌。

**什么时候用：**  
需要中文标题、东方文化、博物馆或文化品牌海报时使用。

## 9. fantasy-dongfang-jianyuehaibao

[仓库](https://github.com/dacnay816y62-hub/fantasy-dongfang-jianyuehaibao)

**具体作用：**  
面向东方文化的“简约编辑海报”专用 skill，比通用中文海报更聚焦于现代、克制、文化物证和视觉系统。

**关键特点：**

- SKILL 文件较大，包含 assets、references、examples 和 v2-tests，说明它有持续迭代和测试导向。
- 强调真实文化物件、材料、建筑结构、工艺痕迹和可验证的视觉来源。
- 支持 A/B/C 三联方向比较，不急于一次确定最终方案。
- 避免把传统文化处理成符号堆砌，倾向用材质、结构、文字比例和留白表达东方性。
- 与 `chinese-poster-skill` 的区别：后者覆盖范围更广且有批量脚本；本项目更像一套针对东方简约海报的深度 art direction。

**什么时候用：**  
做传统文化、器物、建筑、工艺、茶香、展览或东方生活方式品牌，并要求现代简约而非古风时使用。

## 10. regional-culture-poster

[仓库](https://github.com/dacnay816y62-hub/regional-culture-poster)

**具体作用：**  
把中国地域文化转成当代大字海报、编辑海报和文化视觉，而不是旅游宣传页。

**关键特点：**

- 重点是地域的结构性证据：建筑、材料、地貌、字体、工艺、物产、色彩来源和生活方式。
- 约束“景点拼贴”和“泛中国风”，要求视觉判断具有地域专属性。
- 支持大标题、文化对象、现代排版和非旅游化的叙事。
- 适合城市文化、地方博物馆、地域品牌、非遗活动和文化传播。

**什么时候用：**  
输入是某个省市、地域、地方工艺或地方文化主题时优先使用。

## 11. culture-fragment-poster-engine

[仓库](https://github.com/dacnay816y62-hub/culture-fragment-poster-engine)

**具体作用：**  
快速把零散的文化碎片、物件、文字、纹理和象征元素组织成一张海报 KV 主视觉。

**关键特点：**

- 更像“海报主视觉引擎”，强调快速搭建、视觉碎片组织和 KV 输出。
- 仓库同时包含 SKILL、README、示例图片、素材目录和压缩包，偏向可直接复用的视觉资产/交付包。
- 适合把多个文化线索压缩成一个主画面，但不一定承担完整的文化研究或品牌系统。
- 与 regional-culture 的区别：regional-culture 负责地域文化的专属性与转译逻辑；本项目负责把已有文化线索快速组织成视觉主画面。

**什么时候用：**  
已有文化关键词、物件和视觉素材，需要快速出活动 KV、主海报或多版视觉方向时使用。

## 12. fantasy-qiqiguaiguai-skill

[仓库](https://github.com/dacnay816y62-hub/fantasy-qiqiguaiguai-skill)

**具体作用：**  
制作轻松、奇趣、反常识的社交媒体视觉，包括 3:4 海报、拼贴、街拍、宠物、旅行和中文排版。

**关键特点：**

- 目标不是电影写实，而是让视觉有记忆点、幽默感和社交传播性。
- 支持现实照片、动物、旅行和生活场景的混搭。
- 兼顾中文标题、图文关系和社交平台比例。
- MIT License，公开可复用性较好。
- 与 photo-revival 的区别：photo-revival 偏诗意和温柔；qiqiguaiguai 偏趣味、反差和内容传播。

**什么时候用：**  
做小红书/抖音/朋友圈内容、趣味海报、宠物梗图、旅行视觉或需要“有点怪但好看”的内容时使用。

## 13. photo-revival

[仓库](https://github.com/dacnay816y62-hub/photo-revival)

**具体作用：**  
把日常照片变成诗意的白纸手绘插画，尽量保留原照片的生活关系、动作和情绪。

**关键特点：**

- 不是把照片完全重画成复杂插画，而是保留生活瞬间并改变表现媒介。
- 白纸、手绘、线条和留白形成统一视觉语言。
- 适合家庭照、旅行照、日常记录和纪念性图像。
- 与 street-photo-illustration 的区别：本项目倾向整体照片插画化；street 项目强调只替换人物、保持原环境。

**什么时候用：**  
用户提供一张普通照片，希望得到温柔、手绘、纪念册或文艺插画效果时使用。

## 14. street-photo-illustration-skill

[仓库](https://github.com/dacnay816y62-hub/street-photo-illustration-skill)

**具体作用：**  
把街拍或生活方式照片中的人物改成插画角色，同时严格保留现实环境、动作关系、衣服轮廓、配饰、手持物和透视。

**关键特点：**

- “只改人，不改环境”是核心约束。
- 有 BLACK INK 与 COLOR CHIBI 两种明确模式。
- BLACK INK 适合黑白线稿、纸感角色；COLOR CHIBI 适合彩色生活方式和社交内容。
- prompts、assets、examples 分离，便于稳定调用。
- 这是一个局部编辑 skill，不是从零生成完整插画。

**什么时候用：**  
想保留街道、商店、地铁、咖啡店等真实场景，只把人物变成线稿或 chibi 时使用。

## 15. window-scenery-skill

[仓库](https://github.com/dacnay816y62-hub/window-scenery-skill)

**具体作用：**  
生成从交通工具窗户向外看的旅行景色，核心是“被窗框限制的观看”，而不是普通风景图。

**关键特点：**

- 窗框、玻璃反射、运动模糊、室内外曝光差、座位视角和行进方向构成固定语法。
- 适合火车、汽车、飞机或船舱视角。
- 有中英文 README、references、examples、scripts，适合结构化复用。
- 可以表达旅行、通勤、离别、等待和移动中的片刻。

**什么时候用：**  
用户明确要求“车窗外”“火车旅行”“从车里看风景”“移动中的风景”时使用。

## 16. minimal-logo-design

[仓库](https://github.com/dacnay816y62-hub/minimal-logo-design)

**具体作用：**  
为品牌探索原创极简 Logo 方向，不把所有项目都做成黑白建筑图标。

**关键特点：**

- 先判断品牌的主角是定制字标、抽象几何标、图形系统还是趣味手绘形。
- 使用 70/20/10 层级：70% 主识别、20% 支持语言/符号、10% 描述信息。
- 中文/英文品牌都可做字形比例、字腔、切割、重组、字距和留白设计。
- 默认同时考虑核心 Logo、双语锁定版和延展系统版。
- 强调先读出品牌名，再记住结构；不把现成字体直接冒充最终商标。
- 明确不用于复刻现有品牌或参考 Logo。

**什么时候用：**  
做建筑、艺术、摄影、音乐、时尚、家具、酒店、生活方式品牌的 Logo 方向探索时使用。

## 组合工作流

### A. 角色到电影海报

`character-casting-studio-skill → cinema-dna-21x9x3 → fantasy-movie-poster-skill`

先锁人物身份、材质和服装，再设计场景与镜头，最后把分镜核心冲突提炼成海报。

### B. 单帧电影视觉

`zy-cinematic-realism`

如果题材复杂，可先用 `fantasy-photography-simulation-github` 做地点摄影判断，再交给 `zy-cinematic-realism` 做模型编译。

### C. 东方文化品牌

`regional-culture-poster` 或 `fantasy-dongfang-jianyuehaibao` → `minimal-logo-design`

前者负责文化视觉，后者负责品牌识别；不要用 Logo skill 代替文化研究。

### D. 照片再创作

- 整体转手绘：`photo-revival`
- 只改人物：`street-photo-illustration-skill`
- 做窗外旅行景色：`window-scenery-skill`

### E. 文化活动主视觉

`regional-culture-poster` 负责地域逻辑，`culture-fragment-poster-engine` 负责快速组织 KV，`chinese-poster-skill` 负责中文标题与东方排版。

## 边界判断

- “电影感”不等于都用 `cinema-dna`：单帧提示词工程用 `zy-cinematic-realism`，三联/九镜叙事用 `cinema-dna`。
- “东方”不等于都用宣纸和印章：优先判断是文化研究、地域文化、东方简约，还是商业海报。
- “照片变插画”要先判断是整体媒介转换，还是仅人物替换。
- Logo、海报、电影剧照是不同交付物，不能只靠换几个风格词互相替代。
