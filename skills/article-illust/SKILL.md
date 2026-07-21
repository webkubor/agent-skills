---
name: article-illust
description: 微信公众号文内配图 — 意境插图，16:9 横图，金句集成，暗色高级感
platform: wechat
category: illustration
model: gpt-image-2
ratio: "16:9"
pipeline: studio
quantity: 2-3
---

# 公众号文内配图

微信公众号「苏梦城」文章内插图。金句 + 意境，用于段落间视觉断点，防止阅读疲劳。

## 核心公式

```
段落实义 + 金句文字 + 光影意境 + 大量留白
```

## 设计原则

- **配合段落情绪**：每张图对应文章一个核心段落，选该段最锋利的金句
- **视觉断点**：每 2-3 段文字配一张图，打破纯文字疲劳
- **暗色高级感**：与封面风格一致，深色底 + 光影焦点
- **金句集成排版**：7-14 字直接写进 prompt，让模型排版

## Prompt 模板

```
Fine art photograph, [段落核心意象描述], [光影氛围],
Chinese text [段落金句] as elegant typography integrated into composition,
photorealistic, minimalist, museum quality, negative space, cinematic
```

## 放置规则

| 位置 | 图 | 作用 |
|------|-----|------|
| 开篇（第一节前） | 图1：核心冲突 | 钩子，抓住注意力 |
| 中段（核心论证后） | 图2：方法论总结 | 强化记忆点 |
| 结尾（反思前/后） | 图3：升华 + 行动指引 | 余韵，引导转发 |

> 弹性 2-3 张，不强制 3 张。文章短或节奏紧凑时 2 张即可。

## 金句选取

- 从该图对应段落中选最有张力的一句
- 不能和封面金句重复
- 每张图金句不同，形成递进

## 风格红线

同 article-cover：
- ❌ 动漫、卡通、插画
- ❌ 直白物体罗列
- ❌ 文字后期叠加
- ✅ 摄影质感 + 电影感
- ✅ 抽象意境 + 大量留白

## 出图管线

```
Studio 中台 → token4ai-upstream-1 → gpt-image-2 → R2 CDN
```

## 质量检查

- [ ] 至少 2 张，是否均匀分布在文中？
- [ ] 每张图的金句是否和对应段落有逻辑关联？
- [ ] 连续纯文字是否 ≤ 3 段（有图打断）？
- [ ] 风格是否与封面统一？
