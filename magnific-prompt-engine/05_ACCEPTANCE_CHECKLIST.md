# 05 — Acceptance Checklist

Build verification and acceptance criteria for the Magnific Prompt Engine system.

---

## Markdown Build Verification Rule

Before claiming the system build is complete, verify:

1. Required repo tree exists.
2. Only approved `.md` files exist.
3. No forbidden file types exist.
4. Every required file is present.
5. `instructions.md` exists at repo root.
6. `03_OUTPUT_SCHEMA.md` includes full templates.
7. README includes the required exact order.
8. `product-runs/example-product/` files are placeholders only.
9. No unsupported model lanes are introduced.
10. No automation, API, CLI, MCP, Agent integration, or Spaces automation is implemented.
11. Required campaign, prompt, and review rules are present.
12. This acceptance checklist has been reviewed.

Any completion claim must include the verification evidence checked.

---

> **Status key:** `[PASS]` = verified working; `[FAIL]` = issue found; `[NOT VERIFIED]` = pending user confirmation; `[N/A]` = not applicable in current state.
>
> **Protection disclosure:** System file protection is policy-enforced by Claude Code instructions and plan mode only. No executable hook guard is active in this repo.

## Build Structure Checks

- `[PASS]` `instructions.md` exists at the correct path (committed directly, no download/rename needed)
- `[PASS]` Required minimum repo tree exists (exceptions for `graphify-out/`, additional product runs, and test files are now documented)
- `[PASS]` `.claude/settings.json` exists
- `[PASS]` `.claude/settings.json` sets `permissions.defaultMode` to `plan`
- `[PASS]` `.claude/skills/` project skills exist (5 skill files verified)
- `[PASS]` Every SKILL.md has required YAML frontmatter
- `[PASS]` Every operational skill has `disable-model-invocation: true`
- `[PASS]` No skill grants broad `allowed-tools` by default
- `[PASS]` Skill body concision rule exists
- `[PASS]` Skill responsibility boundary rule exists
- `[PASS]` Only `.md` files exist except `.claude/settings.json`
- `[PASS]` No non-approved folders exist (all exceptions documented: `graphify-out/`, additional product runs, additional test files)
- `[PASS]` Artifact Routing Map is followed
- `[PASS]` Dedicated files and prompt-pack sections are correctly routed
- `[PASS]` BUILD MODE and PRODUCT RUN MODE are defined
- `[PASS]` Fast Mode Boundary Rule exists
- `[PASS]` Superpowers Skill Invocation Rule exists
- `[PASS]` Superpowers Order Rule exists
- `[PASS]` Superpowers Preflight Rule exists (submodule check before workflows)
- `[PASS]` Clarification After Skill Rule exists
- `[PASS]` Workflow Routing Rule exists
- `[PASS]` Fast Mode and Controlled Mode are defined
- `[PASS]` System files are protected during product runs
- `[PASS]` Protected System File Approval Rule exists
- `[PASS]` Permission-first protected-file behavior exists
- `[PASS]` Hook language correctly discloses policy-only enforcement (no hook scripts present)
- `[PASS]` Optional PreToolUse Hook Target Rule is documented as future-only
- `[PASS]` Hook Handler Decision Rule confirms no default hook scripts
- `[PASS]` No executable hook scripts exist unless separately approved

## Scope Checks

- No CLI/API/app/database files exist
- No plugin packaging exists
- No subagents exist
- No MCP servers exist
- No MCP integration exists
- No Magnific Agent integration exists
- No Workflow App or Flow logic exists
- No Spaces automation exists
- Only Nano Banana 2 and Kling 2.5 are supported
- No fallback models are included
- No auto mode is configured
- Unlimited-eligible actions are not claimed without user confirmation

## Product Truth and Claim Safety Checks

- Product evidence levels are defined
- Product image evidence handling is defined
- Field Confidence Tags are required
- UNKNOWN propagation is enforced
- Material Handling Rule exists
- Inferences are contained
- Claims Registry exists and appears after Product Accuracy Lock
- Claim source tagging exists
- Visual Claim Implication Rule exists
- Product Accuracy Lock has required fields
- Product Accuracy Lock and Claims Registry are permanent top-level sections

## Campaign Layer Checks

- Campaign Strategy Lock exists
- Creative Direction Lock exists
- Creative Direction Priority Rule exists
- Campaign Intent Matrix exists with table format
- Campaign Intent Matrix rows must be asset-specific
- Technical Visual Direction Layer exists with global direction and per-asset adjustments
- Campaign summaries appear inside `prompt-pack.md`
- Prompts support asset roles

## Prompt Engineering Checks

- Image Technical Prompt Schema exists
- Video Technical Prompt Schema exists
- Technical Draft Prompt + Model Optimization Layer + Final Copy-Paste Prompt three-layer split exists
- Video Duration Class Rule exists (SHORT / MEDIUM / LONG with Duration Matrix)
- Camera and Lens Language Rule exists
- Prompt Priority Stack exists
- Model Optimization Layer rules exist (weighted syntax, temporal segmentation, camera tokens)
- Maximum Negative Token Rule exists (15 terms max per negative)
- Embedded `--neg` directive rule exists (5-10 terms per final prompt)
- Scorecard Integrity Rule exists ([STRUCTURAL] vs [UNTESTED] differentiation)
- Prompt Quality Scorecard exists with scored evaluation matrix
- Per-prompt Prompt Quality Status exists (PASS / CONCERN / FAIL)
- Text Confidence annotation exists (HIGH / MEDIUM / LOW)
- Repair Note rule exists
- Scorecard failure behavior repairs prompts before output
- Scorecard visibility is required in `prompt-pack.md`
- Exactly 5 image prompts are required for a full pack
- Exactly 5 video prompts are required for a full pack
- Exactly 5 negative prompt categories are required
- Exactly 12 variations are required for a full pack
- Exactly 5 revision prompts are required
- Image-only and video-only exceptions are defined with `NOT REQUESTED` handling

## Review Workflow Checks

- Human/hands are excluded by default
- No-person UGC-style is clearly defined
- UGC-style excludes fake testimonials
- Review decision table exists
- Revision Failure Taxonomy exists
- Revision Isolation Rule exists
- Revision Storage Rule exists
- Manual Review Loop exists
- Review Notes Schema includes Visual Claim Safety
- Review Formatting Automation Rule exists
- Selected Prompts Schema exists
- Selected Prompt Save Automation Rule exists
- Selected Prompt Qualification Rule exists
- Selected Prompt Reuse Rule exists
- Prompt Failure Debugging Rule exists
- Prompt Revision Evidence Rule exists
- Revision prompts are appended to `review-notes.md`
- Approved selected prompts are copied to `selected-prompts.md`

## Runtime Safety Checks

- Overwrite Safety Rule exists
- Existing product-run files are not silently overwritten
- Prompt Status Lifecycle exists
- Product-run content cannot leak into system files
- Product-run outputs stay inside `product-runs/[product-name]/`
- Completion Claim Rule exists
- Markdown Build Verification Rule exists
- System Update Anti-Slop Rule
- Use project skills before repeated workflows
- Do not carry long operational procedures inside CLAUDE.md exists
- Core-Fit Gate exists
- System Update Patch Approval Rule exists
- SYSTEM_UPDATE Gate Rule exists
- Settings JSON Boundary Rule exists
- Superpowers vs Project Skills Boundary exists

## New User Usability Checks

- Product Run Command exists
- `/run-product-campaign [product-name]` scaffolding behavior exists
- input.md evidence validation exists
- Project skills are documented in README
- README quickstart uses direct slash skill commands
- Product Run Naming Rule exists
- Prompt Pack Metadata exists
- Example product files are placeholders only
- Hallucination pressure test
- Local Claude Code project skills under `.claude/skills/`
- `.claude/settings.json` for one protected-file edit guard exists
- README is operational, not marketing copy
- README includes exact required order
- README includes Start Here
- README includes Responsibility Split table
- README includes `/permissions` inspection step
- README includes Quickstart: First Product Run
- README includes Run One Product Campaign copy-paste command block
- Manual review remains the final quality gate