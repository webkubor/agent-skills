---
name: shangui-four-seasons
zh_name: 山鬼映画·四时有物
description: 新东方极简艺术海报——美术馆展览级别、真实材质装置摄影、疏朗留白、四季器物。用于小红书艺术海报、系列创作、品牌视觉资产。
type: style-base
ratio: "3:4"
category: image-gen
genre: 艺术海报
platform: xiaohongshu
# ── 质量追踪 ──
{
  "status": "tested",
  "rating": "★★★★★",
  "last_used": "2026-07-25",
  "total_uses": 1,
  "trace": [
    {"date":"2026-07-25","usage":"春·春生 — 青白玉石裂开新芽","result":"✅ 出图成功，美术馆质感"}
  ]
}
---

# 山鬼映画｜四时有物

> 新东方哲学美学 · 美术馆展览海报 · 艺术装置摄影
> 安静克制、疏朗留白、现代东方审美

## 固定风格核心

### 整体基调

新东方极简主义，不是传统山水插画，不是古风人物海报，不是商业电商海报——而是一件具有真实材质与东方意境的**当代艺术装置作品**。

### 背景与质感

- 温润米白、象牙白或浅灰白背景
- 手工宣纸、微水泥、石膏墙或细腻矿物涂料质感
- 保留轻微颗粒、纤维、自然色差和低对比度浮雕纹理
- 若隐若现的东方水纹、风痕、山形或流动弧线（不抢主体）
- **禁止**：纯白背景、平滑塑料感、脏黄

### 构图规范

- 负空间 **65%—75%**
- 画面只设**一个核心艺术装置主体**，位于下半部或偏侧，避免正中对称
- 主体占比 **25%—40%**，周围充足呼吸感
- 只表达一个瞬间/一个动作/一种变化
- 自然柔和侧光，真实阴影、透光层次、材质细节
- 像高端美术馆画册、国际设计年鉴

### 材质要求

主体必须具备真实高级物理材质：玉石、玻璃、冰、陶瓷、木、金属、丝绸、纸张或矿石。
材质需要呈现：真实厚度、半透明结构、断裂边缘、折射、微小瑕疵、手工痕迹、自然光泽。
**禁止**：廉价水晶摆件感、普通3D建模感、高饱和塑料质感。

### 文字排版

固定竖排东方排版，清晰克制：

```
主标题（宋体/明朝体，竖排，纤细端正）
副文案（较小竖排）
四时有物 · No.{编号}
山鬼映画
SHANGUI YINGHUA
{YYYY.MM.DD}
```

- 文字必须真实可读，不能乱码/伪汉字/错误英文
- 品牌名「山鬼映画」必须准确，不修改字形
- 可加一枚极小朱红色「山鬼」印章作点缀，位置低调

### 色彩控制

配色限制在：米白 + 灰白 + 墨黑 + **一种低饱和季节色**

| 季节 | 主色点缀 |
|------|---------|
| 春 | 嫩芽绿或浅玉青 |
| 夏 | 水蓝、青绿或琥珀金 |
| 秋 | 赭红、银杏黄或枯叶棕 |
| 冬 | 冷白、冰蓝或墨灰 |

全图最多使用一种强调色。

### 摄影与画质

超写实艺术装置摄影，真实棚拍质感，柔和自然侧光，细腻阴影，真实接触阴影，轻微胶片颗粒，高分辨率但不锐化，低饱和克制。

### 禁止

复杂背景、人物大脸、满版元素、俗气国潮、金色边框、大红大紫、莲花祥云灯笼堆砌、仙侠感、二次元、网红模板、节气插画、廉价海报感、杂乱排版、乱码、错误日期、随机英文、错误品牌名、过多装饰文字。

---

## 可变参数

| 参数 | 说明 | 示例 |
|------|------|------|
| `{{季节}}` | 春/夏/秋/冬 | 春 |
| `{{作品标题}}` | 两字标题 | 春生 |
| `{{核心器物}}` | 画面主体的物件 | 一块被自然裂开的半透明青白玉石 |
| `{{自然元素}}` | 伴随主体的自然元素 | 从玉石裂缝中生长出的细嫩新芽 |
| `{{动作状态}}` | 主体正在发生的变化 | 玉石裂开一道缝，新芽向光缓慢生长 |
| `{{主色点缀}}` | 低饱和季节强调色 | 低饱和嫩芽绿与浅玉青 |
| `{{作品短句}}` | 画面副文案 | 万物从裂缝开始。 |
| `{{编号}}` | 系列编号 | 001 |
| `{{日期}}` | 发布日期 | 2026.07.25 |

---

## Prompt 模板

```
A contemporary art installation photograph for a museum exhibition poster, Eastern minimalist aesthetic, vertical 3:4 composition.

Background: Warm ivory white #F5F0EB with subtle handmade rice paper texture, faint micro-cement grain, barely visible flowing water lines and mountain contours in low relief, natural color variation, slight fiber specks. Not pure white, not plastic-smooth, not yellowish.

Composition: 70% negative space. A single central art object positioned in the lower half, slightly off-center. The object occupies 30% of the frame, surrounded by generous breathing room. Soft natural side lighting casting real shadows, translucent layers, and material depth. Museum gallery catalog quality.

Subject: {{核心器物}}. {{动作状态}}. From within/around the object, {{自然元素}}.

Material: The object rendered with true-to-life physical materiality — [玉石/玻璃/冰/陶瓷/木/金属/丝绸/纸/矿石]. Visible real thickness, semi-translucent structure, fractured edges, subtle refraction, micro imperfections, handmade traces, natural surface luster. No cheap crystal ornament feel, no generic 3D render look, no saturated plastic texture.

Color palette: Ivory white + warm gray + ink black + a single muted seasonal accent color: {{主色点缀}}. Only one accent color in the entire image.

Typography: Clean vertical Chinese typography in the upper portion:
- Main title in Song/Ming typeface, slender vertical: 「{{作品标题}}」
- Subtitle smaller vertical: 「{{作品短句}}」
- Series line: 「四时有物 · No.{{编号}}」
- Brand: 「山鬼映画」
- English: 「SHANGUI YINGHUA」
- Date: 「{{日期}}」
All text readable, no garbled characters, no pseudo-Chinese, no incorrect English, no random dates, brand name 「山鬼映画」 must be exact.

A tiny vermillion red seal 「山鬼」 as subtle accent, positioned discreetly. If seal text cannot render correctly, omit it entirely.

Photographic quality: Hyperrealistic art installation photography, real studio lighting, soft natural side light, delicate shadows, real contact shadows, slight film grain, high resolution but not oversharpened, desaturated, restrained, sophisticated. Suitable for Xiaohongshu vertical art poster display.

Negative constraints: NO complex background, NO human faces, NO crowded elements, NO tacky guochao style, NO gold borders, NO red-purple saturation, NO lotus/cloud/lantern clutter, NO xianxia fantasy, NO anime, NO influencer templates, NO seasonal illustration style, NO cheap poster feel, NO messy typography, NO garbled text, NO wrong dates, NO random English, NO incorrect brand name, NO excessive decorative text. aspect ratio 3:4
```

---

## 季节性预设

### 春 · 春生

| 参数 | 值 |
|------|-----|
| 核心器物 | 一块被自然裂开的半透明青白玉石 |
| 自然元素 | 从玉石裂缝中生长出的细嫩新芽 |
| 动作状态 | 沉寂许久的玉石裂开一道缝，新芽向光缓慢生长 |
| 主色点缀 | 低饱和嫩芽绿与浅玉青 |
| 作品短句 | 万物从裂缝开始。 |

### 夏 · 夏鸣

| 参数 | 值 |
|------|-----|
| 核心器物 | 一只薄胎白瓷碗，盛着半碗清水 |
| 自然元素 | 水面落下一片青绿梧桐叶，泛起涟漪 |
| 动作状态 | 梧桐叶轻触水面的瞬间，涟漪向外扩散 |
| 主色点缀 | 低饱和水蓝与青绿 |
| 作品短句 | 听见夏天的声音。 |

### 秋 · 秋落

| 参数 | 值 |
|------|-----|
| 核心器物 | 一块粗陶残片，表面布满细密冰裂纹 |
| 自然元素 | 一片枯黄的银杏叶恰好落入陶片裂纹中 |
| 动作状态 | 银杏叶落下的瞬间，被裂缝温柔接住 |
| 主色点缀 | 低饱和赭红与银杏黄 |
| 作品短句 | 坠落也是一种抵达。 |

### 冬 · 冬藏

| 参数 | 值 |
|------|-----|
| 核心器物 | 一块不规则天然冰体，内部封存着一枝干枯的梅枝 |
| 自然元素 | 冰体表面凝结着细密霜花 |
| 动作状态 | 梅枝被封存在冰中，等待春天 |
| 主色点缀 | 低饱和冷白与墨灰 |
| 作品短句 | 沉默是最大的力量。 |
