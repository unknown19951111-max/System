# 04 — Review and Revision

## Review Decision Table

### APPROVE

Use when:
- Product identity is preserved
- Product shape is correct
- Packaging is correct
- Logo/label placement is correct
- Campaign direction is matched
- Asset role is fulfilled
- Visual quality is commercially usable
- No unsupported claims appear
- No visual claim implication appears

### REVISE

Use when:
- Output is close but needs correction
- One controllable issue exists
- No fake claim appears
- No severe identity distortion appears
- Campaign direction is mostly intact

### REJECT

Use when:
- Product identity changed
- Product shape changed
- Logo or label is wrong
- Packaging is warped
- Fake text appears
- Unsupported claim appears
- Visual claim implication appears
- Video morphs
- Video flickers severely
- Product changes across frames
- Output contradicts campaign strategy

## Revision Failure Taxonomy

When reviewing an output, classify the failure type before revising:

1. **Product distortion**
2. **Logo/label issue**
3. **Fake text**
4. **Packaging error**
5. **Unsupported claim**
6. **Visual claim implication**
7. **Bad composition**
8. **Lighting/style mismatch**
9. **Material/reflection mismatch**
10. **Background/prop issue**
11. **Campaign direction mismatch**
12. **Platform usability issue**
13. **Motion instability**
14. **Continuity failure**
15. **Other**

## Revision Isolation Rule

Each revision prompt must change one failure type only.

Do not change:
- Product identity
- Campaign angle
- Platform
- Product claims
- Core composition unless composition is the failed variable

Do not introduce new props unless the failed variable is props/background.

Do not rewrite the whole prompt if a targeted correction is sufficient.

## Prompt Revision Evidence Rule

Before revising a failed prompt, require at least one of:
- User description of the failure
- Screenshot reference
- `review-notes.md` entry
- Specific failure type selected by the user

If none is provided, ask for the observed failure before revising.

## Required Revision Sequence

1. Identify observed failure
2. Map failure to the Revision Failure Taxonomy
3. Identify likely prompt cause — check both the Technical Draft and the Model Optimization Layer
4. Revise one variable only — if the Model Optimization Layer has wrong weights or missing syntax, fix that before changing the Technical Draft
5. Preserve Product Accuracy Lock
6. Preserve Claims Registry
7. Preserve Campaign Strategy Lock unless campaign direction caused the failure
8. Preserve Creative Direction Lock unless creative direction caused the failure
9. Append the revision prompt to `review-notes.md`

### Revision and Model Optimization

When a prompt fails in generation and the failure is structural (bad composition, lighting mismatch, motion instability), the revision should first check:

- Are quality anchors present and ordered correctly?
- Are weighted terms at the right priority (P1-P3)?
- For video: Is temporal segmentation present and duration-appropriate?
- Is the embedded negative targeting the right failure mode?

If the Model Optimization Layer is incomplete or incorrect, revise it before revising the Technical Draft.

## Revision Storage Rule

Revision prompts generated after review must be appended to:
`product-runs/[product-name]/review-notes.md`

If the revised prompt becomes successful, copy the final approved prompt into:
`product-runs/[product-name]/selected-prompts.md`

## Manual Review Loop

For each Magnific output:

1. Name the prompt used
2. Mark **APPROVE**, **REVISE**, or **REJECT**
3. Select the failure type
4. Write one sentence explaining the issue
5. If REVISE, ask Claude Code for a targeted revision prompt
6. Append the revision prompt to `review-notes.md`
7. If APPROVE, save the prompt to `selected-prompts.md`

## Review Notes Schema

`review-notes.md` must use this structure:

```markdown
# Review Notes

Product:
Date:
Magnific Model:
Prompt Name:
Output ID / Screenshot Reference:
Decision: APPROVE / REVISE / REJECT

## Product Accuracy
Shape:
Color:
Logo/Label:
Packaging:
Text:

## Campaign Fit
Matches Campaign Strategy Lock:
Matches Creative Direction Lock:
Matches Asset Role:
Platform Usable:

## Visual Claim Safety
Does the output imply unverified certification?
Does the output imply medical/scientific validation?
Does the output imply sustainability?
Does the output imply customer review/testimonial?
Does the output imply performance results?

## Failure Type
- Product distortion
- Logo/label issue
- Fake text
- Packaging error
- Unsupported claim
- Visual claim implication
- Bad composition
- Lighting/style mismatch
- Material/reflection mismatch
- Background/prop issue
- Campaign direction mismatch
- Platform usability issue
- Motion instability
- Continuity failure
- Other

## Revision Prompt Log
Prompt Name:
Failure Type:
Revision Prompt:
Result:

## Next Action
Approve:
Revise With Prompt:
Reject:
```

## Selected Prompts Schema

`selected-prompts.md` must use this structure:

```markdown
# Selected Prompts

Product:
Campaign:
Date:
Model:
Prompt Type:
Final Prompt:
Reason Selected:
Magnific Output Reference:
Known Strengths:
Known Weaknesses:
Reuse Notes:
```

## Selected Prompt Qualification Rule

A prompt may be saved to `selected-prompts.md` only if:
- Output was marked **APPROVE**
- Product identity was preserved
- No fake claims appeared
- No visual claim implication appeared
- Campaign direction was matched
- User chose it as reusable

## Selected Prompt Reuse Rule

When creating a new prompt pack, Claude Code may review `selected-prompts.md` from the same product run or prior approved runs only if the user provides or approves them as references.

Do not automatically copy old prompts. Use selected prompts only as style/pattern references.

## Visual Claim Safety

Do not use environments, props, people, symbols, badges, or scenes that imply unverified claims.

Examples of visual claim implications:
- Lab setting can imply scientific or medical validation
- Recycling symbols can imply sustainability
- Doctor or white coat can imply medical approval
- Athlete performance scene can imply performance benefit
- Award badges can imply certification or ranking
- Before/after framing can imply proven results
- Testimonial framing can imply customer review evidence

If the claim is not verified, do not imply it visually.