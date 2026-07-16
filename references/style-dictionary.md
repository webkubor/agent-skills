# 风格词典

> **用途**: 跨模态统一风格锚定词，确保 gpt-image-2 和 Seedance 2.0 prompt 使用一致的关键词
> **使用**: 在每个 prompt 的风格段落中，从中选取对应的关键词组合

---

## 一、电影质感（Cinematic）

```yaml
关键词: cinematic, film grain, 35mm, anamorphic lens, shallow depth of field
色调: desaturated, muted palette, high contrast
光影: natural lighting, single source, practical lights
构图: widescreen, golden ratio, negative space
通用负面: no plastic skin, no over-smoothing, no CGI feel, no artificial glow
```

---

## 二、东方武侠电影（Wuxia Cinematic）

```yaml
关键词: neo-oriental wuxia, gu long aesthetics, ink wash palette
色调: desaturated cold tones, muted earth, misty atmosphere
光影: single-source side light, hard shadows, high contrast
质感: 35mm film grain, analog photography, weathered textures
人物: eastern bone structure, sculpted features, weathered skin
负面: no anime effects, no CGI plastic, no glowing aura, no k-pop idol face,
      no neon, no magic particles, no fairy-tale lighting
```

---

## 三、现代都市（Urban Contemporary）

```yaml
关键词: urban contemporary, street photography, editorial style
色调: cool neutral, slight blue shift, muted warm accents
光影: natural daylight, window light, neon practical
质感: crisp digital, slight grain, lens flare acceptable
人物: natural expression, candid feel, diverse features
负面: no studio lighting, no over-posing, no corporate stock photo feel
```

---

## 四、商业产品（Commercial Product）

```yaml
关键词: commercial product photography, premium minimal, clean studio
色调: accurate color reproduction, neutral background
光影: soft box lighting, rim light, controlled highlights
质感: macro lens, 60fps slow motion, glass reflections
负面: no packaging collapse, no logo distortion, no label blur,
      no duplicate product, no dirty background, no color cast
```

---

## 五、社交媒体美学（Social Media Aesthetic）

```yaml
关键词: social media aesthetic, ins-style, lifestyle photography
色调: warm tones, golden hour, slight desaturation
光影: natural light, window light, sunset backlight
质感: handheld feel, slight motion blur acceptable, genuine moment
负面: no studio lighting, no corporate polish, no over-retouching,
      no theatrical posing, no artificial perfection
```

---

## 六、暗黑幻想（Dark Fantasy）

```yaml
关键词: dark fantasy, atmospheric, volumetric light
色调: deep blacks, desaturated, single color accent
光影: candlelight, moonlight, practical fire, god rays
质感: film grain, dust particles, atmospheric haze
负面: no bright studio light, no cheerful colors, no clean surfaces
```

---

## 七、复古胶片（Vintage Film）

```yaml
关键词: vintage film, analog photography, nostalgic
色调: sepia, warm amber, faded color, light leaks
光影: soft natural light, practical tungsten, lens flare
质感: heavy film grain, dust and scratches, vignette
负面: no digital sharpness, no HDR look, no perfect focus
```

---

## 八、极简抽象（Minimal Abstract）

```yaml
关键词: minimal abstract, geometric, Bauhaus influence
色调: limited palette 2-3 colors, high contrast, clean
光影: flat lighting, no shadows, even illumination
质感: vector smooth, sharp edges, no texture
负面: no gradients, no shadows, no decorative elements,
      no complex backgrounds, no photorealism
```

---

## 九、赛博朋克（Cyberpunk）

```yaml
关键词: cyberpunk, neon noir, high tech low life
色调: cyan + magenta + amber neon, deep blacks
光影: mixed color practicals, wet surface reflections, neon signs
质感: rain streaks, steam vents, holographic glints
负面: no natural daylight, no warm sunny scenes, no clean minimal surfaces
```

---

## 十、国风水墨（Ink Wash）

```yaml
关键词: ink wash painting, Chinese watercolor, sumi-e
色调: black ink on rice paper, subtle sepia aging
光影: diffuse natural light, no hard shadows
质感: brush stroke texture, paper grain, bleeding ink edges
负面: no 3D rendering, no glossy surfaces, no vivid color,
      no sharp digital edges, no photorealistic
```

---

## 使用规范

### 在 gpt-image-2 prompt 中使用

```text
风格：[从词典中选取对应关键词组合]
示例：cinematic, 35mm film grain, desaturated cold tones, 
single-source side light, shallow depth of field
```

### 在 Seedance 2.0 prompt 中使用

```text
风格：[从词典中选取对应关键词组合]，保持 video 兼容性
示例：cinematic, film grain, single-source side light, 
24fps, anamorphic lens, desaturated cold tones
```

### 跨模态统一

确保图片和视频 prompt 使用**同一组风格关键词**，只调整模态专属的技术参数（如视频的帧率、运镜）。
