# System — Prompt Engine Workspace

A Claude Code workspace containing `magnific-prompt-engine/` as the primary
local system, with `graphify/` and `superpowers/` mounted as auxiliary git submodules.

## What's Inside

| Directory | Purpose |
|-----------|---------|
| `magnific-prompt-engine/` | Campaign-aware prompt-pack builder for Magnific (Nano Banana 2 + Kling 2.5) |
| `graphify/` | Codebase graph analysis and visualization (submodule) |
| `superpowers/` | Claude Code workflow superpowers (submodule) |

## Quick Start

1. `cd magnific-prompt-engine` — that's where the main system lives
2. Read its `README.md` for the full workflow
3. Run `/run-product-campaign [product-name]` from within that directory

## Submodules

```bash
git submodule update --init --recursive
```