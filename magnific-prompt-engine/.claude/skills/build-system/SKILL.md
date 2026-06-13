---
name: build-system
description: Build or update the Magnific Prompt Engine markdown system after the user approves the build plan.
disable-model-invocation: true
---

# /build-system — Build or Verify the System

## Purpose
Create the Magnific Prompt Engine system files in BUILD MODE, or run a read-only health check.

## When to Use
- User says `/build-system` — build the system
- User says `/build-system --check` — run health check
- User says "build the system" or "check the system"

## Required Inputs
- `instructions.md` — the build contract
- `CLAUDE.md` — project memory
- README.md, numbered system files, skill files, hallucination test, example product files

## Allowed Actions

### BUILD MODE
- Create or update system files (CLAUDE.md, README.md, numbered files, skills, settings, tests)
- Follow Implementation Gate: output plan, wait for `Approved. Build it.`
- Superpowers brainstorming required before build planning

### Health Check Mode (`--check`)
- Verify required files exist
- Verify SKILL.md frontmatter
- Verify `.claude/settings.json` validity
- Verify no forbidden file types exist
- Verify output schema consistency
- Report PASS / FAIL / NEEDS USER DECISION

## Forbidden Actions
- Generate real product prompts
- Run a product campaign
- Modify product-run outputs (except placeholders)

## Required Sequence (BUILD MODE)
1. Read `instructions.md`
2. Invoke Superpowers brainstorming skill
3. Output build plan (Implementation Gate — 10 items)
4. Wait for `Approved. Build it.`
5. Create files per repo tree lock
6. Run Markdown Build Verification Rule

## Output Files
- CLAUDE.md, README.md, instructions.md
- 01_MASTER_PROMPT_ENGINE.md, 02_PRODUCT_INPUT_TEMPLATE.md, 03_OUTPUT_SCHEMA.md, 04_REVIEW_AND_REVISION.md, 05_ACCEPTANCE_CHECKLIST.md
- `.claude/settings.json`
- `.claude/skills/*/SKILL.md` (5 skills)
- `product-runs/example-product/*` (6 placeholder files)

## Verification Checklist
Before claiming build complete, verify:
1. Required repo tree exists
2. Only approved `.md` files exist
3. No forbidden file types exist
4. Every required file is present
5. `instructions.md` exists at repo root
6. `03_OUTPUT_SCHEMA.md` includes full templates
7. README includes the required exact order
8. `product-runs/example-product/` files are placeholders only
9. No unsupported model lanes are introduced
10. No automation, API, CLI, MCP, Agent integration, or Spaces automation is implemented
11. Required campaign, prompt, and review rules are present
12. `05_ACCEPTANCE_CHECKLIST.md` has been reviewed