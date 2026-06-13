# README Audit Repair — Design Document

**Date:** 2026-06-12  
**Status:** Approved design, ready for implementation planning

## Problem

The workspace READMEs score ~6/10 on professionalism. The main issues are:
- Root README is too thin (no purpose, flow, or boundaries)
- Nested README explains files before explaining the system
- No system diagram, no Input/Output Contract, no Accuracy Model, no Example Run
- Commands are overloaded before new users understand the happy path
- Manual vs Automated table is buried too deep
- Root and nested READMEs disagree on where to open Claude Code

## Design Overview

### Root README — Full Replacement

Replace the minimal root README with a professional landing page containing:
- Title and system description
- Directory table with roles
- Mermaid system-flow diagram
- Quick Start (6 steps)
- Important Boundary statement (text prompts only)
- Submodules command

## Nested README — Restructured with New Sections

The new section order (replacing the locked order in instructions.md Section 81):

1.  **What This Is** — system identity
2.  **What This Is Not** — boundaries
3.  **How the System Works** — Mermaid diagram (NEW)
4.  **Input and Output Contract** — file purpose table (NEW)
5.  **Accuracy Model** — Verified facts / Inferences / Unknowns (NEW)
6.  **Start Here** — files users touch
7.  **New User Only Needs This** — 6-step quickstart
8.  **Responsibility Split** — renamed from Manual vs Automated, with "Claude Code Handles" / "User Handles" headers
9.  **Supported Lanes** — model lanes table
10. **Example Run** — concrete fake product walkthrough (NEW)
11. **Project Skills** — split into Normal User Commands and System Maintainer Commands
12. **Folder Structure** — tree
13. **Quickstart: First Product Run** — 14-step detailed walkthrough
14. **How to Paste into Magnific** — instructions
15. **Manual Review Loop** — review process
16. **How to Save Selected Prompts** — approval
17. **How to Inspect Permissions** — permissions check
18. **Constraints** — rules
19. **No Guarantees Statement** — disclaimer

## Files to Modify

1. `README.md` (root) — full replacement
2. `magnific-prompt-engine/README.md` — restructure with new sections
3. `magnific-prompt-engine/instructions.md` — update Section 81 locked order
4. `instructions.md` (root) — fix start-location wording to match

## Key Changes per Audit Issue

| Issue | Fix |
|-------|-----|
| #1 — Root README too thin | Full replacement with purpose, diagram, quickstart, boundary |
| #2 — Start location contradiction | Both READMEs say "open Claude Code at repo root" |
| #3 — No system diagram | Mermaid diagram in nested README section 3 |
| #4 — Files before why | New order: What → How → Contract → Accuracy → Start Here |
| #5 — Skills verification | Remove ambiguity — all 5 SKILL.md files confirmed exist |
| #6 — Input/output contract | New section 4 with file-purpose table |
| #7 — Command overload | Split into Normal User Commands / System Maintainer Commands |
| #8 — Manual vs Automated placement | Renamed to Responsibility Split, moved to section 8 |
| #9 — Accuracy model not explained | New section 5 (Verified / Inferred / Unknown) |
| #10 — No example run | New section 10 with ceramic-coffee-mug example |

## Non-Changes

- All SKILL.md files remain untouched (they already exist and work)
- `.claude/settings.json` remains untouched
- No new files are created outside the two READMEs and their references
- No automation, API, MCP, or Magnific integration is added

## Verification

After implementing:
1. Read both READMEs front-to-back — verify no contradictions
2. Verify start location is consistent across both READMEs
3. Verify new sections don't conflict with instructions.md rules
4. Verify no forbidden patterns or claims appear in new content
5. Verify Mermaid syntax renders correctly (standard flowchart TD)