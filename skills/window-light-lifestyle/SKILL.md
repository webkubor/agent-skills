---
name: window-light-lifestyle
zh_name: 窗光高级生活照
description: 窗边午后的高级生活人像，自然肤质、柔光体积感、真人摄影质感。场景/服装/发型可替换。
type: style-base
platform: xiaohongshu
ratio: "3:4"
category: image-gen
genre: 人像写真
style: 现代
---

# 窗光高级生活照

> 风格核心：Sony 85mm 摄影质感 × 暖窗自然光 × 真人感（去AI味）。GPT-Image-2 专属优化。

## 固定风格核心

```
人物类型：不同面孔的漂亮东方女性，辨识度高，避免AI网红脸。
          自然优雅鹅蛋脸，精致骨相，杏仁眼，略高鼻梁，饱满嘴唇，明亮笑容。
          看起来新鲜、自信、轻松有吸引力，不过度完美。

肌肤标准：健康瓷白暖调肤色，半透明光泽，可见毛孔，淡桃色腮红，
          真实皮肤纹理，自然反光。无塑料皮肤，无重度美颜，无过度磨皮。

光线风格：暖调午后阳光从侧窗进入，头发高光、面部和肩膀柔和轮廓光、
          真实阴影、体积光、丰富电影级对比度，同时保持自然曝光。
          这是最重要的改善项。

画面质感：Sony A7R V + 85mm f/1.4 的实拍感，看起来是经验丰富的摄影师拍的真人照片，
          而非AI生成图像。保留微小瑕疵、自然不对称、真实肤质纹理、
          细微发丝飞散、真实光影、强烈的人类存在感。

禁止元素：网红审美、夸张美貌、二次元特征、娃娃脸、过度对称、
          塑料皮肤、浓妆、过度锐化、扁平光线、不真实比例、明显AI感
```

## 可变参数

| 参数 | 默认值 | 可替换为 |
|------|--------|---------|
| 场景 | 窗边木质窗框，纱帘，绿植，白花，暖木家具，奶油色背景虚化 | 阳台/花园/书房/咖啡厅窗边 |
| 服装 | 象牙白真丝吊带 + 轻奶油色针织开衫，丰富面料纹理 | 颜色/款式可换，保持高级简约 |
| 发型 | 松散浪漫低盘发，柔和刘海，空气感，珍珠发饰 | 散发/低马尾/编发，保持松弛感 |
| 构图 | 上半身取景，平视镜头，放松坐姿，眼神交流 | 构图可调 |
| 光线色调 | 暖调午后阳光 | 晨光/柔光/金色黄昏 |

## 负面约束固定

```
网红审美，夸张美貌，二次元特征，娃娃脸，过度对称，塑料皮肤，
浓妆，过度锐化，扁平光线，不真实比例，明显AI生成感，
影楼精修，过度磨皮，死白皮肤，假睫毛，夸张美瞳
```

## 去 AI 味增强（推荐附加）

出图时追加以下段落，显著提升真人感：

```
The portrait should immediately feel believable at first glance.
People should assume it is a real photograph rather than an AI-generated image.
Preserve tiny imperfections, natural asymmetry, realistic skin texture,
subtle hair flyaways, authentic lighting, and a strong sense of human presence.
```

## 使用方式

```
固定风格核心 + 场景=X + 服装=Y + GPT-Image-2 优化句 → 生成完整 prompt
```

## 参考图

![参考图](https://img.webkubor.online/skills/window-light-lifestyle/preview/sample-output.jpg)

---

<!-- tracking
{"status":"tested","rating":"★★★★★","last_used":"2026-07-15","total_uses":1,"trace":[{"date":"2026-07-15","usage":"用户提供GPT-Image-2优化 prompt+参考图，脱水入库","result":"✅ 首个GPT-Image-2专属SKILL"}]}
-->
