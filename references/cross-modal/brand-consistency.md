# 跨模态品牌一致性

> **定位**: 确保同一主题/品牌在图片和视频两种模态中保持视觉一致
> **涉及**: gpt-image-2 + Seedance 2.0 + wuxia-cinematic 风格系统

---

## 核心原则

**视觉语言统一 = 色彩系统 + 光影规则 + 人物特征 + 构图偏好 的一致性**

---

## 一致性锚定清单

### 1. 色彩系统

```yaml
# 示例：wuxia-cinematic
主色调: 青灰 (#8A9BA8) + 暗金 (#B8963E)
辅色: 墨绿 (#2D3A2D)、赭石 (#8B5E3C)
对比度: 中等偏低
饱和度: 15-30%（低饱和）
色温: 5500K 偏冷
```

在图片和视频 prompt 中**使用完全相同的色彩关键词**：
- 图片: `desaturated cold tones, muted earth palette, ink wash undertones`
- 视频: `desaturated cold tones, muted earth palette, ink wash undertones`

### 2. 光影规则

```yaml
光源类型: 单光源为主，实用光源
光源方向: 侧逆光（左或右 45°）
阴影: 硬阴影，边缘清晰
光比: 高对比（key:fill ≈ 4:1）
环境光: 微弱 fill，不消除阴影
```

### 3. 人物特征

```yaml
面部结构: 东方骨相，雕塑感，颧骨明显
皮肤质感: 风霜感，可见纹理，自然光泽
表情: 冷峻、沉静、不刻意
年龄感: 25-40岁，有阅历感
```

### 4. 构图偏好

```yaml
画幅比例: 3:4（图片）/ 16:9（视频电影感）
留白: 大量负空间，不对称平衡
视觉重心: 下三分之一或黄金分割点
裁切: 允许部分裁切，增强电影感
```

---

## 组织实施

### 在项目中创建品牌配置文件

```markdown
# brands/wuxia-cinematic.md

## 色彩系统
- 图片prompt片段: "desaturated cold tones, muted earth palette, 
  ink wash undertones"
- 视频prompt片段: "desaturated cold tones, muted earth palette, 
  ink wash undertones"

## 光影规则
- 图片prompt片段: "single-source side light, hard shadows, 
  high contrast, 35mm film"
- 视频prompt片段: "single-source side light, hard shadows, 
  high contrast, 35mm film grain"

## 人物特征
- 图片prompt片段: "eastern bone structure, sculpted features, 
  weather-worn skin texture, natural sheen, cold expression"
- 视频prompt片段: "eastern bone structure, sculpted features, 
  weather-worn skin texture, no plastic skin, face identity consistent"

## 构图
- 图片prompt片段: "negative space, asymmetrical balance, 
  3:4 portrait, golden ratio"
- 视频prompt片段: "negative space, asymmetrical balance, 
  16:9 widescreen, golden ratio"
```

### 在 SKILL.md 中引用

每个品类的 SKILL.md 应包含：

```markdown
## 跨模态一致性

本品类遵循 `brands/[品牌名].md` 的色彩/光影/人物/构图规范。
在切换到视频模态时，引用相同的风格锚定词。
```

---

## 一致性检查清单

在产出前，用以下清单检查跨模态一致性：

- [ ] 两张图之间色彩一致（同一品牌/主题的图片）
- [ ] 图片与视频之间色彩一致
- [ ] 光影逻辑连续（光源不跳跃）
- [ ] 人物面部特征一致（同一角色的图/视频）
- [ ] 构图偏好一致（留白/比例/视觉重心）
- [ ] 风格关键词一致（prompt 中使用同一套关键词）
- [ ] 禁止项一致（相同的 negative prompt 规则）
