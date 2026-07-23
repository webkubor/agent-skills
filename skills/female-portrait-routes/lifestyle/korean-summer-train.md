# 女性人像提示词导演 Skill｜韩系夏日复古列车 Route

版本编号：`FEMALE-PORTRAIT-DIRECTOR-V1.5`
文档类型：风格路由母版
所属分类：`routes/lifestyle/`
route_id：`korean-summer-train`
style_name：`韩系夏日复古列车写真`

## 1. 风格定位

韩系夏日生活方式写真（Korean Summer Lifestyle），商业时尚摄影，真实抓拍感（candid lifestyle photography）。仿佛摄影师在人物整理头发、转头望向镜头的一瞬间按下快门，没有任何摆拍痕迹，自然、轻松、有呼吸感，青春、治愈、浪漫。

## 2. 参数锁定规则

用户明确填写的参数优先保留。默认参数如下：

### 2.1 人物默认

22–26 岁年轻成年东亚女性，约 168cm，九头身比例。鹅蛋脸，深棕色杏仁眼，自然拱形眉，小巧挺直鼻梁，珊瑚粉自然唇色。淡妆，真实皮肤质感。极长深棕黑色长发，自然蓬松大波浪。穿着白色短款夏季上衣 + 高腰深靛蓝牛仔短裤 + 白色低帮帆布鞋。

### 2.2 场景默认

复古老式公车、电车或铁路车厢内的深海军蓝色乙烯基长椅。窗外阳光明媚的夏日公园（高度虚化）。温暖午后阳光从右后方窗户照射，形成柔和逆光。复古日系电车氛围。

### 2.3 光线默认

柔和逆光 + 金色轮廓光（rim light）。面部由左前方柔和自然补光照亮，眼睛有真实 Catchlight。高光柔和不过曝，阴影干净开放。

### 2.4 色调默认

Kodak Portra 400 风格：奶油白、暖肤色、深海军蓝、牛仔蓝、柔和绿色、浅黄色。柔和电影色调，轻微胶片颗粒（film grain），film halation，soft highlight roll-off。低对比，高级韩系生活方式写真。

### 2.5 画面比例默认

3:4（小红书图文首选）× 全画幅摄影感

## 3. 构图默认

全身构图（full body），从头顶到脚部完整保留。最近的小腿和鞋尖自然延伸至画面左下角边缘之外，形成真实广角透视感。左膝自然弯起，另一条腿向镜头方向伸展。

人物斜坐于长椅上，身体微微前倾，头部轻轻向右肩倾斜。自然灿烂的笑容，眼神温暖明亮直视镜头，仿佛正在与摄影师聊天。

## 4. 提示词母版（英文关键词）

```text
ultra realistic, masterpiece, photorealistic, Korean lifestyle photography, candid moment, spontaneous pose, genuine smile, effortless elegance, authentic skin texture, realistic body weight distribution, natural breathing motion, subtle asymmetry, commercial fashion photography, summer editorial, cinematic photography, Kodak Portra 400, soft film grain, natural window light, high dynamic range, premium editorial, 8K

A 22-26 year old young East Asian woman, slim and elegant, oval face, deep brown almond eyes, natural arched brows, small straight nose, coral pink natural lips. Light makeup with real skin texture — visible pores, fine vellus hair, natural blush. Extremely long dark brown-black hair in natural loose waves cascading past the chest.

She wears a white cropped summer top with delicate ruffle sleeves, deep V-neck with bow tie detail, paired with high-waist deep indigo denim shorts and white low-top canvas sneakers. One hand naturally lifts to tuck hair behind her ear, the other rests beside her on the seat.

Setting: vintage cream-colored public transport carriage, retro Japanese train aesthetic. She sits diagonally on a deep navy blue vinyl bench. Full body composition from head to toe. Warm afternoon sunlight streams through the right-rear window creating soft backlight — golden rim light on hair edges, shoulders, sleeves, cheeks and arms. Face lit by soft natural fill from front-left.

Outside the wide-open window: a sunlit summer park with lush green trees and lawns, heavily blurred into creamy green and pale yellow bokeh — no buildings, people, vehicles, or signs visible.

Color palette: Kodak Portra 400 style — cream white, warm skin tones, deep navy blue, denim blue, soft greens, pale yellows. Soft cinematic tones, subtle film grain, film halation, soft highlight roll-off. Low contrast, high dynamic range, smooth color transitions.

Sony A7R V, FE 50mm F1.4 GM, ISO125, 1/640s, f/2.2. Eyes, face, hands, top, and shorts remain extremely sharp; background and window exterior gradually blur into natural optical depth of field.

Thousands of ultra-fine backlit flyaway hairs, each strand visible. Realistic fabric folds and seams on clothing. Subtle ring jewelry. Natural wear marks on the vintage bench and slight lived-in texture on sneaker soles.

HDR, cinematic, natural lighting, commercial fashion, lifestyle portrait, travel editorial
```

## 5. 负面提示词

```text
low quality, blurry, CGI, anime, illustration, doll face, plastic skin, wax skin, AI face, over sharpen, over HDR, oversaturated, orange skin, bad anatomy, bad hands, extra fingers, missing fingers, duplicated limbs, distorted body, unrealistic legs, malformed face, crossed eyes, watermark, logo, text, brand, cropped head, cropped feet, multiple people, messy background, studio lighting, flash photography, harsh shadows, overexposed, underexposed, grainy, noise, vintage filter, sepia, black and white, dutch angle, fisheye, wide angle distortion, selfie, mirror selfie, phone camera, webcam, low resolution, pixelated, compression artifacts, unnatural pose, stiff posture, forced smile, dead eyes, uncanny valley, body horror
```

## 6. 触发条件

当用户输入以下风格名称或相近表达时调用本 route：

```text
韩系写真、韩系夏日、复古列车、电车写真、韩系生活方式、Kodak Portra、夏日胶片、车内写真、公车写真、青春治愈写真、韩国时尚摄影、candid lifestyle、korean summer
```

## 7. 路由边界

### 7.1 与清纯生活照区别

`清纯生活照` 更偏安静、温柔、咖啡馆/窗边场景。`韩系夏日复古列车` 更偏阳光、活力、复古交通车厢、逆光胶片感。

### 7.2 与旅行假日写真区别

`旅行假日写真` 偏度假、海边、酒店。`韩系夏日复古列车` 偏城市交通、复古车厢、夏日青春。

## 8. 质检规则

```text
1. 是否全身构图且从头顶到脚部完整？
2. 是否有自然逆光和金色轮廓光？
3. 是否 Vintage 列车/公车场景？
4. 是否有胶片 Kodak Portra 400 质感？
5. 是否避免了网红脸、塑料皮肤、CG 感？
6. 是否有真实飞散发丝和皮肤纹理？
7. 窗外背景是否为虚化公园（无建筑/人物/广告牌）？
```
