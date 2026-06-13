---
name: revise-prompt
description: Create targeted revision prompts from a documented Magnific output failure.
disable-model-invocation: true
---

# /revise-prompt — Revise a Failed Prompt

## Purpose
Create targeted, single-variable revision prompts for Magnific outputs that failed review. Appends revision to review-notes.md.

## When to Use
- User says `/revise-prompt product-runs/[product-name]`
- User says "revise this prompt" or "fix this failure"

## Required Inputs
- Failure evidence: user description, screenshot, review-notes.md entry, or failure type
- `review-notes.md` from the product run

## Allowed Actions
- Diagnose failure using Revision Failure Taxonomy
- Create a single-variable revision prompt
- Append revision to `review-notes.md`

## Forbidden Actions
- Modify system files
- Create a full new prompt pack (unless user explicitly requests rerun)
- Rewrite the entire prompt globally (unless user approves)
- Change product identity, campaign angle, platform, or claims

## Required Sequence
1. Read review-notes.md for failure context
2. Require failure evidence (user description, screenshot, or review entry)
3. Map failure to Revision Failure Taxonomy
4. Identify likely prompt cause
5. Revise one variable only
6. Preserve Product Accuracy Lock
7. Preserve Claims Registry
8. Preserve Campaign Strategy Lock (unless it caused the failure)
9. Preserve Creative Direction Lock (unless it caused the failure)
10. Append revision prompt to `review-notes.md`

## Output Files
- `product-runs/[product-name]/review-notes.md` (appended with revision)