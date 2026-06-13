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

## System Flow

```mermaid
flowchart TD
    A[Product evidence] --> B[input.md]
    B --> C[Claude Code validates evidence]
    C --> D{Campaign-ready?}
    D -->|No| E[Fill input.md fields]
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

## Quick Start

1. Clone the repo and initialize submodules
2. Open Claude Code at the repo root (not inside a subdirectory)
3. Run `/run-product-campaign [product-name]`
4. Fill `product-runs/[product-name]/input.md` with product evidence
5. Run `/run-product-campaign [product-name]` again to generate the prompt pack
6. Manually test prompts in Magnific, review outputs, and save winners

## Important Boundary

This system creates **text prompts only**. You copy them into Magnific manually.
It does not generate images, videos, or automated campaigns.
It does not integrate with Magnific APIs, Spaces, or any automation platform.

## Submodules

```bash
git submodule update --init --recursive
```