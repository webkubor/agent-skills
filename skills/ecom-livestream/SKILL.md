---
name: ecom-livestream
zh_name: 直播间截图
description: 模拟抖音/淘宝直播间真实截图——手持产品展示、弹幕飘过、点赞特效、限时标签。适用于直播预告封面、直播切片、带货素材。
ratio: "3:4"
type: style-base
platform: shared
category: image-gen
genre: 电商
---

# 直播间截图风格

模拟真实带货直播间的手机截图质感。

## 核心铁律

- **anti-AI 痕迹**：轻微噪点、低画质压缩感、屏幕反光
- 产品在画面中央偏上，手持展示
- 必须包含直播UI元素：点赞图标、弹幕文字、购物车按钮
- 产品占比 **40%**

## UI 元素清单

每张图必须包含 3 个以上：
- 左下角：`❤️ 2.3w` 点赞数
- 顶部飘过：`「已买，质量太好了」` 弹幕
- 右下角：`🛒 去购买` 购物车按钮
- 左上角：`🔥 热卖中` 或 `限时优惠` 标签
- 底部：商品名称 + 价格 `¥299`

## Prompt 模板

```
Smartphone screenshot from a livestream shopping app. A hand holding [#product] in the center, studio ring light illuminating the face and product. Dislike icon ❤ 2.3w bottom left, comment floating text across screen, shopping cart button 🛒 bottom right. Slight image compression noise, screen glare reflection. Product occupies 40%. Resolution loss ≈720p feel. 不要出现真人主播的脸。文字用中文。
```
