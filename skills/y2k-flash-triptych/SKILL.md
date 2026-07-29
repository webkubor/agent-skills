---
name: y2k-flash-triptych
zh_name: Y2K 千禧直闪三联自拍
platform: xiaohongshu
type: style-base
category: image-gen
ratio: "9:16"
description: 2000s 数码相机直闪质感三联拼图 — 同一人物三格不同角度，CCD复古颗粒，白色细分隔线
engine: Token4AI (gpt-image-2)
---

# Y2K 千禧直闪三联自拍

> 最后更新：2026-07-18 | 来源：用户需求 | 状态：待验证
> 三格同一个人、同一张脸、同一肤色发色，姿势角度变化但不跑脸。

---

## 风格定位

2000 年代早期数码相机 + 手机直闪自拍质感。浅灰白中性背景，极简干净，轻微杂志感。强烈正面闪光，明亮高光，轻微过曝，复古 CCD 质感。

---

## 人物锚点（需替换 {{ }} 部分）

- 成年东亚女性，脸型/五官/肤色从参考图提取
- 黑色长发蓬松丰盈，自然凌乱 + 细碎发丝
- 狐狸眼妆，眼线轻微上扬，睫毛清晰
- 皮肤白皙通透但保留真实纹理，水润玻璃唇
- 白色细肩带上衣 / 白色背心

---

## 三格分镜

### 第一格 — 眨眼特写
极近距离面部特写，脸部占画面大部分。一只眼睁着看镜头，另一只眼自然眨眼。肩膀微抬，发丝从脸颊与嘴角前穿过，俏皮但克制。构图略微倾斜，随手自拍的不完美感。

### 第二格 — 回眸
中近景背肩回眸。人物背对镜头露出肩背线条，再转头看镜头。长发蓬松铺在背部，部分发丝横过脸颊与嘴唇。眼神冷静慵懒，自然不刻意。

### 第三格 — 发遮单眼
贴近镜头怼脸特写。头微前倾，黑色长发遮住左眼，只露右眼直视镜头。嘴唇轻抿带若有若无嘟嘴。安静疏离时髦。发丝贴近镜头有轻微动态柔化。

---

## 摄影质感

- iPhone 17 Pro Max 前置/后置直闪效果
- 强烈正面闪光，明亮高光，轻微过曝
- 皮肤带自然反光，背景保留浅灰阴影
- 轻微复古数码颗粒、细小噪点
- 柔和运动模糊、轻微失焦
- 边缘不完全规整，早期 CCD 相机质感
- 三格之间白色细分隔线（8-12px）

---

## English Prompt（替换 {{FACE_ANCHOR}} 后直接出图）

```
A 9:16 vertical triptych of the same young East Asian woman, three panels
separated by clean white thin divider lines, light grey-white seamless
background, minimal and clean, slight magazine editorial feel.

FACE IDENTITY (must be identical across all three panels):
{{FACE_ANCHOR}}

HAIR & MAKEUP (consistent across all panels):
Long black hair, voluminous and fluffy, naturally messy with fine stray strands.
Fox-eye makeup, subtly lifted eyeliner, clearly defined lashes.
Fair porcelain skin, translucent and dewy but with subtle real texture,
NOT plastic, NOT airbrushed. Glossy glass lips. White thin-strap tank top.

PANEL 1 — BLINKING CLOSE-UP (left or top):
Extreme close-up, face fills most of frame. One eye open looking at camera,
the other eye mid-blink, naturally closed. Shoulders slightly raised.
Hair strands falling across cheek and corner of mouth. Playful but restrained
expression. Slightly tilted imperfect selfie composition, intimate camera distance.

PANEL 2 — OVER-SHOULDER LOOKING BACK (center):
Medium-close shot from behind, bare shoulders and back visible,
head turned back to look at camera. Long black hair spreading across back,
some strands crossing cheek and lips. Eyes calm and languid, relaxed but not stiff.
Natural casual pose, not posed, not editorial.

PANEL 3 — HAIR COVERING ONE EYE (right or bottom):
Ultra-close face shot, head slightly tilted forward. Black hair covers left eye
completely, only right eye visible staring directly into camera. Lips slightly
pressed together with subtle pout. Quiet, aloof, chic. Strands close to lens
creating soft motion blur.

PHOTOGRAPHY STYLE:
iPhone 17 Pro Max front/rear direct flash effect. Strong frontal flash,
bright highlights, slight overexposure. Skin with natural sheen,
background with subtle grey shadows. Vintage digital grain, fine noise,
soft motion blur, slight defocus, imperfect edges, early CCD camera texture.
Real photography feel like actual phone/digital camera shot.

COLORS: pale skin, black hair, white top, light grey background, no warm tones.

QUALITY: photorealistic, natural skin, NOT studio, NOT AI painting,
NOT plastic, NOT airbrushed, NOT deformed, NOT doll-like, NOT European,
NOT childlike, NO text, NO watermark, NO date, NO borders.
```

---

## 硬约束

| # | 规则 |
|---|------|
| 1 | **三张同一个人** — 同一张脸、同一肤色、同一发色 |
| 2 | **不跑脸** — 允许姿势/表情/角度变化，五官比例不变 |
| 3 | **真实摄影感** — 不是 AI 绘画、不是棚拍、不是塑料皮肤 |
| 4 | **白色细分隔线** — 8-12px，干净利落 |
| 5 | **无文字/水印/日期/边框** |
| 6 | **不欧美化、不幼态化、不面部畸变** |
| 7 | **Y2K 氛围** — 直闪+过曝+CCD颗粒+轻微失焦 |

---

## 禁止项

❌ 棚拍感、商业广告感
❌ AI 绘画感、塑料皮肤、过度磨皮
❌ 夸张大眼、改变脸型、欧美化、幼态化
❌ 面部畸变、五官错位
❌ 多余人物、多余肢体
❌ 文字、水印、日期、边框装饰
❌ 三张脸不一样（跑脸）
❌ 深色/霓虹/高饱和背景
❌ 精修写真感

---

## 使用流程

1. **发参考人像** → SCULPT 逆向提取 `{{FACE_ANCHOR}}`
2. **替换模板** → 将面部描述填入 `{{FACE_ANCHOR}}`
3. **出图** → 把拼好的完整 prompt 提交给图像生成工具，画幅 9:16
4. **验证** → 检查三张脸是否一致、Y2K 质感是否到位

---

## 参考

- 风格参考：2000s 日系杂志自拍页、早期 CCD 数码相机样片
- 摄影参考：iPhone 直闪夜拍、Terry Richardson 正面闪光风格
- 排版参考：品牌 Lookbook 三联排版
