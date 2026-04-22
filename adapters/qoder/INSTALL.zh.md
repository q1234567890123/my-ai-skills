# Qoder 接入 my-ai-skills

统一技能库：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 推荐方式

Qoder 支持 `SKILL.md`。个人级 skill 目录：

```text
~/.qoder/skills/{skill-name}/SKILL.md
```

项目级 skill 目录：

```text
.qoder/skills/{skill-name}/SKILL.md
```

建议：

- 常用通用技能放 `~/.qoder/skills/`。
- 项目专用技能放 `.qoder/skills/`。

## 单个 skill 安装示例

以 `debug-pro` 为例，将 GitHub 目录：

```text
https://github.com/q1234567890123/my-ai-skills/tree/main/dev/debug-pro
```

同步到：

```text
~/.qoder/skills/debug-pro/
```

目录结构应为：

```text
~/.qoder/skills/debug-pro/
├── SKILL.md
└── README.zh.md
```

## 使用方式

```text
使用 debug-pro skill 分析这个错误。
```

或：

```text
/debug-pro
```

具体触发方式以当前 Qoder 版本为准。

## 中文规则

如果 Qoder 只读取 `SKILL.md`，可以在请求里补一句：

```text
优先参考 README.zh.md，用中文回复。
```

