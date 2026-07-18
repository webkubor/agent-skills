---
name: character-consistency
zh_name: 人物一致性换装
platform: shared
type: style-base
ratio: "3:4"
description: 参考人像出图基础SKILL — 锁定人物身份，仅换场景/服装/风格。换装、换场景、换事情，都走这个。
category: image-gen
genre: 角色风格
---
# ── 质量追踪 ──
{
  "status": "draft",
  "rating": "★★☆☆☆",
  "last_used": "2026-07-16",
  "total_uses": 0,
  "trace": [
    {"date": "2026-07-16", "usage": "收录 agent-skills", "result": "⏳ 待出样图验证"}
  ]
}

# 人物一致性换装

> 参考一张人物图，生成同一人物在不同场景/服装/风格下的新图。
> 核心原则：人物必须是同一个人，不是五官相似的另一个模特。

## 适用

- 基于参考图给同一人物换装、换场景、换事情
- 给同一角色生成多套 Look（专辑封面、场景照、生活照）
- 所有需要「换衣服不换脸」的出图需求

## 核心约束（五段式）

### 1. 人物身份约束

仅参考上传图片中的人物身份特征。保留同一位成年人物的核心辨识度：脸型轮廓、五官比例、眼型、眉形、鼻梁、鼻尖、嘴唇形状、下颌线、发际线和整体气质。人物必须看起来是同一个人，而不是五官相似的另一位模特。

### 2. 参考范围限制

不要继承参考图中的背景、场景、服装、饰品、姿态、镜头角度、构图、光线、滤镜、色调和摄影风格。参考图只用于人物身份一致性。

### 3. 目标画面

将同一位人物重新拍摄为[场景描述]。场景、服装、姿态由具体出图需求指定。

### 4. 摄影风格

由具体出图需求指定。可包含光质、色调、颗粒、画质、真实感等参数。

### 5. 一致性约束（禁止项）

- ❌ 不要更换人物
- ❌ 不要重新设计五官
- ❌ 不要把人物生成成相似类型的陌生人
- ❌ 不要夸张大眼、尖下巴、高鼻梁或过度瘦脸
- ❌ 不要改变人物年龄和种族特征
- ❌ 不要过度磨皮、不要网红脸
- ✅ 保持自然面部结构和真实比例

## English Prompt Keywords

```
same person, consistent facial features, natural face proportions,
preserve face shape, preserve eye shape, preserve nose bridge,
preserve lip shape, preserve jawline, preserve hairline,
no facial redesign, no plastic surgery look, no exaggerated features,
natural skin texture, real person look, candid photography
```

## SCULPT 映射

```
S = 参考图人物（锁定身份，不换人）
C = 新场景构图（不继承参考图构图）
U = 新风格/新场景（不继承参考图风格）
L = 新光影（不继承参考图光线）
P = 无文字
T = 真实摄影质感（不过度磨皮）
```

## 使用方式

出图时将此 SKILL 的约束文本附加到 prompt 末尾：

```
[粘贴 核心约束 第 1-5 段]
目标画面：[填写具体场景/服装/姿态]
摄影风格：[填写具体风格参数]
```

## 样例

> 目标画面：同一位人物穿浅水蓝修身针织上衣与奶白色休闲短裙，坐在白色街角咖啡馆户外圆桌旁，身体轻微侧向镜头，表情自然放松。
> 摄影风格：高色温自然光，冷白高光，蓝白清透，轻微柔闪，极轻颗粒，真实生活抓拍感。
