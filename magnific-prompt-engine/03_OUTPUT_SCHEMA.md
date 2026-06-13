# 03 — Output Schema: prompt-pack.md

This file defines the exact structure of `product-runs/[product-name]/prompt-pack.md`. Every prompt pack must follow this order exactly.

## 1. Prompt Pack Metadata

```markdown
# Prompt Pack Metadata

Prompt Pack Version: 1.0
Created Date: [YYYY-MM-DD]
Product Run: [product-name]
Campaign Version: 1
Model Lane: Nano Banana 2 + Kling 2.5
Prompt Status: DRAFT / TESTED / SELECTED / RETIRED
```

### Prompt Status Lifecycle

- **DRAFT**: Generated but not tested in Magnific
- **TESTED**: Used in Magnific and reviewed
- **SELECTED**: Output approved and saved to `selected-prompts.md`
- **RETIRED**: Prompt no longer recommended due to failure or replacement

## 2. Product Evidence Level

```markdown
# Product Evidence Level

Level: [0 / 1 / 2 / 3]
Description: [brief rationale]
```

## 3. Verified Product Facts

```markdown
# Verified Product Facts

- Product type: [VERIFIED]
- Shape: [VERIFIED]
- Color(s): [VERIFIED]
- Logo placement: [VERIFIED]
- Label placement: [VERIFIED]
- Visible text: [VERIFIED]
- Packaging structure: [VERIFIED]
- Other visible details: [VERIFIED]
```

## 4. Reasonable Marketing Inferences

```markdown
# Reasonable Marketing Inferences

- Likely audience: [INFERRED]
- Likely product category: [INFERRED]
- Likely brand positioning: [INFERRED]
- Likely campaign angle: [INFERRED]
- Likely platform fit: [INFERRED]
- Likely visual style: [INFERRED]
```

## 5. Unknown / Do Not Assume

```markdown
# Unknown / Do Not Assume

- Brand name: [UNKNOWN]
- Material: [UNKNOWN]
- Capacity/size: [UNKNOWN]
- Price: [UNKNOWN]
- Claims / certifications: [UNKNOWN]
- Ingredients: [UNKNOWN]
- Technical specifications: [UNKNOWN]
- Reviews / testimonials: [UNKNOWN]
```

## 6. Product Accuracy Lock

```markdown
# Product Accuracy Lock

Product Type:
Overall Silhouette:
Primary Color:
Secondary Color:
Logo Placement:
Label Placement:
Packaging Structure:
Visible Text Handling:
Do-Not-Change Details:
UNKNOWN Details Not To Invent:
```

## 7. Claims Registry

```markdown
# Claims Registry

### Allowed Claims

- Claim:
  Source: [visible on packaging / product page / user-provided / documentation]
  Exact Wording:

### Forbidden Claims

- [list of claims that must not appear]

### Unknown Claims

- [claim categories that are unverified and must not be implied]
```

## 8. Campaign Strategy Summary

```markdown
# Campaign Strategy Summary

Campaign Objective: [VERIFIED / USER-PROVIDED / INFERRED / UNKNOWN]
Target Audience: [with tag]
Buyer Emotion: [with tag]
Brand Positioning: [with tag]
Primary Message: [with tag]
Funnel Stage: [with tag]
Platform Context: [with tag]
Creative Direction Summary: [with tag]
Visual Consistency Rules: [with tag]
Do-Not-Do Rules: [with tag]
```

## 9. Creative Direction Summary

```markdown
# Creative Direction Summary

Visual Style: [with tag]
Lighting Family: [with tag]
Color Palette: [with tag]
Camera Language: [with tag]
Environment Family: [with tag]
Surface / Set Direction: [with tag]
Prop Policy: [with tag]
Human Policy: [with tag]
Composition Rules: [with tag]
Motion Style: [with tag] (video only)
Consistency Rules: [with tag]
Forbidden Style Drift: [with tag]
```

## 10. Campaign Intent Matrix

```markdown
# Campaign Intent Matrix

| Asset | Campaign Role | Funnel Stage | Buyer Emotion | Visual Strategy | Platform Use | Prompt Priority | Primary Risk | Success Criteria |
|---|---|---|---|---|---|---|---|---|
| Product Hero Image | | | | | | | | |
| Lifestyle Product Image | | | | | | | | |
| Clean E-commerce Image | | | | | | | | |
| Paid Social Ad Base Image | | | | | | | | |
| Macro / Detail Image | | | | | | | | |
| Product Reveal Video | | | | | | | | |
| Lifestyle Use-Case Video | | | | | | | | |
| UGC-Style Product Video | | | | | | | | |
| Premium Cinematic Product Video | | | | | | | | |
| Short Social Ad Video | | | | | | | | |
```

## 11. Technical Visual Direction Layer

```markdown
# Technical Visual Direction Layer

## Global Technical Direction

### Environment Direction
-

### Lighting Direction
-

### Material / Reflection Direction
-

### Camera / Optics Direction
-

### Composition Direction
-

### Color Direction
-

### Props Direction
-

### Platform Direction
-

### Video Motion Direction
-

### Continuity Direction
-

## Per-Asset Technical Adjustments

### Product Hero Image
-

### Lifestyle Product Image
-

### Clean E-commerce Image
-

### Paid Social Ad Base Image
-

### Macro / Detail Image
-

### Product Reveal Video
-

### Lifestyle Use-Case Video
-

### UGC-Style Product Video
-

### Premium Cinematic Product Video
-

### Short Social Ad Video
-
```

## 12. Nano Banana 2 Image Prompt Pack

Each image prompt must have three layers: Technical Draft Prompt, Model Optimization Layer, and Final Copy-Paste Prompt.

### Model Optimization Rule

Every final image prompt MUST be optimized for how diffusion models interpret input:

1. **Token ordering:** Quality anchors first → subject → environment → lighting → camera → format
2. **Weighted syntax:** Use `(term:1.1)` to `(term:1.4)` weighting for critical visual elements
3. **Quality anchors:** Include 3-5 quality boosters at the prompt start (e.g., `(masterpiece:1.2)`, `(best quality:1.1)`)
4. **Integrated negative:** Append `--neg [5-10 prioritized terms]` directly to each final prompt
5. **Aspect ratio:** Include explicit `[aspect: W:H]` notation
6. **Term limit:** Keep text strings to 5 words max — long text degrades image quality
7. **Label text handling:** Use shortest anchor text only; mark long text as requiring post-processing

### Prompt Structure

```markdown
### [Prompt Name]

#### Technical Draft Prompt

1. Product Identity:
2. Product Accuracy Lock:
3. Campaign Strategy Lock:
4. Creative Direction Lock:
5. Asset Role:
6. Visual Objective:
7. Scene / Environment:
8. Lighting Design:
9. Material / Reflection Behavior:
10. Camera System:
11. Lens / Framing:
12. Composition:
13. Background Design:
14. Surface / Props Policy:
15. Color Palette / Color Accuracy:
16. Depth / Focus Behavior:
17. Brand / Label Protection:
18. Platform Format:
19. Allowed Creative Flex:
20. Forbidden Changes:
21. Negative Prompt:
22. Prompt Priority Stack:

#### Model Optimization Layer

[Quality anchors, weight assignments, and syntax decisions]

- Token Order:
- Quality Anchors:
- Integrated Negative (max 10 terms):
- Aspect Ratio Param:
- Text Rendering Strategy:

#### Final Copy-Paste Prompt

(quality anchor 1:1.2), (quality anchor 2:1.1), (quality anchor 3:1.2),
[subject description with key weighted terms],
[environment description with weighted terms],
[lighting description with weighted terms],
[camera/lens with weighted terms],
[specific visual quality directives],
[platform format: aspect ratio notation]

--neg [5-10 comma-separated prioritized terms]

Prompt Quality Status: PASS / NEEDS REVIEW / CONCERN
Text Confidence: [HIGH / MEDIUM / LOW] — note any text rendering risk
```

### Example Final Prompt Structure

```markdown
(masterpiece:1.2), (best quality:1.1), (professional commercial product photography:1.3),
a tall white cylindrical (facial spray bottle:1.2) with (white spray nozzle:1.1),
(standing on a clean white surface:1.1), (soft diffused bright studio lighting:1.3),
(85mm lens look:1.1), (shallow depth of field:1.2), (sharp focus:1.1)
--neg people, hands, text errors, distortion, medical, warm tones
[aspect: 4:5]
```

### Default Image Prompts (full pack)

1. Product Hero Image
2. Lifestyle Product Image
3. Clean E-commerce Image
4. Paid Social Ad Base Image
5. Macro / Detail Image

## 13. Kling 2.5 Video Prompt Pack

Each video prompt must have three layers: Technical Draft Prompt, Model Optimization Layer, and Final Copy-Paste Prompt.

### Video Model Optimization Rule

Every final video prompt MUST be optimized for how video diffusion models handle motion and temporal structure:

1. **Temporal segmentation:** Use `[t_start-t_end: description]` markers to structure the video sequence
2. **Camera-control syntax:** Use structured motion tokens: `(cam_orbit_left:1.3)`, `(cam_dolly_in:1.2)`, `(motion_smooth:1.4)`
3. **Motion weighting:** Weight motion-critical terms `(gentle movement:1.3)`, `(stable bottle:1.5)`
4. **Duration-aware structure:** Adapt temporal segments to the target duration — use the matrix below
5. **Integrated negative:** Append `--neg [5-10 prioritized motion-specific terms]`
6. **Start/end anchoring:** First segment defines opening frame; last segment defines end frame
7. **Product consistency:** All segments must reference identical product description

### Duration Matrix

| Duration | Structure | Segment Count | Camera Complexity |
|----------|-----------|---------------|-------------------|
| Short (3-5s) | Tighter scene, faster reveal | 2-3 segments | Single camera move |
| Medium (6-10s) | Standard temporal sequence | 3-4 segments | 2 camera moves |
| Long (11-15s) | Expanded sequence | 4-5 segments | Multiple camera moves + pause |

Default: MEDIUM (6-10s). Label variations in the Controlled Variation Matrix.

### Prompt Structure

```markdown
### [Prompt Name]

#### Technical Draft Prompt

1. Product Identity:
2. Product Accuracy Lock:
3. Campaign Strategy Lock:
4. Creative Direction Lock:
5. Asset Role:
6. Video Objective:
7. Platform Context:
8. Duration: [MEDIUM / SHORT / LONG — default MEDIUM]
9. Opening Frame:
10. Scene Setup:
11. Lighting Over Time:
12. Material / Reflection Behavior:
13. Camera Motion Design:
14. Product Motion Rules:
15. Temporal Shot Sequence:
16. Continuity Protection:
17. Focus / Depth Behavior:
18. End Frame Design:
19. Forbidden Motion Failures:
20. Negative Prompt:
21. Prompt Priority Stack:

#### Model Optimization Layer

- Duration Class:
- Temporal Segments:
- Camera Syntax Tokens:
- Motion Weighting:
- Integrated Negative (max 10 terms):

#### Final Copy-Paste Prompt

(motion_quality_token:weight), (camera_token:weight),
(consistency_token:weight), [opening scene description]

[t0-t1: temporal segment — camera control, subject action, lighting]
[t1-t2: next segment — camera transition, subject state change]
[t2-t3: final segment — end frame, settling motion]

--neg [5-10 comma-separated prioritized motion-specific terms]

Prompt Quality Status: PASS / NEEDS REVIEW / CONCERN
Duration: [SHORT / MEDIUM / LONG]
```

### Example Final Prompt Structure

```markdown
(motion_smooth:1.4), (stable_product:1.5), (consistent_label:1.3),
a white facial spray bottle on a clean white surface, soft studio lighting

[0-3s: cam_orbit_left(1.3), front view centered, label readable, bottle stationary]
[3-6s: cam_slow_pan(1.2), moving to side angle, soft reflections shift]
[6-8s: cam_hold(1.1), pause at side, bottle in sharp focus, gentle lighting]

--neg flicker, morph, label warp, shake, people, hands
Duration: MEDIUM
```

### Default Video Prompts (full pack)

1. Product Reveal Video
2. Lifestyle Use-Case Video
3. UGC-Style Product Video
4. Premium Cinematic Product Video
5. Short Social Ad Video

## 14. Negative Prompt Pack

### Negative Embedding Rule

Every final copy-paste prompt MUST include an embedded `--neg` directive with 5-10 prioritized terms. The reference negatives below are supplementary documentation. The embedded per-prompt negative is what the user copies.

### Maximum Negative Token Rule

No single negative prompt (reference or embedded) may exceed 15 comma-separated terms. Prioritize the 5-10 most impactful tokens for each specific asset. Do not create generic mega-lists.

### Per-Prompt Negative Strategy

Each asset has distinct failure modes. Tailor negatives by asset type:

- **Hero / E-commerce:** focus on product distortion, label errors, shadow issues
- **Lifestyle:** focus on people, clutter, medical cues
- **Macro / Detail:** focus on heavy spray, dripping, focus errors
- **Video:** focus on flicker, morphing, continuity breaks, shake

```markdown
# Negative Prompt Pack

### 1. Universal Reference Negative
[Supplementary — use embedded per-prompt negatives for actual generation]
[10-15 general terms covering: product distortion, unwanted elements, quality issues]

### 2. Product Accuracy Reference Negative
[Supplementary — per-prompt negative takes priority]
[10-15 terms targeting: bottle shape, label issues, packaging errors]

### 3. Text / Logo Reference Negative
[Supplementary — 10-15 terms targeting: fake text, wrong label text, font issues]

### 4. Video Motion Reference Negative
[Supplementary — 10-15 terms targeting: flicker, morphing, instability, continuity breaks]

### 5. Human / Hand Reference Negative
[NOT APPLICABLE if no people/hands]
```

## 15. Controlled Variation Matrix

```markdown
# Controlled Variation Matrix

### Lighting Variations (3)
1. [One variable change]
2. [One variable change]
3. [One variable change]

### Background Variations (3)
1. [One variable change]
2. [One variable change]
3. [One variable change]

### Camera / Composition Variations (3)
1. [One variable change]
2. [One variable change]
3. [One variable change]

### Platform Variations (3)
1. [One variable change]
2. [One variable change]
3. [One variable change]
```

## 16. Prompt Quality Scorecard

### Scorecard Integrity Rule

The scorecard must differentiate between:

- `[STRUCTURAL]` checks verified by prompt analysis (token order, weighted syntax, temporal structure)
- `[UNTESTED]` checks that require actual model generation to verify (text rendering accuracy, motion quality, label consistency)

Every prompt pack must have at least 3 `[UNTESTED]` markers acknowledging what has not been verified.

### Scoring Per Prompt

Each prompt receives a score on three dimensions:

| Dimension | PASS | CONCERN | FAIL |
|-----------|------|---------|------|
| Structure | All syntax rules followed | Minor syntax gap | Missing critical syntax |
| Safety | No claim violations | Low-risk implication | Direct claim violation |
| Completeness | All fields populated | 1-2 missing fields | Major gaps |

### Scorecard Template

```markdown
# Prompt Quality Scorecard

### Image Prompts

| Prompt | Structure | Safety | Completeness | Text Confidence | Notes |
|--------|-----------|--------|--------------|----------------|-------|
| Product Hero Image | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | HIGH/MEDIUM/LOW | [model reliability note] |
| Lifestyle Product Image | | | | | |
| Clean E-commerce Image | | | | | |
| Paid Social Ad Base Image | | | | | |
| Macro / Detail Image | | | | | |

**UNTESTED checks:** [list what requires actual generation to verify]

### Video Prompts

| Prompt | Structure | Safety | Completeness | Motion Confidence | Notes |
|--------|-----------|--------|--------------|-------------------|-------|
| Product Reveal Video | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | HIGH/MEDIUM/LOW | [model reliability note] |
| Lifestyle Use-Case Video | | | | | |
| UGC-Style Product Video | | | | | |
| Premium Cinematic Product Video | | | | | |
| Short Social Ad Video | | | | | |

**UNTESTED checks:** [list what requires actual generation to verify]
```

## 17. Revision Prompts

```markdown
# Revision Prompts

### Revision 1
Target Prompt:
Failure Type:
Revision Prompt:

### Revision 2
Target Prompt:
Failure Type:
Revision Prompt:

### Revision 3
Target Prompt:
Failure Type:
Revision Prompt:

### Revision 4
Target Prompt:
Failure Type:
Revision Prompt:

### Revision 5
Target Prompt:
Failure Type:
Revision Prompt:
```