# OpenClaw Film Analysis Skills

电影/纪录片拉片分析工具套件，基于 [OpenClaw](https://github.com/nicepkg/openclaw) 平台。

## 作者

**李夹心**

## 包含的 Skills

### 1. film-analysis

一站式电影/纪录片拉片分析工具。整合剧本分析、镜头分析、场景时间轴、音乐音响分析、剪辑节奏分析，支持从视频链接或本地文件完成完整拉片。

- 剧本结构拆解
- 镜头语言分析
- 场景时间轴构建
- 音乐音响分析
- 剪辑节奏分析

### 2. screenplay-analysis

剧本分析工具，用于电影/纪录片拉片学习。

- 剧本结构拆解
- 角色弧线追踪
- 对白分析
- 场景功能标注
- 叙事技巧识别
- 支持自建 LLM 分析和 Prescene API 增强两种模式

### 3. video-expert-analyzer

> ⚠️ **来源说明：** 本 skill 原始代码来自 [ALBEDO-TABAI/video-expert-analyzer](https://github.com/ALBEDO-TABAI/video-expert-analyzer)，特此致谢。

高级视频分析与筛选工具，AI 驱动的自动评分系统。整合 Walter Murch 的剪辑规则与动态加权算法，支持专业级视频质量评估。

- 支持 Bilibili、YouTube、抖音、小红书等平台
- AI 自动评分与场景筛选
- 最佳镜头/高光片段提取
- 竞品视频分析

## 安装方法

1. 克隆本仓库到 OpenClaw skills 目录：

```bash
git clone https://github.com/lijiaxinhhh/openclaw-film-skills.git ~/.openclaw/workspace/skills
```

2. 或者将单个 skill 目录复制到你的 OpenClaw workspace/skills 下：

```bash
cp -r film-analysis ~/.openclaw/workspace/skills/
cp -r screenplay-analysis ~/.openclaw/workspace/skills/
cp -r video-expert-analyzer ~/.openclaw/workspace/skills/
```

3. 在 OpenClaw 配置中启用对应的 skill 即可使用。

## 许可证

MIT License
