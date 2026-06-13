# Magnific Prompt Engine v6.6.1

## Start Here

**Most users only touch:**

1. `product-runs/[product-name]/input.md` — paste product info here
2. `product-runs/[product-name]/prompt-pack.md` — copy prompts from here
3. `product-runs/[product-name]/review-notes.md` — track review results
4. `product-runs/[product-name]/selected-prompts.md` — save winning prompts

**Do not edit unless improving the system:**
- `instructions.md`
- `CLAUDE.md`
- `.claude/settings.json`
- `.claude/skills/`
- numbered system files

## What This Is

A **deterministic workflow and schema-guided prompt-pack builder** for generating campaign-aware, copy-paste-ready prompts for manual use in Magnific.

## What This Is Not

- ❌ NOT an automation tool — you paste prompts manually
- ❌ NOT a Magnific API — no integration, no Spaces automation
- ❌ NOT a visual generator — it only creates text prompts
- ❌ NOT a quality guarantee — Magnific outputs vary; you review them

## New User Only Needs This

```
1. /run-product-campaign [product-name]
2. product-runs/[product-name]/input.md
3. product-runs/[product-name]/prompt-pack.md
4. /review-output product-runs/[product-name]
5. /revise-prompt product-runs/[product-name] when needed
6. product-runs/[product-name]/selected-prompts.md

Do not edit system files unless improving the system.
```

## Supported Lanes

| Lane | Model | Prompt Type |
|---|---|---|
| Image | Nano Banana 2 | Copy-paste image prompts |
| Video | Kling 2.5 | Copy-paste video prompts |

## Project Skills

| Command | Action |
|---|---|
| `/build-system` | Build or verify the system |
| `/build-system --check` | Read-only health check |
| `/run-product-campaign [product-name]` | Generate prompt pack from input |
| `/review-output product-runs/[product-name]` | Format and track Magnific output reviews |
| `/revise-prompt product-runs/[product-name]` | Create targeted revision prompts |
| `/update-system` | Audit or patch system files |

## Manual vs Automated

| Automated by Claude Code | Manual by User |
|---|---|
| Product-run folder scaffolding | Product truth/evidence input |
| Placeholder file creation | Claim evidence confirmation |
| Input.md evidence validation | Magnific prompt pasting |
| Campaign strategy lock generation | Magnific model lane selection |
| Creative direction lock generation | Magnific generation |
| Prompt-pack generation | Visual quality judgment |
| Review-note formatting | Final output approval |
| Selected-prompt saving after user approval | Deciding when to update the system |
| Build health check | |
| Protected system file approval prompts | |

## Folder Structure

```
magnific-prompt-engine/
├── CLAUDE.md
├── README.md
├── instructions.md
├── 01_MASTER_PROMPT_ENGINE.md
├── 02_PRODUCT_INPUT_TEMPLATE.md
├── 03_OUTPUT_SCHEMA.md
├── 04_REVIEW_AND_REVISION.md
├── .claude/
│   ├── settings.json
│   └── skills/
│       ├── build-system/SKILL.md
│       ├── run-product-campaign/SKILL.md
│       ├── review-output/SKILL.md
│       ├── revise-prompt/SKILL.md
│       └── update-system/SKILL.md
├── tests/
│   └── hallucination-pressure-test.md
└── product-runs/
    └── example-product/
        ├── input.md
        ├── campaign-strategy-lock.md
        ├── creative-direction-lock.md
        ├── prompt-pack.md
        ├── review-notes.md
        └── selected-prompts.md
```

## Quickstart: First Product Run

1. Open Claude Code in the repo root
2. Run `/run-product-campaign [product-name]`
3. If the folder does not exist, Claude Code scaffolds it and stops
4. Paste product evidence into `product-runs/[product-name]/input.md`
5. Run `/run-product-campaign [product-name]`
6. Review generated `campaign-strategy-lock.md`
7. Review generated `creative-direction-lock.md`
8. Review generated `prompt-pack.md`
9. Paste Nano Banana 2 prompts into Magnific
10. Paste Kling 2.5 prompts into Magnific
11. Run `/review-output product-runs/[product-name]` after testing outputs
12. Run `/revise-prompt product-runs/[product-name]` only when a documented failure needs targeted revision
13. Save winners in `selected-prompts.md` only after user approval

## Run One Product Campaign

```
Run one product campaign.

Use PRODUCT RUN MODE.

Invoke:

/run-product-campaign [product-name]

State A — product-run folder does not exist:

1. Normalize [product-name] to lowercase kebab-case.
2. Create product-runs/[product-name]/.
3. Create required placeholder files:
   - input.md
   - campaign-strategy-lock.md
   - creative-direction-lock.md
   - prompt-pack.md
   - review-notes.md
   - selected-prompts.md
4. Ask the user to fill input.md.
5. Stop. Do not generate prompts yet.

State B — product-run folder exists:

1. Read product-runs/[product-name]/input.md.
2. Validate Product Evidence, Important Restrictions, and Output Needed.
3. If Product Evidence is empty, placeholder-only, or too vague, stop and show the missing fields.
4. If validation passes, read:
   - CLAUDE.md
   - 01_MASTER_PROMPT_ENGINE.md
   - 02_PRODUCT_INPUT_TEMPLATE.md
   - 03_OUTPUT_SCHEMA.md
   - 04_REVIEW_AND_REVISION.md
   - product-runs/[product-name]/input.md
5. Generate:
   - product-runs/[product-name]/campaign-strategy-lock.md
   - product-runs/[product-name]/creative-direction-lock.md
   - product-runs/[product-name]/prompt-pack.md

Do not modify system files.

If target files already exist, preserve approved content and append a new version section instead of overwriting.

Generate product-runs/[product-name]/prompt-pack.md containing, in this exact order:

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

Follow:
- Product Accuracy Lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- Output Schema
- Review Rules
```

## How to Paste into Magnific

1. Open Magnific in your browser
2. Select the correct model lane (Nano Banana 2 or Kling 2.5)
3. Copy the **Final Copy-Paste Prompt** from `prompt-pack.md`
4. Paste into Magnific's prompt field
5. Generate and download the output
6. Name the output file with the prompt name for tracking

## Manual Review Loop

For each Magnific output:
1. Name the prompt used
2. Mark **APPROVE**, **REVISE**, or **REJECT**
3. Select the failure type
4. Write one sentence explaining the issue
5. If REVISE, run `/revise-prompt` for a targeted revision
6. If APPROVE, run `/review-output` to save to selected-prompts.md

## How to Save Selected Prompts

After a prompt output is approved:
1. Run `/review-output product-runs/[product-name]`
2. Confirm the prompt name and output reference
3. Use approval wording: `Approve this output and save it.`
4. The prompt will be saved to `selected-prompts.md`

## How to Inspect Permissions

To inspect project permissions, run:

```
/permissions

Confirm:
- default mode is plan
- protected system files require approval before edits
- product-runs/ is the normal write area during product runs
```

## Constraints

- Only Nano Banana 2 (image) and Kling 2.5 (video) are supported
- No people or hands by default
- No fake claims, fake text, or invented product facts
- UNKNOWN details must not be presented as factual
- Manual review is always the final quality gate
- Claims Registry must be obeyed by every prompt

## No Guarantees Statement

This system generates prompts for manual copying into Magnific. It does not guarantee Magnific output quality, model behavior, or campaign results. Generated prompts are never equivalent to approved visuals. Manual review is the final quality gate.