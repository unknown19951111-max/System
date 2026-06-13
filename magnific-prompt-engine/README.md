# Magnific Prompt Engine v6.6.1

[![Version](https://img.shields.io/badge/Version-6.6.1-orange)](CHANGELOG.md)
[![Model](https://img.shields.io/badge/Model-Nano%20Banana%202%20%2B%20Kling%202.5-blue)](https://magnific.com)

Generates campaign-aware, copy-paste-ready prompt packs for manual use in Magnific. You provide product facts. The system structures them into technical prompts for **Nano Banana 2** (images) and **Kling 2.5** (video). You test the outputs manually in Magnific and decide what to keep.

---

## What This Is Not

- NOT an automation tool — you paste prompts into Magnific by hand
- NOT a Magnific API — no integration, no Spaces, no browser automation
- NOT a visual generator — this repo only produces text prompts
- NOT a quality guarantee — Magnific outputs vary; you review every one

---

## Who This Is For

- Product marketers creating campaign visuals in Magnific
- Prompt engineers who want structured, repeatable workflows
- Anyone who needs evidence-controlled prompts instead of free-form guessing

---

## Quick Start

```bash
git clone https://github.com/unknown19951111-max/System.git
cd System
git submodule update --init --recursive
cd magnific-prompt-engine && claude
```

> **⚠️ Claude Code must be running from the `magnific-prompt-engine/` directory.** This is the most common setup mistake. If slash commands don't appear, you're probably in the wrong folder.

Once Claude Code is open, run your first campaign:

```
/run-product-campaign ceramic-coffee-mug
```

**First run behavior:** The folder doesn't exist yet, so Claude Code creates the scaffolding (`input.md`, placeholder files) and **stops**. This is expected. Fill in `input.md` with your product details, then run the command again.

Product names use **kebab-case**: lowercase letters, hyphens instead of spaces.
- ✅ `ceramic-coffee-mug`, `biona-hypochlorous-spray`
- ❌ `Ceramic Coffee Mug`, `ceramic_coffee_mug`

---

## Health Check

Run these in Claude Code to verify the system is wired correctly:

```
/permissions
```

Expected output: `defaultMode` is `plan`. Product-run files show as the normal write area.

Then check that the required files exist:

```bash
ls .claude/settings.json .claude/skills/*/SKILL.md
```

Expected: no errors — every listed file exists.

If anything is missing, run `git submodule update --init --recursive` from the repo root and re-launch Claude Code from `magnific-prompt-engine/`.

---

## Core Workflow

```
You fill input.md → Claude Code validates → Claude Code generates prompt pack
→ You paste prompts in Magnific → You review outputs → You approve/revise/reject
```

In more detail:

1. **Fill** `product-runs/[product-name]/input.md` with product facts
2. **Run** `/run-product-campaign [product-name]` to generate the prompt pack
3. **Test** prompts manually in Magnific (copy, paste, generate)
4. **Run** `/review-output product-runs/[product-name]` to record approvals, revisions, or rejections
5. **Run** `/revise-prompt product-runs/[product-name]` for targeted fixes (only when needed)

---

## Product-Run Folder Structure

After scaffolding, each product-run folder looks like this:

```
product-runs/[product-name]/
├── input.md                    ← Your product evidence (you fill this)
├── campaign-strategy-lock.md   ← Strategy locked from your input
├── creative-direction-lock.md  ← Visual direction locked from your input
├── prompt-pack.md              ← Generated prompts (copy from here)
├── review-notes.md             ← Your Magnific output review log
├── run-status.md               ← Status manifest (DRAFT/TESTED/SELECTED/RETIRED)
└── selected-prompts.md         ← Approved winning prompts saved here
```

You only need to touch `input.md` (fill facts) and copy from `prompt-pack.md` (paste into Magnific). Everything else is system-managed.

---

## Editable vs Protected Files

| ✅ You can edit | ❌ Protected (do not edit during product runs) |
|---|---|
| `product-runs/[product-name]/input.md` | `instructions.md` — build contract |
| `product-runs/[product-name]/review-notes.md` | `CLAUDE.md` — project rules |
| `product-runs/[product-name]/selected-prompts.md` | System files (`01_*.md` to `04_*.md`) |
| (your evidence files, notes) | `.claude/settings.json` |
| | `.claude/skills/*/SKILL.md` — command definitions |

Protected files can be edited with approval when improving the system (use `/update-system` or `/build-system`), but should not be modified during normal product runs. Protection is policy-enforced (plan mode + instructions), not by an executable guard.

---

## Claude Code Commands

| Command | When to use | Reads from | Writes to |
|---|---|---|---|
| `/run-product-campaign [name]` | New or regenerated campaign | `input.md` | `prompt-pack.md` |
| `/review-output product-runs/[name]` | After testing in Magnific | `prompt-pack.md` | `review-notes.md`, `selected-prompts.md` |
| `/revise-prompt product-runs/[name]` | Documented failure needs fix | `review-notes.md` | Updated `prompt-pack.md` |
| `/build-system` | System creation or health check | System files | System files or report |
| `/build-system --check` | Verify wiring (read-only) | System files | Report only |
| `/update-system` | Audit or patch system files | System files | System files |

**New users only need these:**

```
/run-product-campaign [product-name]
product-runs/[product-name]/input.md
product-runs/[product-name]/prompt-pack.md
/review-output product-runs/[product-name]
/revise-prompt product-runs/[product-name]  (only when needed)
product-runs/[product-name]/selected-prompts.md
```

---

## Manual Magnific Testing

Prompts are text. They do not generate visuals automatically.

1. **Open Magnific** and select the model lane: Nano Banana 2 for images, Kling 2.5 for video
2. **Copy the Final Copy-Paste Prompt** from `product-runs/[product-name]/prompt-pack.md`
3. **Paste into Magnific** and generate

Save outputs with this naming convention: `[product-name]-[prompt-name]-[attempt-number].png`

Example: `ceramic-coffee-mug-hero-shot-01.png`

The system does not connect to Magnific accounts, APIs, browser sessions, or model backends.

---

## Review and Revision Workflow

After testing prompts in Magnific:

1. Run `/review-output product-runs/[product-name]`
2. Name the prompt you tested. For each Magnific output, choose one:
   - **APPROVE** — saved to `selected-prompts.md`
   - **REVISE** — run `/revise-prompt product-runs/[product-name]` for a targeted fix
   - **REJECT** — note in `review-notes.md`; do not reuse
3. Run `/revise-prompt product-runs/[product-name]` only when a failure is documented in `review-notes.md`

Approved prompts are saved to `selected-prompts.md` only when you confirm approval during review. Claude Code does not save prompts as "selected" based on its own opinion.

---

## Status Lifecycle

Every prompt pack and `run-status.md` file uses one of these statuses:

| Status | Meaning |
|---|---|
| `DRAFT` | Generated but not tested in Magnific |
| `TESTED` | Used in Magnific and reviewed |
| `SELECTED` | Output approved, saved to `selected-prompts.md` |
| `RETIRED` | Prompt no longer recommended (failure or replacement) |

---

## Responsibilities

| Claude Code handles | User handles |
|---|---|
| Folder scaffolding and file creation | Product evidence input |
| Input validation | Magnific prompt pasting |
| Campaign strategy lock generation | Model lane selection |
| Creative direction lock generation | Magnific generation |
| Prompt-pack generation | Visual quality judgment |
| Review-note formatting | Final output approval |
| Selected-prompt saving (after user approval) | Deciding when to update the system |

---

## Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| Slash command not found | Claude Code opened from wrong directory, or `.claude/skills/` missing | `cd magnific-prompt-engine/` and retry; verify `.claude/skills/` exists |
| "Stop and request missing fields" | `input.md` lacks required evidence | Add Product Evidence, Important Restrictions, Output Needed |
| Folder scaffolds then stops | First run — this is expected | Fill `input.md` and run the command again |
| Submodule folders are empty | Not initialized | Run `git submodule update --init --recursive` in repo root |
| Skill doesn't activate | Wrong CWD, or `.claude/settings.json` missing | Check CWD is `magnific-prompt-engine/`; verify settings file exists |
| Prompt pack shows DRAFT | Pack generated but not tested | Normal — change to TESTED after testing in Magnific |
| Permission error editing system files | Plan mode is active (default) | Use `/update-system` or `/build-system` for system changes |
| Product folder exists but prompt pack does not generate | `input.md` still has placeholder content, or overwrite safety blocked it | Fill `input.md` with real product evidence, or confirm overwrite when prompted |
| Magnific output has wrong details | Prompt references unverified claims | Add missing evidence to `input.md` and regenerate |
| Magnific output has bad visual quality | Model behavior, not a prompt issue | Revise prompt with specific failure type via `/revise-prompt`; or adjust Magnific settings |
| Label text renders incorrectly | Magnific model text rendering behavior | Add text-anchoring instructions to the prompt; or render text as post-processing |
| User accidentally edits system files | Opened system file during product run | Discard changes — system files are regeneratable from git. Use `/update-system` for intentional changes |
| Prompt question: "Does this generate images?" | User assumes this repo is an image generator | See "What This Is Not" above — manual Magnific only |

---

## Repository Map

```
magnific-prompt-engine/
├── README.md                     ← This file — operator manual
├── CLAUDE.md                     ← Project memory and routing rules
├── instructions.md               ← Build contract (89 rules)
├── 01_MASTER_PROMPT_ENGINE.md    ← Runtime sequence
├── 02_PRODUCT_INPUT_TEMPLATE.md  ← input.md template
├── 03_OUTPUT_SCHEMA.md           ← prompt-pack.md structure
├── 04_REVIEW_AND_REVISION.md     ← Review workflow and failure taxonomy
├── .claude/
│   ├── settings.json             ← Plan-mode config
│   └── skills/                   ← Slash command definitions
│       ├── build-system/
│       ├── run-product-campaign/
│       ├── review-output/
│       ├── revise-prompt/
│       └── update-system/
├── product-runs/                 ← Your campaign folders
│   └── example-product/          ← Placeholder template
└── tests/
    └── hallucination-pressure-test.md
```

---

## Current Limitations

- **Only two model lanes:** Nano Banana 2 (images) and Kling 2.5 (video). No other models, no fallbacks.
- **No automation:** This system does not generate images or video. It produces text prompts for manual use.
- **No MCP, API, or browser integration.** Magnific is used independently.
- **No quality guarantee.** Generated prompts are not equivalent to approved visuals. Manual review is always the final quality gate.
- **No default human subjects.** People, hands, and faces require explicit approval per campaign.
- **Protection is policy-based.** System file protection relies on plan mode and instructions, not an executable hook guard.

---

## Maintenance Notes

- See [CHANGELOG.md](CHANGELOG.md) for version history.
- To update the system (after verified issues and approval): run `/update-system`.
- To run a build health check: run `/build-system --check`.
- Hallucination pressure test: see `tests/hallucination-pressure-test.md` and the `product-runs/hallucination-pressure-test/` run folder.

Only Nano Banana 2 and Kling 2.5 are supported. No other image or video models should be used with this system.