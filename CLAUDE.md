# CLAUDE.md — System Workspace Rules

## Workspace Structure

This repo is a **workspace** that groups multiple projects.
**magnific-prompt-engine/** is the primary system. graphify/ and superpowers/
are git submodules with their own rules.

## Rules

1. Default working directory is `magnific-prompt-engine/` — that's where
   `/run-product-campaign` and other project skills live.
2. Read `instructions.md` inside `magnific-prompt-engine/` before
   modifying system files.
3. Do not modify `graphify/` or `superpowers/` files — they are
   upstream submodules.
4. Root `instructions.md` is the workspace index — non-negotiable
   operating law lives there.

## First-Time Setup

```bash
git submodule update --init --recursive
```