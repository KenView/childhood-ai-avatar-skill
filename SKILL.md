---
name: childhood-ai-avatar-v2
description: >
  将用户上传的童年/婴幼儿照片作为人物身份主参考，生成高一致性的 9 张白底萌娃头像、
  3x3 九宫格合集，并支持更多可扩展效果与风格。适用于“参考这张小时候的照片做AI头像”、
  “做成抖音同款”、“给我9张单独图片”、“再做一张九宫格合集”等需求。
---

# Childhood AI Avatar Skill V2（9张增强版）

## 核心定位

把用户提供的真实童年照片作为**人物身份的最高优先级参考**，在尽量保持人物核心五官、
脸型、发型、年龄感与整体气质的前提下，生成：

1. **9 张独立的 1:1 白底头像**
2. **1 张 3:4 或 1:1 的 3×3 九宫格合集**
3. **可扩展多种风格 / 材质 / 特效版本**

> 核心原则：**先保人，再做风格；先保脸，再加效果。**

---

# 1. 研究结论（用于增强本 Skill 的设计思路）

本 Skill 的增强逻辑参考了主流官方产品中的通用图像生成原则：

1. **风格参考 ≠ 人物复制**
   Midjourney 官方的 Style Reference 明确强调：参考图主要负责颜色、媒介、纹理、光线等整体风格，而不是复制人物本体。
   因此本 Skill 规定：**用户童年照负责“是谁”，示例图负责“做成什么样”**。

2. **角色一致性是单独的控制目标**
   Midjourney 的 Character / Omni Reference 说明：参考图可用于保持人物的发型、面部特征和一致性。
   因此本 Skill 把“同一个孩子”作为最高优先级，不允许 9 张图变成 9 个不同的孩子。

3. **艺术化越强，偏脸风险越高**
   Midjourney 的 Stylize 文档说明：艺术化程度越高，模型自由发挥越大，也越可能偏离原始细节。
   因此在本 Skill 中：
   - 默认先出高保真白底版本；
   - 再做动画、黏土、毛绒、水彩等风格扩展。

4. **常见可拓展维度：效果 / 光线 / 色调 / 角度 / 滤镜 / 贴纸化**
   Adobe Firefly 官方文档提到可通过 effects、color tone、lighting、camera angle 等细化生成；
   Canva 官方也明确支持 cartoon、anime、art、sticker 等类型。
   因此本 Skill 扩展为更多“效果”和“风格”分支，而不只是原来的 4 张头像。

---

# 2. 触发场景

当用户表达以下意图时启用本 Skill：

- “根据我这张小时候的照片做”
- “做成抖音同款”
- “帮我生成9个表情/效果”
- “给我9张单独图片”
- “做个九宫格”
- “多增加一些效果”
- “还能做别的风格吗”
- “注意，根据我给你的图片”
- “做成白底萌娃贴纸”

---

# 3. 输入优先级

## A. 人物身份参考图（最高优先级）
用户上传的童年照片。

必须尽量保留：

- 脸型
- 头型
- 发际线
- 发型与头发长度
- 眉眼比例
- 眼睛大小与形状
- 鼻子
- 嘴型
- 两颊轮廓
- 耳朵形态
- 肤色
- 年龄感
- 婴幼儿特征
- 原图中最明显的辨识度

## B. 风格参考图（次优先级）
例如抖音截图、案例图、四宫格/九宫格示例。

仅用于参考：

- 构图
- 白底贴纸感
- 表情类别
- 小配饰
- 光线
- 画面质感
- 排版方式

**禁止风格参考图覆盖人物身份参考图。**

---

# 4. 标准工作流（9图版）

## Step 1：先提取人物特征

在开始生成前，先从原始童年照中提炼一段简洁身份描述，例如：

- very short black hair
- round baby face
- full cheeks
- large dark eyes
- small nose
- soft fair warm skin
- infant / toddler appearance
- calm innocent expression

不要擅自改变：

- 性别表达
- 年龄
- 脸型
- 发型
- 种族/族裔外观
- 关键五官比例

---

## Step 2：生成 9 张独立头像（1:1）

统一要求：

- pure white background
- floating head only
- no body
- centered composition
- clean studio lighting
- semi-realistic
- cute but natural
- polished child portrait
- high identity consistency
- same child in all 9 images
- no text
- no watermark
- no app UI

---

# 5. 九张默认效果方案

## 图 1：嘟嘴（Pout）
- 正面看镜头
- 轻微嘟嘴 / kissy pout
- 可爱呆萌

## 图 2：侧目 + 墨镜（Side Glance + Sunglasses）
- 眼睛侧看
- 微微偷笑
- 米色/浅棕色墨镜放在头顶
- 不遮挡眼睛

## 图 3：眨眼 + 粉色泡泡（Wink + Bubble Gum）
- 单眼眨眼
- 吹浅粉色泡泡糖泡泡
- 泡泡位于嘴前
- 不要挡住鼻子和整张脸

## 图 4：侧目露齿笑（Side Smile with Baby Teeth）
- 眼睛侧看
- 开心微笑
- 可露少量婴幼儿乳牙
- 不生成成人牙齿

## 图 5：惊讶 O 嘴（Surprised O-face）
- 双眼略睁大
- 嘴巴是小小的 O 形
- 有一点惊喜 / 懵懂感

## 图 6：眯眼大笑（Squinty Laugh）
- 双眼笑得微微眯起
- 嘴角上扬更明显
- 传达开心、奶萌的氛围

## 图 7：脸颊红晕 + 小爱心（Blush + Tiny Heart Accent）
- 微微脸红
- 柔和甜笑
- 允许在头旁边添加一个很小的爱心点缀
- 重点仍然是脸，不要做成复杂贴纸

## 图 8：小皇冠 / 生日帽（Tiny Crown / Party Accent）
- 保持白底头像
- 头顶加一个非常小巧的皇冠或迷你生日帽
- 表情可以是轻轻微笑
- 避免复杂装饰遮挡脸部

## 图 9：天使感柔笑（Soft Angelic Smile）
- 眼神温柔
- 自然甜笑
- 可以允许非常淡的柔光 halo 感，但背景仍为白底
- 不要变成宗教画风

> 说明：9 张图里，1-6 偏“表情变化”，7-9 偏“轻效果变化”。
> 这样既能增加“效果”，又不会因为配饰过多而削弱人物相似度。

---

# 6. 九张单图通用 Prompt 模板

```text
Use the user's uploaded childhood photo as the PRIMARY identity reference.

Preserve the same child's recognizable facial identity:
[IDENTITY_FEATURES].

Generate one standalone floating-head portrait of the SAME child.

Style:
- pure white background
- head only, no body
- centered composition
- soft clean studio lighting
- semi-realistic child photography
- natural baby skin texture
- cute, polished and high-detail
- strong identity consistency
- same age as the reference photo

Expression / effect:
[EXPRESSION_OR_EFFECT]

Important:
The uploaded childhood photo determines WHO the child is.
Any other reference image only determines STYLE / EXPRESSION / LAYOUT.
Do not replace the child's facial identity with the style reference.
Do not significantly change face shape, eye shape, hairline, hairstyle, age, or overall appearance.

Identity preservation has higher priority than beautification.
Do not idealize the face into a generic cute baby.
Keep the original child's eye spacing, face width, forehead proportion,
hairline, cheek shape, nose size and mouth proportions.

No text, no watermark, no app interface, no extra objects unless requested.
```

---

# 7. 九宫格合集（3×3）

当 9 张单图完成后，再生成一张九宫格合集。

## 默认参数
- 画幅：优先 3:4，也可 1:1
- 背景：纯白
- 排版：3 × 3
- 每张头像大小尽量一致
- 保留足够白边
- 不要加入分割线
- 不要加入标题
- 不要改变 9 张头像的人物身份

## 推荐布局

```text
┌────────┬────────┬────────┐
│ 1 嘟嘴 │ 2 墨镜 │ 3 泡泡 │
├────────┼────────┼────────┤
│ 4 露齿 │ 5 惊讶 │ 6 大笑 │
├────────┼────────┼────────┤
│ 7 爱心 │ 8 皇冠 │ 9 柔笑 │
└────────┴────────┴────────┘
```

## 九宫格 Prompt 模板

```text
Create one clean 3x3 composite image using the nine generated portraits.

Layout:
- pure white background
- 3x3 grid
- equal visual size
- generous white space
- no divider lines
- no text
- no watermark

Positions:
1. pout
2. side glance with sunglasses on top of the head
3. wink with a light pink bubble gum bubble
4. cheerful side-glancing smile with a few baby teeth
5. surprised O-mouth expression
6. squinty laughing smile
7. soft smile with a tiny heart accent
8. light smile with a tiny crown or party accent
9. gentle angelic smile

Preserve the same child identity across all nine portraits.
Do not regenerate the child into nine different-looking children.
The final image should feel like one polished portrait sticker sheet.
```

---

# 8. 身份一致性规则（最重要）

## 必须做到
每次生成时明确强调：

- `PRIMARY identity reference`
- `same child`
- `preserve recognizable facial identity`
- `reference photo determines WHO the child is`
- `style image determines STYLE only`

## 如果模型容易漂脸，追加强化：
```text
Identity preservation has higher priority than stylization.
Keep the original child's eye spacing, face width, forehead ratio,
hairline, hair length, cheek volume, nose size, mouth shape and toddler age.
Do not transform the child into a generic internet baby face.
```

---

# 9. 禁止行为

不要：

- 根据风格参考图直接复制另一个孩子的脸
- 自动变成网红统一宝宝脸
- 把短发变成长发
- 改成明显更大年龄
- 把婴儿牙齿做成成人整齐牙齿
- 过度磨皮导致失去人物辨识度
- 9 张图分别像 9 个不同孩子
- 自作主张加浓妆、耳环、复杂帽饰
- 在用户没有要求时改变性别表达
- 让装饰道具遮住核心五官

---

# 10. 可扩展更多风格（在 9 图基础上二次生成）

如果用户说“还能多种风格吗”，在保留同一人物身份的前提下，可扩展：

## Style A：白底半写实（默认）
```text
clean white studio background,
semi-realistic baby portrait,
soft diffused lighting,
natural skin texture,
minimalist,
high identity fidelity
```

## Style B：3D 毛绒公仔
```text
3D plush toy style,
soft fuzzy fabric,
round cute proportions,
warm soft lighting,
preserve facial identity
```

## Style C：黏土手办
```text
cute clay figure style,
handmade polymer clay texture,
soft rounded facial features,
preserve identity
```

## Style D：日系漫画
```text
Japanese anime-inspired portrait,
clean line art,
soft flat shading,
cute child proportions,
identity-consistent eyes
```

## Style E：绘本水彩
```text
soft watercolor children's book illustration,
gentle paper texture,
warm pastel palette,
preserve recognizable facial proportions
```

## Style F：复古儿童照
```text
1990s childhood studio photography,
slight film grain,
warm faded tones,
retro family photo aesthetic,
preserve identity
```

## Style G：贴纸 / 透明背景
```text
cute sticker portrait,
clean white outline,
transparent background,
recognizable expression,
same child identity
```

## Style H：卡通滤镜
```text
cartoonified portrait,
playful simplified shapes,
clean edges,
cute but identity-preserving
```

## Style I：Anime / Kawaii
```text
soft anime portrait,
kawaii expression,
light pastel rendering,
preserve identity cues
```

## Style J：盲盒手办
```text
designer blind-box figurine,
vinyl toy finish,
oversized cute head,
studio product photography,
preserve facial identity
```

## Style K：轻素描 / 手绘线稿
```text
soft pencil sketch portrait,
light paper texture,
minimal monochrome linework,
preserve facial proportions
```

## Style L：奶油柔光写真
```text
creamy soft-light child portrait,
gentle glow,
pastel tonal mood,
studio-clean finish,
preserve identity
```

---

# 11. 多风格生成规则

当用户要求多个风格时：

1. **不要同时改变“人物身份 + 年龄 + 风格”。**
2. 每种风格都继续使用原童年照片作为身份参考。
3. 优先保持：
   - 脸型
   - 眼距
   - 发型
   - 年龄
4. 风格只改变：
   - 材质
   - 光线
   - 绘画方式
   - 背景
   - 轻度比例
   - 局部装饰

---

# 12. 默认输出策略

如果用户只说：

> 帮我制作

默认：
1. 先生成 **1 张九宫格预览图**；
2. 如用户认可，再生成 **9 张单独版**。

如果用户说：

> 给我9张单独图片

直接分别生成 9 张 1:1。

如果用户说：

> 再给我一张九张放一起 / 九宫格

直接基于前面 9 张单图生成 3×3 九宫格。

如果用户说：

> 注意，根据我给你的图片

立即提高身份参考权重：

```text
The user's uploaded childhood photo is the PRIMARY and dominant identity reference.
Do not substitute the face from any style reference.
Identity consistency is more important than decoration.
```

---

# 13. 用户沟通原则

不需要反复追问。

只要用户已经上传一张清晰可用的童年照片，就直接开始。

只有以下情况才提示补图：

- 人脸被严重遮挡
- 原图完全看不清五官
- 用户要求极高相似度，但当前图片分辨率严重不足

否则直接生成。

---

# 14. 推荐最终交付（9图版）

标准完整交付为：

- `01_pout.png`
- `02_sunglasses.png`
- `03_bubble.png`
- `04_smile_teeth.png`
- `05_surprised.png`
- `06_laughing.png`
- `07_blush_heart.png`
- `08_crown_party.png`
- `09_soft_smile.png`
- `10_collage_3x3.png`

可选扩展：

- `style_plush_3x3.png`
- `style_clay_3x3.png`
- `style_anime_3x3.png`
- `style_watercolor_3x3.png`
- `style_retro_3x3.png`
- `style_sticker_3x3.png`

---

# 15. 一句话核心指令

> 永远把用户上传的童年照片当作“人物是谁”的主参考，把案例图当作“画面怎么做”的风格参考；先锁定人物身份，再扩展到 9 张表情 / 效果，并在需要时继续做多风格版本。
