# 01 — Master Prompt Engine Runtime Sequence

This file defines the exact runtime sequence for generating campaign-aware prompt packs.

## Runtime Sequence

1. **Classify the request** using the Workflow Routing Rule.
2. **Read product input** from `product-runs/[product-name]/input.md`.
3. **Classify product evidence level** (0-3).
4. **Extract verified facts, inferences, and unknowns** from product evidence.
5. **Apply Field Confidence Tags** (`[VERIFIED]`, `[USER-PROVIDED]`, `[INFERRED]`, `[UNKNOWN]`).
6. **Create Product Accuracy Lock** with required fields.
7. **Create Claims Registry** with allowed, forbidden, and unknown claims.
8. **Create Campaign Strategy Lock** with field confidence tags.
9. **Create Creative Direction Lock** with visual direction and constraints.
10. **Create Campaign Intent Matrix** with asset-specific table rows.
11. **Create Technical Visual Direction Layer** with global direction and per-asset adjustments.
12. **Apply Model Optimization Layer** to each image prompt — add weighted syntax, quality anchors, integrated negatives, and aspect ratio parameters per the Image Prompt Schema.
13. **Apply Model Optimization Layer** to each video prompt — add temporal segmentation, camera-control syntax, motion weighting, and duration-specific structure per the Video Prompt Schema.
14. **Generate section-specific image prompts** (Nano Banana 2) with the Model Optimization Layer embedded.
15. **Generate section-specific video prompts** (Kling 2.5) with the Model Optimization Layer embedded.
16. **Generate negative prompts** (exactly 5 reference categories, plus per-prompt embedded negatives).
17. **Generate controlled variations** (exactly 12).
18. **Run Prompt Quality Scorecard** — evaluate each prompt on Structure, Safety, and Completeness. Mark `[STRUCTURAL]` vs `[UNTESTED]` checks. Repair FAIL items before output.
19. **PASS/CONCERN/FAIL status** and **Text Confidence / Motion Confidence** on each prompt.
20. **Generate revision prompts** (exactly 5).
21. **Refuse to invent unsupported facts or claims.**

## Core Chain

Every prompt must follow this chain:

```
Product Truth
→ Claims Registry
→ Campaign Strategy
→ Creative Direction
→ Technical Visual Direction
→ Model Optimization Layer
→ Prompt Quality Scorecard
→ Manual Review
```

## Field Confidence Tags

All campaign and product interpretation fields must use one of these tags:

- `[VERIFIED]` — directly visible in product evidence
- `[USER-PROVIDED]` — explicitly stated by the user
- `[INFERRED]` — reasonable marketing inference
- `[UNKNOWN]` — missing or unverified

## Unknown Propagation

Any detail marked `UNKNOWN` must not appear as a factual detail in prompts. Use generic descriptions only.

## Product Evidence Levels

| Level | Description | Action |
|---|---|---|
| 0 — No Evidence | No product info | Stop; request evidence |
| 1 — Rough Text Only | Partial text description | Partial prompt pack; mark unknowns |
| 2 — Image or Detailed Description | Visual or detailed text | Normal prompt pack |
| 3 — Image + Brand Notes | Full evidence with branding | Full prompt pack; still mark unknowns |

## Contract Hierarchy

1. `instructions.md` is the build contract
2. `CLAUDE.md` is persistent project memory
3. Numbered markdown files are system artifacts
4. `product-runs/` files are examples or run outputs

If any file conflicts with `instructions.md`, `instructions.md` wins.