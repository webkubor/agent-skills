---
name: article-cover
description: 微信公众号封面图 — 金句海报，16:9 横图，暗色高级感，文字集成排版
platform: wechat
category: cover
model: gpt-image-2
ratio: "16:9"
pipeline: studio
---

# 公众号封面图

微信公众号「苏梦城」文章封面。金句海报风格，暗色高级感，文字直接集成进画面构图。

## 核心公式

```
情绪基调 + 光影质感 + 空间留白 + 金句集成排版
```

## 设计原则

- **暗色系为主**：深蓝黑底、虚空感，匹配成熟男性读者（74%，26-60 岁）
- **金句即封面**：选文章最锋利的一句（7-14 字），直接写进 prompt 让模型排版
- **海报感**：不是场景图，是海报——文字是画面的一部分，不是底部贴条
- **大量留白**：负空间构图，博物馆级质感
- **不写直白物体**：写情绪+光线，不写「茶杯+书桌+窗帘」

## Prompt 模板

```
Fine art photograph, dark void with [光影描述], [核心意象], 
Chinese text [金句7-14字] as elegant typography integrated into composition, 
photorealistic, minimalist, museum quality, negative space, cinematic
```

## 金句选取

- 7-14 字，有张力、可独立传播
- 看完封面就想点开
- 示例：「被玩的人关不掉」「你到底是真在用AI还是换了个更贵的玩具」

## 风格红线

- ❌ 动漫、卡通、插画、二游风
- ❌ 赛博朋克、科技芯片、机器人
- ❌ 直白物体罗列（= 素材库风）
- ❌ 文字后期叠加（imagemagick 叠字 = low）
- ✅ 摄影质感（photography/photorealistic）
- ✅ 电影感（cinematic/film grain）
- ✅ 抽象意境 + 大量留白

## 出图管线

```
Studio 中台 → token4ai-upstream-1 → gpt-image-2 → R2 CDN
```

## 质量检查

- [ ] 金句是否一眼可读？
- [ ] 画面是否有海报感（不是场景图）？
- [ ] 色温是否匹配文章调性（走心=暖色暗光，冷静=冷蓝暗光）？
- [ ] 是否避免了素材库存照风？

## 参考

- 审美画像：高级感 99 / 留白 97 / 东方美学 98 / 真实感 95
- 色系：蓝紫 #6B7CFF / 青蓝 #4CC9F0 / 深海蓝 #0F172A
- 出图踩坑：2.35:1 易超时，统一 16:9；金句 7-14 字；prompt 简洁 > 堆砌
