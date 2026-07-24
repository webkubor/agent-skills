---
name: apple-design
description: Apple-inspired interface design for responsive feedback, fluid motion, translucent materials, typography, accessibility, and interaction quality. Use when designing or reviewing web UI, navigation, drawers, previews, task progress, drag/swipe interactions, or polished motion.
argument-hint: "<page-or-component>"
user-invocable: true
type: procedure
category: coding
platform: shared
---

# Apple Design × Studio 暗色主题

将 Apple 的交互原则用于 Studio，不复制白色苹果视觉。目标是：响应直接、层级清楚、动效可中断、材质克制，并保留 Studio 的暗色东方创作气质。

## Studio 视觉基线

- 背景：`#14110e`
- 主色：`#ff8a50`（珊瑚橙，只用于主行动和重要状态）
- 主文字：`#f2ece5`
- 次文字：`#a89e93`
- 辅助金：`#d9b96a`
- 卡片：深棕半透明 + `backdrop-filter`
- 字体：优先系统字体，不为了 Apple 感引入大体积字体
- 圆角：统一 10–14px，避免每个组件一套圆角

## 八项设计原则

1. **Purpose**：每个控件都必须服务于创作、发现或管理，不为装饰增加操作成本。
2. **Agency**：任务可取消、失败可重试、删除等不可逆操作明确确认。
3. **Responsibility**：生成中明确展示状态，不伪装成功；敏感操作给出后果。
4. **Familiarity**：关闭、返回、预览、下载等位置和行为保持一致。
5. **Flexibility**：桌面侧栏、移动底部导航、窄屏抽屉都要能完成核心流程。
6. **Simplicity**：默认展示常用路径，高级参数收进二级面板。
7. **Craft**：字距、行高、对齐、加载、空态和错误态都要完整。
8. **Delight**：只在完成、收藏、成功等有意义的节点提供轻量反馈。

## 交互与动效

### 响应

- 按下时立即反馈，不等 `click` 完成后才变化。
- 生成任务提交后立即显示任务卡，不让用户等待同步请求。
- 图片加载、上传、切换预览都要有明确的进行中状态。

### 动效

- 普通 UI 默认使用无弹簧或临界阻尼的平滑过渡。
- 抽屉、侧栏、图片预览从触发源方向进入，也从同一方向退出。
- 可拖动元素必须从当前位置接管，不能跳到目标点再开始动画。
- 只有拖拽/滑动携带速度时才使用轻微回弹；普通菜单禁止夸张弹跳。
- 优先动画 `transform` 和 `opacity`，避免动画布局属性。
- 不使用大型、缓慢、持续循环的背景动画干扰创作。

### Studio 组件建议

- **任务坞**：非阻塞悬浮层；显示排队、生成、完成、失败；完成后可直接查看结果。
- **图片预览**：从作品卡片位置展开；支持左右切换、关闭、设为参考图。
- **左侧一级导航**：桌面固定；折叠时保留图标和 tooltip；移动端转为底部导航。
- **底部二级操作**：只放筛选、排序、视图切换和平台预览，不抢主内容空间。
- **灵感卡片**：hover/press 反馈即时；操作靠近对象，不隐藏唯一入口。

## 材质与层级

- 毛玻璃用于导航、任务坞、抽屉等浮层，不要所有卡片都叠加 blur。
- 深色重材质用于结构区域；橙色只用于行动、焦点和重要状态。
- 大浮层使用更强 blur 和阴影，小控件使用轻材质。
- 半透明表面上的文字必须保持高对比度；复杂背景上增加不透明度。
- 浮层覆盖内容时使用柔和边缘渐变，避免到处堆 1px 分割线。

## 状态与可访问性

每个异步任务必须覆盖：

- 排队中
- 处理中
- 已完成
- 失败
- 已取消
- 连接中断/轮询兜底

不要在没有真实进度时伪造精确百分比，使用“正在处理 · 通常需要 1–3 分钟”等可信文案。

必须支持：

```css
@media (prefers-reduced-motion: reduce) {
  /* 滑入/弹簧改为短暂淡入，取消大位移 */
}

@media (prefers-contrast: more) {
  /* 提高边框和文字对比度，降低透明度 */
}
```

## Review 清单

- [ ] 按下操作是否立刻有反馈？
- [ ] 异步任务是否可见、可取消、可重试？
- [ ] 动效是否从当前视觉位置开始，并可被打断？
- [ ] 进入和退出路径是否对称？
- [ ] 毛玻璃是否造成文字对比度下降？
- [ ] 桌面和移动端是否都有清晰导航？
- [ ] 空态、加载态、错误态、完成态是否完整？
- [ ] reduced-motion / high-contrast 是否有降级？
- [ ] 是否为了装饰增加了等待、滚动或认知负担？

## Studio 适配规则

保持 Studio 的暗棕、珊瑚橙、米白和金色，不改成苹果白色官网风格。Apple Design 只负责交互质量、空间层级、材质和动效；品牌气质仍然是东方、克制、沉浸式创作工作台。
