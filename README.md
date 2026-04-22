# my-ai-skills

这是我的 AI Skills 统一仓库，用来集中管理不同 AI 编辑器可复用的行业技能。

目标是：**所有技能只在这个 GitHub 仓库维护一份**，然后通过安装、同步或规则路由，让 Claude Code、Cursor、Antigravity、Codex、Trae、Qoder、CodeBuddy 等工具按需使用。

## 这个仓库解决什么问题

如果每个 AI 编辑器都单独复制一份规则，后续会出现三个问题：

- 每个工具都有一份副本，维护很麻烦。
- 修改一个 skill 后，其他工具容易忘记同步。
- 把全部规则都塞进上下文会浪费 token，还会让 AI 混用不相关技能。

这个仓库的设计方式是：

```text
GitHub 仓库 = 唯一技能源头
支持 SKILL.md 的工具 = 安装或同步单个 skill
只支持 Rules 的工具 = 使用 adapters 里的路由规则
```

## 两种接入方式

### 1. Skills 安装模式

适合原生支持 `SKILL.md` 的工具，例如：

- Codex
- Claude Code
- Qoder
- CodeBuddy

这类工具通常需要把某个技能目录同步到自己的全局 skills 目录，例如：

```text
Codex       ~/.codex/skills/
Claude      ~/.claude/skills/
Qoder       ~/.qoder/skills/
CodeBuddy   ~/.codebuddy/skills/
```

它们一般只在启动时读取 `name` 和 `description`，真正触发某个技能时才加载完整 `SKILL.md`。

### 2. Rules 路由模式

适合主要支持规则文件的工具，例如：

- Cursor
- Trae
- Antigravity
- 其他支持 `AGENTS.md`、`.rules`、User Rules、Project Rules 的工具

这类工具不一定认识 `SKILL.md`，所以不能指望它们自动加载整个技能库。正确做法是在规则里写一个很短的路由说明：

```text
当用户说“使用 clean-code skill”时，
只读取 coding/clean-code/SKILL.md。

如果需要中文，
再读取 coding/clean-code/README.zh.md。

不要加载整个仓库。
```

对应配置在 `adapters/` 目录里。

## 项目架构

```text
my-ai-skills/
├── README.md                         # 仓库首页，说明项目用途和目录结构
├── DIRECTORY.zh.md                   # 中文目录说明
├── adapters/                         # 各 AI 编辑器的接入配置和安装说明
├── coding/                           # 编程规范、代码质量、AI 编程习惯
├── game-dev/                         # 游戏开发、Cocos/Unity、玩法与性能优化
├── video-edit/                       # 短视频剪辑、竖屏内容、节奏卡点
├── psychology/                       # 自信重塑、外貌焦虑、关系心理、气质提升
├── aesthetic/                        # 医美美学、医美材料设备、咨询回复
├── style/                            # 穿搭、体态、表情、个人气质
├── creative/                         # AI 漫剧、竖屏短剧、角色和分镜创作
├── dev/                              # 专业调试、BUG 定位、工程排错
└── prompt/                           # AI 提示词工程、精准指令、Agent 工作流
```

## 技能目录说明

### coding 编程类

| 目录 | 中文说明 |
| --- | --- |
| `coding/karpathy-guidelines/` | Karpathy 启发的 AI 编码行为准则，减少过度设计、乱改代码、隐藏假设等问题。 |
| `coding/karpathy-coding/` | 极简、高信号、高可读性的编码风格，适合写代码、重构、审查 AI 生成代码。 |
| `coding/clean-code/` | Clean Code、命名、模块边界、错误处理、测试、可维护性和重构规范。 |

### game-dev 游戏开发类

| 目录 | 中文说明 |
| --- | --- |
| `game-dev/game-coding/` | 游戏玩法代码规范，适合 Cocos Creator、Unity、输入、UI、动画、关卡状态。 |
| `game-dev/game-performance/` | 游戏性能优化，适合帧率、内存、DrawCall、GC、资源加载、移动端卡顿排查。 |

### video-edit 短视频类

| 目录 | 中文说明 |
| --- | --- |
| `video-edit/short-video-master/` | 短视频剪辑、竖屏短剧、变美前后对比、节奏卡点、字幕和完播率优化。 |

### psychology 心理与自信类

| 目录 | 中文说明 |
| --- | --- |
| `psychology/confidence-rebuild/` | 自信重塑、外貌焦虑、亲密关系安全感、社交自信、气质提升。 |

### aesthetic 医美类

| 目录 | 中文说明 |
| --- | --- |
| `aesthetic/medical-design/` | 医美审美设计、面部比例分析、抗衰优先级、方案表达、术前术后评价。 |
| `aesthetic/device-material/` | 医美材料和设备原理解释，包含玻尿酸、光电、射频、超声、胶原刺激等。 |
| `aesthetic/consulting-reply/` | 高情商医美咨询回复、私信话术、价格异议、自然感担忧、术后关怀。 |

### style 形象气质类

| 目录 | 中文说明 |
| --- | --- |
| `style/outfit-confidence/` | 穿搭、体态、表情、发型、妆容、第一印象和拍照表现优化。 |

### creative AI 创作类

| 目录 | 中文说明 |
| --- | --- |
| `creative/ai-comic-drama/` | AI 漫剧、竖屏短剧、漫画分镜、角色设定、图片/视频生成提示词。 |

### dev 调试排错类

| 目录 | 中文说明 |
| --- | --- |
| `dev/debug-pro/` | 专业调试、BUG 定位、崩溃排查、测试失败、构建失败、根因分析。 |

### prompt 提示词类

| 目录 | 中文说明 |
| --- | --- |
| `prompt/ai-prompt-enhance/` | AI 提示词工程、精准指令、系统提示词、Agent 工作流、图像/视频提示词。 |

## adapters 接入目录说明

`adapters/` 不是技能正文，而是给不同 AI 编辑器使用的接入模板。

| 目录 | 适用工具 | 作用 |
| --- | --- | --- |
| `adapters/README.zh.md` | 所有工具 | 解释 Skills 安装模式和 Rules 路由模式。 |
| `adapters/universal/AGENTS.md` | 通用 | 支持 `AGENTS.md` 的工具都可以参考。 |
| `adapters/cursor/my-ai-skills.mdc` | Cursor | Cursor Rules 路由配置，建议 Agent Requested。 |
| `adapters/trae/.rules` | Trae | Trae 规则路由配置。 |
| `adapters/antigravity/AGENTS.md` | Antigravity | Antigravity 项目规则配置。 |
| `adapters/codex/INSTALL.zh.md` | Codex | 说明如何把单个 skill 安装到 `~/.codex/skills/`。 |
| `adapters/claude-code/INSTALL.zh.md` | Claude Code | 说明如何把单个 skill 安装到 `~/.claude/skills/`。 |
| `adapters/qoder/INSTALL.zh.md` | Qoder | 说明如何把单个 skill 同步到 `~/.qoder/skills/`。 |
| `adapters/codebuddy/INSTALL.zh.md` | CodeBuddy | 说明如何把单个 skill 同步到 `~/.codebuddy/skills/`。 |

## 使用示例

### 编程

```text
使用 clean-code skill，帮我审查这个模块的可维护性。
```

```text
使用 debug-pro skill，帮我定位这个报错的根因。
```

### 游戏开发

```text
使用 game-coding skill，检查这个 Cocos 输入逻辑有没有生命周期风险。
```

```text
使用 game-performance skill，分析这个场景为什么掉帧。
```

### 医美咨询

```text
使用 consulting-reply skill，帮我回复一个担心做完不自然的客户。
```

```text
使用 medical-design skill，帮我做一个非诊断性的面部审美分析。
```

### 短视频和创作

```text
使用 short-video-master skill，帮我设计一个变美类短视频剪辑节奏。
```

```text
使用 ai-comic-drama skill，帮我做一个 AI 漫剧角色设定和分镜表。
```

### 提示词

```text
使用 ai-prompt-enhance skill，把这段模糊需求改成稳定可执行的 AI 指令。
```

## 使用原则

- 只加载当前任务需要的那个 skill。
- 不要一次加载整个仓库。
- 英文 `SKILL.md` 用于 AI 编辑器识别和执行。
- 中文 `README.zh.md` 用于人工阅读和中文理解。
- 修改 skill 时，优先更新 GitHub 这一份源头，再同步到各工具。

## 编码和格式

本仓库文本文件统一使用 UTF-8 编码。

建议：

- Markdown 文件使用 UTF-8。
- 换行使用 LF。
- 不要用 GBK/ANSI 保存中文文件。
- 如果看到乱码，优先检查编辑器文件编码是否为 UTF-8。
