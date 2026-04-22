# CodeBuddy 接入 my-ai-skills

统一技能库：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 推荐方式

CodeBuddy 支持 Skills，目录结构是每个 skill 一个文件夹，里面有 `SKILL.md`。

常见位置：

```text
~/.codebuddy/skills/{skill-name}/SKILL.md
```

或项目级：

```text
.codebuddy/skills/{skill-name}/SKILL.md
```

## 单个 skill 安装示例

以 `consulting-reply` 为例，将 GitHub 目录：

```text
https://github.com/q1234567890123/my-ai-skills/tree/main/aesthetic/consulting-reply
```

同步到：

```text
~/.codebuddy/skills/consulting-reply/
```

目录结构：

```text
~/.codebuddy/skills/consulting-reply/
├── SKILL.md
└── README.zh.md
```

## CodeBuddy 导入方式

如果当前版本提供“Import Skill / 导入 Skill”按钮，可以直接选择对应 skill 文件夹或 `SKILL.md`。

## 使用方式

```text
使用 consulting-reply skill 写一段医美咨询回复。
```

```text
使用 game-coding skill 检查游戏输入逻辑。
```

## 中文规则

本仓库每个新 skill 都有中文说明 `README.zh.md`。需要中文时明确要求：

```text
使用 consulting-reply skill，并参考 README.zh.md，用中文回复。
```

