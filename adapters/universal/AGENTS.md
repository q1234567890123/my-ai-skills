# My AI Skills Router

统一技能库：

```text
https://github.com/q1234567890123/my-ai-skills
```

## 语言规则

- 默认使用中文回复。
- 执行过程、计划、风险提示、验证结果都用中文说明。
- 代码标识符、命令、文件路径保持原文。

## 技能读取规则

当用户说“使用 xxx skill”“调用 xxx 技能”“按 xxx 规范处理”时：

1. 只读取对应目录的 `SKILL.md`。
2. 如果用户需要中文，或 `SKILL.md` 是英文，同时读取同目录 `README.zh.md`。
3. 不要加载整个 `my-ai-skills` 仓库。
4. 不要复制整个仓库到当前项目。
5. 找不到技能时，先查看仓库根目录的 `DIRECTORY.zh.md`。
6. 如果当前工具不能访问 GitHub，提示用户需要先把对应 skill 同步到本地。

## 技能索引

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

## 执行纪律

- 复杂任务先给计划，等待用户批准后再改文件。
- 修改前先读取现有文件。
- 保持最小改动，不做无关重构。
- 完成后说明验证结果。

