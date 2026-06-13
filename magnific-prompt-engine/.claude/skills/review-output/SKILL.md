---
name: review-output
description: Review manually generated Magnific outputs and update review-notes.md or selected-prompts.md.
disable-model-invocation: true
---

# /review-output — Review Magnific Outputs

## Purpose
Convert rough user feedback into structured review-notes.md entries, and save approved prompts to selected-prompts.md after user approval.

## When to Use
- User says `/review-output product-runs/[product-name]`
- User says "review this output" or "save this as selected"

## Required Inputs
- User's observed failure description or approval
- Product run folder: review-notes.md, selected-prompts.md

## Allowed Actions
- Format user feedback into structured review entries
- Mark APPROVE / REVISE / REJECT with failure type
- Check product accuracy, campaign fit, visual claim safety
- Append review entries to `review-notes.md`
- Save to `selected-prompts.md` only after explicit user approval

## Forbidden Actions
- Generate a new full prompt pack
- Modify system files
- Invent observations the user did not provide
- Save prompts as selected without user approval

## Required Sequence
1. Read current `review-notes.md`
2. Ask user for prompt name, output observations
3. Apply Review Decision Table
4. Check product accuracy: shape, color, logo/label, packaging, text
5. Check campaign fit: strategy lock, creative direction, asset role, platform
6. Check visual claim safety: implied certifications, medical claims, etc.
7. Classify failure type from taxonomy
8. Write structured review entry
9. If APPROVE and user confirms, save to `selected-prompts.md`

## Output Files
- `product-runs/[product-name]/review-notes.md` (appended)
- `product-runs/[product-name]/selected-prompts.md` (appended, after approval only)