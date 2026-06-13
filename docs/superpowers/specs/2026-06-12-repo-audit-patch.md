# System Repo — Forensic Audit & Minimal Patch

## Context

Auditor rated the repo 1/10 citing empty shell at root level despite
`magnific-prompt-engine/` being a fully functional system underneath.

## Verified Issues

1. ❌ No root `README.md`
2. ❌ No root `CLAUDE.md`
3. ❌ Root `instructions.md` misplaced (belongs in magnific-prompt-engine/)
4. ❌ Root `instructions_v6_6_1.md` duplicate backup

## Approach: Minimal Patch (A)

Per user selection. Add README + CLAUDE.md at root, relocate instructions.md,
remove duplicate backup.

### README.md

Concise workspace README identifying this as a Prompt Engine Workspace
with magnific-prompt-engine as primary system and graphify/superpowers
as submodule auxiliaries.

### CLAUDE.md

Lightweight workspace rules — set working directory to magnific-prompt-engine/,
respect submodules, read instructions.md before modifying system files.

### instructions.md relocation

- Move root `instructions.md` → `magnific-prompt-engine/instructions.md`
- Delete root `instructions.md` and `instructions_v6_6_1.md`