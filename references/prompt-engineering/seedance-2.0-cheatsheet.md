# Seedance 2.0 速查表

## 一句话口诀
> 谁 + 干什么 + 在哪 + 什么氛围 + 怎么拍 + 风格 + 画质 + 不用什么

## 模式选择
```
纯文字出视频 → Text-to-Video（先写主体，动作物理化，运镜简单）
有首帧图 → Image-to-Video（先引用图，一层运动，不变身份）
要一致性 → Reference-to-Video（先写固定什么，再加轻量指令）
```

## 标准单段模板（≤15秒）
```
[时长]秒 [主题]，[时间分镜]：
0-N秒：[运镜] [主体] [动作] [场景] [台词] [音效]
N-M秒：[运镜] [主体] [动作] [场景] [台词] [音效]
M-结尾：[收束镜头] [主体收场] [音效渐弱]
负面：no shaky camera, no deformation, no watermark, no subtitles, no random text
```

## 多段拼接模板（>15秒）
```
第1段（0-15秒）：正常生成
衔接点：[本段结尾画面描述]

第2段（15-30秒）：视频延长
操作：将@视频1延长15秒
提示词：接上段 [衔接描述] → [新内容]
```

## 运镜速查
```
推近特写 → push in / dolly zoom
跟踪运动 → tracking shot / follow
环绕展示 → orbit around
手持纪实 → handheld / shaky cam
俯拍大全 → overhead / bird's eye
仰拍权威 → low angle
固定观察 → static / locked-off
慢动作 → slow motion
快速切换 → whip pan
```

## 负面约束（按场景选）
```
通用：no shaky camera, no object melting, no random text, no muddy lighting, no watermark, no subtitles
产品：no logo distortion, no packaging collapse, no duplicate product, no label blur
人物：no extra fingers, no face drift, no lip mismatch, no plastic skin, no anime face
```

## 平台硬限制
```
单次：4-15秒
图片：≤9张，单张≤30MB，jpeg/png/webp
视频：≤3段，2-15秒，单段≤50MB，480p-720p
音频：≤3段，总≤15秒，单段≤15MB
总文件：≤12个
禁止：含真实人脸的照片/视频
```
