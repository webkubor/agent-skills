---
name: brand-symbol-system
zh_name: 品牌符号系统
description: 一个符号撑起整个品牌世界——东方美学品牌四图提案（世界观封面 + Logo符号 + 色彩字体材质 + 包装空间应用）。适用于香氛、茶、器物、生活方式等东方品牌。
type: style-base
ratio: "3:4"
category: image-gen
genre: 品牌提案
platform: xiaohongshu
# ── 质量追踪 ──
{
  "status": "tested",
  "rating": "★★★★☆",
  "last_used": "2026-07-30",
  "total_uses": 1,
  "trace": [
    {"date":"2026-07-30","usage":"砚雾四图品牌提案","result":"✅ 四图出图成功，东方极简香氛调性"}
  ]
}
---

# 品牌符号系统｜一个符号，撑起整个品牌世界

> 东方极简品牌美学 · 四图完整提案
> 克制、留白、材质感、符号驱动

## 设计哲学

**核心命题：** 找到一个符号，让它成为品牌的一切。

不是"设计一个好看的 Logo"，而是**从品牌世界观推导出一个符号**，再用这个符号贯穿所有视觉触点——包装、空间、材质、色彩、字体。

适合品牌类型：东方香氛、茶、器物、书店、生活方式、独立设计工作室。

---

## 四图结构

| 图序 | 内容 | 比例 | 核心任务 |
|------|------|------|---------|
| 图一 | 品牌世界观与概念封面 | 3:4 | 建立品牌精神氛围，不出现 Logo |
| 图二 | Logo 符号与生成逻辑 | 1:1 | 核心符号 + 设计推导 |
| 图三 | 色彩、字体与材质系统 | 3:4 | 视觉系统全景 |
| 图四 | 包装、产品与空间应用 | 3:4 | 真实场景中的符号延展 |

---

## 固定风格核心

### 整体基调

东方极简主义，不是传统国潮、不是复古堆砌、不是日式侘寂——而是**现代东方品牌的克制美学**。安静、高级、有呼吸感。

### 背景与质感

- 米白、暖灰、浅驼色手工纸质感
- 微水泥、手工宣纸、哑光陶土
- 保留轻微颗粒、纤维、自然色差
- **禁止**：纯白背景、光滑塑料感、脏黄

### 构图规范

- 负空间 60%—70%
- 主体居中或偏侧，不贴边
- 单图只表达一个核心概念
- 自然柔和侧光，真实阴影

### 色彩控制

每套品牌配色限制在 **3—4 色**：

| 角色 | 用途 |
|------|------|
| 主色 | 品牌核心色，贯穿四图 |
| 辅色 | 材质/背景色 |
| 强调色 | 极少使用，点缀 |
| 文字色 | 深灰/墨黑 |

### 禁止

- 复杂背景、满版元素、金边红底
- 国潮堆砌（莲花祥云灯笼龙凤）
- 渐变霓虹、发光特效、3D 金属质感
- 杂乱排版、乱码文字
- 廉价模板感、网文海报风

---

## 可变参数

| 参数 | 说明 | 示例 |
|------|------|------|
| `{{品牌名}}` | 品牌中文名 | 砚雾 |
| `{{品牌英文}}` | 品牌英文/拼音 | YANWU |
| `{{品类}}` | 品牌品类 | 东方香氛 |
| `{{核心符号}}` | 品牌核心符号描述 | 一方砚台，墨雾从砚中升起 |
| `{{符号抽象}}` | 符号的极简几何表达 | 不规则椭圆 + 向上扩散的渐变弧线 |
| `{{世界观}}` | 品牌世界观一句话 | 以墨为雾，以砚为山 |
| `{{主色}}` | 品牌核心色 | 墨灰 #3A3A3A |
| `{{辅色}}` | 材质/背景色 | 暖白 #F5F0EB |
| `{{强调色}}` | 极少点缀 | 青灰 #7A8B7A |
| `{{材质}}` | 品牌核心材质 | 哑光黑陶、手工宣纸、毛玻璃 |
| `{{字体风格}}` | 字体方向 | 宋体/明朝体，纤细端正 |

---

## 图一 Prompt 模板：品牌世界观封面

```
A minimalist brand concept cover for an Eastern luxury brand, vertical 3:4 composition, editorial photography style.

Background: Warm ivory #F5F0EB with subtle handmade paper texture, faint ink wash atmosphere, barely visible mist or smoke curling upward, natural surface grain, slight mineral speckles. Not pure white, not plastic.

Composition: 65% negative space. The visual is abstract and atmospheric — no logo, no product, no text. The mood is {{世界观}}.

Visual elements: {{核心符号}} rendered as an abstract, poetic visual — soft focus, shallow depth of field, misty atmosphere. The object is partially visible, partially dissolved into the surrounding air. Soft natural side lighting, real shadows, translucent layers.

Material: {{材质}} with true-to-life texture — matte surfaces, subtle imperfections, natural surface variations, delicate light absorption.

Color palette: {{辅色}} dominant, {{主色}} as shadow and depth, {{强调色}} as barely perceptible accent. Only these colors.

Mood: Quiet, sophisticated, meditative, luxurious but not loud. Like a museum exhibition catalog for a niche fragrance house.

Photographic quality: Hyperrealistic still life photography, soft natural light, shallow depth of field, slight film grain, high resolution but not oversharpened, desaturated, restrained.

Negative constraints: NO logo, NO text, NO product, NO human figures, NO gold borders, NO red, NO traditional Chinese motifs (lotus, dragon, phoenix, clouds, lanterns), NO neon, NO glow effects, NO 3D metallic, NO cheap template feel, NO garish colors. aspect ratio 3:4
```

---

## 图二 Prompt 模板：Logo 符号与生成逻辑

```
A brand logo design presentation for "{{品牌名}}", square 1:1 composition, minimalist editorial layout.

Background: {{辅色}} with handmade paper texture, slightly off-white, natural grain.

Center: The core brand symbol — {{符号抽象}}. The symbol is rendered as a clean, minimalist graphic in {{主色}}. It should feel like a single continuous gesture — one stroke, one shape, one idea. No text, no decoration, just the pure symbol.

Below the symbol (small, minimal): The brand name 「{{品牌名}}」in {{字体风格}}, {{主色}}, delicate and restrained. Below that, 「{{品牌英文}}」in thin sans-serif.

The symbol should be the hero — occupying 30-40% of the frame, centered. The text is small and quiet.

Style: Clean design studio presentation, not a commercial logo mockup. No gradients, no shadows, no 3D effects. Pure flat graphic design with subtle paper texture beneath.

Negative constraints: NO complex shapes, NO multiple elements combined, NO gradients, NO shadows, NO 3D, NO glowing effects, NO gold, NO red, NO decorative borders, NO traditional motifs, NO English taglines, NO QR codes, NO mockup frames. aspect ratio 1:1
```

---

## 图三 Prompt 模板：色彩、字体与材质系统

```
A brand visual system board for "{{品牌名}}", vertical 3:4 composition, premium design studio presentation.

Background: {{辅色}} with subtle handmade paper texture.

Layout: Three horizontal bands, cleanly separated by thin {{主色}} lines:

TOP BAND (25%): Color palette — three to four color swatches arranged horizontally on small textured cards. {{主色}} (primary), {{辅色}} (base), {{强调色}} (accent). Each swatch is a small square of textured material, not a digital color block. Visible paper grain, slight variation.

MIDDLE BAND (35%): Typography — 「{{品牌名}}」in {{字体风格}}, displayed large and elegant in {{主色}}. Below it, 「{{品牌英文}}」in thin sans-serif. A sample line of Chinese text in smaller size. The typography is clean, readable, with generous tracking and leading.

BOTTOM BAND (40%): Material study — A close-up still life of {{材质}}. The materials are arranged as an artful composition: surfaces overlapping, different textures interacting. Natural light, real shadows, visible imperfections. Matte surfaces, subtle reflections where appropriate.

Overall style: High-end design studio presentation, editorial quality, like a spread from a luxury brand guidelines book. All text is real and readable — no garbled characters.

Negative constraints: NO digital color blocks without texture, NO glossy plastic, NO 3D renders, NO gold, NO red, NO traditional motifs, NO cluttered layout, NO random English, NO QR codes. aspect ratio 3:4
```

---

## 图四 Prompt 模板：包装、产品与空间应用

```
A brand application showcase for "{{品牌名}}", vertical 3:4 composition, editorial photography.

Background: {{辅色}} with subtle texture.

Composition: A curated still life / interior scene showing the brand applied across touchpoints:

- A {{品类}} product package in {{主色}} with {{材质}} finish, featuring the brand symbol {{符号抽象}} debossed or printed subtly
- A small product card or tag with 「{{品牌名}}」in {{字体风格}}
- A glimpse of the brand symbol applied to a surface — wrapping paper, a shop window, a ceramic surface
- Soft natural lighting, real shadows, depth of field

The scene feels like a corner of a niche boutique in a quiet alley — not a shopping mall, not a department store. Warm, intimate, sophisticated.

Materials: {{材质}} throughout — matte, tactile, real. Paper grain, ceramic texture, subtle imperfections.

The brand symbol is present but not loud — it's integrated into the environment, not slapped on everything.

Negative constraints: NO crowded retail scenes, NO shopping bags, NO bright lights, NO gold, NO red, NO traditional motifs, NO human faces, NO busy backgrounds, NO price tags, NO barcodes, NO QR codes. aspect ratio 3:4
```

---

## 预设案例：砚雾（YANWU）

东方香氛品牌「砚雾」——以墨为雾，以砚为山。

### 品牌参数

| 参数 | 值 |
|------|-----|
| 品牌名 | 砚雾 |
| 品牌英文 | YANWU |
| 品类 | 东方香氛 |
| 核心符号 | 一方砚台，墨雾从砚中升起，化为无形 |
| 符号抽象 | 一个不规则椭圆（砚池）+ 向上扩散的三条渐变弧线（墨雾） |
| 世界观 | 以墨为雾，以砚为山 |
| 主色 | 墨灰 #3A3A3A |
| 辅色 | 暖白 #F5F0EB |
| 强调色 | 青灰 #7A8B7A |
| 材质 | 哑光黑陶、手工宣纸、毛玻璃 |
| 字体风格 | 宋体，纤细端正 |

### 四图快速启动

替换 Prompt 模板中的 `{{变量}}` 为上述砚雾参数即可直接出图。四图分别产出：

1. **品牌世界观封面**：墨雾从砚台升起的抽象氛围
2. **Logo 符号**：不规则椭圆 + 三条扩散弧线，装饰「砚雾 / YANWU」
3. **色彩字体材质**：墨灰/暖白/青灰色板 + 宋体字 + 黑陶宣纸毛玻璃材质
4. **包装空间应用**：香氛瓶身 + 包装盒 + 产品卡片 + 空间一角

---

## 扩展方向

同一套符号系统可延伸出：

- **品牌 VI 手册**：多页系统规范
- **产品线延展**：不同香型/品类共用同一符号
- **社交媒体模板**：品牌符号 + 产品 + 文案排版
- **空间设计**：店铺/展厅/快闪店的符号应用

> 核心不变：一个符号，贯穿一切。

---

## 参考图（砚雾案例）

| 图序 | 内容 | 预览 |
|:--:|------|------|
| ① | 品牌世界观封面 | ![世界观](https://img.webkubor.online/skills/brand-symbol-system/preview/yanwu-01-worldview.png) |
| ② | Logo 符号 | ![Logo](https://img.webkubor.online/skills/brand-symbol-system/preview/yanwu-02-logo.png) |
| ③ | 色彩字体材质 | ![系统](https://img.webkubor.online/skills/brand-symbol-system/preview/yanwu-03-system.png) |
| ④ | 包装空间应用 | ![应用](https://img.webkubor.online/skills/brand-symbol-system/preview/yanwu-04-application.png) |

> 生成引擎：tronzen / gpt-image-2 | 日期：2026-07-30