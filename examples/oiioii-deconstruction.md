# 完整示例：以 OiiOii 为例拆解一个 Multi-Agent 平台

> 本文件是 `ai-product-deconstruction` Skill 的完整示例，展示六层框架的实际应用。内容基于公开资料整理，标注"已查证"与"推断"。

---

## 1. 拆解对象与一句话定位

- **一句话定位**：OiiOii 是**全球首个动画创作 Agent**，把一整套动画制作团队抽象成"前台一个输入框 + 后台一条多智能体管线"，以**交付动画成片**为目标的端到端工作流。
- **产品构成**：前台是输入框（托管/对话两种模式），后台是约 7 个专业角色 Agent 组成的虚拟制片团队 + 模型调度层 + 资产/知识库。
- **面向用户**：PUGC/PGC（半专业与专业内容创作）：内容创作者、动画爱好者、IP 运营者、音乐人、教育内容制作者。
- **应用场景**：
  - 剧情动画短片：快速生成故事动画，适合自媒体/短剧/微电影
  - 音乐 MV 制作：按音乐风格和歌词生成匹配动画 MV
  - 知识科普动画：帮助教育工作者/知识博主把复杂内容动画化
  - IP 二创与衍生：基于经典 IP 或热门作品二次创作
  - 动态壁纸与素材：设计师与创意工作者的个性化素材

---

## 2. 产品介绍

成立不到半年、团队仅十余人的初创公司，产品处于内测阶段即引来近 10 万人排队申请（已查证：2025 年底内测引爆 10 万人排队，2026 年中升级 2.0）。

---

## 3. 效果体验：用一个场景测试它的能力

### 测试场景：30 秒人物向故事短片（剧情故事短片模式 + 对话模式）

测试 OiiOii 的多智能体协作、一致性控制及端到端交付能力。测试脚本（分镜示例）：

```text
通过室内静谧与窗外喧嚣的强烈对比，烘托一种大隐隐于市的奇遇感。
分镜一【入场】：深山古道旁的木质两层茶馆，夕阳西下，金晖洒在飘动的【茶】字布幌上。青衣少侠（背负斗笠、腰间玉佩）缓步走进茶馆大门，背影拉出长影。大远景，固定转小幅推镜。风吹竹林沙沙声、远处蝉鸣、低沉古琴入场。
分镜二【偶遇·近景对话】：茶馆内部光影斑驳，小二倒茶。小二：客官，您打听的那位，刚才就在窗边坐着。主角：茶留下，人往哪儿去了？中近景聚焦主角眼神特写。
分镜三【变故·POV窗外远眺】：主角侧头看窗外，POV 竟是一处喧闹艳丽的古镇集市，红衣神秘女子一闪而过。主观视角，暗调切高饱和亮调，声音瞬间爆发（叫卖、锣鼓、马蹄），古琴转急促琵琶。
```

### 评估权重

| 评估维度 | 权重 | 核心考察点 |
|---|---|---|
| 端到端效果 | 40% | 成片观赏性、一致性、有趣度 |
| 交互共创层 | 20% | 流程顺滑感、指令转化 |
| Agent 协作层 | 25% | 信息传递准确、纠偏 |
| 基础能力层 | 15% | 模型调度、资产复用 |

### 能力维度评测表（实测得分）

| 能力层级 | 评测维度 | 打分逻辑 | 满分 | 得分 |
|---|---|---|---|---|
| 端到端 | 成品质量与叙事 | 可消费价值；有无音色突变/逻辑断层 | 20 | 13 |
| 端到端 | 视觉资产一致性 | 角色闪烁/形象错乱/风格跳变 | 20 | 19 |
| 用户层 | 意图理解与引导 | 指令转化精准度 | 15 | 14 |
| 用户层 | 反馈机制与灵活性 | 跳出-回归是否顺畅 | 10 | 8 |
| 技术层 | 多智能体协作 | 信息同步率 | 15 | 14 |
| 技术层 | 行业知识库应用 | 复杂运镜/节奏控制 | 10 | 9 |
| 模型层 | 多模型动态调度 | 分镜匹配最优模型 | 5 | 5 |
| 模型层 | 资产复用与沉淀 | 资产精准调用 | 5 | 5 |

**总分：87 / 100**（评级：70~89，流程通顺，少量人工干预可得不错视频，复杂细节仍有瑕疵。）

### 分数评级参考

- 90~100：稳定产出高质量长时长动画，一致性近乎完美
- 70~89：流程通顺，少量干预可得不错视频，复杂细节（手指、文字）仍有瑕疵
- 60~69：有角色闪烁或逻辑断档，但创意启发和快速草图出色（接近 OiiOii 的自我定位阶段）
- <60：高频逻辑错误，无法交付完整叙事

---

## 4. 产品定位：它和其他 AIGC 产品有什么差异点

OiiOii 的独特点不在模型，而是 **动画垂直 + 交付导向**。

### 垂直到只干一件事

> 创始人：如果只说一点差异，那就是我们只专注动画，一切以交付动画成片为目标。

- 不做通用 AIGC 工作台，所有交互围绕 角色–分镜–剧本–短片。
- 全是影视术语，对专业创作者极友好。
- 对比：即梦、可灵、可画强调全模态全场景，牺牲深度换广度；OiiOii 把模型藏到底层，把动画工种知识提到最前台。

### 把 Agent 做成动画专业角色

直接用行业内真实角色命名 Agent：艺术总监、编剧、分镜师、角色设计师、场景设计师、音乐总监、产品设计师。用户是在"远程带一个动画团队"，而不是"调度一堆工具"。效果：

- 低门槛：小白知道跟编剧改剧情、跟分镜师说多几个特写
- 高信任：专业创作者能精准定位问题出在哪个环节
- 扩展性极强：每个 Agent 能力可独立升级，对用户只是某个工种变强了

### 托管模式 vs 对话模式：为两类创作者同时服务

- **托管模式**：丢一句想法/一张照片，全权交给系统跑完整流程（小白秒得哇塞结果，形成传播）
- **对话模式**：每一步可插手，改分镜、换角色、调色调（给专业创作者控制感）
- **两模式可串联**：托管快速出 v1 → 对话逐镜精修 → 托管批量衍生（同一 IP 系列短片）

---

## 5. 产品拆解：OiiOii 是怎么把团队装进一个平台的？

### 5.1 市场层拆解

#### 市场情况（已查证）

2025 年是公认的**漫剧元年**，也是 AIGC 目前落地变现最清晰的赛道之一。制作成本压缩至传统 1/5~1/10（一部漫剧综合成本可低至 10~15 万），制作周期从月缩短至周，10 人以内小团队即可运转。当前短剧市场突破 500 亿元，漫剧市场可达 200 亿元；抖音、快手、腾讯、爱奇艺、网易等平台跨界布局漫剧并出台激励政策。

#### 竞争格局

- **第一层：工具/基础设施玩家**
  - **巨日禄**：漫剧制作工具标杆，极垂直，只服务专业漫剧团队，核心优势是多模型调度 + 一站式工作流（文案-分镜-视觉-配音-成片），TOP 榜单一半以上作品由其制作，爆款率比大盘高 40% 以上。
  - **OiiOii**：差异化动画 Agent，7 个 AI 智能体组成虚拟制片团队，161+ 种动画风格模板，卖点是连贯叙事的完成度而非单镜头素材；创始人明确不以漫剧为主攻方向，更偏向独立动画创作者。
- **第二层：平台**：抖音、快手、红果、爱奇艺、腾讯、百度（七猫）、阅文等几乎全部主流平台入场，推扶持政策和分账机制（爱奇艺独家分账最高达 100%）。
- **第三层：模型厂商**：Seedance 2.0 被业内评为"杀死比赛级"产品（效率提升 180 倍）；可灵偏影视级，在动作控制、音画同步有专业优势。

### 5.2 商业层拆解

#### 为什么 OiiOii 能火

- 产品定位：以交付动画成片为出发点的端到端工作流
- 专业化 AI：专业导演对于需求的顶级理解力
- 交互机制：既有规矩（托管）又能跳出（对话）
- 产品气质：纯粹、热血的品牌气质与社区文化

#### 变现方式（已查证）

订阅制，四档会员：

| 档位 | 价格 | 每日生成 | 分镜数 | 高清导出 |
|---|---|---|---|---|
| Free | $0 | 100 盒饭 | — | — |
| Base | $9/月 | 1000 | 10 | 100 次 |
| Star | $25/月 | 3000 | 15 | 1000 次 |
| Pro | $84/月 | 8000 | 16 | 4000 次 |

#### 护城河：不是模型，而是动画工艺知识 + 多模型编排能力

- 模型层整合 GPT-4o、Midjourney、nanoBanana pro、Sora2、Veo3.1、海螺 02 等，本身不是护城河（大家都能接 API）。
- 护城河在：如何把**动画工艺流程映射成可自动化的 Agent 管线**；如何在底层不同模型间做**风格统一、角色一致性、节奏控制**；如何用简单界面承载全部复杂性，让用户只感知"一个团队在给我干活"。
- 产业视角：OiiOii 真正沉淀的是**行业工作流的算法化表达（工艺知识）**。

> 体验决定用户是否被激活，流程决定能不能每天出十条，模型决定基础画质，数据决定壁垒。

### 5.3 场景/用户层拆解

> 原则：没有真实决策动作，都是伪需求。交互入口在哪？输入什么、输出什么？如何降低上手难度？

#### 功能模块

- **快速**：快速生视频、音乐概念短片。侧重即时满足感，由艺术总监直接调用模型出片。
- **专业**：剧情故事短片。侧重全流程控制，唤醒包括编剧、分镜师在内的 7 个 Agent 依次协作。
- **创意**：衍生品设计。满足差异化实体转化需求，可调用产品设计师 Agent。

#### 使用路径

- **正向流程**：用户输入想法/照片 → 艺术总监理解与拆解 → 编剧出剧本 → 角色/场景设计师定资产 → 分镜师生成分镜 → 音乐总监配乐 → 剪辑整合 → 成片输出。
- **逆向/异常流程**：用户对任意环节不满意 → 跳出到该 Agent 单独修改 → 状态回滚到稳定节点 → 回到主流程继续（跳出-回归机制）。

### 5.4 技术层拆解

> 它背后是 Workflow 还是单 Agent 还是 Multi-Agent？有没有接 RAG？接了哪些外部插件？如何处理生成中的不确定性（信息不全怎么办）？

**结论**：Multi-Agent 架构 + 全局共享上下文 + RAG 风格库 + 表单式 HITL（human in the loop）。

#### Agent 构成

| Agent | 角色定位 | 核心职责 |
|---|---|---|
| 艺术总监（主 Agent） | 全流程起点 | 确定动画基本方向与视觉调性，理解/澄清/拆解需求，Agent 路由，制定上游约束 |
| 编剧 | 剧本骨架 | 生成剧本摘要，细化角色描述与分镜情节描述词，提供报价单 |
| 角色设计师 | 角色资产 | 文字设定 → 角色主图 → 三视图概念图，同步至资产库保一致性 |
| 场景设计师 | 场景资产 | 场景图生成，优化提示词解决构图单一/对称/居中问题，提升场景一致性 |
| 分镜师 | 分镜片段 | 按角色形象+剧情生成分镜视频，支持单镜重建/裁剪/合并 |
| 音乐总监 | 音画同步 | 背景解说（旁白）生成，匹配音乐与环境音效，MV 模式运镜与听感融合 |
| 产品设计师 | 衍生品设计 | 特定物件、道具或衍生产品设计，确保与整体风格统一 |

#### 全局上下文（一致性问题的解法）

**核心问题：OiiOii 如何解决角色 & 场景一致性？**

上下文工程的艺术：增删改查。全局上下文不仅是存储空间，更像整个项目的 PRD——确保艺术总监制定的计划能被角色设计师、分镜师读取，所有 Agent 上下文保持一致，通过**强引用关系**让各 Agent 互不打架。

```yaml
1. 项目元数据 (Project Meta)
   project_id / version / technical_spec(比例、时长、帧率)

2. 核心剧本字段 (Core Scripting Fields)
   script_summary / emotional_tone / visual_style_tags / scene_count

3. 角色字典 (Character Library - 共享关键)
   characters[]: { char_id, name, description, main_image_uri, concept_sheet_uri }

4. 分镜资产流水线 (Storyboard Assets - 链式核心)
   storyboard_scenes[]: { shot_id, shot_description, asset_uri,
     actual_duration[], actor_lines[], storyboard_audio[], actor_refs[] }
```

#### 艺术总监 Agent

**逻辑梳理**：输入需求 → 判断是否含分镜/剧情/角色设定（缺则追问）→ 识别 IP 角色（有则弹模型选择卡片）→ 初始化短片信息（时长/比例/语言）→ 初始化角色（确认风格）→ RAG 风格检索 → 情绪基调分析 → 输出结构化创作 Brief → 调度下游。

**构成推导**：**Planner-Executor**（而非 ReAct）。原因：生产、长链路高耦合任务；通过字段更新实现强状态管理；Plan 模式天然支持审批流（人为介入）；支持断点续传（中间步骤出错只需回滚该步骤，不必整个 Agent 重新 ReAct 一遍）。

**可用工具推导**：RAG 风格库 / 上下文管理（manage_global_context）/ 状态管理（rollback_state）/ 表单工具×4（基础设置、模型选择、风格选择、情绪词选择）/ 追问工具（ask_user）/ Agent 调度工具（dispatch_agent）。

**提示词推导（摘要）**：

```markdown
## 1. 角色定义 (Role)
你是 OiiOii 团队的资深 AI 动画制片人兼艺术总监。把用户原始想法转化为《结构化创作 Brief》，
在关键节点拦截等待用户决策，驱动下游多 Agent 协作流。必须遵守 Plan-and-Execute 与全局状态管理。

## 2. 输入契约 (Input Contract)
用户原始需求 {{user_brief}} / 表单回填 {{form_submission}} / 下游回写回调。
每次激活先读取 {{project_context}} 当前状态（status、brief_meta、visual_style_tags、emotional_tone、approval_log）。

## 3. 输出契约 (Output Contract)
只负责项目元数据与全局调性，严禁触碰剧本细节（由编剧产出）。
通过 manage_global_context 写入 status / brief_meta / visual_style_tags / emotional_tone / approval_log。

## 4. 硬约束 (Hard Constraints)
- 严禁跨步执行，必须按 Workflow Step A→E 顺序推进
- visual_style_tags 必须来自 search_film_style 候选集，禁止自创
- 每个用户确认节点必须写入 approval_log，决策可追溯
- 用户提修改意见必须 rollback_state 回置稳定节点，禁止脏数据上叠加
- 输出必须是合法 JSON，禁止 JSON 外自然语言

## 5. 任务处理流程 (Workflow)
Step A 需求获取与初判 → Step B IP 识别与模型预选 → Step C 项目初始化（并行）
→ Step D 视觉与情绪基调构建（RAG 风格 + 情绪词确认）→ Step E 结构化 Brief 合成与输出
→ Step F 状态回置（任意时刻可触发）

## 6. 工具调用规范 (Tool Instructions)
[T1] manage_global_context(action, path, value)  全局上下文统一读写
[T2] search_film_style(keywords, top_k)          RAG 风格库检索
[T3] push_form_card(type, payload)               推送 UI 表单卡片拦截等待决策
[T4] ask_user(question, hint)                    开放问题追问（仅 Step A 缺失时）
[T5] dispatch_agent(target, instruction, context_refs)  调度下游
[T6] rollback_state(target_step, reason)         状态回置

## 7. 输出格式 (Response Format)
严格的 JSON 对象：{ tool_calls[], form_card, brief, next_action, next_hints }
```

#### 编剧 Agent

**逻辑梳理**：识别任务模式（full_draft / rewrite_shot / rewrite_character）→ 生成剧本摘要 → 角色字典（≤5 角色）→ 分镜脚本 + 音效需求（每镜 8~10s）→ 调用计价工具 → 等待用户确认后流转。

**可用工具推导**：剧本优化引擎 / 分镜拆解工具（强制 8~10s/镜）/ 成本估算工具（calculate_pricing）/ 上下文管理。

**提示词推导（摘要）**：

```markdown
## 1. 角色定义 (Role)
资深 AI 动画编剧。把用户想法转化为可被下游消费的「剧本骨架」，提交【报价单+剧本预览】等待确认。

## 2. 输入契约 (Input Contract)
从 {{project_context}} 只读：brief_meta / emotional_tone / visual_style_tags；rewrite 模式读 characters、storyboard_scenes、sfx_brief。

## 3. 输出契约 (Output Contract)
只写剧本骨架，严禁写 asset_uri / main_image_uri / concept_sheet_uri / actual_duration / storyboard_audio。
写入：script_summary / scene_count / sfx_count / characters[] / storyboard_scenes[] / sfx_brief[]

## 4. 硬约束 (Hard Constraints)
- 单分镜口播+动作预估时长 ∈ [8s, 10s]，超 10s 拆镜、不足 8s 合并
- actor_lines 单条 ≤20 中文字 / ≤40 拉丁字符
- actor_refs 必须能在 characters[] 找到（引用完整性）
- 不得引入未声明的新角色；情绪/风格必须在每个 shot 体现

## 5. 任务处理流程 (Workflow)
Step A 模式识别 → B 剧本摘要 → C 角色字典 → D 分镜+音效 → E 计价 → F/G 局部重写

## 6. 工具调用规范 (Tool Instructions)
[T1] manage_global_context(action, path, value)
[T2] calculate_pricing(character_count, scene_count, sfx_count)  # 单价由工具维护，禁止硬编码
[T3] dispatch_agent(target, instruction)  # 等用户确认 pricing 后由主 Agent 触发

## 7. 输出格式 (Response Format)
严格 JSON：{ tool_calls[], canvas{script_summary, characters, storyboard_scenes}, pricing, next_action }
```

#### 角色设计师 Agent

**逻辑梳理**：读取编剧的 name/description → 视觉扩写（瞳色/发型/下装/配饰）→ 生成角色主图 → 表单确认 → 特征锁定生成三视图（character sheet, three-view drawing, white background）→ 资产归档到全局上下文。

**可用工具推导**：提示词生成（转 Midjourney 语法）/ 角色图生成 / 表单工具5（确认信息）/ 概念图生成（引用 main_image_uri）/ 上下文管理。

**提示词推导（摘要）**：

```markdown
# 角色设计师 Agent
## 1. 角色定义：顶尖 AI 角色设计师，读取编剧结构化设定，创作高一致性角色形象并持久化 URI。
## 2. 全局上下文协作协议：基于 {{project_context.character_vault}}，读 name/description，写 main_image_uri/concept_sheet_uri。
## 3. 核心处理流程：
   一阶段 视觉扩写与主图生成（compile_prompt → draw_main_image → 表单确认 → 重绘循环）
   二阶段 特征提取与概念图构建（强制 character sheet, three-view, white background，一致性检查）
   三阶段 资产归档（update_field → 发任务完结信号）
## 4. 视觉一致性规范 (Visual Guardrails)：
   - Cref 引用主图 URI 作为 Character Reference
   - 禁止幻觉：设定琥珀色眼睛严禁改为其他颜色
   - 对齐 visual_style_tags 整体调性
## 5. 工具调用格式：compile_prompt / draw_main_image / draw_concept_sheet / update_field
```

#### 场景设计师 Agent 【本次补完】

**逻辑梳理**：读取分镜的场景描述与全局风格约束 → 生成/优化场景提示词（解决构图单一、对称、居中问题）→ 调用生图模型生成场景图 → 表单确认 → 将 asset_uri 写回分镜资产，保证跨镜头场景一致性。

**可用工具推导**：

- 场景提示词生成：基于 shot_description + visual_style_tags，编译含光影、景深、构图指导的英文 Prompt
- 构图优化规则：检测并打破居中/对称构图，生成多样机位（三分法、前景遮挡、留白引导）
- 场景图生成：调用生图模型（如 Midjourney / seedream 4.5）生成场景主图
- 表单工具：确认场景效果是否满意，不满意进入重绘循环
- 上下文管理：读写 storyboard_scenes[].asset_uri、场景一致性参考

**提示词推导（摘要）**：

```markdown
# 场景设计师 Agent (Scene Designer v1.0)
## 1. 角色定义
你是 OiiOii 团队的场景设计师，负责把编剧/分镜师的环境描述转化为风格统一、构图专业的场景资产，
为分镜视频提供背景与氛围基础，并通过统一的场景规范保障跨镜头场景一致性。

## 2. 输入契约 (Input Contract)
从 {{project_context}} 只读：
- storyboard_scenes[].shot_description（当前镜头的场景与环境描述）
- visual_style_tags（全局视觉风格）
- emotional_tone（全局情绪基调，影响光影与氛围）

## 3. 输出契约 (Output Contract)
只负责场景资产，严禁触碰角色形象与角色一致性的字段。
通过 manage_global_context 写入：
- storyboard_scenes[].asset_uri（确认后的场景图地址）
- scene_style_notes（该项目的场景风格规范，供后续镜头引用）

## 4. 硬约束 (Hard Constraints)
- 禁止默认居中/对称构图：必须输出多样的构图方案（三分法、引导线、前景遮挡等）
- 场景视觉风格必须对齐 visual_style_tags，禁止自行引入新风格
- 同一项目内重复出现的场景（如"茶馆内景"）必须复用场景资产，保持跨镜头一致
- 用户确认前不得将 asset_uri 写入全局上下文
- 输出必须是合法 JSON

## 5. 任务处理流程 (Workflow)
Step A: 读取分镜场景描述与全局风格
Step B: 生成 2~3 个构图候选（打破单一构图的提示词变体）
Step C: 调用场景图生成，推送表单工具确认
Step D: 确认后写入 asset_uri 与 scene_style_notes，发完结信号

## 6. 工具调用规范 (Tool Instructions)
[T1] compile_scene_prompt(shot_desc, style_tags, composition)  场景提示词编译
[T2] generate_scene_image(prompt, style_ref)                   场景图生成
[T3] push_form_card(type="scene_confirm", candidates)          场景效果确认
[T4] manage_global_context(action, path, value)                写入场景资产与规范
```

#### 音乐总监 Agent 【本次补完】

**逻辑梳理**：读取成片的分镜/镜头与情绪曲线 → 规划音频结构（BGM / SFX / 旁白）→ 调用音频模型生成（BGM：Suno/Udio；SFX：AudioCraft；TTS：ElevenLabs/Azure TTS）→ 对齐画面节奏与时长 → 音乐概念短片模式下确保运镜张力与听感深度融合 → 写回 storyboard_audio。

**可用工具推导**：

- 音频结构规划：基于 emotional_tone 与分镜节奏设计 BGM/SFX/旁白布局
- BGM 生成：Suno / Udio，按情绪曲线生成背景音乐
- SFX 生成：AudioCraft，生成环境音效（脚步声、风声、打斗声）
- TTS：ElevenLabs / Azure TTS，生成背景解说旁白
- 音画对齐：确保音乐段落/音效与分镜时长、情绪节点对齐
- 上下文管理：读写 storyboard_audio、情绪曲线

**提示词推导（摘要）**：

```markdown
# 音乐总监 Agent (Music Director v1.0)
## 1. 角色定义
你是 OiiOii 团队的音乐总监，负责让整部短片"有灵魂的声音"：为画面匹配音乐、环境音效与旁白解说，
并确保音乐情绪曲线与叙事节奏深度绑定。在音乐概念短片模式下，你还负责让运镜张力与音乐听感融合。

## 2. 输入契约 (Input Contract)
从 {{project_context}} 只读：
- emotional_tone（全局情绪基调）
- storyboard_scenes[]（分镜列表，含时长与情节）
- 音乐概念短片模式：用户上传的音乐/风格/主题（BPM、情绪标签或音频文件）

## 3. 输出契约 (Output Contract)
只负责音频层，严禁触碰画面与角色字段。
通过 manage_global_context 写入：
- storyboard_scenes[].storyboard_audio（该分镜的 BGM/SFX 引用）
- audio_plan（全局音频结构：BGM 段落、SFX 位置、旁白文本）

## 4. 硬约束 (Hard Constraints)
- 音乐与分镜时长严格对齐，音画同步优先
- 情绪曲线必须与叙事节奏绑定：关键情节点（如变故、反转）必须有音乐/音效强化
- 旁白文本需要与 actor_lines 不冲突（避免抢戏/重复）
- 音乐概念短片模式：运镜节奏必须与 BPM/情绪标签匹配
- 输出必须是合法 JSON

## 5. 任务处理流程 (Workflow)
Step A: 读取分镜与情绪曲线，生成音频结构规划
Step B: 按段落调用 BGM 生成（Suno/Udio）
Step C: 生成环境音效（AudioCraft）与旁白（TTS）
Step D: 音画对齐校验，写回 storyboard_audio
Step E: 推送表单确认，不满意进入局部重做

## 6. 工具调用规范 (Tool Instructions)
[T1] plan_audio(shots, emotional_tone)            音频结构规划
[T2] generate_bgm(emotion_curve, style)           BGM 生成
[T3] generate_sfx(scene_tags)                    环境音效生成
[T4] generate_narration(text, voice)              旁白 TTS
[T5] align_audio(segments)                        音画对齐校验
[T6] manage_global_context(action, path, value)   写入音频资产
```

#### 产品设计师 Agent 【本次补完】

**逻辑梳理**：读取用户选定的角色/IP 资产与衍生品需求 → 设计衍生品（抱枕、徽章、T恤）预览方案，确保设计元素与整体风格统一 → 调用生图生成预览图 → 表单确认 → 输出可商业化衍生品方案（支持 8K 高清静帧）。

**可用工具推导**：

- 衍生品设计提示词：把角色资产（角色主图、三视图）+ 衍生品类型编译为设计 Prompt
- 衍生品图生成：调用生图模型生成抱枕/徽章/T恤等预览图
- 风格统一校验：确保衍生品设计与短片/角色视觉风格一致（复用角色 asset 与 style tags）
- 表单工具：确认衍生品方案，支持迭代
- 上下文管理：读写角色资产引用、设计稿 URI

**提示词推导（摘要）**：

```markdown
# 产品设计师 Agent (Product Designer v1.0)
## 1. 角色定义
你是 OiiOii 团队的产品设计师，专注于把动画角色/IP 转化为可商业化的实体衍生品设计方案
（抱枕、徽章、T恤、手办等），确保每一件衍生品都与角色形象和作品风格高度统一。

## 2. 输入契约 (Input Contract)
从 {{project_context}} 只读：
- characters[]（目标角色，含 main_image_uri、concept_sheet_uri）
- visual_style_tags（作品视觉风格）
- 用户选择的衍生品类型与诉求

## 3. 输出契约 (Output Contract)
通过 manage_global_context 写入：
- merchandise[].design_uri（衍生品设计预览图地址）
- merchandise[].type（抱枕/徽章/T恤等）
- merchandise[].spec（材质、尺寸、印刷说明）

## 4. 硬约束 (Hard Constraints)
- 衍生品设计必须复用角色主图/三视图资产，禁止凭空重新设计角色形象
- 设计元素（配色、纹理、构图）必须对齐 visual_style_tags 与作品风格
- 输出支持商业化要求：可出 8K 高清静帧、多角度预览
- 输出必须是合法 JSON

## 5. 任务处理流程 (Workflow)
Step A: 读取目标角色资产与风格标签
Step B: 生成衍生品设计方案（含多角度预览）
Step C: 推送表单确认，用户不满意进入迭代
Step D: 确认后写入 design_uri，支持导出高清静帧

## 6. 工具调用规范 (Tool Instructions)
[T1] compile_merch_prompt(character_assets, type, style_tags)  衍生品设计提示词
[T2] generate_merch(prompt, ref_uri)                           衍生品图生成
[T3] push_form_card(type="merch_confirm", candidates)          方案确认
[T4] export_hires(design_uri)                                  高清导出
[T5] manage_global_context(action, path, value)                写入设计资产
```

#### 分镜师 Agent

**逻辑梳理**：素材聚合与预视化（读 shot_description、actor_refs、main_image_uri）→ 视听指令编译（音乐提示词、场景提示词、视频提示词）→ 循环生成与校验（HITL，支持单镜重测）→ 成片整合（视频合并）。

**可用工具推导**：上下文管理 / 音频提示词生成 / 场景提示词生成 / 视频提示词生成 / 视频生成 / 音频生成 / 视频合并工具 / 表单确认。

**提示词推导（摘要）**：

```markdown
# 分镜师 Agent
## 1. 角色定位：精通视觉叙事与 AI 视频技术的分镜师，把静态资产转化为符合电影逻辑的动态分镜视频。
## 2. 核心变量管理：读 shot_description / actor_refs / main_image_uri；写 asset_uri / actual_duration / storyboard_audio。
## 3. 处理流程：
   一阶段 素材聚合与预视化（情感曲线、运镜规划）
   二阶段 视听指令编译（音乐提示词 / 场景提示词 / 视频提示词）
   三阶段 循环生成与校验 HITL（Video Gen API → 预览 → 单镜微调重测）
   四阶段 成片整合（Video Merging Tool 合并片段/音频/旁白）
## 4. 生成规范：
   - 角色继承：视频指令强制包含 main_image_uri 维持角色长相
   - 时长一致性：视频时长反馈至 actual_duration，确保音画同步
   - 镜头多样性：避免连续居中构图，灵活使用特写/全景/跟拍
## 5. 工具调用格式：fetch_shot_context / compile_av_prompts / generate_video_clip / merge_final_video
```

### 5.5 模型层拆解

#### 模型范围

- **图片模型（7）**：Nano Banana Pro、Midjourney V6、Stable Diffusion（SDXL）、seedream 4.5、Stable Diffusion 等
- **视频模型（7）**：Sora 2、SeeDance 2.0、Kling 2.1、海螺 02、Vidu、Pika 2.0、Runway Gen-3、可灵 Kling 3.0 Omni
- **音频模型**：BGM（Suno / Udio）、SFX（AudioCraft）、TTS（ElevenLabs / Azure TTS）
- **文本模型**：未明确

#### 路由逻辑

每个模型有独特优势与能力，先与**风格库**做匹配，同时部分场景下灵活调用。

| 模型类别 | 模型名称 | 核心优势 | 推荐适用场景 |
|---|---|---|---|
| 生图 | Nano Banana Pro | 原生高性能，响应快、深度集成 | 快速原型、基础角色填充 |
| 生图 | Midjourney V6 | 美学标杆、光影细腻、电影感 | 主图生成、高质量场景基调 |
| 生图 | Stable Diffusion | 极致控制力（ControlNet 像素级控制） | 复杂道具、特定风格深度定制 |
| 生图 | seedream 4.5 | 风格一致性保持、上下文理解 | 需视觉连贯的概念图 |
| 视频 | Sora 2 | 物理世界模拟器、动态逼真 | 高动态动作分镜（打斗、崩塌） |
| 视频 | Kling 2.1 | 超长时长、人体动作流畅、强一致 | 多人物交互的长分镜 |
| 视频 | Runway Gen-3 | 运镜控制专家（推拉摇移） | 特定运镜（航拍、推近特写） |
| 视频 | Pika 2.0 | 局部动画与特效（火球、流雾） | 奇幻特效、小物件点缀 |
| 视频 | Vidu / 海螺 02 | 响应快、东方审美优化 | 快速预览、情感文戏分镜 |

### 5.6 基础层拆解

- **知识库**：风格库（161+/162+ 种导演级画风，支持参考图"克隆"风格）、视频知识库、内置影视专业知识（希区柯克变焦、环绕镜头、定格动画帧率控制等）、模型表现得分知识
- **数据**：剧本数据、角色库（角色三视图/主图，供跨项目复用）、用户反馈
- **全局上下文**：所有 Agent 共享一套标准 Schema，保证一致性

> 设计启示：
> - 全局上下文的一致性协议在生图产品中尤其重要，必须确保所有 Agent 共享一套标准 Schema
> - 视觉与情绪的映射：AI 产品经理要关注如何把模糊情绪转化为模型可理解的视觉参数（参考知识或映射表）
> - 风格库的动态维护：引入新模型后需重新评测并更新该模型对不同艺术风格的适配度

---

## 6. OiiOii 没做好的地方

**现象**：用户说"不再需要修改分镜 3 视频，继续下一流程"后，Agent 未继续执行。

1. **可能原因推测**：下一步工具调用失败；状态更新失败
2. **解决方案**：
   - 在提示词中增加指令：当用户确认不再修改，**即调用下一步工具**，严禁在调用工具前重复口头确认
   - 工具层检查：若当前状态已是 `confirmed`，直接返回成功，不重复触发逻辑
   - 若 Agent 连续两次输出相同内容，主控 Agent（艺术总监）介入检查工具执行状态并启动备用方案

---

## 7. 架构总结

**一句话总结**：OiiOii 的本质是**把一个动画制作工作室的分工（艺术总监/编剧/角色/场景/分镜/音乐/产品设计）算法化封装成一个 Multi-Agent 平台**——表层是"一句话生成动画"，底层是一个模拟真实动画工作室分工的多智能体系统，由全局共享上下文保证一致性，由模型路由层保证质量，由风格库/角色库/数据沉淀构成壁垒。

**分层架构**：

```text
┌─────────────────────────────────────────────┐
│ 应用层：项目创作（快速/专业/创意）、我的项目   │
├─────────────────────────────────────────────┤
│ Agent 层：主 Agent（艺术总监）+ 7 个角色 Agent │
│   （编剧/角色/场景/分镜/音乐/产品 + 剪辑）     │
│   全局共享上下文 · 表单式 HITL · 状态管理      │
├─────────────────────────────────────────────┤
│ 模型层：生图(7) · 视频(7) · 音频 · 文本       │
│   路由：先与风格库匹配 + 场景灵活调用          │
├─────────────────────────────────────────────┤
│ 基础层：知识库（风格库/视频知识/专业/模型得分） │
│   数据（角色库/剧本/用户反馈）· RAG            │
└─────────────────────────────────────────────┘
```

**关键洞察**：

- 前台用"导演/团队"语义降低用户心智负担，后台用全局上下文 + Planner-Executor 保证工程可控
- 护城河不在模型（可接 API），而在**动画工艺知识的算法化表达 + 多模型编排 + 数据沉淀**
- 托管/对话双模式 + 跳出-回归机制，同时服务小白与专业创作者
- 待改进点在 Agent 的"下一步动作触发"与状态机健壮性
