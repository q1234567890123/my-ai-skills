# Codex 接入 my-ai-skills

统一技能库：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 推荐方式

Codex 原生支持 `SKILL.md`，建议把需要的 skill 安装到：

```text
~/.codex/skills/{skill-name}/SKILL.md
```

安装后重启 Codex，让它重新加载技能元数据。

## 单个 skill 安装方式

在 Codex 里使用 `$skill-installer`，按 GitHub 目录安装某一个 skill。

示例：

```text
$skill-installer install https://github.com/q1234567890123/my-ai-skills/tree/main/coding/clean-code
```

再例如：

```text
$skill-installer install https://github.com/q1234567890123/my-ai-skills/tree/main/dev/debug-pro
```

## 不建议一次安装全部

虽然可以批量同步，但建议先安装常用技能，例如：

```text
karpathy-guidelines
clean-code
debug-pro
ai-prompt-enhance
```

原因：

- 技能越多，启动时需要读取的 metadata 越多。
- 虽然完整正文一般按需加载，但技能列表太大也会增加选择噪音。

## 使用方式

安装后可以直接说：

```text
使用 clean-code skill 审查这段代码。
```

或：

```text
使用 debug-pro skill 定位这个报错。
```

## 中文规则

本仓库每个新 skill 都有 `README.zh.md`。如果英文 `SKILL.md` 看不懂，可以要求：

```text
使用 clean-code skill，并优先参考 README.zh.md，用中文回复。
```

