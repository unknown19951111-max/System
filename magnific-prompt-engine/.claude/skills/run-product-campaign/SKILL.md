---
name: run-product-campaign
description: Generate one campaign-aware Magnific prompt pack from product-runs/[product-name]/input.md.
disable-model-invocation: true
---

# /run-product-campaign — Generate a Prompt Pack

## Purpose
Generate a full campaign-aware prompt pack from product input. Supports two states (scaffolding and generation).

## When to Use
- User says `/run-product-campaign [product-name]`
- User says "generate a prompt pack" or "run a campaign"

## Required Inputs
- `product-runs/[product-name]/input.md` — product evidence and campaign info
- System files: CLAUDE.md, 01-04 numbered files, 03_OUTPUT_SCHEMA.md

## Allowed Actions

### State A — Folder Does Not Exist
1. Normalize product name to lowercase kebab-case
2. Create `product-runs/[product-name]/` with 6 placeholder files
3. Ask user to fill `input.md`
4. Stop — do not generate prompts

### State B — Folder Exists + Valid input.md
1. Validate Product Evidence, Important Restrictions, Output Needed
2. If validation fails, stop and show missing fields
3. Read system files and input.md
4. Generate `campaign-strategy-lock.md`
5. Generate `creative-direction-lock.md`
6. Generate `prompt-pack.md` with all 17 sections

## Forbidden Actions
- Modify system files
- Overwrite approved content silently (use version append)
- Generate prompts without validated input.md
- Review or revise tested Magnific outputs

## Output Files
- `product-runs/[product-name]/campaign-strategy-lock.md`
- `product-runs/[product-name]/creative-direction-lock.md`
- `product-runs/[product-name]/prompt-pack.md`

## Output Schema Order (prompt-pack.md)
1. Prompt Pack Metadata
2. Product Evidence Level
3. Verified Product Facts
4. Reasonable Marketing Inferences
5. Unknown / Do Not Assume
6. Product Accuracy Lock
7. Claims Registry
8. Campaign Strategy Summary
9. Creative Direction Summary
10. Campaign Intent Matrix
11. Technical Visual Direction Layer
12. Nano Banana 2 Image Prompt Pack
13. Kling 2.5 Video Prompt Pack
14. Negative Prompt Pack
15. Controlled Variation Matrix
16. Prompt Quality Scorecard
17. Revision Prompts