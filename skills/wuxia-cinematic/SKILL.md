---
name: wuxia-cinematic
zh_name: 东方武侠电影感
description: 新东方电影感武侠基调——人物海报、角色设定图、江湖场景。古龙式危险美感,骨相美学,电影级写实光影。用于小红书封面、视频号角色海报、公众号配图。
type: style-base
ratio: "3:4"
category: image-gen
genre: 角色风格
# ── 质量追踪 ──
{
  "status": "tested",
  "rating": "★★★★☆",
  "last_used": "2026-07-16",
  "total_uses": 1,
  "trace": [
    {"date": "2026-07-16", "usage": "收录 agent-skills", "result": "✅ 已有样图"}
  ]
}
platform: shared
---

# 东方武侠电影感(Wuxia Cinematic)

> 风格基调 skill —— 管"出图长什么样",不管"出什么内容"。
> 不绑定平台/账号/选题。小红书、视频号、公众号均可复用。
> 适配工具:ChatGPT image 2 / Google Flow / Midjourney / Nano Banana / Seedream

## 用途

把人物设定、故事片段、关键词转换成可直接用于出图工具的提示词。

默认输出 3 个选项(A/B/C),不同侧重:
- **A**: 最强社交封面冲击力,清晰人物轮廓,强标题空间
- **B**: 最强电影氛围,重阴影,故事张力
- **C**: 最强人物气质,安静特写,情绪留白

## 输入

接受任意组合(稀疏时自动补全,不追问):

- **人物档案**:名字、身份、性格、命运、关系、武器、服饰、地位、情绪状态
- **故事片段**:场景、冲突、背叛、相遇、告别、复仇、隐秘往事、转折
- **关键词**:氛围、场景、配色、道具、季节、镜头风格、文字风格

## 核心美学规则(不可妥协)

### ✅ 必须

- **新东方电影感武侠**,不是仙侠/游戏偶像/二次元/古偶剧
- **古龙式危险美感**:安静的威胁、情感距离、命运感、孤独、未解的张力
- **东方骨相**:强骨相、成熟面部、贵气克制、自然不对称、非网红脸
- **电影级写实摄影**:单自然光源、日落侧逆光、局部阴影、胶片质感、真实皮肤、风吹碎发
- **情绪暧昧**:不商业微笑,不刻意摆拍,像在想一件痛苦或危险的事
- **高级留白构图**:干净负空间、可读标题区、书法字体与人物名融合
- **低 AI 感**:无塑料皮、无过度磨皮、无均匀补光、无娃娃脸、无发光特效

### ❌ 禁止

- 动漫风、仙侠发光、塑料皮肤、网红脸、幼态甜妹
- 过度对称、过度磨皮、均匀补光、娃娃脸
- 廉价古偶质感、杂乱背景、夸张奇幻特效、网文海报风
- 可爱/甜美/偶像/仙女/发光女神/完美对称脸/超白皮肤/游戏CG

## 提示词结构(单段完整英文)

每个提示词是一段完整英文,自然融入:

1. 主体与身份(Subject & identity)
2. 情绪与故事张力(Emotional state & story tension)
3. 服装/发型/妆容/道具(Clothing, hair, makeup, props)
4. 场景与氛围(Setting & atmosphere)
5. 镜头/焦段/构图(Camera angle, lens feel, framing)
6. 灯光与配色(Lighting & color palette)
7. 标题排版区(如需要)(Cover typography area)
8. 质量约束 + 负面约束(Quality & negative constraints)
9. 比例说明:默认 `aspect ratio 3:4`(竖图),可按需改 16:9/1:1/4:3

> 注:不用 `--ar` 等 Midjourney 专属语法,用通用英文 `aspect ratio 3:4` 描述,
> 各工具(ChatGPT image 2/Flow/Nano/MJ)都能理解。

## 风格校准词典

### 优先用

cinematic still, natural sunset backlight, partial face shadow, wind-touched hair, real skin texture, restrained cold gaze, old jianghu atmosphere, elegant danger, fate-heavy silence, premium editorial cover, calligraphic Chinese title integration, single-source lighting, film grain, Eastern bone structure, mature presence

### 避免用

cute, sweet, idol, fairy, ethereal glowing goddess, perfect symmetrical face, ultra white skin, game CG, 2D anime, over-detailed accessories, neon fantasy aura, plastic doll face

## 输出格式

```
A. [完整提示词段落,以 aspect ratio 3:4 结尾]

B. [完整提示词段落,以 aspect ratio 3:4 结尾]

C. [完整提示词段落,以 aspect ratio 3:4 结尾]
```

不标注长解释,只用 A/B/C。除非用户明确要求解释。

## 示例输入

```
人物:玄弓萧烬弦,天榜第七,南楚王府第一战力
武器:乌麟玄角长弓,十象之力
情绪:沉默的杀意,北境归来仅剩两人
场景:雪夜,孤崖,风
```

## 示例输出

A. Cinematic still of a tall lean wuxia archer standing alone on a snow cliff at night, holding a black horn longbow, cold iron gaze, wind-blown loose hair, dark heavy robe with frost, single natural moonlight side-back light, partial face shadow, real skin texture with cold flush, restrained dangerous silence, old jianghu atmosphere, fate-heavy loneliness, negative space at top for calligraphic title, film grain, Eastern bone structure, mature presence, avoid anime style xianxia glow plastic skin influencer face, aspect ratio 3:4

B. [类似结构,侧重阴影和故事张力]

C. [类似结构,侧重安静特写和情绪留白]

---

## 小红书发布规范（⚠️ 违规红线）

### 提示词处理

出图 prompt 通常很长，**不能塞正文**，也不要用「评论区回复获取」引导互动。

**合规方案：提示词做第 2 张图**
```
封面（角色大脸 60-75%） → 第 2 张（提示词截图） → 第 3-N 张（更多出图结果）
```

### 文案铁律

| ❌ 绝对禁止 | ✅ 合规替代 |
|------------|-----------|
| 「关注我，评论区回复XX，我发你」 | 不要任何引导获取提示词的话 |
| 「点赞抽奖送提示词」 | 正文只写角色介绍/金句 |
| 「评论区扣1，私发」 | 想互动就问：「你们还想看哪个角色？」 |

**默认文案模板：**
```
[角色名]
[一句话介绍/金句/氛围描述]

🎨 本图由 AI 生成
```

- 不加「想要提示词的扣1」
- 不加「关注领取」
- 不做任何条件交换

### 违规后处理

帖子被判「诱导互动」→ 点「修改笔记」，删掉引导话术，重新发布（比申诉快）。

## 参考图

![出图示例](https://img.webkubor.online/skills/wuxia-cinematic/preview/sample-output.png)
