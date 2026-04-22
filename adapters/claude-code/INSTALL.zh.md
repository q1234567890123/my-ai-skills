# Claude Code 接入 my-ai-skills

统一技能库：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 推荐方式

Claude Code 原生支持 Agent Skills。个人级 skill 通常放在：

```text
~/.claude/skills/{skill-name}/SKILL.md
```

项目级 skill 通常放在：

```text
.claude/skills/{skill-name}/SKILL.md
```

建议个人常用技能放个人级目录，项目专用技能放项目级目录。

## 单个 skill 手动安装

以 `clean-code` 为例：

```text
~/.claude/skills/clean-code/SKILL.md
```

文件来源：

```text
https://github.com/q1234567890123/my-ai-skills/tree/main/coding/clean-code
```

安装后重启 Claude Code。

## Plugin 方式

如果后续要团队统一安装，可以把本仓库再包装成 Claude Code plugin。

当前这一版先不做 plugin，只提供：

- GitHub 统一源头；
- 单 skill 安装路径；
- 通用 `AGENTS.md` 路由规则。

## 使用方式

```text
使用 clean-code skill 重构这个模块。
```

```text
使用 game-performance skill 分析掉帧问题。
```

## 中文规则

默认要求 Claude Code 中文回复。需要中文解释时，读取对应目录的 `README.zh.md`。

