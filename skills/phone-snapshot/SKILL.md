---
name: phone-snapshot
zh_name: 手机随手拍
description: 真实手机街拍质感 — 手抖动态模糊、柔光朦胧、轻微噪点、不完美构图。像普通人用手机随手拍的生活照。
type: style-base
platform: xiaohongshu
ratio: "3:4"
category: image-gen
genre: 生活写真
style: 现代
---

# 手机随手拍

> 风格核心：真实手机拍摄 × 自然日光 × 不完美生活感。场景/人物/服装自由替换。

## 固定风格核心

```
画质标准：真实智能手机拍摄质感，无明显后期痕迹。轻微噪点，细节不够锐利，
          整体柔和朦胧感（手机镜头特性），非单反画质，非棚拍质感。
动态特征：手持拍摄的轻微手抖，头发边缘和身体轮廓出现自然的动态模糊，
          非刻意摆拍，有抓拍的随机感。
光影风格：自然日光或城市环境光，暖调为主，光线不均匀，有真实过曝/欠曝区域，
          禁止人工补光、轮廓光、完美曝光。
构图规则：不完美构图，人物可能稍偏、裁切不精准，有路人或街景元素入镜，
          禁止对称构图、黄金比例摆拍、影棚背景。
色调倾向：温暖自然，轻微偏黄或偏暖，手机自动白平衡效果，
          禁止电影级调色、高饱和滤镜。
背景处理：轻微自然虚化（手机光学限制），非大光圈浅景深，
          街景/建筑/行人作为真实环境元素。
禁止元素：单反感，棚拍感，完美构图，人工光，过度锐化，精美修图，
          网红脸，摆拍僵硬感，电影级调色，大光圈虚化，纯色背景
```

## 可变参数

| 参数 | 默认值 | 可替换为 |
|------|--------|---------|
| 人物 | 年轻女孩，浅色连衣裙，手持咖啡杯 | 任意人物/服装/道具 |
| 场景 | 阳光街角，城市街道 | 公园/地铁/商场/校园/菜市场 |
| 天气/时间 | 晴天午后 | 阴天/黄昏/夜晚路灯/雨天 |
| 动作 | 自然站立，拿咖啡 | 走路/看手机/等红灯/靠墙发呆 |
| 构图 | 中景，稍偏左，轻微裁切 | 全身远景/近景/低角度仰拍 |

## 负面约束固定

```
单反画质，棚拍，完美构图，人工补光，锐利细节，磨皮美颜，
电影色调，大光圈浅景深，干净背景，摆拍感，对称构图，
过度修图，完美曝光，无噪点，三脚架稳定感
```

## 使用方式

```
固定风格核心 + 人物=X + 场景=Y + 动作=Z → 生成完整 prompt
```

## 提示词模板

直接复制使用，替换 `[...]` 部分：

```
A candid smartphone photo of [人物描述], [动作描述], at [场景描述].
Shot on a regular phone camera with slight hand shake,
creating natural motion blur at the edges of hair and body silhouette.
Soft overall haziness typical of phone lenses, details not overly sharp.
Background slightly blurred with natural depth of field.
Warm natural colors, slight noise and grain like a real phone photo.
Casual imperfect composition, not professionally framed.
Authentic everyday snapshot aesthetic, not staged, not DSLR.
--ar 3:4
```

### 示例

```
A candid smartphone photo of a young woman in a light summer dress,
holding a coffee cup, standing at a sunny street corner.
Shot on a regular phone camera with slight hand shake,
creating natural motion blur at the edges of hair and body silhouette.
Soft overall haziness typical of phone lenses, details not overly sharp.
Background slightly blurred with natural depth of field.
Warm natural colors, slight noise and grain like a real phone photo.
Casual imperfect composition, not professionally framed.
Authentic everyday snapshot aesthetic, not staged, not DSLR.
--ar 3:4
```

---

<!-- tracking
{"status":"draft","rating":"","last_used":"","total_uses":0,"trace":[]}
-->
