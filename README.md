# System — Claude Code Prompt Engine Workspace

A workspace for building structured, evidence-controlled product campaign
prompt packs for manual use in Magnific.

The primary system is `magnific-prompt-engine/`. It generates campaign-aware
prompt packs for **Nano Banana 2** image prompts and **Kling 2.5** video
prompts. The system does **not** automate Magnific, call an API, or guarantee
final visual quality — it creates structured prompt assets that you manually
test, review, revise, and approve.

## What's Inside

| Directory | Role |
|---|---|
| `magnific-prompt-engine/` | Main prompt-pack system (campaign work happens here) |
| `graphify/` | Codebase graph analysis and visualization (submodule) |
| `superpowers/` | Claude Code workflow superpowers (submodule) |

| File | Role |
|---|---|
| `README.md` | This file — workspace overview |
| `CLAUDE.md` | Claude Code workspace rules |
| `instructions.md` | Workspace index and operating law |

## System Flow

```mermaid
flowchart TD
    A[Product evidence] --> B[product-runs/product-name/input.md]
    B --> C[Claude Code validates evidence]
    C --> D{Campaign-ready?}
    D -->|No| E[Fill input.md fields in product-runs/]
    E --> C
    D -->|Yes| F[Campaign strategy lock]
    F --> G[Creative direction lock]
    G --> H[prompt-pack.md]
    H --> I[Manual Magnific testing]
    I --> J[review-notes.md]
    J --> K{Approve, revise, or reject?}
    K -->|Approve| L[selected-prompts.md]
    K -->|Revise| M[Targeted revision prompt]
    M --> H
    K -->|Reject| N[Do not reuse prompt]
```

**Commands used:** `/run-product-campaign [product-name]` handles validation through prompt-pack generation. `/review-output product-runs/[product-name]` handles the review step. `/revise-prompt product-runs/[product-name]` handles revision prompts.

## Quick Start

1. Clone the repo and initialize submodules
2. Open Claude Code in the `magnific-prompt-engine/` directory (not at the repo root — skills live there)
3. Run `/run-product-campaign [product-name]` — if the folder doesn't exist, Claude Code creates the scaffolding and stops, waiting for your input
4. Fill `product-runs/[product-name]/input.md` with product evidence
5. Run `/run-product-campaign [product-name]` again to generate the prompt pack
6. Run `/review-output product-runs/[product-name]` after testing outputs. Record which visuals you approve, revise, or reject. Approved outputs are saved to `selected-prompts.md`.
7. (Optional) Run `/revise-prompt product-runs/[product-name]` when a specific prompt needs targeted revision. Document the failure first in review-notes.md.

## Important Boundary

This system creates **text prompts only**. You copy them into Magnific manually.
It does not generate images, videos, or automated campaigns.
It does not integrate with Magnific APIs, Spaces, or any automation platform.

## Submodules

```bash
git submodule update --init --recursive
```