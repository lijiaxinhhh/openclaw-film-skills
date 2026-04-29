---
name: screenplay-analysis
description: >
  剧本分析工具，用于电影/纪录片拉片学习。支持剧本结构拆解、角色弧线追踪、对白分析、场景功能标注、叙事技巧识别，并可关联镜头语言。输入剧本文件（PDF/TXT/Markdown）或剧本文本，输出结构化分析报告。支持自建 LLM 分析和 Prescene API 增强两种模式。
  Screenplay analysis tool for film/documentary study. Supports structure breakdown, character arc tracking, dialogue analysis, scene function tagging, narrative technique identification, and cinematography linkage. Input screenplay files (PDF/TXT/Markdown) or pasted text, output structured analysis reports. Supports self-built LLM analysis and optional Prescene API enhancement.
---

# Screenplay Analysis - 剧本分析工具

用于电影/纪录片**拉片学习**的专业剧本分析工具。将剧本拆解为结构化数据，帮助创作者理解叙事设计、角色塑造和对白技巧。

## ⚠️ 翻译原则

**始终从音频重新翻译，不使用现有字幕的翻译。** 原因：
- 现有字幕翻译常不准确，不够信达雅
- 翻译不符合故事情景和语境
- 官方字幕可能有删减或改编

**流程：**
1. 用 Whisper 从音频提取原始语言逐字稿
2. 由 LLM 结合上下文、故事情景进行意译（非直译）
3. 专有名词、俚语、文化梗需特别处理
4. 现有字幕仅作参考对照，不作为最终翻译来源

## 核心特性

- ✅ **层级结构拆解** — Act → Sequence → Scene → Beat 四级分析
- ✅ **角色弧线追踪** — 主要人物从起点到终点的变化轨迹
- ✅ **对白深度分析** — 潜台词、冲突、信息量、人物声音区分度
- ✅ **场景功能标注** — 建置/转折/高潮/解决/过渡
- ✅ **叙事技巧识别** — 悬念、伏笔、闪回、多线叙事、不可靠叙述者等
- ✅ **镜头语言关联** — 剧本意图如何通过视听语言实现
- ✅ **中英双语术语** — 所有专业术语附中文释义
- ✅ **双模式运行** — 自建分析（免费）+ Prescene API（可选增强）

## 术语对照表 (Terminology)

### 结构层级 (Structure Hierarchy)

| 英文术语 | 中文释义 | 说明 |
|---------|---------|------|
| **Act** | 幕 | 故事的最大结构单位，通常三幕（Setup / Confrontation / Resolution） |
| **Sequence** | 序列 | 由若干场景组成的情节段落，服务于一个戏剧目标 |
| **Scene** | 场景 | 在同一时间/地点发生的连续动作，剧本的基本单位 |
| **Beat** | 节拍 | 场景内的最小戏剧单元，一次动作/反应构成一个节拍 |
| **Turning Point** | 转折点 | 故事方向发生根本性变化的时刻 |
| **Inciting Incident** | 激励事件 | 打破主角日常生活的催化事件 |
| **Midpoint** | 中点 | 故事中间的重大转折，通常改变主角的目标或认知 |
| **Climax** | 高潮 | 全剧最高张力点，核心冲突的最终对决 |
| **Resolution** | 解决 | 高潮之后的收尾，展示新秩序的建立 |

### 场景功能 (Scene Functions)

| 功能 | 英文 | 说明 |
|------|------|------|
| **建置** | Setup | 建立人物、世界、规则、基调 |
| **冲突** | Confrontation | 推动矛盾升级，制造障碍 |
| **转折** | Turning Point | 改变故事方向或人物认知 |
| **高潮** | Climax | 张力顶点，核心矛盾的爆发 |
| **解决** | Resolution | 矛盾化解，新秩序确立 |
| **过渡** | Transition | 连接不同段落，调整节奏 |
| **揭示** | Revelation | 向观众或角色透露关键信息 |
| **镜像/回声** | Mirror/Echo | 呼应前文场景，形成对照 |

### 角色分析 (Character Analysis)

| 术语 | 英文 | 说明 |
|------|------|------|
| **角色弧线** | Character Arc | 角色从故事开始到结束的内在变化轨迹 |
| **动机** | Motivation | 驱动角色行动的内在需求或欲望 |
| **缺陷** | Flaw | 角色的性格弱点，也是成长空间 |
| **欲望 vs 需求** | Want vs Need | 角色追求的目标（Want）和真正需要学会的（Need） |
| **对手** | Antagonist | 阻碍主角达成目标的力量（可以是人、制度、自然、自我） |
| **盟友** | Ally | 帮助主角的角色，也可作为主角的镜像 |
| **声音区分度** | Voice Distinction | 不同角色的对白应有可辨识的语言风格差异 |

### 对白分析 (Dialogue Analysis)

| 术语 | 英文 | 说明 |
|------|------|------|
| **潜台词** | Subtext | 角色真正想表达但没有直接说出口的内容 |
| **信息量** | Information Density | 单位对白中传递的有效信息（情节/人物/世界观） |
| **冲突层级** | Conflict Level | 对白中的对抗程度：表面礼貌 → 暗流涌动 → 正面对抗 |
| **省略** | Omission | 角色刻意回避或无法说出的内容，往往比说出的更重要 |
| **节奏** | Rhythm | 对白的快慢、长短交替，影响场景张力 |

### 叙事技巧 (Narrative Techniques)

| 技巧 | 英文 | 说明 |
|------|------|------|
| **悬念** | Suspense | 让观众知道危险但角色不知，制造紧张感 |
| **伏笔** | Foreshadowing | 前期埋下线索，后期产生回报 |
| **闪回** | Flashback | 中断当前叙事，回溯过去的事件 |
| **多线叙事** | Multi-thread | 多条故事线并行推进 |
| **不可靠叙述者** | Unreliable Narrator | 叙述者的视角或信息存在偏差或欺骗 |
| **非线性叙事** | Non-linear Narrative | 打破时间顺序的叙事结构 |
| **戏剧反讽** | Dramatic Irony | 观众知道的信息比角色多，产生张力或讽刺效果 |
| **契诃夫之枪** | Chekhov's Gun | 每个出现的元素都应该在后续发挥作用 |

## 分析方法论

本工具综合以下经典编剧理论和行业工具的分析框架：

### Walter Murch 剪辑六法则（应用于剧本层面）

按优先级排序：
1. **Emotion (情感)** — 这一刻是否传达了正确的情感？
2. **Story (故事)** — 是否推进了叙事？
3. **Rhythm (节奏)** — 节奏是否正确？
4. **Eye-trace (视线追踪)** — 观众的注意力是否被正确引导？
5. **Two-dimensional plane of screen (2D平面)** — 画面构图是否合理？
6. **Three-dimensional space (3D空间)** — 空间关系是否连贯？

> 在剧本分析中，法则 4-6 转化为：场景的空间描写是否清晰、视觉提示是否到位、导演可执行性如何。

### Callaia Coverage 分析框架

借鉴 Callaia 的剧本评估报告（Coverage）结构：
- **Logline (一句话梗概)** — 用一句话概括核心故事
- **Synopsis (剧情梗概)** — 按结构节点梳理完整剧情
- **Character Analysis (角色分析)** — 主要角色的动机、弧线、关系
- **Dialogue Rating (对白评分)** — 对白的自然度、信息效率、风格一致性
- **Originality Rating (原创性评分)** — 题材、视角、手法的新颖程度
- **Structure Rating (结构评分)** — 节奏把控、转折设置、因果链的严密性

### Prescene 结构化数据输出

参考 Prescene 的数据结构设计：
- **Scene Context (场景上下文)** — 每个场景的时间、地点、在场人物、情绪基调
- **Character Relationship Map (角色关系图)** — 人物之间的动态关系
- **Dialogue Patterns (对白模式)** — 角色的语言习惯、高频词汇、句式特征

## 工作流程

### 模式 A：自建分析（免费，LLM 直接分析）

适用于：快速分析、学习拉片、无 API Key 的场景。

**输入方式：**
- 剧本文件路径（PDF / TXT / Markdown）
- 直接粘贴剧本文本

**分析流程：**

```
Step 1: 解析剧本
  ├── PDF → 使用 pdf 解析工具提取文本
  ├── TXT → 直接读取
  └── Markdown → 直接读取

Step 2: 预处理
  ├── 识别场景分隔符（INT./EXT.、场景编号等）
  ├── 区分对白与动作描写
  └── 标记幕/序列边界

Step 3: 结构化拆解
  ├── 建立 Act → Sequence → Scene → Beat 层级
  ├── 标注每个场景的功能类型
  └── 识别关键转折点

Step 4: 逐维度分析
  ├── 角色弧线追踪
  ├── 对白分析（潜台词、冲突、信息量）
  ├── 叙事技巧识别
  └── 与镜头语言的关联建议

Step 5: 生成报告
  └── 输出结构化 Markdown 分析报告
```

**示例 Prompt 模板（供 Agent 使用）：**

```
你是一位专业的剧本分析师，精通 Robert McKee、Syd Field、Blake Snyder 的编剧理论。
请对以下剧本进行全方位分析：

1. 结构拆解：识别 Act / Sequence / Scene / Beat 层级
2. 场景功能标注：每个场景的主要功能（建置/转折/高潮/解决/过渡/揭示/镜像）
3. 角色弧线：主要角色从起点到终点的变化
4. 对白分析：潜台词、冲突层级、信息效率
5. 叙事技巧：使用的技巧及其效果
6. 镜头语言关联：关键场景的视听实现建议
7. 综合评价：优点、不足、学习要点

请用中英双语标注所有专业术语。
```

### 模式 B：Prescene API 集成（可选增强）

适用于：需要精确结构化数据、批量分析的场景。

**前置条件：**
- 需要 Prescene API Key
- 设置环境变量 `PRESCENE_API_KEY` 或在 `TOOLS.md` 中记录

**流程：**

```
Step 1: 上传剧本到 Prescene API
  POST https://api.prescene.com/v1/analyze
  Headers: Authorization: Bearer {API_KEY}
  Body: { "screenplay": "<text>" }

Step 2: 获取结构化数据
  - 场景列表 + 上下文
  - 角色关系图
  - 对白模式统计

Step 3: 在自建分析基础上叠加
  - 用 Prescene 数据补充/校验 LLM 分析
  - 生成更精确的结构化报告
```

> **注意：** Prescene API 为可选增强。模式 A 的自建分析已可独立完成高质量报告。

## 输出格式

分析报告采用结构化 Markdown，包含以下章节：

### 报告模板

```markdown
# 🎬 剧本分析报告：《片名》

## 📋 总览 (Overview)
- **片名 / Title:**
- **类型 / Genre:**
- **时长 / Runtime:**
- **Logline (一句话梗概):**
- **核心主题 / Theme:**
- **综合评分:**

## 🏗️ 结构拆解 (Structure Breakdown)

### 三幕结构 (Three-Act Structure)
| 幕 | 范围 | 核心事件 | 功能 |
|----|------|---------|------|
| Act I (第一幕/建置) | — | — | — |
| Act II (第二幕/对抗) | — | — | — |
| Act III (第三幕/解决) | — | — | — |

### 序列分析 (Sequence Analysis)
...

### 场景清单 (Scene List)
| # | 场景 | 位置 | 功能 | 主要节拍 | 评估 |
|---|------|------|------|---------|------|
| 1 | INT. 起居室 - 夜 | Act I | 建置 | — | — |

## 👤 角色弧线 (Character Arcs)

### 主角：[Name]
- **起点状态:** ...
- **欲望 (Want):** ...
- **需求 (Need):** ...
- **缺陷 (Flaw):** ...
- **弧线轨迹:** ...
- **终点状态:** ...

### 角色关系图 (Relationship Map)
...

## 💬 对白分析 (Dialogue Analysis)

### 对白风格总评
- **自然度:**
- **潜台词密度:**
- **声音区分度:**

### 关键对白解读
| 场景 | 对白 | 表面含义 | 潜台词 | 冲突层级 |
|------|------|---------|--------|---------|
| — | "..." | — | — | — |

## 🎭 叙事技巧 (Narrative Techniques)

| 技巧 | 出现场景 | 效果评估 |
|------|---------|---------|
| 悬念 | — | — |
| 伏笔 | — | — |
| 闪回 | — | — |

## 🎥 镜头语言关联 (Cinematography Linkage)

### 关键场景视听建议
| 场景 | 剧本意图 | 建议景别 | 运镜 | 光线 | 声音 |
|------|---------|---------|------|------|------|
| — | — | — | — | — | — |

> 💡 **交叉引用提示：** 本报告的镜头语言建议可与 `video-expert-analyzer` 的镜头评分报告交叉对照。

## 📊 综合评价 (Overall Assessment)

### 优点
...

### 不足
...

### 学习要点
...

## 📚 参考理论 (References)
...
```

## 使用示例

### 示例 1：分析本地剧本文件

```
用户：帮我分析这个剧本 /path/to/screenplay.pdf

Agent：
1. 读取并解析 PDF 文件
2. 按照模式 A 的流程进行结构化分析
3. 输出完整分析报告
```

### 示例 2：分析粘贴的剧本文本

```
用户：分析以下剧本片段：
INT. 咖啡厅 - 日
李明坐在角落，盯着手机。王芳推门进来。
...

Agent：
1. 解析粘贴的文本
2. 识别场景、对白、动作描写
3. 输出分析报告
```

### 示例 3：与 video-expert-analyzer 联合使用

```
用户：我有一个电影片段的视频，帮我同时分析剧本和镜头

Agent：
1. 使用 screenplay-analysis 分析剧本结构和对白
2. 使用 video-expert-analyzer 分析镜头语言
3. 交叉引用两份报告，生成综合拉片笔记
```

## 理论参考 (Theoretical References)

| 著作 | 作者 | 核心贡献 |
|------|------|---------|
| **《Story》** | Robert McKee | 故事设计原理、场景分析、价值转变理论 |
| **《Screenplay》** | Syd Field | 三幕结构理论、情节点（Plot Point）概念 |
| **《Save the Cat》** | Blake Snyder | 15 节拍表（Beat Sheet）、类型分类 |
| **《In the Blink of an Eye》** | Walter Murch | 剪辑六法则、情感优先原则 |
| **《Film Art》** | David Bordwell & Kristin Thompson | 叙事学、电影风格分析框架 |
| **《The Anatomy of Story》** | John Truby | 22 步故事结构、角色网络理论 |
| **《Adventures in the Screen Trade》** | William Goldman | "Nobody knows anything"、剧本实战经验 |

---

> **交叉引用：** 与 [`video-expert-analyzer`](../video-expert-analyzer/) 配合使用，可实现从文字到视听的完整拉片分析。剧本分析提供叙事意图，视频分析验证视听执行，两者互补形成深度学习闭环。
