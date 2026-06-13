# Product Run Input

Copy this template into `product-runs/[product-name]/input.md` and fill in every section.

```markdown
Product Evidence:
[Product image description, product page, product listing, packaging notes, or attached-image notes]

Known Product Info:
[Optional. Brand name, product name, category, etc.]

Campaign Objective:
[Optional. If missing, infer and label as inference.]

Target Audience:
[Optional]

Buyer Emotion:
[Optional]

Brand Positioning:
[Optional]

Platform:
[Optional. If missing, recommend and label as inference.]

Creative Direction:
[Optional. Visual style, mood, composition preferences.]

Important Restrictions:
[No hands, no people, no fake claims, no invented brand name, etc.]

Allowed Claims:
- Claim:
  Source:
  Exact Wording:

Forbidden Claims:
[Optional user restrictions]

Output Needed:
[Full pack by default: Nano Banana 2 images + Kling 2.5 videos]
[Or image-only / video-only]
```

## Required Minimum Fields

Before any prompt pack can be generated, the following fields must be non-empty and specific:

1. **Product Evidence** — must contain actual product description, not placeholder text
2. **Important Restrictions** — must list at least one restriction
3. **Output Needed** — must state what output is required

## Product Image Evidence

Product images may be:
1. Described manually in `input.md`
2. Referenced by local path if images are stored outside the repo
3. Attached directly to Claude Code session if supported

If image details are not visible, mark them `UNKNOWN` in the prompt pack.