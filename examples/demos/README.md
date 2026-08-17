# Public-domain demo gallery

这些 Demo 使用历史档案中的公有领域或“无已知版权限制”儿童照片作为身份参考，展示 `childhood-ai-avatar-v2` 对不同质量输入的处理效果。生成结果由 Codex 内置图像生成工具依据本仓库 `SKILL.md` 的默认九宫格流程生成。

> 生成式模型只能近似保持人物身份。历史照片越模糊、角度越偏，输出中的推断成分越多；本页面不声称精确还原真实人物。

## Demo 1：1880 年坐姿婴儿

| 输入 | 3×3 输出 |
| --- | --- |
| ![1880 seated baby source](01-seated-baby-1880/source.jpg) | ![1880 seated baby generated 3x3 demo](01-seated-baby-1880/output_3x3.png) |

- 原作：*Portrait of a seated baby, ca. 1856–1900*，约 1880 年，摄影者不详。
- 来源：[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Portrait_of_a_seated_baby,_ca._1856-1900._(4732551110).jpg)，馆藏提供方为 Fylkesarkivet i Sogn og Fjordane。
- 权利状态：Flickr Commons / Wikimedia Commons 标注为 **No known copyright restrictions**。

## Demo 2：约 1850 年 NGA 儿童银版照

| 输入 | 3×3 输出 |
| --- | --- |
| ![NGA child source](02-nga-child-1850/source.jpg) | ![NGA child generated 3x3 demo](02-nga-child-1850/output_3x3.png) |

- 原作：*Portrait of a Child*，British 19th Century，约 1850 年，银版摄影。
- 来源：[Wikimedia Commons / National Gallery of Art](https://commons.wikimedia.org/wiki/File:British_19th_Century,_Portrait_of_a_Child,_c._1850,_NGA_102580.jpg)。
- 权利状态：[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)。

## Demo 3：1860 年代低分辨率儿童肖像

| 输入 | 3×3 输出 |
| --- | --- |
| ![University of Washington child source](03-uw-child-1860s/source.jpg) | ![University of Washington child generated 3x3 demo](03-uw-child-1860s/output_3x3.png) |

- 原作：*Portrait of a child, carte-de-visite photograph*，A. C. Moore，约 1860–1867 年。
- 来源：[Wikimedia Commons / University of Washington Special Collections](https://commons.wikimedia.org/wiki/File:Portrait_of_a_child,_carte-de-visite_photograph,_circa_1860-1867_(PORTRAITS_2263).jpg)。
- 权利状态：Wikimedia Commons 标注为 **Public domain in the United States**；其他司法辖区请自行核对。
- 说明：原文件仅 338×600 像素，因此此案例专门展示低清输入下的限制。

## 生成约束

三个输出均使用相同的默认顺序：

1. 嘟嘴
2. 侧目与头顶墨镜
3. 眨眼与粉色泡泡
4. 侧目露齿笑
5. 惊讶 O 嘴
6. 眯眼大笑
7. 红晕与小爱心
8. 小皇冠
9. 天使感柔笑

统一要求为纯白背景、仅头部、3×3 排列、无文字和水印，并把每张历史照片作为唯一人物身份参考。

## 许可说明

原始输入图片保留上面逐项列出的权利状态与来源说明，不因被收录到本仓库而改为 MIT License。生成的 Demo 输出在法律允许的范围内随本仓库 MIT License 提供，不作身份相似度、版权状态或特定用途适用性的保证。
