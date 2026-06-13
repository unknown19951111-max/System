---
name: update-system
description: Audit or patch the Magnific Prompt Engine system files after verified issues and user approval.
disable-model-invocation: true
---

# /update-system — Audit or Patch the System

## Purpose
Run a read-only system audit or apply verified, scoped updates to system files after user approval.

## When to Use
- User says `/update-system` or `/update-system --audit`
- User says "check the system" or "audit the system"

## Required Inputs
- System files and instructions.md

## Allowed Actions

### Audit Mode (default)
- Inspect wiring, scope, claims, drift, usability, and output correctness
- Report findings with PASS / FAIL / NEEDS USER DECISION
- Do not edit files

### Update Mode (after user approval)
- Apply only verified fixes
- Follow System Update Anti-Slop Rule
- Follow Core-Fit Gate
- Follow System Update Patch Approval Rule

## Forbidden Actions
- Add speculative features
- Add unsupported models, automation, plugins, APIs
- Add plugin packaging, subagents, MCP
- Generate product campaign prompts
- Add optional or experimental bloat

## Required Sequence (Audit)
1. Verify required files exist
2. Check for drift from instructions.md
3. Check for forbidden patterns
4. Check output schema consistency
5. Check skill concision (no duplication of instructions.md)
6. Report findings

## Required Sequence (Update)
1. Verified issue list
2. Affected sections
3. Proposed patch plan
4. Wait for user approval
5. Apply changes
6. Run Markdown Build Verification Rule

## Output Files (Update Mode)
- Modified system files per approved patch plan