# Game Coding 中文版

路径：`game-dev/game-coding/`

## 这个技能是干什么的

这个技能用于指导 AI 写游戏代码，尤其适合 Cocos Creator、Unity、玩法系统、输入交互、动画回调、关卡状态、UI 交互等。

核心目标：规则归规则，表现归表现。不要让节点、Prefab、动画、粒子、摄像机偷偷成为玩法规则的源头。

## 来源与参考链接

以下链接已在 2026-04-22 确认可以访问：

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/godot-gdscript-patterns
- https://github.com/sickn33/antigravity-awesome-skills/blob/main/CATALOG.md

建议关注的 catalog 路径：`game-development/multiplayer`、`godot-gdscript-patterns`。

说明：本技能内容是为本仓库重新整理编写，不是整段复制第三方正文。上面的链接用于标明参考来路，方便你后续追踪更新。

## 分层规则

游戏代码应分为三层：

- 纯逻辑层：规则、状态、胜负、分数、随机种子。
- 表现层：节点、坐标、Sprite、动画、粒子、音效、输入。
- 编排层：场景切换、存档、广告、SDK、埋点、平台接口。

不要让 UI 节点成为玩法状态的唯一来源。节点可以显示状态，但核心规则应该能脱离节点被理解。

## Cocos Creator 规则

1. 触摸事件必须绑定在有 `UITransform` 和可见渲染组件的节点上。
2. 不要在 `TOUCH_START` 到 `TOUCH_END` 之间修改当前触摸节点的父级。
3. 节点 Layer 必须和 Camera Visibility 匹配。
4. `Canvas.cameraComponent` 必须始终有效。
5. 不要随意动态创建全屏 `BlockInputEvents` 遮罩。
6. 高频生成销毁的节点要使用对象池。
7. 节点进入对象池前要停止 tween、schedule、事件监听和动画状态。

## Unity 规则

1. `Update()` 只做轻量调度，不写大段业务。
2. 高频访问的组件要缓存引用。
3. 子弹、特效、飘字、列表项使用对象池。
4. 热路径禁止频繁 `FindObjectOfType`、`GameObject.Find`。
5. 物理相关逻辑放在 `FixedUpdate` 或明确的物理步骤。
6. 稳定配置可以考虑 ScriptableObject，场景行为放在 MonoBehaviour。

## 状态机建议

常见游戏流程可以拆成：

- `idle`：等待输入；
- `dragging`：拖拽或操作中；
- `resolving`：结算中，禁止重复输入；
- `success`：成功；
- `failed`：失败；
- `paused`：暂停；
- `destroyed`：对象已销毁或已回收。

## 常见 BUG

- 连点触发两次结算。
- 动画回调在节点销毁后才执行。
- 通关逻辑被多个系统重复调用。
- UI 遮罩挡不住下层点击。
- 对象池节点残留旧事件、旧缩放、旧透明度。
- 广告奖励未确认就提前发奖。
- 场景重载后旧回调继续改状态。

## 输出要求

AI 使用本技能时，应说明：

- 玩法规则放在哪；
- 表现组件放在哪；
- 输入和生命周期有什么风险；
- 是否需要对象池；
- 如何验证正常路径、重复输入、取消、暂停、重进场景。
