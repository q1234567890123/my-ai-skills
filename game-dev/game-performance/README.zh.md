# Game Performance 中文版

路径：`game-dev/game-performance/`

## 这个技能是干什么的

这个技能用于优化游戏性能，特别是 Cocos Creator、Unity、移动端、WebGL、实时渲染项目中的卡顿、掉帧、内存飙升、DrawCall 过多、GC 抖动、加载慢等问题。

## 来源与参考链接

以下链接已在 2026-04-22 确认可以访问：

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/performance-optimizer
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/performance-profiling
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/application-performance-performance-optimization

说明：本技能内容是为本仓库重新整理编写，不是整段复制第三方正文。上面的链接用于标明参考来路，方便你后续追踪更新。

## 性能优化原则

先测量，再优化。游戏卡顿不一定是你看到的那个模块造成的，可能来自：

- 脚本 CPU 开销；
- GPU 过绘制；
- 贴图上传；
- GC；
- 物理模拟；
- UI Layout 重建；
- Shader 编译；
- 日志输出；
- 资源加载。

## 性能预算

- 60 FPS：每帧约 16.6ms。
- 30 FPS：每帧约 33.3ms。
- 移动端必须给发热降频留余量。
- 热路径不能频繁分配内存。
- 稳定帧时间比偶尔高帧率更重要。

## 排查流程

1. 在可控场景复现问题。
2. 记录基线：FPS、帧耗时、CPU、GPU、内存、DrawCall、Batch、三角形、贴图内存、GC。
3. 判断瓶颈类型。
4. 一次只做一个优化。
5. 用同一设备、同一场景对比前后结果。
6. 只有测量有效才保留优化。

## Cocos Creator 优化重点

- 合图、共用材质、调整节点顺序来减少 DrawCall。
- 密集 UI 列表中避免频繁切换材质、混合模式、遮罩、贴图。
- 高频对象使用对象池。
- 节点禁用、销毁、回收时停止 tween 和 schedule。
- 大层级 UI 避免频繁 Layout 重建。
- `update(dt)` 中不要反复 `getComponent` 或查找节点。
- UI 文本和进度条尽量事件驱动更新。
- 按平台压缩贴图。

## Unity 优化重点

- 使用 Profiler、Frame Debugger、Memory Profiler。
- `Update`、`LateUpdate`、`FixedUpdate` 中避免分配内存。
- 高频对象用对象池。
- 合理使用静态批处理、动态批处理、GPU Instancing、SRP Batcher。
- 动态 UI 和静态 UI 分 Canvas。
- 减少透明过绘制。
- AI、寻路、排序等重任务分帧。

## 热路径禁忌

- 禁止每帧创建数组、闭包、字符串、对象。
- 禁止每帧扫描节点树或场景树。
- 禁止在热路径做复杂排序。
- 禁止用日志刷屏调试性能问题。
- 禁止没测量就宣称性能提升。

## 输出要求

AI 使用本技能时，应输出：

- 基线数据；
- 判断的瓶颈类型；
- 优化动作；
- 前后对比；
- 剩余风险；
- 下一步测量建议。
