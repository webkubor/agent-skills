---
name: ecom-before-after
zh_name: 前后对比图
description: 使用前 vs 使用后对比——左右分屏，清晰展示产品效果差异。适用于护肤/美白/清洁/健身/家电等需要效果证明的品类。
ratio: "1:1"
type: style-base
platform: shared
category: image-gen
genre: 电商
---

# 前后对比图

左右分屏对比，让效果一目了然。

## 核心铁律

- 左边 = 使用前（Before），右边 = 使用后（After）
- 左右两边**光线、角度、背景必须完全一致**
- 中间用细线 `|` 分隔
- 顶部标签：「使用前」左 / 「使用后」右
- 产品放在下方中央
- 不要虚构效果数据

## 分屏布局

```
┌─────────┬─────────┐
│ 使用前   │ 使用后   │
│          │          │
│ (before) │ (after)  │
├─────────┴─────────┤
│    产品 + logo     │
└───────────────────┘
```

## Prompt 模板

```
Split screen comparison layout. Left half labeled 「使用前」showing [before_state]. Right half labeled 「使用后」showing [after_state]. Both sides identical lighting, angle, and background #FFFFFF. Thin vertical divider line in middle. Product placed centered at bottom. Clean pharmaceutical-grade presentation. Product occupies 20%. Whitespace 45%+. 不要虚构数据或认证。不要夸大效果。文字用中文。
```
