# Magnific Prompt Engine — Project Memory

## Project Identity

**Magnific Prompt Engine v6.6.1 — Campaign-Aware Technical Prompt System**

A markdown-first, deterministic-workflow prompt-pack builder for manual use in Magnific (Nano Banana 2 for images, Kling 2.5 for video). Claude Code generates campaign-aware prompt packs; the user copies them into Magnific, generates visuals, reviews, and selects winners.

## Operating Model

```
Claude Code = workflow-routed, schema-guided campaign-aware prompt-pack builder
instructions.md = build contract
README.md = user control panel
.claude/skills/ = local project workflows
Nano Banana 2 = image prompt lane
Kling 2.5 = video prompt lane
Magnific = manual generation platform
User = final reviewer and selector
```

## Allowed Model Lanes

1. **Nano Banana 2** — image prompts
2. **Kling 2.5** — video prompts

No fallback models. No alternative models. No model comparisons.

## Forbidden Defaults

- MCP integration
- Magnific Agents
- Spaces automation
- CLI, web app, API, database
- Shell scripts, automation code, plugin packaging
- Other image/video models (Runway, Veo, Sora, Midjourney, Flux, Seedance)
- Audio, 3D, or stock tools

## Core Workflow Flow

```
Product Truth → Claims Registry → Campaign Strategy → Creative Direction → Technical Visual Direction → Model Optimization Layer → Prompt Quality Scorecard → Manual Review
```

## BUILD MODE vs PRODUCT RUN MODE

**BUILD MODE**: Create or update system files. Requires `Approved. Build it.` approval. No real product prompts.

**PRODUCT RUN MODE**: Generate product-run files from user input. Do not modify system files.

## Workflow Routing Rule

Classify every request into one route:
- `BUILD_MODE_SYSTEM_CREATION` → `/build-system`
- `PRODUCT_RUN_FULL_PACK` → `/run-product-campaign`
- `PRODUCT_RUN_IMAGE_ONLY` → `/run-product-campaign` with Output Needed: image-only
- `PRODUCT_RUN_VIDEO_ONLY` → `/run-product-campaign` with Output Needed: video-only
- `PROMPT_REVISION` → `/revise-prompt`
- `OUTPUT_REVIEW` → `/review-output`
- `SELECTED_PROMPT_LIBRARY_UPDATE` → `/review-output` or `/run-product-campaign`
- `SYSTEM_AUDIT` → `/update-system` (audit-only)
- `SYSTEM_UPDATE` → `/update-system`

## Completion Claim Rule

Allowed: `Prompt pack generated and ready for manual Magnific testing.`
Forbidden: `production-ready`, `guaranteed accurate`, `campaign complete`, `approved prompt`, `claim-safe output`

## System Update Anti-Slop Rule

Only implement changes that satisfy ALL:
1. Issue is verified
2. Affected file/rule is identified
3. Solution is scoped to the issue
4. No unsupported models/automation/plugins added
5. Improves wiring, usability, accuracy, reviewability, or prompt quality
6. Does not duplicate an existing rule
7. Output remains markdown-first and manual-Magnific compatible

## Project Skills

Use project skills before repeated workflows. Do not carry long operational procedures inside this file.

- `/build-system` — BUILD MODE, health check
- `/run-product-campaign` — prompt-pack generation
- `/review-output` — manual review formatting
- `/revise-prompt` — targeted revision
- `/update-system` — audit and patch

## Manual Review

Manual review is always the final quality gate. Generated prompts are never equivalent to approved visuals.