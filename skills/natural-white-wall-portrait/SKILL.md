---
name: natural-white-wall-portrait
zh_name: 自然白墙人像换背景
description: 将实拍人物照片的复杂室内背景替换为自然浅灰白墙，保留人物、服装、配饰与手机摄影真实感，带轻微墙面纹理和柔和环境阴影，避免硬抠图和 AI 重绘感
type: style-base
platform: shared
ratio: "3:4"
category: image-gen
genre: 人像写真
ref_required: true
---

# 自然白墙人像换背景

> 风格核心：不是纯白证件照，也不是硬抠贴图，而是像人物原本就在浅灰白墙前拍摄的自然照片。

适合把实拍人物照中的窗帘、家具、挂画、音响、花瓶、桌面等复杂背景，统一替换为自然浅灰白墙。重点是保留人物真实摄影感，让边缘、头发、手指、衣服和配饰看起来不生硬。

## 适用场景

- 明星/模特/素人人像统一换成干净背景。
- 多张人物图批量换成同一套浅灰白墙视觉。
- 用户明确要求“自然白底”“别像硬抠”“摄影感真实”。
- 原图是手机实拍、室内写真、生活照，需要去掉杂乱环境。

## 固定风格核心

- 背景是自然 off-white / light-gray wall，不是纯 `#ffffff`。
- 墙面有非常轻微的真实纹理、照片颗粒和不均匀明暗。
- 人物身后有很淡、很柔的环境阴影，让主体自然贴合墙面。
- 人物边缘保留真实发丝和衣服轮廓，不出现白边、硬轮廓或贴纸感。
- 整体仍像手机或轻棚拍照片，不像 AI 重绘的商业棚拍图。

## 可变参数

| 参数 | 默认值 | 可替换为 |
|------|--------|----------|
| 背景 | 自然浅灰白墙，轻微纹理 | 暖白墙 / 浅米灰墙 / 浅灰墙 |
| 阴影 | 很淡的柔和环境阴影 | 更轻 / 稍明显，但不能戏剧化 |
| 前景锁定 | 人物、衣服、手势、配饰全部保留 | 按图片补充帽子、耳机、墨镜、包带、手串等 |
| 输出 | 与原图同画幅，PNG | 用户指定格式或比例 |
| 批量目录 | `out/` | 用户指定目录 |

## 固定处理流程

1. 先选一张代表性图片做测试图。
2. 让用户确认测试效果后，再批量处理全部图片。
3. 批量时使用同一张已确认成品作为风格参考图，并保留对应切换前原图做对比。
4. 每张图都把原图作为 edit target，把确认成品只作为 background style reference。
5. 输出到当前任务的 `out/` 目录，不覆盖原图。
6. 文件名尽量保持原始文件名，只把格式统一为 PNG。
7. 批量完成后检查 `out/` 中成品数量与原图数量一致。

## 必须保留

- 人物身份、五官、脸型、发型、发丝、表情和肤色。
- 原始姿势、身体比例、手势、手指结构和头部角度。
- 衣服颜色、款式、面料纹理、褶皱、拼接和垂坠感。
- 帽子、耳机、墨镜、手串、包带、包边等所有前景配饰。
- 原始构图、画幅比例、人物大小、裁切和手机摄影真实感。

## 必须去除

- 窗帘、墙角、天花板、灯、挂画、相框、桌子、柜子。
- 音响、花瓶、树枝、线缆、家具和所有室内装饰物。
- 原场景遗留的阴影、反光、边缘残片和背景色污染。

## 背景要求

- 使用浅灰白、暖白、自然白或浅米灰墙面。
- 不要纯白色块，不要证件照死白底。
- 不要墙角、踢脚线、地面、摄影棚纸卷或道具。
- 墙面可以有轻微纹理和照片颗粒，但不能抢主体。
- 阴影只能是很淡的 diffuse ambient shadow，不能戏剧化。

## 负面约束固定

禁止：硬抠边、白色描边、发丝缺失、边缘发光、锯齿、人物变脸、磨皮、美颜、瘦脸、重绘衣服、改变服装颜色、改变配饰、塑料皮肤、过度锐化、AI 棚拍感、纯白背景、道具、文字、水印。

## 使用方式

固定风格核心 + 目标图 = Image 1 + 已确认样张 = Image 2 + 按图补充前景锁定项 → 生成完整背景替换 prompt。

## 默认提示词

```text
Edit Image 1 only. Image 2 is only the approved style reference for a natural off-white/light-gray wall with subtle wall texture, mild photo grain, and faint soft body shadow.

Replace only Image 1's background with that natural white-wall effect. Keep the Image 1 person locked and unchanged as much as possible: same face, identity, hair, expression, skin texture, pose, hands, accessories, clothing colors and wrinkles, body shape, crop, camera angle, and casual phone-photo realism.

Do not retouch, beautify, smooth, reshape, relight, recolor, sharpen, upscale, redraw, or change clothing/accessories.

Remove all room elements: curtains, ceiling, wall art, furniture, speaker, branches, vase, cables, lights, and corners.

Add only a faint diffuse ambient shadow behind the subject so it feels naturally photographed against the wall, not pasted.

Avoid hard cutout outline, white halo, jagged edges, missing hair strands, altered fingers/accessories, leftover background, pure #ffffff, floor, props, text, or watermark.

Same aspect ratio and framing as Image 1.
```

## 单图强化提示

按图片内容把前景配饰补进 `accessories`，例如：

```text
Keep the cap/hat, headphones, sunglasses, bracelets, crossbody bag strap, visible bag edge, raised hand, fingers, and all clothing wrinkles unchanged.
```

如果衣服是黑色，追加：

```text
Use a faint diffuse wall shadow so the black clothing edge blends naturally against the wall, without a white rim or sticker-like outline.
```

如果衣服是白色，追加：

```text
Keep white clothing fabric texture visible and avoid overexposure; separate the white clothing from the off-white wall with natural tonal contrast and soft shadow.
```

## 批量执行规范

1. 原图作为 Image 1。
2. 用户确认过的样张作为 Image 2。
3. 每张图都复用默认提示词，并按该图补充帽子、耳机、墨镜、手串、包带、手势等前景锁定项。
4. 输出命名建议：`out/<原始文件名去扩展名>.png`。
5. 不要把测试图、参考图或临时图混进批量输入。
6. 最后用文件数量检查确认全部完成。

## 参考效果

先看切换前，再看 AI 替换后。对比重点不是人物有没有“变好看”，而是背景从复杂室内环境变成自然浅灰白墙，同时人物身份、姿势、衣服和配饰尽量不变。

### 切换前

![sample-input](https://img.webkubor.online/skills/natural-white-wall-portrait/sample-input.jpg)

### AI 替换后

![sample-output](https://img.webkubor.online/skills/natural-white-wall-portrait/preview/sample-output.jpg)

<!-- tracking
{"status":"tested","rating":"★★★★★","last_used":"2026-07-20","total_uses":1,"trace":[{"date":"2026-07-20","usage":"13张室内人物图统一替换为自然浅灰白墙背景，用户确认效果：自然不生硬，不像硬抠","result":"✅ 沉淀为长期复用出图 skill"}]}
-->
