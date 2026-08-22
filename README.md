# Bress-On Street Photo Scoring Master

Creator: [胶着状态 In A Film State on Xiaohongshu](https://xhslink.cn/m/ArZr9m8zJZ1) · [@j1mmywoo on Instagram](https://www.instagram.com/j1mmywoo/)

**中文说明在下方。**

Bress-On is a Codex skill for scoring, comparing, and editing street photographs with a transparent 100-point rubric. It turns a vague reaction such as “this photo feels stronger” into a repeatable evaluation: what works, what weakens the frame, and what the photographer can do next.

“Bress-On” is an English wordplay inspired by the Chinese name “布列紧,” a playful echo of “布列松.”

## What this skill does

- Scores one photograph or a full set on the same six-part, 100-point scale.
- Explains one main strength, one main weakness, and one practical improvement.
- Ranks a group, selects the top N, or filters photographs by a score threshold.
- Uses filenames so the result stays traceable to the original files.
- Separates photographic meaning and visual structure from technical polish.
- Calibrates judgment with historically important photographs and a photobook-based aesthetic profile rather than a generic image-quality checklist.

It is useful for contact-sheet editing, portfolio preparation, post-shoot review, and learning why one frame succeeds more than a nearby alternative.

## Scope: street photography only

This scoring system is designed specifically for street photography: candid or observational photographs made in public or shared spaces, where timing, human behavior, visual coincidence, and the relationship between people and environment are central to the image.

It is **not calibrated for portrait, landscape, commercial, or product photography**. Those genres have different goals and need different standards—for example, direction and likeness in portraiture, spatial and environmental interpretation in landscape, or client intent, styling, and product communication in commercial work. Do not use a low or high Bress-On score as a judgment of quality in those genres.

## Evaluator identity

When the skill evaluates photographs in Chinese, it identifies itself as **布列紧**. In an English evaluation, it uses **Bress-On Master**. A full English critique is headed `Bress-On Master Review`; the name may also appear naturally in a verdict or conclusion without being repeated in every paragraph.

These names describe the skill's evaluator persona. They do not represent a real photographer, human judge, official institution, or professional credential.

## Installation

Clone the repository into your Codex skills folder:

```bash
git clone https://github.com/J1mmyWoo/bress-on-street-photo-scoring-master.git ~/.codex/skills/bress-on-street-photo-scoring-master
```

Restart Codex so it can discover the skill. Then attach one or more photographs and explicitly name the skill in your request.

## Quick start

Try one of these prompts:

```text
Use Bress-On Street Photo Scoring Master to score these photos.
```

```text
Score every image, rank them from strongest to weakest, and explain the top three.
```

```text
Select the five images scoring 80 or above. Do not critique the rejected images.
```

```text
Compare these two near-duplicate frames and tell me which one to keep and why.
```

For a more useful result, say whether to score every frame or only shortlist candidates, how many photographs you want to keep, whether you want compact or detailed feedback, and whether the set should be judged individually or as a coherent series.

## Output format

The default response is concise and file-based:

```text
Bress-On Master Review

DSCF0123.jpg — 84/100
Strength: The crossing gestures create a clear human relationship and hold the frame together.
Weakness: A bright shape at the right edge competes with the main interaction.
Improvement: Reframe slightly earlier or crop the right edge to protect the visual hierarchy.
Confidence: High
```

With multiple photographs, the skill can also return a ranked list, a top-N selection, or only the photographs that clear a requested threshold. A full critique additionally includes all six category scores and a separate aesthetic-fit rating. It does not invent titles or submission metadata unless the user explicitly asks for a separate task.

## Knowledge-distillation framework

The skill does not contain or redistribute scans of copyrighted photobooks. It also does not retrain or fine-tune the underlying model. “Distillation” here means converting prior photobook study into inspectable principles, diagnostic questions, score gates, and comparison tests. Five reference files are read before scoring:

- **Historical scoring calibration:** lessons from Henri Cartier-Bresson's `Behind the Gare Saint-Lazare`, Dorothea Lange's `Migrant Mother`, Robert Frank's `Trolley, New Orleans`, and Richard Kalvar's `Woman in the Window` contact sheet.
- **Photobook-based aesthetic profile:** preferences derived from Rinko Kawauchi's `Illuminance` and `Hanabi`, Joel Meyerowitz's `A Question of Color`, Alex Webb's `The Suffering of Light`, selected Henri Cartier-Bresson work, Gregory Halpern's `ZZYZX` and `Let the Sun Beheaded Be`, Todd Hido's `Intimate Distance`, and Josef Koudelka's `Wall`.
- **Distilled photographer principles:** an individual card for each of those seven photographers, separating transferable questions from superficial stylistic shortcuts.
- **Scoring decision protocol:** an evidence-first procedure with replaceability, timing, subject-removal, color, edge, and repeated-viewing tests, plus stricter gates for scores above 80, 85, and 90.
- **Street-editing principles:** near-duplicate selection, reading people inside environments, separating observation from invention, and ethical treatment of photographed people.

These references calibrate questions and scoring severity; they are never templates for imitation. A photograph receives no extra points for resembling a famous photographer. Personal aesthetic fit is reported separately and cannot change the absolute score.

The seven distilled references are Rinko Kawauchi, Joel Meyerowitz, Alex Webb, Henri Cartier-Bresson, Gregory Halpern, Todd Hido, and Josef Koudelka. Their work changes the questions the evaluator asks—not the visual style it tries to reproduce.

## Scoring logic

The final score is the sum of six independently considered categories. A technically clean image does not automatically score highly: moment, meaning, structure, and voice carry 75 of the 100 available points.

| Category | Maximum | Core question |
|---|---:|---|
| Moment and human meaning | 25 | Is there a meaningful, well-timed event, gesture, expression, or relationship? |
| Composition and visual organization | 20 | Does the frame direct attention clearly and use its space and edges intentionally? |
| Layering and context | 15 | Do people, objects, and the environment create depth and useful relationships? |
| Light, tonality, and color | 15 | Do light, tonal separation, and color strengthen the subject and atmosphere? |
| Originality and authorial voice | 15 | Does the photograph show a personal point of view rather than a familiar formula? |
| Technical execution | 10 | Do focus, exposure, motion, and processing serve the image's intent? |

### 1. Moment and human meaning — 25 points

This is the highest-weight category. It considers timing, gesture, expression, interaction, emotional charge, ambiguity, and narrative potential.

- **21–25:** A rare or decisive moment with strong human meaning; timing is essential to the image.
- **16–20:** A clear and engaging event or relationship, with minor limitations in timing or emotional force.
- **10–15:** The subject is understandable, but the moment feels ordinary, early, late, or only mildly revealing.
- **0–9:** Little meaningful action or connection; the frame depends mainly on subject matter without a compelling moment.

### 2. Composition and visual organization — 20 points

This category looks at subject placement, balance, visual hierarchy, geometry, negative space, frame edges, overlaps, and whether the viewer knows where to look.

- **17–20:** The frame feels intentional, resolved, and easy to read without becoming static.
- **13–16:** Strong overall organization with one minor distraction, awkward overlap, or imbalance.
- **8–12:** The main subject is visible, but competing elements, dead space, or weak edges dilute it.
- **0–7:** The frame lacks hierarchy or contains major structural distractions that undermine the subject.

### 3. Layering and context — 15 points

Layering is not simply having objects in the foreground and background. The layers should interact, add information, create depth, or reveal a relationship between the subject and the place.

- **13–15:** Multiple planes work together and deepen the meaning of the scene.
- **10–12:** Clear spatial depth and useful environmental context, with small separations or overlaps that could improve.
- **6–9:** Some context is present, but the layers feel incidental or weakly connected.
- **0–5:** The frame feels flat, cluttered, or detached from its environment.

### 4. Light, tonality, and color — 15 points

The evaluator considers direction and quality of light, highlight and shadow control, subject separation, tonal rhythm, color relationships, and atmosphere. Dramatic light is not required; appropriate light is.

- **13–15:** Light or color is integral to the image and strengthens mood, depth, and attention.
- **10–12:** Good control and separation with minor tonal or color distractions.
- **6–9:** Usable but ordinary, muddy, harsh, or inconsistent light/color.
- **0–5:** Exposure, tonal merging, or color conflict materially damages readability or intent.

### 5. Originality and authorial voice — 15 points

This category asks whether the photograph goes beyond a familiar street-photography recipe. It rewards a personal viewpoint, visual risk, ambiguity, surprise, and a recognizable way of seeing.

- **13–15:** Distinctive, surprising, and difficult to substitute with another photographer's frame.
- **10–12:** A clear point of view with some familiar devices or subject matter.
- **6–9:** Competent but derivative, predictable, or dependent on a common visual cliché.
- **0–5:** Little evidence of an individual decision beyond recording the scene.

### 6. Technical execution — 10 points

Technical quality is judged in relation to intent, not perfection. Motion blur, deep shadow, grain, or unusual focus can score well when they strengthen the photograph.

- **9–10:** Technique is controlled and fully supports the image.
- **7–8:** Minor imperfections that do not meaningfully reduce impact.
- **4–6:** Noticeable focus, exposure, motion, or processing problems.
- **0–3:** Technical failure prevents the intended moment or structure from being read.

## Evaluation workflow

For each photograph, the skill follows the same reasoning sequence:

1. Identify the likely main subject and the event or visual idea.
2. Read the entire frame, including corners, borders, background, and small competing highlights.
3. Judge the six categories independently rather than letting one striking feature inflate every score.
4. Check common weaknesses: missed timing, accidental overlaps, distracting edges, empty or redundant space, weak separation, staging, repetition, and visual cliché.
5. Add the category scores and map the total to a score band.
6. Assign high, medium, or low confidence according to how clearly the photograph communicates its intent.
7. Give one specific strength, one priority weakness, and one actionable shooting, framing, editing, or sequencing suggestion.

The system does not apply automatic fixed deductions. A flaw matters in proportion to how much it damages the photograph. For example, slight motion blur may reduce technical points in one image but strengthen energy and timing in another.

## Score bands

| Score | Interpretation | Editing decision |
|---:|---|---|
| 90–100 | Exceptional, memorable, and highly resolved | Anchor image; serious portfolio candidate |
| 85–89 | Strong, with only minor weaknesses | Portfolio or final-sequence candidate |
| 80–84 | Good and worth keeping | Keep and refine; compare with neighboring frames |
| 70–79 | Competent but missing a stronger moment, structure, or voice | Secondary choice; keep only if the series needs it |
| 60–69 | Weak, despite a recognizable intention | Usually remove from the edit |
| Below 60 | Major problems in meaning, structure, or execution | Reject from the edit |

Scores are most useful for comparison within the same shoot or editing goal. A two-point difference is not an objective truth; use the written reasoning and confidence level when photographs are close.

## Working with sets and near-duplicates

When reviewing a sequence, ask the skill to distinguish image quality from series function. A quieter transition frame may be useful in a project even if it scores below the strongest standalone photograph. For near-duplicates, the comparison should prioritize meaningful differences in gesture, eye direction, overlap, spacing, and background—not tiny technical differences alone.

## Limitations and disclaimer

This rubric reflects the creator's personal approach to street-photography editing. It is intended for personal review, learning, and selection—not serious artistic adjudication, professional jury decisions, or commercial evaluation. Scores are subjective reference opinions, not objective measures of artistic value.

The skill works from the visible photograph. It does not inspect EXIF by default and cannot know the photographer's real-world circumstances or intent unless that context is provided.

This project is not affiliated with Henri Cartier-Bresson, Magnum Photos, Leica, or LFI.

## License

MIT

---

# 中文说明｜布列紧街拍评分大师

创作者：[胶着状态 In A Film State（小红书）](https://xhslink.cn/m/ArZr9m8zJZ1) · [@j1mmywoo（Instagram）](https://www.instagram.com/j1mmywoo/)

布列紧街拍评分大师是一套用于 Codex 的街头摄影评分、比较和选片 Skill。它用公开、统一的 100 分标准，把“我感觉这张更好”拆成可以复查的判断：照片好在哪里、主要问题是什么、拍摄者下一步可以怎么改。

“布列紧”是对“布列松”的中文谐音梗；英文名 Bress-On 也带有“继续按下快门”的意味。

## 这个 Skill 能做什么

- 用同一套六维、100 分标准评估单张照片或整组照片。
- 为每张入选照片指出一个主要优点、一个核心问题和一个可执行建议。
- 对一组照片进行排序、选出前 N 张，或筛出达到指定分数的照片。
- 始终使用原始文件名，方便结果和照片一一对应。
- 把“摄影的意味与画面结构”和“技术完成度”分开判断，不让清晰、锐利自动等于好照片。
- 使用历史名作与摄影书审美档案校准判断，而不是只做通用的画质检查。

适合用于拍摄后的初选、联系表编辑、作品集准备、组照筛选，以及比较连续拍摄的相似画面。

## 适用范围：仅限街头摄影

这套评分系统专门针对街头摄影：在公共或共享空间中完成的抓拍或观察式摄影，其中拍摄时机、人的行为、视觉巧合，以及人物与环境之间的关系，是照片成立的重要部分。

它**不适用于人像、风景、商业或产品摄影**。这些类型有不同的创作目标，也需要不同的评价标准，例如人像摄影中的引导和人物呈现、风景摄影中的空间与自然表达，以及商业摄影中的客户目标、造型和产品信息传达。不要用布列紧街拍评分的高低，判断这些类型作品的质量。

## 评审身份

使用中文评价照片时，这个 Skill 自称 **布列紧**；使用英文评价时，自称 **Bress-On Master**。完整中文点评使用标题 `布列紧评价`，英文点评使用标题 `Bress-On Master Review`。名称可以自然出现在结论中，但不会在每一段机械重复。

这是 Skill 的评审人格名称，不代表真实摄影师、真人评委、官方机构或专业资质。

## 安装方法

把仓库克隆到 Codex 的 skills 文件夹：

```bash
git clone https://github.com/J1mmyWoo/bress-on-street-photo-scoring-master.git ~/.codex/skills/bress-on-street-photo-scoring-master
```

重启 Codex，让它重新发现这个 Skill。然后上传一张或多张照片，并在指令中明确说出 Skill 名称。

## 快速使用

可以直接使用下面这些提示词：

```text
用布列紧街拍评分大师给这些照片打分。
```

```text
给每张照片打分，按从强到弱排序，并详细解释前三张。
```

```text
筛出 80 分以上的照片，最多保留 5 张；不要点评被淘汰的照片。
```

```text
比较这两张连拍照片，告诉我应该留下哪一张，以及决定性的差别是什么。
```

为了得到更准确的结果，可以补充说明：需要评完所有照片还是只做 shortlist、最终想保留几张、需要简短还是详细点评，以及这组照片应该作为单张作品判断，还是作为一个系列整体判断。

## 默认输出格式

默认结果简洁，并以文件名为索引：

```text
布列紧评价

DSCF0123.jpg — 84/100
优点：两个人交错的动作形成清晰关系，支撑了整个画面。
问题：右侧边缘的亮色物体与主要互动争夺注意力。
建议：更早一点按下快门，或轻微裁掉右侧，保护视觉层级。
置信度：高
```

上传多张照片时，也可以要求它输出完整排序、前 N 名，或者只显示达到指定门槛的照片。完整点评还会给出六项分数，以及与绝对分数分开的审美匹配度。除非用户另外提出要求，否则它不会擅自为照片起标题，也不会生成投稿说明或其他元数据。

## 知识蒸馏体系

Skill 不会收录或重新发布受版权保护的摄影书扫描页，也不会重新训练或微调底层模型。这里的“蒸馏”是指把之前对摄影书和作品的研究，转化成可以检查的观察原则、诊断问题、分数门槛和比较测试。评分前会读取五份参考文件：

- **历史名作评分校准：** 从 Henri Cartier-Bresson 的 `Behind the Gare Saint-Lazare`、Dorothea Lange 的 `Migrant Mother`、Robert Frank 的 `Trolley, New Orleans`，以及 Richard Kalvar 的 `Woman in the Window` 联系表中提炼评分原则。
- **摄影书审美档案：** 来源包括川内伦子的 `Illuminance` 与 `Hanabi`、Joel Meyerowitz 的 `A Question of Color`、Alex Webb 的 `The Suffering of Light`、Henri Cartier-Bresson 的部分作品、Gregory Halpern 的 `ZZYZX` 与 `Let the Sun Beheaded Be`、Todd Hido 的 `Intimate Distance`，以及 Josef Koudelka 的 `Wall`。
- **摄影师原则卡：** 为上述七位摄影师分别整理可迁移的判断问题，并明确哪些表面风格不能当成高分依据。
- **评分决策协议：** 先列可见证据，再执行可替代性、时机、主体移除、色彩、边缘和重复观看测试，并为 80、85、90 分以上设置逐级证据门槛。
- **街拍选片原则：** 涵盖相似连拍比较、人物与环境的共同阅读、事实与推断的分离，以及对被摄者的伦理处理。

这些参考只用于校准问题和评分严格度，不是模仿模板。照片不会因为像某位摄影大师而加分；个人审美匹配度会单独报告，不能改变绝对分数。

目前提炼的七位摄影师是：川内伦子、乔尔·迈耶罗维茨、亚历克斯·韦布、亨利·卡蒂埃-布列松、格雷戈里·哈尔彭、托德·希多、约瑟夫·寇德卡。他们的作品改变的是评审提出的问题，而不是要求照片复制他们的视觉风格。

## 评分逻辑

最终得分是六个维度独立评分后的总和。技术干净并不等于高分：瞬间、人的意味、画面组织、环境关系与作者表达合计占 75 分，技术完成度只占 10 分。

| 评分维度 | 满分 | 核心问题 |
|---|---:|---|
| 瞬间与人的意味 | 25 | 是否捕捉到了有意义、时机准确的动作、表情、事件或人物关系？ |
| 构图与画面组织 | 20 | 画面是否清楚地引导注意力，并有意识地使用空间和边缘？ |
| 层次与环境关系 | 15 | 人物、物体和环境是否共同形成深度与有效关系？ |
| 光线、影调与色彩 | 15 | 光线、明暗分离和色彩是否强化了主体与气氛？ |
| 独创性与作者表达 | 15 | 照片是否体现个人观看方式，而不只是复制熟悉套路？ |
| 技术完成度 | 10 | 对焦、曝光、动态和后期是否服务于照片意图？ |

### 1. 瞬间与人的意味 — 25 分

这是权重最高的一项。它判断时机、动作、表情、互动、情绪张力、含蓄性和叙事可能。

- **21–25 分：** 稀有或决定性的瞬间，具有强烈的人物意味；拍摄时机对照片不可替代。
- **16–20 分：** 事件或关系清楚、有吸引力，但时机或情绪力度仍有轻微不足。
- **10–15 分：** 能理解拍摄对象，但瞬间偏普通、偏早、偏晚，或只提供有限信息。
- **0–9 分：** 缺少有意义的动作或联系，主要依赖题材本身，瞬间没有真正成立。

### 2. 构图与画面组织 — 20 分

这一项检查主体位置、平衡、视觉层级、几何关系、负空间、画面边缘、物体重叠，以及观看者是否能迅速知道应该看哪里。

- **17–20 分：** 画面有明确意图，组织完整，易读但不僵硬。
- **13–16 分：** 整体组织较强，仅有一个较小的干扰、重叠或失衡。
- **8–12 分：** 主体仍然可见，但杂乱元素、空洞空间或薄弱边缘削弱了它。
- **0–7 分：** 缺少视觉层级，或存在足以破坏主体的重大结构问题。

### 3. 层次与环境关系 — 15 分

层次不等于前景和背景里“有东西”。不同空间层应该彼此作用，增加信息、形成深度，或揭示主体与地点之间的关系。

- **13–15 分：** 多个空间层共同工作，明显加深了照片的意义。
- **10–12 分：** 空间深度和环境信息清楚，只有轻微的分离或重叠问题。
- **6–9 分：** 有一定环境信息，但层次比较偶然，彼此联系较弱。
- **0–5 分：** 画面扁平、混乱，或主体与环境脱节。

### 4. 光线、影调与色彩 — 15 分

判断光线方向与质量、高光和阴影控制、主体分离、影调节奏、色彩关系和整体气氛。这里并不要求“戏剧化的光”，而是要求光线适合照片。

- **13–15 分：** 光线或色彩是照片不可分割的一部分，明显强化气氛、深度和注意力。
- **10–12 分：** 控制和分离良好，只有轻微的影调或色彩干扰。
- **6–9 分：** 基本可用，但偏普通、灰闷、生硬或色彩关系不统一。
- **0–5 分：** 曝光、影调粘连或色彩冲突严重破坏了可读性和表达。

### 5. 独创性与作者表达 — 15 分

这一项判断照片是否超越常见的街拍公式。它鼓励个人视角、视觉风险、含蓄性、意外感和可辨认的观看方式。

- **13–15 分：** 具有明显个性和惊喜，很难被其他摄影师的类似画面替代。
- **10–12 分：** 观点比较清楚，但仍使用了一些熟悉的手法或题材。
- **6–9 分：** 完成度尚可，但偏模仿、可预期，或依赖常见视觉套路。
- **0–5 分：** 除了记录场景之外，几乎看不到个人选择和作者判断。

### 6. 技术完成度 — 10 分

技术应当相对于照片意图来判断，而不是追求绝对完美。只要能够强化作品，动态模糊、深阴影、颗粒或非常规对焦也可以获得高分。

- **9–10 分：** 技术控制成熟，完全服务于照片。
- **7–8 分：** 有轻微瑕疵，但没有明显降低照片影响力。
- **4–6 分：** 对焦、曝光、动态或后期问题比较明显。
- **0–3 分：** 技术失败导致目标瞬间或画面结构无法成立。

## 完整评估流程

对于每张照片，Skill 会使用相同的判断顺序：

1. 找到最可能的主体，以及照片想表达的事件或视觉想法。
2. 阅读整个画面，包括四角、边缘、背景和容易抢眼的小亮点。
3. 分别判断六个维度，避免因为一个很突出的特点而把所有项目都打高。
4. 检查常见问题：错过时机、意外重叠、边缘干扰、空洞或重复空间、主体分离不足、摆拍感、内容重复和视觉俗套。
5. 汇总六项得分，并对应到总分区间。
6. 根据照片意图是否清晰，给出高、中或低置信度。
7. 指出一个具体优点、一个最优先解决的问题，以及一个可执行的拍摄、取景、后期或编排建议。

这套系统不会机械套用固定扣分。一个问题应该按照它对照片造成的实际伤害来判断。例如，轻微动态模糊在某张照片里会降低技术分，在另一张照片里却可能强化速度感和时机。

## 总分区间

| 分数 | 含义 | 选片建议 |
|---:|---|---|
| 90–100 | 杰出、难忘、完成度极高 | 可作为核心作品或作品集重点候选 |
| 85–89 | 很强，只有轻微弱点 | 可进入作品集或最终序列 |
| 80–84 | 良好，值得保留 | 保留并继续优化，与相邻画面比较 |
| 70–79 | 合格，但瞬间、结构或表达仍不够强 | 次要选择；只有组照确实需要时保留 |
| 60–69 | 有明确意图，但整体偏弱 | 通常从本轮选片中移除 |
| 60 以下 | 意味、结构或技术存在重大问题 | 建议淘汰 |

分数最适合用于同一次拍摄或同一个选片目标内部的比较。两张照片相差 2 分并不代表客观真理；当分数接近时，应优先阅读文字理由和置信度。

## 组照与相似连拍

评估一个系列时，可以要求 Skill 区分“单张照片强度”和“在组照中的功能”。一张安静的过渡画面，单张分数可能低于核心作品，但在项目里仍然必要。比较相似连拍时，应优先观察动作、眼神方向、人物重叠、空间间隔和背景变化，而不是只比较很小的清晰度差别。

## 局限与使用声明

这套标准反映创作者个人的街头摄影选片方法，适用于个人复盘、学习和筛选，不适用于严肃艺术评审、专业赛事评委工作或商业评价。所有分数都是主观参考意见，不是艺术价值的客观结论。

Skill 只根据照片中可见的信息判断。默认不会读取 EXIF；如果用户没有主动提供，它也无法知道摄影师当时的现实条件和创作意图。

本项目与 Henri Cartier-Bresson、Magnum Photos、Leica 或 LFI 没有隶属或合作关系。

## 许可证

MIT
