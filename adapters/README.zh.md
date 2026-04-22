# adapters 适配器说明

这个目录不是技能正文目录，而是“接入模板目录”。

你的唯一技能源头仍然是：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 为什么需要 adapters

不同 AI 编辑器对 Skill 的支持不一样，不能只靠一个 GitHub 地址让所有工具自动统一加载。

目前分两类：

1. **原生 Skills 模式**
   - 工具认识 `SKILL.md`。
   - 需要把某个 skill 同步/安装到工具自己的全局 skills 目录。
   - 适合：Codex、Claude Code、Qoder、CodeBuddy。

2. **Rules 路由模式**
   - 工具不一定认识 `SKILL.md`，但支持规则文件。
   - 规则文件只写“去哪里找 skill”，不复制完整 skill 内容。
   - 适合：Cursor、Trae、Antigravity，以及其他支持 `AGENTS.md` 或 rules 的工具。

## 不要把所有 skill 全部复制到 Rules

错误做法：

```text
把整个 my-ai-skills 仓库内容塞进 Cursor Rules / Trae rules / AGENTS.md
```

这样会浪费上下文 token，也容易让 AI 同时混用多个不相关技能。

正确做法：

```text
Rules 里只写技能索引和读取规则。
用户点名哪个 skill，AI 才读取哪个 SKILL.md。
需要中文时，再读取对应 README.zh.md。
```

## 推荐使用方式

### 支持 Skills 的工具

从 GitHub 同步到本地全局 skills 目录：

```text
Codex       ~/.codex/skills/
Claude      ~/.claude/skills/
Qoder       ~/.qoder/skills/
CodeBuddy   ~/.codebuddy/skills/
```

这类工具通常只在启动时读取 `name` 和 `description`，真正触发时才加载完整 `SKILL.md`。

### 支持 Rules 的工具

复制对应 adapter：

```text
Cursor       adapters/cursor/my-ai-skills.mdc
Trae         adapters/trae/.rules
Antigravity  adapters/antigravity/AGENTS.md
通用工具      adapters/universal/AGENTS.md
```

这些文件只负责告诉 AI：

- 统一技能库在哪里；
- 每个 skill 对应哪个路径；
- 只读取被点名的 skill；
- 不要加载整个仓库；
- 默认中文回复。

## 当前技能索引

```text
karpathy-guidelines -> coding/karpathy-guidelines/SKILL.md
karpathy-coding     -> coding/karpathy-coding/SKILL.md
clean-code          -> coding/clean-code/SKILL.md
game-coding         -> game-dev/game-coding/SKILL.md
game-performance    -> game-dev/game-performance/SKILL.md
short-video-master  -> video-edit/short-video-master/SKILL.md
confidence-rebuild  -> psychology/confidence-rebuild/SKILL.md
medical-design      -> aesthetic/medical-design/SKILL.md
device-material     -> aesthetic/device-material/SKILL.md
consulting-reply    -> aesthetic/consulting-reply/SKILL.md
outfit-confidence   -> style/outfit-confidence/SKILL.md
ai-comic-drama      -> creative/ai-comic-drama/SKILL.md
debug-pro           -> dev/debug-pro/SKILL.md
ai-prompt-enhance   -> prompt/ai-prompt-enhance/SKILL.md
```

