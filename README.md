# Bress-On Street Photo Scoring Master

Creator: [胶着状态 In A Film State on Xiaohongshu](https://xhslink.cn/m/ArZr9m8zJZ1) · [@j1mmywoo on Instagram](https://www.instagram.com/j1mmywoo/)

[中文说明](README.zh-CN.md)

Bress-On is a Codex skill for scoring, comparing, and editing street photographs with a transparent 100-point rubric. It turns a vague reaction such as “this photo feels stronger” into a repeatable evaluation: what works, what weakens the frame, and what the photographer can do next.

“Bress-On” is an English wordplay inspired by the Chinese name “布列紧,” a playful echo of “布列松.”

## What this skill does

- Scores one photograph or a full set on the same six-part, 100-point scale.
- Explains one main strength, one main weakness, and one practical improvement.
- Ranks a group, selects the top N, or filters photographs by a score threshold.
- Uses filenames so the result stays traceable to the original files.
- Separates photographic meaning and visual structure from technical polish.

It is useful for contact-sheet editing, portfolio preparation, post-shoot review, and learning why one frame succeeds more than a nearby alternative.

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
DSCF0123.jpg — 84/100
Strength: The crossing gestures create a clear human relationship and hold the frame together.
Weakness: A bright shape at the right edge competes with the main interaction.
Improvement: Reframe slightly earlier or crop the right edge to protect the visual hierarchy.
Confidence: High
```

With multiple photographs, the skill can also return a ranked list, a top-N selection, or only the photographs that clear a requested threshold. It does not invent titles or submission metadata unless the user explicitly asks for a separate task.

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
