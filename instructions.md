# System Workspace Instructions

This repository is a **Claude Code workspace** that groups multiple projects.

## Primary System

The primary system is:

`magnific-prompt-engine/`

All product campaign work must happen inside that directory. See its `README.md` for the full workflow.

## Submodules

`graphify/` and `superpowers/` are auxiliary git submodules. Do not modify their files unless explicitly requested.

## Required Read Order

When working in this workspace, read these files in order:

1. Root `README.md` — workspace overview and entry point
2. Root `CLAUDE.md` — workspace-level Claude rules
3. This root `instructions.md` — workspace index
4. `magnific-prompt-engine/README.md` — system overview
5. `magnific-prompt-engine/CLAUDE.md` — project Claude rules
6. `magnific-prompt-engine/instructions.md` — build contract

## Operating Rule

If workspace-level files conflict with `magnific-prompt-engine/` files, the more specific `magnific-prompt-engine/` rule wins for product campaign work.