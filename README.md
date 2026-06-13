# System — Magnific Prompt Engine Workspace

<img width="1448" height="1086" alt="ChatGPT Image Jun 13, 2026, 12_17_45 AM" src="https://github.com/user-attachments/assets/ae1a017e-4502-4b64-b87d-841337e582c0" />


[![Status](https://img.shields.io/badge/Status-Active-green)](https://github.com/unknown19951111-max/System)
[![Model](https://img.shields.io/badge/Model-Nano%20Banana%202%20%2B%20Kling%202.5-blue)](https://magnific.com)
[![Version](https://img.shields.io/badge/Version-6.6.2-orange)](magnific-prompt-engine/CHANGELOG.md)

A workspace for building prompt packs for manual use in Magnific. The primary system is `magnific-prompt-engine/`.

**This repo does not generate images or video — it produces text prompts that you copy into Magnific manually.** No automation, no API, no browser integration.

---

## Quick Start

```bash
git clone https://github.com/unknown19951111-max/System.git
cd System
git submodule update --init --recursive
cd magnific-prompt-engine && claude
```

Then in Claude Code:

```
/run-product-campaign ceramic-coffee-mug
```

**First run** creates scaffolding and stops — fill `input.md`, then run the command again.

---

## What's Inside

| Directory | Role |
|---|---|
| `magnific-prompt-engine/` | Prompt-pack system — all campaign work happens here |
| `graphify/` | Codebase graph analysis (submodule) |
| `superpowers/` | Claude Code workflow tools (submodule) |

---

## Commands

| Command | Purpose |
|---|---|---|
| `/run-product-campaign [name]` | Generate prompt pack from your product facts |
| `/review-output product-runs/[name]` | Record Magnific output reviews |
| `/revise-prompt product-runs/[name]` | Targeted prompt revision for documented failures |
| `/build-system [--check]` | System creation or health check (maintainer) |
| `/update-system` | Audit and patch system files after verified issues (maintainer) |

---

## Submodules

```bash
git submodule update --init --recursive
```

---

**Full documentation:** [magnific-prompt-engine/README.md](magnific-prompt-engine/README.md)
