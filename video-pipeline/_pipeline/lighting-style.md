# 光影风格 Skill

> **管线位置**: 专项技能模块 — 为 Seedance 和 gpt-image-2 prompt 提供光影/色彩的标准词汇
> **关联**: 本技能与 `references/style-dictionary.md` 互补，此处侧重视频动态光影

---

## 一、光源设计

### 光源类型
| 光源 | 英文关键词 | 视觉效果 |
|------|-----------|----------|
| 自然日光 | natural daylight, sun | 明亮、真实、户外感 |
| 黄金时刻 | golden hour, sunset light | 温暖、柔和、电影感 |
| 蓝色时刻 | blue hour, twilight | 冷调、诗意、孤独感 |
| 窗户光 | window light, practical light | 室内、柔和的单侧光 |
| 烛光/火光 | candlelight, firelight | 温暖摇曳、亲密感 |
| 霓虹灯 | neon light, colored practical | 赛博朋克、都市感 |
| 月光 | moonlight, cool ambient | 冷寂、神秘、夜间 |
| 阴天散射 | overcast, diffused light | 均匀、柔和、低对比 |

### 光源数量与方向
| 设置 | 英文关键词 | 效果 |
|------|-----------|------|
| 单光源 | single source, key light only | 高对比、戏剧性 |
| 双光源 | key + fill light | 柔和、经典好莱坞 |
| 三点布光 | three-point lighting | 专业、均衡 |
| 逆光 | backlight, rim light | 剪影、轮廓强调 |
| 侧光 | side light, split lighting | 立体感、神秘感 |
| 顶光 | top light, overhead | 压迫感、审讯感 |
| 底光 | underlighting, from below | 恐怖、诡异 |

---

## 二、光影质感

### 硬光 vs 柔光
| 质感 | 英文关键词 | 阴影特征 |
|------|-----------|----------|
| 硬光 | hard light, crisp shadows | 边缘清晰、高对比 |
| 柔光 | soft light, diffused | 边缘渐变、低对比 |
| 混合 | hard key + soft fill | 有层次但不过曝 |

### 特殊光影
| 效果 | 英文关键词 | 视觉特征 |
|------|-----------|----------|
| 丁达尔效应 | volumetric light, god rays | 光线穿过尘埃/雾气可见 |
| 镜头光晕 | lens flare, anamorphic flare | 横条纹蓝光晕 |
| 水中折射 | caustics, underwater light | 波动光斑 |
| 雨夜反光 | wet pavement reflection, rain | 地面倒影、霓虹反射 |
| 烟雾弥漫 | atmospheric haze, fog | 光线散射、层次感 |

---

## 三、色彩调性（视频专属）

### 色调预设
| 调性 | 英文关键词 | 色彩特征 |
|------|-----------|----------|
| 青橙调 | teal and orange | 阴影青/蓝 + 高光橙/金（好莱坞标配） |
| 冷调低饱 | desaturated cold, muted | 青灰主调 + 低饱和度（武侠/悬疑） |
| 暖调电影 | warm cinematic, amber | 琥珀色主调 + 柔和高光（怀旧/温情） |
| 黑白高对比 | high contrast B&W, monochrome | 纯粹光影、极简 |
| 粉紫梦幻 | pink and purple, dreamy | 粉色+紫色柔和过渡（少女/MV） |
| 绿调阴沉 | green tint, sickly green | 病态、压抑（惊悚/赛博） |
| 金黄复古 | vintage gold, sepia | 复古照片质感（年代戏） |

---

## 四、时间段氛围模板

### 早晨（5-7点）
```text
soft morning light, cool blue shadows, warm golden highlights,
fog rising from ground, long shadows, crisp air feel
```

### 正午（11-13点）
```text
harsh overhead sunlight, deep short shadows, high contrast,
bleached highlights, heat haze shimmer
```

### 黄金时刻（16-18点）
```text
golden hour, warm amber light, long soft shadows, backlit glow,
dust particles dancing in light, everything wrapped in gold
```

### 蓝色时刻（18-19点）
```text
blue hour, twilight, deep blue sky, warm artificial lights turning on,
soft ambient, peaceful melancholy
```

### 夜晚（20-翌日）
```text
moonlight, cool blue ambient, practical light sources,
deep shadows, city lights bokeh in distance
```

---

## 五、光影连续性问题

在视频制作中，相邻镜头的光影必须保持一致：

- [ ] 光源方向一致（太阳不能左右跳跃）
- [ ] 色温一致（不能前一镜暖调后一镜冷调跳变）
- [ ] 阴影密度一致（硬度统一）
- [ ] 曝光一致（亮度连贯）
- [ ] 特殊光影（霓虹/烛光）的存在性一致

**约束写法**: 在 prompt 中添加 `consistent lighting continuity, [光源] remains at [方向]`
