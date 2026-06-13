# Changelog

## v6.6.2 — 2026-06-12

### Fixed (audit-driven)
- Troubleshooting table now mentions `.claude/settings.json` and missing SKILL.md as root causes for "Command not found" and "Skill doesn't activate"
- Acceptance checklist converted from flat checkboxes to `[PASS]`/`[FAIL]` status-prefixed format with protection disclosure
- Tree Lock no longer claims "exactly this structure" — now "Required minimum structure" with documented approved exceptions (`graphify-out/`, additional product runs, test files)
- `instructions.md` Rule 00: removed bootstrap "After downloading this file" language — clean file placement rule
- `instructions.md`: added Superpowers Preflight Rule (submodule check before workflows)
- Output schema: split single evidence level into Text Evidence Level + Visual Evidence Level with definitions
- Output schema: added LOW Confidence Text Behavior rule — short anchor only in final prompts, full text reserved for post-processing
- Output schema: Technical Draft Negative Prompt limited to 15 terms (was unconstrained); Final `--neg` remains 5–10 terms
- Root README: `/run-product-campaign` now documented as a two-state command (scaffold vs generate)
- BIONA prompt pack: replaced long exact label text in final LOW-confidence prompts with short anchor text
- Added `product-runs/example-product/run-status.md` as optional status manifest schema template
- README and acceptance checklist now include explicit protection disclosure: "policy-enforced by Claude Code instructions and plan mode only"

### Known Unresolved
- No executable hook guard for protected files (policy-only enforcement — adequate for current use)
- Product pack evidence levels use single score in generated packs — text/visual split applied to schema but existing packs not retrofitted
- No `run-status.md` manifests exist for real product runs yet (example-product template added but biona/iphone/hallucination-test not populated)
- All `review-notes.md` and `selected-prompts.md` files across product runs are empty templates — no Magnific testing completed

## v6.6.1 — 2026-06-12

### Fixed
- Root README: resolved conflicting working-directory instruction ("repo root" → "magnific-prompt-engine/")
- Root README: diagram `input.md` path now includes `product-runs/product-name/` prefix
- Root README: quickstart now explains scaffolding-and-stop behavior
- Root README: added diagram-to-command mapping after mermaid flowchart
- Nested README: consolidated 4 onboarding sections into 2 ("Start Here" + "Quickstart")
- Nested README: folder structure tree now includes all 4 product runs, `tests/`, and `graphify-out/`
- Nested README: added Testing section documenting hallucination pressure test
- Nested README: added Troubleshooting table with common error states
- Nested README: simplified "How to Paste into Magnific" instructions
- Nested README: rephrased "Do not edit" section to "Read these to understand the system"

### Added
- Testing section documenting hallucination pressure test
- Troubleshooting section with error-state guidance
- CHANGELOG.md for version history