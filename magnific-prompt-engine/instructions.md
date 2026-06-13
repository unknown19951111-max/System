# instructions.md

# Magnific Prompt Engine v6.6.1 — Stale Wiring Cleanup + Schema Consistency Patch

## 00. File Placement Rule

This file must exist at:

```text
magnific-prompt-engine/instructions.md
```

Do not duplicate, rename, or archive alternate instruction files inside the active project unless explicitly approved.

---

## 01. Non-Negotiable Build Summary

Build a markdown-only, campaign-aware prompt system for manual Magnific use.

Do not build automation.  
Do not add code.  
Do not add APIs.  
Do not add extra models.  
Do not add MCP.  
Do not add Magnific Agents.  
Do not add Spaces automation.

Use official Claude Code project skills for repeated workflows.

Use one minimal Claude Code settings file only for permission-first protected file approval behavior.

Default Claude Code posture for this repo is `plan` mode.

Automate local repo scaffolding and documentation formatting only.

Do not automate Magnific use.

Default output is:

- Nano Banana 2 image prompts
- Kling 2.5 video prompts
- Manual review workflow
- Targeted revision prompts
- Selected prompt library

Every request must follow the Superpowers Order Rule first when Superpowers is required, then pass through the Workflow Routing Rule.

Every prompt must follow this chain:

```text
Product Truth
→ Claims Registry
→ Campaign Strategy
→ Creative Direction
→ Technical Visual Direction
→ Prompt Quality Scorecard
→ Manual Review
```

The system can lock workflow, file structure, output order, required sections, and review process.

The system cannot guarantee exact Magnific image/video output quality.

---

## 02. Precondition

Superpowers is already installed in Claude Code before this project begins.

Do not spend time installing, configuring, debugging, or verifying Superpowers unless the user explicitly asks.

Use Superpowers only as the build methodology for this project.

### Superpowers Preflight Rule

Before invoking Superpowers-dependent workflows, check whether the `superpowers/` submodule directory exists and is non-empty. If not initialized, stop and instruct the user to run:

```bash
git submodule update --init --recursive
```

Do not debug Superpowers internals unless explicitly asked.

---

## 03. Superpowers Skill Invocation Rule

When Superpowers is available, Claude Code must use the Superpowers skill mechanism as designed by the Superpowers repo.

Required behavior:

1. Invoke the relevant Superpowers skill using the Skill tool before any build action.
2. Do not merely imitate a skill informally.
3. Follow the invoked skill unless it conflicts with `instructions.md`.
4. If a Superpowers skill conflicts with `instructions.md`, `instructions.md` wins.
5. Do not add Superpowers plugin packaging, hooks, subagents, Git workflows, or TDD machinery to this project unless the user explicitly approves those in a separate request.

Required Superpowers skill use:

- BUILD MODE: invoke `brainstorming` before proposing the build plan.
- SYSTEM_UPDATE: invoke the relevant planning/review behavior before editing system files.
- PROMPT_REVISION: use the systematic-debugging pattern before revising failed prompts.
- COMPLETION CLAIMS: use the verification-before-completion pattern before saying the build or product-run output is complete.

---

## 04. Superpowers Order Rule

When Superpowers is available, Superpowers skill invocation comes before internal workflow routing.

Required order:

1. Invoke the relevant Superpowers skill using the Skill tool.
2. Classify the request using the Workflow Routing Rule.
3. Continue with the selected route.

This rule prevents the internal router from bypassing the Superpowers methodology.

---

## 05. Clarification After Skill Rule

If the user request is ambiguous:

1. Invoke the relevant Superpowers skill using the Skill tool first.
2. Then ask whether the user means BUILD MODE, PRODUCT RUN MODE, SYSTEM_AUDIT, or SYSTEM_UPDATE.

Do not ask clarification questions before required skill invocation.

---

## 06. System Mode Separation

There are two modes.

### Mode 1 — BUILD MODE

Used only to create the markdown repo files.

In BUILD MODE:

- create system files only
- do not generate real product prompts
- do not run a product campaign
- do not modify product-run outputs except placeholders
- stop before implementation until the user approves with `Approved. Build it.`

### Mode 2 — PRODUCT RUN MODE

Used only after the repo exists.

In PRODUCT RUN MODE:

- read system files
- read `product-runs/[product-name]/input.md`
- generate only product-run files
- do not modify system files
- do not modify templates
- do not modify `instructions.md`
- do not modify `CLAUDE.md`
- do not modify README or numbered system files


If the user request is ambiguous, follow the Clarification After Skill Rule before asking whether they mean BUILD MODE or PRODUCT RUN MODE.

---

## 07. Workflow Routing Rule

Before acting, classify the user request into exactly one workflow route.

Allowed workflow routes:

1. `BUILD_MODE_SYSTEM_CREATION`
2. `PRODUCT_RUN_FULL_PACK`
3. `PRODUCT_RUN_IMAGE_ONLY`
4. `PRODUCT_RUN_VIDEO_ONLY`
5. `PROMPT_REVISION`
6. `OUTPUT_REVIEW`
7. `SELECTED_PROMPT_LIBRARY_UPDATE`
8. `SYSTEM_AUDIT`
9. `SYSTEM_UPDATE`

After classifying the route, state the selected route in the build-plan output or product-run response, then follow only the rules for that route.

Do not mix workflow routes unless the user explicitly asks.

### Route Behavior

`BUILD_MODE_SYSTEM_CREATION`:
- create or update system files
- obey Implementation Gate
- do not generate real product prompts

`PRODUCT_RUN_FULL_PACK`:
- read one product input
- generate full image + video prompt pack
- do not modify system files

`PRODUCT_RUN_IMAGE_ONLY`:
- generate only Nano Banana 2 image prompts
- mark Kling 2.5 section as `NOT REQUESTED`

`PRODUCT_RUN_VIDEO_ONLY`:
- generate only Kling 2.5 video prompts
- mark Nano Banana 2 section as `NOT REQUESTED`

`PROMPT_REVISION`:
- revise one failed prompt using the Revision Failure Taxonomy
- preserve Product Accuracy Lock and Claims Registry

`OUTPUT_REVIEW`:
- classify output as `APPROVE`, `REVISE`, or `REJECT`
- write review notes
- do not generate unrelated new prompts

`SELECTED_PROMPT_LIBRARY_UPDATE`:
- save only user-approved prompts
- do not copy untested prompts into selected-prompts.md

`SYSTEM_AUDIT`:
- inspect wiring, scope, claims, drift, usability, and output correctness
- do not edit files unless the user separately asks for implementation

`SYSTEM_UPDATE`:
- apply only verified fixes
- avoid speculative features
- preserve hard scope

---

## 08. Fast Mode vs Controlled Mode

Default mode is `FAST MODE`.

### FAST MODE

Use when the user wants fast execution.

Claude Code may generate:

- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- prompt pack

in one pass.

### CONTROLLED MODE

Use when the user asks for stricter control, approval gates, or high-stakes campaign direction.

In CONTROLLED MODE:

1. Create Campaign Strategy Lock.
2. Create Creative Direction Lock.
3. Create Campaign Intent Matrix.
4. Stop and ask for approval before final prompt generation.

Approval phrase for controlled prompt generation:

```text
Approved. Generate prompt pack.
```

Do not require controlled approval in normal fast runs unless the user requests it.

### Fast Mode Boundary Rule

Fast Mode applies only to PRODUCT RUN MODE.

Fast Mode does not override BUILD MODE Implementation Gate.

In BUILD MODE, Superpowers brainstorming and user approval are required before file creation.

SYSTEM_UPDATE also requires the System Update Patch Approval Rule before editing system files.

---

## 09. Prompt Failure Debugging Rule

Before revising a failed Magnific output, diagnose the failure before rewriting the prompt.

### Prompt Revision Evidence Rule

Before revising a failed prompt, require at least one of:

- user description of the failure
- screenshot reference
- `review-notes.md` entry
- specific failure type selected by the user

If none is provided, ask for the observed failure before revising.

Required sequence:

1. Identify observed failure.
2. Map failure to the Revision Failure Taxonomy.
3. Identify likely prompt cause.
4. Revise one variable only.
5. Preserve Product Accuracy Lock.
6. Preserve Claims Registry.
7. Preserve Campaign Strategy Lock unless campaign direction caused the failure.
8. Preserve Creative Direction Lock unless creative direction caused the failure.
9. Append the revision prompt to `review-notes.md`.

Do not rewrite the entire prompt globally unless the failure is broad and the user approves a full rewrite.

---

## 10. Completion Claim Rule

Claude Code may say:

- `Prompt pack generated and ready for manual Magnific testing.`
- `Revision prompt generated for manual testing.`
- `Review notes updated.`
- `Selected prompt saved after user approval.`

Claude Code may not say:

- `production-ready`
- `guaranteed accurate`
- `final campaign assets selected`
- `campaign complete`
- `approved prompt`
- `claim-safe output`

unless the user manually reviewed the Magnific output and approved it.

Generated prompts are never equivalent to approved visuals.

### Markdown Build Verification Rule

Before claiming the system build is complete, verify:

1. Required repo tree exists.
2. Only approved `.md` files exist.
3. No forbidden file types exist.
4. Every required file is present.
5. `instructions.md` exists at repo root.
6. `03_OUTPUT_SCHEMA.md` includes full templates.
7. README includes the required exact order.
8. `product-runs/example-product/` files are placeholders only.
9. No unsupported model lanes are introduced.
10. No automation, API, CLI, MCP, Agent integration, or Spaces automation is implemented.
11. Required campaign, prompt, and review rules are present.
12. `05_ACCEPTANCE_CHECKLIST.md` has been reviewed.

Any completion claim must include the verification evidence checked.

---

## 11. System Update Anti-Slop Rule

When updating this system, only implement changes that satisfy all of these conditions:

1. The issue is verified.
2. The affected file or rule is identified.
3. The solution is scoped to the issue.
4. The change does not add unsupported models, automation, plugins, APIs, or extra infrastructure.
5. The change improves wiring, usability, accuracy, reviewability, or prompt quality.
6. The change does not duplicate an existing rule.
7. The final output remains markdown-first and manual-Magnific compatible.

Do not add speculative features just because they sound useful.

Do not add plugin packaging, session hooks, subagents, Git workflows, TDD machinery, or extra workflow folders unless the user explicitly approves them in a separate request.

### Core-Fit Gate

A system update may be added to `instructions.md` only if it belongs in the core system.

Do not add it to `instructions.md` if it is:

- optional
- experimental
- domain-specific beyond this Magnific prompt system
- plugin-specific
- future-roadmap material
- already covered by an existing rule

### System Update Patch Approval Rule

Before updating `instructions.md`, Claude Code must output:

1. Verified issue list
2. Sections affected
3. Proposed exact rule changes
4. What will not be changed
5. Expected operational improvement

Then wait for explicit user approval before applying the update, unless the user has already explicitly said to implement the audit findings.

### SYSTEM_UPDATE Gate Rule

SYSTEM_UPDATE must follow the same planning and approval discipline as BUILD MODE before editing system files.

Required before edits:

1. verified issue list
2. affected sections
3. proposed patch plan
4. approval from user

---

## 12. New User Quality-of-Life Rule

The system must be easy for a new user to operate without understanding every internal file.

README.md must be the user control panel.

README.md must include a top-level section named:

```text
Start Here
```

The Start Here section must clearly state:

```text
Most users only touch:

1. product-runs/[product-name]/input.md
2. product-runs/[product-name]/prompt-pack.md
3. product-runs/[product-name]/review-notes.md
4. product-runs/[product-name]/selected-prompts.md

Do not edit unless improving the system:

- instructions.md
- CLAUDE.md
- .claude/settings.json
- .claude/skills/
- numbered system files
```

README.md must show which command to run:

```text
First-time build:
/build-system

Check system health:
/build-system --check

New product campaign:
/run-product-campaign [product-name]

Review tested Magnific output:
/review-output product-runs/[product-name]

Revise a failed prompt:
/revise-prompt product-runs/[product-name]

Audit or update the system:
/update-system
```

---

## 13. Permission-First Operations Rule

Use Claude Code permissions before hook scripts.

`.claude/settings.json` must set this repo to planning-first behavior:

```json
{
  "permissions": {
    "defaultMode": "plan"
  }
}
```

Do not use `auto` mode for this repo.

Do not configure broad automatic write access.

Protected system file edits should require approval through Claude Code permissions and normal edit approval flow.

Hard hook enforcement is not active unless the user separately approves a hook handler script.

Rename user-facing protection language from:

```text
Protected System File Approval Rule
```

to:

```text
Protected System File Approval Rule
```

unless an executable hook handler is actually implemented.

---

## 14. Product Run Scaffolding Rule

`/run-product-campaign` must support two states.

### State A — Product Run Folder Does Not Exist

If the user runs:

```text
/run-product-campaign [product-name]
```

and the folder does not exist, Claude Code must:

1. normalize `[product-name]` to lowercase kebab-case
2. create `product-runs/[product-name]/`
3. create the required product-run files
4. write placeholder content into `input.md`
5. stop and ask the user to fill `input.md`

Required scaffolded files:

```text
product-runs/[product-name]/input.md
product-runs/[product-name]/campaign-strategy-lock.md
product-runs/[product-name]/creative-direction-lock.md
product-runs/[product-name]/prompt-pack.md
product-runs/[product-name]/review-notes.md
product-runs/[product-name]/selected-prompts.md
```

Do not generate prompts during State A.

### State B — Product Run Folder Exists and input.md Has Evidence

If the folder exists and `input.md` contains non-placeholder Product Evidence, Claude Code may generate:

```text
campaign-strategy-lock.md
creative-direction-lock.md
prompt-pack.md
```

while preserving overwrite safety.

---

## 15. Product Evidence Preflight Rule

Before generating any prompt pack, `/run-product-campaign` must check `input.md`.

Required minimum fields:

1. Product Evidence
2. Important Restrictions
3. Output Needed

If Product Evidence is empty, placeholder-only, or not specific enough to identify the product, Claude Code must:

1. create no prompt pack
2. ask the user to complete `input.md`
3. show the exact missing fields

Do not infer a full campaign from an empty or placeholder-only `input.md`.

---

## 16. Review Formatting Automation Rule

Manual visual judgment remains the user's responsibility.

Formatting review notes is Claude Code's responsibility.

`/review-output` must accept rough user feedback and convert it into structured `review-notes.md`.

Example rough user feedback:

```text
Output 1 made the cap silver and added fake text.
```

Must become structured review data:

```text
Prompt Name:
Decision: REVISE
Failure Type:
Observed Issue:
Next Action:
```

Do not invent observations that the user did not provide.

---

## 17. Selected Prompt Save Automation Rule

`/review-output` may append to `selected-prompts.md` only when the user explicitly approves the output.

Accepted approval wording examples:

```text
Approve this output and save it.
Save this as selected.
This one is approved; add it to selected-prompts.md.
```

Do not save prompts as selected based only on Claude Code's opinion.

Manual user approval is required.

---

## 18. Build Health Check Rule

`/build-system --check` must perform a read-only health check unless the user explicitly asks to fix issues.

The health check must verify:

1. required files exist
2. required `.claude/skills/` files exist
3. `.claude/settings.json` exists
4. every `SKILL.md` has required YAML frontmatter
5. every operational skill has `disable-model-invocation: true`
6. README.md includes Start Here
7. README.md includes direct slash skill commands
8. `product-runs/example-product/` exists
9. no forbidden files exist
10. `.claude/settings.json` is valid JSON
11. no Magnific automation exists
12. no MCP, plugin packaging, subagents, API, CLI, or web app exists
13. output section order is identical across Artifact Routing Map, Product Run Command, and 03_OUTPUT_SCHEMA.md
14. no SKILL.md duplicates large sections of instructions.md instead of referencing system files

Health check output must use:

```text
PASS:
-

FAIL:
-

NEEDS USER DECISION:
-
```

If output section orders differ, report:

```text
FAIL:
- prompt-pack output schema mismatch
```

---

## 19. Manual vs Automated Boundary Rule

README.md must include this table.

```text
Automated by Claude Code:
- product-run folder scaffolding
- placeholder file creation
- input.md evidence validation
- campaign strategy lock generation
- creative direction lock generation
- prompt-pack generation
- review-note formatting
- selected-prompt saving after explicit user approval
- build health check
- protected system file approval prompts through permissions

Manual by user:
- product truth/evidence input
- claim evidence confirmation
- Magnific prompt pasting
- Magnific model lane selection
- Magnific generation
- visual quality judgment
- final output approval
- deciding when to update the system
```

Do not automate anything listed as manual.

---

## 20. Project Identity

Build a local markdown-first Claude Code prompt-engineering system named:

**Magnific Prompt Engine v6.6.1 — Campaign-Aware Technical Prompt System**

The system creates structured, campaign-aware, copy-paste prompt packs for manual use in Magnific.

The system is restricted to:

1. Nano Banana 2 image generation
2. Kling 2.5 video generation
3. Unlimited-eligible Magnific actions only when explicitly confirmed by the user

The system does not generate visuals.  
The system does not automate Magnific.  
The system does not control Spaces.  
The system does not use MCP by default.  
The system does not use Magnific Agents by default.  
The system does not recommend models outside the allowed lane.

The user manually copies prompts into Magnific, generates outputs, reviews them, rejects weak outputs, revises prompts, and selects final visuals.

The system must not randomly generate prompts. It must understand the product, campaign objective, creative direction, asset role, and technical visual direction before creating prompts.

Use the phrase:

```text
deterministic workflow and schema-guided prompt-pack builder
```

Do not overclaim that prompt generation or Magnific outputs are fully deterministic.

---

## 21. Locked Means / Does Not Mean

### Locked Means

The following are locked:

- workflow
- file structure
- required files
- output order
- required prompt sections
- supported model lanes
- manual review process
- claim-safety process
- product-run artifact routing

### Locked Does Not Mean

The following are not guaranteed:

- Magnific outputs are guaranteed
- model behavior is deterministic
- image/video results will always be correct
- prompt wording will be identical every run
- manual review can be skipped
- generated visuals are automatically production-ready

Manual review is always the final quality gate.

---

## 22. Contract Hierarchy

1. `instructions.md` is the build contract.
2. `CLAUDE.md` is the persistent project memory.
3. Numbered markdown files are system artifacts.
4. `product-runs/` files are examples or run outputs.

If any file conflicts with `instructions.md`, `instructions.md` wins.

If any implementation instruction conflicts with the hard scope, stop and ask the user.

---

## 23. Hard Scope

Build only a local markdown-first prompt-pack generator for manual Magnific use.

Allowed:

- Product analysis
- Product fact lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- Generated product brief
- Product image description
- Nano Banana 2 image prompts
- Kling 2.5 video prompts
- Negative prompts
- Controlled variations
- Prompt Quality Scorecard
- Manual review checklist
- Revision prompts
- Review notes schema
- Selected prompts schema
- Hallucination pressure test
- Local Claude Code project skills under `.claude/skills/`
- `.claude/settings.json` for one protected-file edit guard

Forbidden by default:

- MCP integration
- Magnific Agent integration
- Workflow Apps
- Flows
- Spaces automation
- Other image models
- Other video models
- Audio tools
- 3D tools
- Stock tools
- Upscaling/editing workflows unless explicitly approved
- CLI app
- Web app
- API
- Database
- Node/Python automation
- Shell scripts
- Package files
- Plugins
- Subagents
- MCP servers

Allowed exception:

- local project skills under `.claude/skills/`
- `.claude/settings.json` for the protected-file edit guard only

If the build drifts outside the allowed scope, stop and ask for approval.

---

## 24. File Type Allowlist

Allowed file types:

- `.md`
- placeholder folders
- `.json` only for `.claude/settings.json`

Forbidden unless explicitly approved:

- `.py`
- `.js`
- `.ts`
- `.json` except `.claude/settings.json`
- `package.json`
- `requirements.txt`
- `Dockerfile`
- database files
- API files
- web app files
- shell scripts

If code seems useful, propose it separately and wait for approval.

---

## 25. Repo Tree Lock

Required minimum structure:

```text
magnific-prompt-engine/
│
├── CLAUDE.md
├── README.md
├── instructions.md
├── 01_MASTER_PROMPT_ENGINE.md
├── 02_PRODUCT_INPUT_TEMPLATE.md
├── 03_OUTPUT_SCHEMA.md
├── 04_REVIEW_AND_REVISION.md
│
├── .claude/
│   ├── settings.json
│   └── skills/
│       ├── build-system/
│       │   └── SKILL.md
│       ├── run-product-campaign/
│       │   └── SKILL.md
│       ├── review-output/
│       │   └── SKILL.md
│       ├── revise-prompt/
│       │   └── SKILL.md
│       └── update-system/
│           └── SKILL.md
│
├── tests/
│   └── hallucination-pressure-test.md
│
└── product-runs/
    └── example-product/
        ├── input.md
        ├── campaign-strategy-lock.md
        ├── creative-direction-lock.md
        ├── prompt-pack.md
        ├── review-notes.md
        └── selected-prompts.md
```

### Approved Exceptions

The following are approved and may exist outside the minimum structure:

- `graphify-out/` — generated graph analysis output
- `product-runs/[any-product-name]/` — real product runs
- `tests/` — additional test files as needed
- Various supporting product-run files (e.g., `brand-voice.md`, `target-audience-profiles.md`)

No other files or folders outside these approved categories without user approval.

---

## 26. System Files Protection Rule

These files must not be modified during PRODUCT RUN MODE:

- `CLAUDE.md`
- `README.md`
- `instructions.md`
- `01_MASTER_PROMPT_ENGINE.md`
- `02_PRODUCT_INPUT_TEMPLATE.md`
- `03_OUTPUT_SCHEMA.md`
- `04_REVIEW_AND_REVISION.md`
- `tests/hallucination-pressure-test.md`
- `.claude/settings.json`
- `.claude/skills/build-system/SKILL.md`
- `.claude/skills/run-product-campaign/SKILL.md`
- `.claude/skills/review-output/SKILL.md`
- `.claude/skills/revise-prompt/SKILL.md`
- `.claude/skills/update-system/SKILL.md`

Product-run outputs belong only in:

```text
product-runs/[product-name]/
```

---

## 27. Artifact Routing Map

Dedicated product-run files:

- `campaign-strategy-lock.md`
- `creative-direction-lock.md`

Sections inside `prompt-pack.md`:

1. Prompt Pack Metadata
2. Product Evidence Level
3. Verified Product Facts
4. Reasonable Marketing Inferences
5. Unknown / Do Not Assume
6. Product Accuracy Lock
7. Claims Registry
8. Campaign Strategy Summary
9. Creative Direction Summary
10. Campaign Intent Matrix
11. Technical Visual Direction Layer
12. Nano Banana 2 Image Prompt Pack
13. Kling 2.5 Video Prompt Pack
14. Negative Prompt Pack
15. Controlled Variation Matrix
16. Prompt Quality Scorecard
17. Revision Prompts

The dedicated campaign and creative direction files are the source of truth.

`prompt-pack.md` must include short summaries of:

- Campaign Strategy Lock
- Creative Direction Lock

This keeps the prompt pack readable and portable.

---

## 28. Permanent Artifact Placement Rule

Product Accuracy Lock and Claims Registry are permanent top-level sections inside `prompt-pack.md`.

They must never be removed during prompt revision.

Revision prompts may update generated prompts, but must not rewrite Product Accuracy Lock or Claims Registry unless the user provides new verified evidence.

If the user provides new verified evidence, update:

1. Product Information Classification
2. Product Accuracy Lock
3. Claims Registry
4. affected prompts only

---

## 29. Superpowers Scope Binding

Use Superpowers only for:

- using-superpowers bootstrap behavior
- brainstorming this markdown repo
- writing a plan for the approved markdown files
- executing the plan
- verifying completion claims
- reviewing output against `instructions.md`
- debugging failed prompt revisions when applicable

Do not use Superpowers to:

- create a plugin
- create MCP tooling
- create code automation
- create Magnific integrations
- create app infrastructure

Superpowers must not create plugin-packaged skills for this project.

Local Claude Code project skills are allowed only under:

```text
.claude/skills/
```

These local project skills are part of the official Claude Code project structure, not Superpowers plugin packaging.

### Superpowers vs Project Skills Boundary

Superpowers is used for build/update methodology only.

Local `.claude/skills/` are daily operational workflows.

Superpowers is required for:

- BUILD MODE
- SYSTEM_UPDATE
- SYSTEM_AUDIT
- root-cause debugging of system behavior
- completion claims about system build/update

Local project skills are required for:

- normal product-run generation
- output review
- selected prompt saving
- basic prompt revision
- product-run scaffolding
- input validation

Normal product-run execution should use `/run-product-campaign` first and does not require Superpowers unless the user is building, updating, auditing, or debugging the system itself.

Do not confuse Superpowers skills with local Claude Code project skills.

---

## 30. Claude Code Native Skills Rule

Use local Claude Code project skills for repeated operational workflows.

Skills must live only under:

```text
.claude/skills/
```

Allowed project skills:

```text
.claude/skills/build-system/SKILL.md
.claude/skills/run-product-campaign/SKILL.md
.claude/skills/review-output/SKILL.md
.claude/skills/revise-prompt/SKILL.md
.claude/skills/update-system/SKILL.md
```

Do not create any other skills unless the user explicitly approves.

Do not create:

- plugin skills
- marketplace packaging
- global user skills
- subagent-backed skills
- MCP-backed skills
- code automation skills
- Git workflow skills
- TDD machinery skills

### Skill Frontmatter Rule

Every project `SKILL.md` file must include YAML frontmatter.

Minimum required frontmatter:

```yaml
---
name:
description:
disable-model-invocation: true
---
```

The `description` must clearly state exactly when the skill should be used.

Do not omit the frontmatter.

Do not leave generic descriptions such as `use this skill for tasks`.

### Manual Skill Invocation Rule

All operational project skills must use:

```yaml
disable-model-invocation: true
```

Reason:

- these skills can create or modify files
- these skills affect system behavior
- the user must control when they run

Claude Code must not auto-trigger these skills.

When a route requires a skill, Claude Code must state the required slash skill and wait for the user to invoke or confirm it, unless the user has already invoked the skill directly.

### Skill Body Concision Rule

Each `SKILL.md` must be concise.

Each skill body should contain only:

- purpose
- when to use
- required inputs
- allowed files
- forbidden actions
- required sequence
- output files
- verification checklist

Do not duplicate the full `instructions.md` contract inside any skill.

Skills must reference system files instead of copying them.

### No Broad allowed-tools Rule

Do not grant broad `allowed-tools` in project skill frontmatter.

No skill may grant itself wide file-write or command execution access unless the user explicitly approves that in a separate request.

Default: omit `allowed-tools` and rely on normal Claude Code permissions.

### Skill Responsibility Boundary Rule

Project skill boundaries:

`/build-system`:
- only system creation/update planning and build verification
- do not run product campaigns

`/run-product-campaign`:
- only new prompt-pack generation from `input.md`
- do not review tested Magnific outputs
- do not revise failed outputs unless part of initial generation quality repair

`/review-output`:
- only review Magnific outputs and update `review-notes.md`
- only save selected prompts after user approval
- do not generate a new full prompt pack

`/revise-prompt`:
- only create targeted revision prompts from evidence
- do not update system files
- do not create a full new prompt pack unless user explicitly requests rerun

`/update-system`:
- only audit and patch system files after approval
- do not generate product campaign prompts

### Skill Routing Map

Workflow routes must map to project skills:

```text
BUILD_MODE_SYSTEM_CREATION → /build-system
PRODUCT_RUN_FULL_PACK → /run-product-campaign
PRODUCT_RUN_IMAGE_ONLY → /run-product-campaign with Output Needed: image-only
PRODUCT_RUN_VIDEO_ONLY → /run-product-campaign with Output Needed: video-only
OUTPUT_REVIEW → /review-output
PROMPT_REVISION → /revise-prompt
SELECTED_PROMPT_LIBRARY_UPDATE → /review-output or /run-product-campaign depending on context
SYSTEM_AUDIT → /update-system in audit-only mode
SYSTEM_UPDATE → /update-system
```

Claude Code must use the correct project skill instead of manually re-reading the entire `instructions.md` workflow when a skill applies.

Because operational skills use `disable-model-invocation: true`, routing behavior is:

1. classify the workflow route
2. state the required slash skill
3. wait for user invocation or confirmation unless the user already invoked the skill

Example:

```text
Selected workflow route:
PRODUCT_RUN_FULL_PACK

Required project skill:
/run-product-campaign

Waiting for user confirmation or direct skill invocation.
```

---

## 31. Claude Code Settings Rule

The only allowed JSON file is:

```text
.claude/settings.json
```

This file exists only to configure project-level Claude Code behavior and the minimal protected-file edit guard.

### Settings JSON Boundary Rule

`.claude/settings.json` may contain only:

- permissions.defaultMode set to plan
- permission/approval rules for protected system files if explicitly implemented
- optional skill visibility settings if needed

Do not put narrative documentation inside `.claude/settings.json`.

Do not include hook configuration unless the user separately approves real hook enforcement.

It must not contain:

- MCP server configuration
- agent or subagent configuration
- marketplace or plugin settings
- environment variables
- model routing
- shell defaults
- API credentials
- Magnific credentials
- external service configuration

All other `.json` files remain forbidden unless explicitly approved.

Forbidden examples:

- `package.json`
- app config JSON
- API config JSON
- database JSON
- random runtime JSON

---

## 32. Permission-First Protected File Approval Rule

Use permission-first protected-file approval by default.

```text
Protected System File Approval Rule
```

### Optional PreToolUse Hook Target Rule

The protected-file approval rule must not claim active hook enforcement unless a real hook handler is implemented.

Optional future hook enforcement, if separately approved, may target only file-modifying tools:

- `Write`
- `Edit`
- `MultiEdit`

Default protection is permission-first approval; optional future hard enforcement may prevent accidental modification of protected system files.

No protection layer should monitor or block read-only actions.

### Hook Handler Decision Rule

Default v6.5.1 decision:

```text
Do not implement hook handler scripts yet.
```

Reason:

- this system remains markdown-first
- scripts are still forbidden by default
- hard hook enforcement requires a script or command handler
- adding a script needs separate explicit approval

Therefore `.claude/settings.json` may document the intended protected-file approval rule, but must not add executable hook scripts unless the user explicitly approves a single hook-script exception.

No hook scripts are part of the default system.

A hook script may be added only in a future separately approved version, and that version must update the File Type Allowlist first.

Do not include `.claude/hooks/` or hook scripts in the default build.

No hook scripts are allowed by default.

Purpose:

```text
Block edits to protected system files during PRODUCT RUN MODE.
```

Protected files:

```text
CLAUDE.md
README.md
instructions.md
01_MASTER_PROMPT_ENGINE.md
02_PRODUCT_INPUT_TEMPLATE.md
03_OUTPUT_SCHEMA.md
04_REVIEW_AND_REVISION.md
tests/hallucination-pressure-test.md
.claude/settings.json
.claude/skills/build-system/SKILL.md
.claude/skills/run-product-campaign/SKILL.md
.claude/skills/review-output/SKILL.md
.claude/skills/revise-prompt/SKILL.md
.claude/skills/update-system/SKILL.md
```

Allowed write area during PRODUCT RUN MODE:

```text
product-runs/[product-name]/
```

Do not add:

- notification hooks
- formatting hooks
- HTTP hooks
- MCP hooks
- external automation hooks
- multi-hook systems
- command execution hooks beyond the protected-file approval rule
- executable hook scripts unless separately approved

The hook must not automate Magnific.

The hook must not generate prompts.

The hook must only protect system files from accidental edits during PRODUCT RUN MODE.

---

## 33. Implementation Gate

Before creating or editing any file in BUILD MODE, Claude Code must output:

1. Goal restatement
2. Hard scope
3. Non-goals
4. Contract hierarchy summary
5. Proposed repo tree
6. File responsibility matrix
7. Implementation plan with task IDs
8. Native skill responsibility map
9. Permission-first protected file approval summary
10. Verification checklist

Then stop.

Do not create or edit files until the user says exactly:

```text
Approved. Build it.
```

---

## 34. Forbidden Patterns

The repo must not contain implementation of these concepts:

- MCP
- Agent
- Workflow App
- Flow
- Spaces automation
- API
- CLI
- database
- package.json
- requirements.txt
- upscale
- audio
- 3D
- stock
- Runway
- Veo
- Sora
- Midjourney
- Flux
- Seedance

These terms may appear only when listed as forbidden, out of scope, or requiring explicit approval.

### Forbidden Pattern Review Rule

A forbidden term is acceptable only if it appears under:

- Hard Scope forbidden list
- Forbidden Patterns
- What this is not
- Constraints
- Explicit approval required section

A forbidden term is a violation if it appears as:

- supported feature
- implementation step
- recommended workflow
- default model/tool
- generated prompt requirement

---

## 35. Model Lane Lock

Default supported models:

1. Nano Banana 2 for image prompts
2. Kling 2.5 for video prompts

No fallback models.  
No alternative models.  
No model comparisons.  
No model recommendations.  
No model API assumptions.  
No invented model parameters.

Nano Banana 2 and Kling 2.5 are manual Magnific UI lanes in this project.

The system only creates copy-paste prompts.

---

## 36. Unlimited Lane Confirmation Rule

The system must not claim any Magnific action is unlimited.

Allowed default prompt lanes:

- Nano Banana 2 image prompts
- Kling 2.5 video prompts

For any additional Magnific action:

- mark as `REQUIRES USER CONFIRMATION`
- do not include by default
- do not assume credit-free usage
- do not design workflow steps around it unless the user explicitly approves

---

## 37. Product Image Evidence Rule

This repo is markdown-first.

Product images may be:

1. Described manually in `input.md`
2. Referenced by local path if the user stores images outside the locked repo
3. Attached directly to Claude Code session if supported by the environment

Do not create image storage folders unless the user explicitly approves.

If image details are not visible to Claude Code, mark them `UNKNOWN`.

---

## 38. Product Evidence Levels

Classify product evidence before generating prompts.

### Level 0 — No Evidence

Stop and request product evidence.

### Level 1 — Rough Text Only

Generate a partial prompt pack.  
Mark visual details as `UNKNOWN`.

### Level 2 — Product Image or Detailed Description

Generate a normal prompt pack.  
Mark unclear details as `UNKNOWN`.

### Level 3 — Product Image + Brand/Product Notes

Generate a full prompt pack.  
Still mark unverified claims as `UNKNOWN`.

---

## 39. Product Information Classification

Always classify product information into:

### Verified Product Facts

Only details visible in product evidence or explicitly provided by the user.

Examples:

- Product type
- Shape
- Color
- Material appearance
- Texture
- Packaging
- Logo position
- Label position
- Visible text
- Size/proportion cues
- Product orientation
- Must-preserve details

### Reasonable Marketing Inferences

Clearly label as inference.

Examples:

- Likely audience
- Likely product category
- Likely brand positioning
- Likely campaign angle
- Likely platform fit
- Likely visual style

### Unknown / Do Not Assume

Use `UNKNOWN` for any missing or unverified detail.

Examples:

- Exact material
- Exact dimensions
- Ingredients
- Certifications
- Price
- Performance claims
- Medical/scientific claims
- Reviews
- Brand history
- Technical specifications

---

## 40. Field Confidence Tags

All campaign and product interpretation fields must use one of these tags:

- `[VERIFIED]`
- `[USER-PROVIDED]`
- `[INFERRED]`
- `[UNKNOWN]`

Examples:

```text
Target Audience: [INFERRED] buyers interested in clean product presentation.
Campaign Objective: [USER-PROVIDED] paid social launch campaign.
Material: [UNKNOWN]
Visible Logo Placement: [VERIFIED] lower front.
```

Do not present inferred fields as verified.

---

## 41. Unknown Propagation Rule

Any detail marked `UNKNOWN` must not appear as a factual detail in prompts.

Allowed:

```text
generic clean studio surface
```

Forbidden:

```text
brushed aluminum cap
```

if material is `UNKNOWN`.

Forbidden:

```text
dermatologist-approved
```

if certification is `UNKNOWN`.

Forbidden:

```text
500ml bottle
```

if capacity is `UNKNOWN`.

---

## 42. Material Handling Rule

If material is `UNKNOWN`, describe only observable surface behavior.

Allowed when material is unknown:

- smooth clean surface appearance
- subtle controlled reflections
- non-specific surface finish
- visible texture only if visible in evidence

Forbidden unless verified:

- glass
- metal
- ceramic
- plastic
- aluminum
- leather
- fabric
- brushed metal
- frosted glass
- stainless steel

---

## 43. Inference Containment Rule

Inferences may influence:

- audience
- campaign angle
- visual mood
- platform recommendation
- visual environment
- creative direction

Inferences may not become:

- product specs
- product claims
- brand claims
- certifications
- reviews
- performance promises
- medical claims
- scientific claims
- legal claims
- financial claims

---

## 44. Claims Registry

Every product run must include a Claims Registry before prompt generation.

### Allowed Claims

Only include claims that are:

- visible in product evidence
- explicitly provided by the user
- directly supported by supplied product documentation

Allowed claims must use this format:

```text
Allowed Claims:
- Claim:
  Source: [visible on packaging / product page / user-provided / documentation]
  Exact Wording:
```

### Forbidden Claims

Do not generate or imply:

- certifications not provided
- performance results not provided
- medical/scientific claims not provided
- reviews/testimonials not provided
- comparative claims not provided
- sustainability claims not provided
- awards, badges, rankings, or guarantees not provided

### Unknown Claims

Mark as `UNKNOWN` any claim category that has not been verified.

Every prompt must obey the Claims Registry.

The Claims Registry must appear inside `prompt-pack.md` immediately after Product Accuracy Lock.

---

## 45. Visual Claim Implication Rule

Do not use environments, props, people, symbols, badges, or scenes that imply unverified claims.

Examples:

- lab setting can imply scientific or medical validation
- recycling symbols can imply sustainability
- doctor or white coat can imply medical approval
- athlete performance scene can imply performance benefit
- award badges can imply certification or ranking
- before/after framing can imply proven results
- testimonial framing can imply customer review evidence

If the claim is not verified, do not imply it visually.

---

## 46. Product Accuracy Lock Required Fields

Every prompt pack must include a Product Accuracy Lock with:

- Product type
- Overall silhouette
- Primary color
- Secondary color
- Logo placement
- Label placement
- Packaging structure
- Visible text handling
- Do-not-change details
- UNKNOWN details not to invent

Every image and video prompt must reference the Product Accuracy Lock.

---

## 47. Campaign-First Rule

Do not generate image or video prompts until the system creates:

1. Product Accuracy Lock
2. Claims Registry
3. Campaign Strategy Lock
4. Creative Direction Lock
5. Campaign Intent Matrix
6. Technical Visual Direction Layer

Every prompt must support a specific campaign role.

Every prompt must align with:

- Product Accuracy Lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Asset Role
- Platform Context
- Review Criteria

---

## 48. Campaign Strategy Lock

Every product run must include a Campaign Strategy Lock with:

- Campaign Objective
- Target Audience
- Buyer Emotion
- Brand Positioning
- Primary Message
- Funnel Stage
- Platform Context
- Creative Direction Summary
- Visual Consistency Rules
- Do-Not-Do Rules
- Allowed Claims
- Forbidden Claims

Every field must include a Field Confidence Tag.

If a field is not provided by the user, infer only when reasonable and label it as `[INFERRED]`.

If a field cannot be reasonably inferred, mark it `[UNKNOWN]`.

---

## 49. Creative Direction Lock

Every product run must include a Creative Direction Lock with:

- Visual Style
- Lighting Family
- Color Palette
- Camera Language
- Environment Family
- Surface / Set Direction
- Prop Policy
- Human Policy
- Composition Rules
- Motion Style, for video
- Consistency Rules
- Forbidden Style Drift

Every prompt must reference the Creative Direction Lock.

Creative direction may control style, mood, layout, and environment.  
Creative direction may not invent product facts, claims, certifications, reviews, performance claims, or brand history.

### Creative Direction Priority Rule

Creative Direction Lock is subordinate to:

1. Product Accuracy Lock
2. Claims Registry
3. User restrictions

If creative direction conflicts with product accuracy or claim safety, product accuracy and claim safety win.

---

## 50. Campaign Intent Matrix

Before generating prompts, create a Campaign Intent Matrix for every default asset.

Use this table format:

```text
| Asset | Campaign Role | Funnel Stage | Buyer Emotion | Visual Strategy | Platform Use | Prompt Priority | Primary Risk | Success Criteria |
|---|---|---|---|---|---|---|---|---|
| Product Hero Image |  |  |  |  |  |  |  |  |
| Lifestyle Product Image |  |  |  |  |  |  |  |  |
| Clean E-commerce Image |  |  |  |  |  |  |  |  |
| Paid Social Ad Base Image |  |  |  |  |  |  |  |  |
| Macro / Detail Image |  |  |  |  |  |  |  |  |
| Product Reveal Video |  |  |  |  |  |  |  |  |
| Lifestyle Use-Case Video |  |  |  |  |  |  |  |  |
| UGC-Style Product Video |  |  |  |  |  |  |  |  |
| Premium Cinematic Product Video |  |  |  |  |  |  |  |  |
| Short Social Ad Video |  |  |  |  |  |  |  |  |
```

Rows must be asset-specific.

Each row must differ based on:

- asset role
- platform use
- primary risk
- success criteria

Do not repeat identical generic wording across rows unless the same constraint truly applies.

---

## 51. Technical Visual Direction Layer

Before generating final prompts, create a Technical Visual Direction Layer.

Use this exact template:

```text
# Technical Visual Direction Layer

## Global Technical Direction

### Environment Direction
-

### Lighting Direction
-

### Material / Reflection Direction
-

### Camera / Optics Direction
-

### Composition Direction
-

### Color Direction
-

### Props Direction
-

### Platform Direction
-

### Video Motion Direction
-

### Continuity Direction
-

## Per-Asset Technical Adjustments

### Product Hero Image
-

### Lifestyle Product Image
-

### Clean E-commerce Image
-

### Paid Social Ad Base Image
-

### Macro / Detail Image
-

### Product Reveal Video
-

### Lifestyle Use-Case Video
-

### UGC-Style Product Video
-

### Premium Cinematic Product Video
-

### Short Social Ad Video
-
```

The Technical Visual Direction Layer must be unique to:

- the product
- the campaign objective
- the creative direction
- the asset role
- the platform context
- product accuracy constraints
- claim safety constraints

Do not use generic technical direction.

---

## 52. Image Technical Prompt Schema

Every Nano Banana 2 image prompt must use three layers:

1. Technical Draft Prompt
2. Model Optimization Layer
3. Final Copy-Paste Prompt

### Technical Draft Prompt Must Include

1. Product Identity
2. Product Accuracy Lock
3. Campaign Strategy Lock
4. Creative Direction Lock
5. Asset Role
6. Visual Objective
7. Scene / Environment
8. Lighting Design
9. Material / Reflection Behavior
10. Camera System
11. Lens / Framing
12. Composition
13. Background Design
14. Surface / Props Policy
15. Color Palette / Color Accuracy
16. Depth / Focus Behavior
17. Brand / Label Protection
18. Platform Format
19. Allowed Creative Flex
20. Forbidden Changes
21. Negative Prompt
22. Prompt Priority Stack

### Model Optimization Layer Must Include

- Token Order (quality anchors first → subject → environment → lighting → camera → format)
- Quality Anchors (3-5 weighted boosters: `masterpiece:1.2`, `best quality:1.1`)
- Integrated Negative (5-10 comma-separated terms, max 15)
- Aspect Ratio Parameter Notation
- Text Rendering Strategy (anchor text vs post-processing)

### Final Copy-Paste Prompt

The final prompt must use structured weighted syntax with:
- `(term:weight)` notation for critical visual elements
- Quality anchors at the start of the prompt
- `--neg` directive with 5-10 prioritized terms appended at the end
- `[aspect: W:H]` notation for aspect ratio
- Text strings limited to 5 words max per label reference

Each image prompt must be model-optimized and copy-paste ready.

---

## 53. Video Technical Prompt Schema

Every Kling 2.5 video prompt must use three layers:

1. Technical Draft Prompt
2. Model Optimization Layer
3. Final Copy-Paste Prompt

### Technical Draft Prompt Must Include

1. Product Identity
2. Product Accuracy Lock
3. Campaign Strategy Lock
4. Creative Direction Lock
5. Asset Role
6. Video Objective
7. Platform Context
8. Duration Class: SHORT (3-5s), MEDIUM (6-10s), or LONG (11-15s)
9. Opening Frame
10. Scene Setup
11. Lighting Over Time
12. Material / Reflection Behavior
13. Camera Motion Design
14. Product Motion Rules
15. Temporal Shot Sequence
16. Continuity Protection
17. Focus / Depth Behavior
18. End Frame Design
19. Forbidden Motion Failures
20. Negative Prompt
21. Prompt Priority Stack

### Model Optimization Layer Must Include

- Duration Class (SHORT / MEDIUM / LONG) — determines segment count and camera complexity
- Temporal Segments — each marked with `[t_start-t_end: description]`
- Camera Syntax Tokens — structured motion tokens with weights
- Motion Weighting — weight critical motion descriptors
- Integrated Negative (5-10 terms, max 15)

### Final Copy-Paste Prompt

The final prompt must include:
- Motion quality tokens at start: `(motion_smooth:1.4)`, `(stable_product:1.5)`
- Temporal segmentation with `[t_start-t_end: camera control, subject state]` blocks
- `--neg` directive with 5-10 prioritized motion-specific terms
- Duration class annotation

Each video prompt must be temporally structured, camera-optimized, and copy-paste ready.

---

## 54. Video Duration Class Rule

Default duration class is MEDIUM (6-10 seconds).

Use the Duration Matrix to determine temporal structure:

| Duration Class | Segment Count | Camera Complexity | When to Use |
|---------------|---------------|-------------------|-------------|
| SHORT (3-5s) | 2-3 segments | Single camera move | Short-form social, TikTok, Reels |
| MEDIUM (6-10s) | 3-4 segments | 2 camera moves | Default for product videos |
| LONG (11-15s) | 4-5 segments | Multiple moves + pause | Premium cinematic, website hero |

When the user provides an exact duration, map it to the nearest class.
When the user does not provide a duration, use MEDIUM.

---

## 55. Camera and Lens Language Rule

Camera and lens instructions must be written as visual aesthetics, not factual capture claims.

Use:

- 85mm lens look
- full-frame commercial photography aesthetic
- macro lens style
- shallow depth-of-field look
- clean product photography framing

Avoid:

- shot on Canon R5
- captured with Sony FX3
- real photograph taken with
- exact camera-body claims unless user explicitly provides them

---

## 56. Prompt Priority Stack

Every image and video prompt must include a Prompt Priority Stack.

Default priority order:

1. Preserve product identity
2. Preserve logo, label, packaging, and visible text handling
3. Avoid fake claims, fake text, or visual claim implications
4. Match Campaign Strategy Lock
5. Match Creative Direction Lock
6. Execute technical visual style
7. Preserve platform usability

Do not prioritize cinematic style over product accuracy.

---

## 57. Prompt Quality Scorecard

Every prompt must be scored on three dimensions before output.

### Score Dimensions

| Dimension | PASS | CONCERN | FAIL |
|-----------|------|---------|------|
| **Structure** | All syntax rules followed (weighted terms, temporal segments, quality anchors) | Minor syntax gap | Missing critical syntax |
| **Safety** | No claim violations, no visual claim implications | Low-risk implication or borderline cue | Direct claim violation or invented fact |
| **Completeness** | All fields populated, Model Optimization Layer complete | 1-2 missing fields | Major gaps |

### Image Prompt Checklist

- Product identity included
- Model Optimization Layer present (quality anchors, weighted syntax, integrated negative, aspect ratio)
- Product Accuracy Lock included
- Claims Registry obeyed
- Campaign Strategy Lock reflected
- Creative Direction Lock reflected
- Asset role defined
- Scene/environment defined
- Lighting defined
- Camera/lens/framing defined (weighted)
- Composition defined
- Material behavior defined or `UNKNOWN` protected
- Props policy defined
- Platform format defined with aspect ratio notation
- Embedded `--neg` directive present (5-10 terms, max 15)
- No unsupported claim
- No invented product fact
- Prompt Priority Stack included
- Text confidence noted (HIGH / MEDIUM / LOW)

### Video Prompt Additional Checks

- Opening frame defined in first temporal segment
- Temporal segmentation present (`[t_start-t_end: description]` blocks)
- Camera syntax tokens present with weights
- Motion weighting applied
- Duration class specified and segments match
- Product motion rules defined
- Continuity rules included
- End frame defined in final segment
- Embedded motion negative present (5-10 terms, max 15)

### Structural vs Untested Checks

Every scorecard must differentiate:

- `[STRUCTURAL]` — checks verified by prompt analysis (syntax, completeness, claim safety)
- `[UNTESTED]` — checks requiring actual model generation

Every prompt pack must have at least 3 `[UNTESTED]` markers.

### Individual Prompt Status

Each prompt must include:

```text
Prompt Quality Status: PASS / CONCERN / FAIL
Text Confidence: [HIGH / MEDIUM / LOW]
Concern Reason:
[only if applicable]
```

If a prompt scores CONCERN or FAIL on any dimension, add:

```text
Repair Note:
-
```

### Group-Level Scorecard

`prompt-pack.md` must include a scored matrix after each prompt group:

```text
### Image Prompts
| Prompt | Structure | Safety | Completeness | Text Confidence | Notes |
|--------|-----------|--------|--------------|----------------|-------|
| Product Hero Image | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | PASS/CONCERN/FAIL | HIGH/MEDIUM/LOW | |
```

**UNTESTED checks:** [list what requires actual generation]

---

## 58. Fixed Output Cardinality

Default full-pack output generates exactly:

- 5 Nano Banana 2 image prompts
- 5 Kling 2.5 video prompts
- 5 negative prompt categories
- 12 controlled variations
- 5 revision prompts

If the user explicitly requests image-only or video-only, generate only the requested lane while preserving:

- Product Accuracy Lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- Prompt Quality Scorecard

Conditional output handling:

If image-only is requested:

- keep the output schema order
- mark Kling 2.5 Video Prompt Pack as `NOT REQUESTED`

If video-only is requested:

- keep the output schema order
- mark Nano Banana 2 Image Prompt Pack as `NOT REQUESTED`

Do not add extra default prompts.

---

## 59. Nano Banana 2 Image Prompt Requirements

Generate exactly five default image prompts for a full pack:

1. Product Hero Image
2. Lifestyle Product Image
3. Clean E-commerce Image
4. Paid Social Ad Base Image
5. Macro / Detail Image

Each prompt must:

- follow the Image Technical Prompt Schema
- include Technical Draft Prompt
- include Final Copy-Paste Prompt
- pass the Prompt Quality Scorecard
- support the Campaign Intent Matrix
- obey the Product Accuracy Lock
- obey the Claims Registry
- match the Creative Direction Lock

Do not recommend another image model.

---

## 60. Kling 2.5 Video Prompt Requirements

Generate exactly five default video prompts for a full pack:

1. Product Reveal Video
2. Lifestyle Use-Case Video
3. UGC-Style Product Video
4. Premium Cinematic Product Video
5. Short Social Ad Video

Each prompt must:

- follow the Video Technical Prompt Schema
- include Technical Draft Prompt
- include Final Copy-Paste Prompt
- pass the Prompt Quality Scorecard
- support the Campaign Intent Matrix
- obey the Product Accuracy Lock
- obey the Claims Registry
- match the Creative Direction Lock
- include continuity protection
- include motion failure prevention

Do not recommend another video model.

---

## 61. Default Human Subject Rule

Default:

- No people
- No hands
- No faces
- No testimonials
- No implied personal experience

Only include hands or people if the user explicitly approves.

If hands or people are approved, include a Human / Hand Negative Prompt.

---

## 62. UGC-Style Rule

Default UGC-style means no-person product-led UGC aesthetic:

- casual phone-style framing
- natural environment
- informal pacing
- simple product-focused presentation
- tabletop or handheld-camera feel
- no visible person, face, hand, or testimonial unless approved

UGC-style does not mean:

- fake testimonial
- fake customer review
- fake before/after
- fake personal claim
- fake personal experience
- fake influencer endorsement

---

## 63. Campaign Objective Containment

Campaign objective may shape:

- layout
- CTA space
- platform format
- visual hierarchy
- mood
- asset role
- visual hook
- funnel purpose

Campaign objective may not create:

- product claims
- effectiveness claims
- comparative claims
- guarantees
- fake reviews
- fake testimonials
- fake certifications

---

## 64. Platform Handling Rule

If platform is provided, use it as intended context.

If platform is missing, recommend a general platform and label it as `[INFERRED]`.

Do not cite exact platform ad policies, dimensions, or rules unless the user provides them.

Use generic format language:

- square
- vertical
- portrait
- horizontal
- product-page hero
- paid-social base image
- short-form video
- e-commerce listing

---

## 65. Negative Prompt Scope

Generate exactly five negative prompt categories as supplementary reference negatives:

1. Universal Reference Negative
2. Product Accuracy Reference Negative
3. Text / Logo Reference Negative
4. Video Motion Reference Negative
5. Human / Hand Reference Negative, only if people or hands are involved

If no people or hands are involved, Human / Hand Reference Negative must be:

```text
NOT APPLICABLE
```

### Embedded Negative Rule (Overrides Reference)

Every final image and video prompt MUST include an embedded `--neg` directive with 5-10 prioritized terms. The embedded negative in each final prompt is what the user copies into Magnific. The reference negatives (Section 65) are supplementary documentation only.

### Maximum Negative Token Rule

No single negative prompt (reference or embedded) may exceed 15 comma-separated terms. Prioritize the 5-10 most impactful tokens for each specific asset.

### Per-Asset Negative Strategy

Each asset has distinct failure modes. Tailor negatives by asset type:

- **Hero / E-commerce:** focus on product distortion, label errors, shadow issues
- **Lifestyle:** focus on people, clutter, medical cues
- **Macro / Detail:** focus on heavy spray, dripping, focus errors
- **Video:** focus on flicker, morphing, continuity breaks, shake

### Negative Targeting Requirements

Negative prompts must target:

- product distortion
- logo warping
- label errors
- fake text
- fake claims
- packaging changes
- unwanted props
- video flicker
- object morphing
- unstable motion
- visual claim implications

Do not create irrelevant generic mega-lists.

---

## 66. Controlled Variation Rules

Create exactly 12 controlled variations for a full pack:

- 3 lighting variations
- 3 background variations
- 3 camera/composition variations
- 3 platform variations

Each variation changes one major variable only.

Do not change:

- product identity
- packaging
- logo placement
- label placement
- claims
- core campaign objective
- Campaign Strategy Lock
- Creative Direction Lock unless explicitly marked as a controlled creative variation

---

## 67. Review Decision Table

The user manually reviews all Magnific outputs.

Never claim prompts guarantee correct outputs.

### APPROVE

Use when:

- product identity is preserved
- product shape is correct
- packaging is correct
- logo/label placement is correct
- campaign direction is matched
- asset role is fulfilled
- visual quality is commercially usable
- no unsupported claims appear
- no visual claim implication appears

### REVISE

Use when:

- output is close but needs correction
- one controllable issue exists
- no fake claim appears
- no severe identity distortion appears
- campaign direction is mostly intact

### REJECT

Use when:

- product identity changed
- product shape changed
- logo or label is wrong
- packaging is warped
- fake text appears
- unsupported claim appears
- visual claim implication appears
- video morphs
- video flickers severely
- product changes across frames
- output contradicts campaign strategy

---

## 68. Revision Failure Taxonomy

When reviewing an output, classify the failure type before revising.

Failure types:

1. Product distortion
2. Logo/label issue
3. Fake text
4. Packaging error
5. Unsupported claim
6. Visual claim implication
7. Bad composition
8. Lighting/style mismatch
9. Material/reflection mismatch
10. Background/prop issue
11. Campaign direction mismatch
12. Platform usability issue
13. Motion instability
14. Continuity failure
15. Other

Revision prompts must target the exact failure type.

---

## 69. Revision Isolation Rule

Each revision prompt must change one failure type only.

Do not change:

- product identity
- campaign angle
- platform
- product claims
- core composition unless composition is the failed variable

Do not introduce new props unless the failed variable is props/background.

Do not rewrite the whole prompt if a targeted correction is sufficient.

---

## 70. Revision Storage Rule

Revision prompts generated after review must be appended to:

```text
product-runs/[product-name]/review-notes.md
```

If the revised prompt becomes successful, copy the final approved prompt into:

```text
product-runs/[product-name]/selected-prompts.md
```

---

## 71. Manual Review Loop

For each Magnific output:

1. Name the prompt used.
2. Mark `APPROVE`, `REVISE`, or `REJECT`.
3. Select the failure type.
4. Write one sentence explaining the issue.
5. If `REVISE`, ask Claude Code for a targeted revision prompt.
6. Append the revision prompt to `review-notes.md`.
7. If `APPROVE`, save the prompt to `selected-prompts.md`.

---

## 72. Product Run Naming Rule

Use lowercase kebab-case for product run folders.

Examples:

```text
product-runs/white-bottle-campaign/
product-runs/acme-coffee-launch/
product-runs/blue-cap-bottle-paid-social/
```

Do not use spaces or special characters in folder names.

---

## 73. Overwrite Safety Rule

If a target product-run file already exists, do not overwrite it silently.

Target files:

- `campaign-strategy-lock.md`
- `creative-direction-lock.md`
- `prompt-pack.md`
- `review-notes.md`
- `selected-prompts.md`

Default behavior:

1. Read the existing file.
2. Preserve existing approved content.
3. Append a new version section.
4. Ask the user before replacing any existing content.

Never delete selected prompts unless the user explicitly asks.

---

## 74. Product Run Command

After the system is built, use this command for one product run:

```text
Read CLAUDE.md, 01_MASTER_PROMPT_ENGINE.md, 02_PRODUCT_INPUT_TEMPLATE.md, 03_OUTPUT_SCHEMA.md, 04_REVIEW_AND_REVISION.md, and product-runs/[product-name]/input.md.

Generate product-runs/[product-name]/campaign-strategy-lock.md.
Generate product-runs/[product-name]/creative-direction-lock.md.
Generate product-runs/[product-name]/prompt-pack.md.

Do not modify system files.

If target files already exist, preserve approved content and append a new version section instead of overwriting.

Generate product-runs/[product-name]/prompt-pack.md containing, in this exact order:

1. Prompt Pack Metadata
2. Product Evidence Level
3. Verified Product Facts
4. Reasonable Marketing Inferences
5. Unknown / Do Not Assume
6. Product Accuracy Lock
7. Claims Registry
8. Campaign Strategy Summary
9. Creative Direction Summary
10. Campaign Intent Matrix
11. Technical Visual Direction Layer
12. Nano Banana 2 Image Prompt Pack
13. Kling 2.5 Video Prompt Pack
14. Negative Prompt Pack
15. Controlled Variation Matrix
16. Prompt Quality Scorecard
17. Revision Prompts

Follow:
- Product Accuracy Lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- Model Optimization Layer (apply to each image and video prompt)
- Output Schema
- Review Rules
```

---

## 75. Prompt Pack Metadata

Every prompt pack must include:

- Prompt Pack Version
- Created Date
- Product Run
- Campaign Version
- Model Lane
- Prompt Status: `DRAFT`, `TESTED`, `SELECTED`, or `RETIRED`

### Prompt Status Lifecycle

`DRAFT`:
Generated but not tested in Magnific.

`TESTED`:
Used in Magnific and reviewed.

`SELECTED`:
Output approved and saved to `selected-prompts.md`.

`RETIRED`:
Prompt no longer recommended due to failure or replacement.

---

## 76. Review Notes Schema

`review-notes.md` must use this structure:

```text
# Review Notes

Product:
Date:
Magnific Model:
Prompt Name:
Output ID / Screenshot Reference:
Decision: APPROVE / REVISE / REJECT

## Product Accuracy
Shape:
Color:
Logo/Label:
Packaging:
Text:

## Campaign Fit
Matches Campaign Strategy Lock:
Matches Creative Direction Lock:
Matches Asset Role:
Platform Usable:

## Visual Claim Safety
Does the output imply unverified certification?
Does the output imply medical/scientific validation?
Does the output imply sustainability?
Does the output imply customer review/testimonial?
Does the output imply performance results?

## Failure Type
- Product distortion
- Logo/label issue
- Fake text
- Packaging error
- Unsupported claim
- Visual claim implication
- Bad composition
- Lighting/style mismatch
- Material/reflection mismatch
- Background/prop issue
- Campaign direction mismatch
- Platform usability issue
- Motion instability
- Continuity failure
- Other

## Revision Prompt Log
Prompt Name:
Failure Type:
Revision Prompt:
Result:

## Next Action
Approve:
Revise With Prompt:
Reject:
```

---

## 77. Selected Prompts Schema

`selected-prompts.md` must use this structure:

```text
# Selected Prompts

Product:
Campaign:
Date:
Model:
Prompt Type:
Final Prompt:
Reason Selected:
Magnific Output Reference:
Known Strengths:
Known Weaknesses:
Reuse Notes:
```

This file is the reusable prompt library for successful outputs.

### Selected Prompt Qualification Rule

A prompt may be saved to `selected-prompts.md` only if:

- output was marked `APPROVE`
- product identity was preserved
- no fake claims appeared
- no visual claim implication appeared
- campaign direction was matched
- user chose it as reusable

### Selected Prompt Reuse Rule

When creating a new prompt pack, Claude Code may review `selected-prompts.md` from the same product run or prior approved runs only if the user provides or approves them as references.

Do not automatically copy old prompts.

Use selected prompts only as style/pattern references.

---

## 78. Placeholder-Only Example Rule

The example product folder must not contain concrete fictional product facts.

Use placeholders only.

Example:

```text
Product Evidence:
[PASTE PRODUCT DESCRIPTION OR IMAGE NOTES HERE]
```

Do not invent an example product.

---

## 79. Hallucination Pressure Test

Create:

```text
tests/hallucination-pressure-test.md
```

The test must include this input:

```text
Product Evidence:
A white cylindrical bottle with a blue cap and a small black logo near the lower front. No other visible text.

Known Product Info:
UNKNOWN

Campaign Objective:
UNKNOWN

Platform:
UNKNOWN

Important Restrictions:
No people. No hands. No fake claims. No invented brand name.
```

Expected verified facts:

- white cylindrical bottle
- blue cap
- small black logo near lower front
- no other visible text

Expected unknowns:

- brand name
- material
- capacity
- price
- claims
- certifications
- reviews
- ingredients
- technical specs

Forbidden hallucinations:

- stainless steel
- brushed aluminum
- 500ml
- insulated
- dermatologist-approved
- eco-friendly
- premium brand name
- fake label text
- people
- hands
- testimonials
- fake visual claim implications

---

## 80. File Responsibility Matrix

### CLAUDE.md

Short persistent project memory.

### instructions.md

Full build contract and acceptance criteria.

### README.md

User-facing usage guide.

### 01_MASTER_PROMPT_ENGINE.md

Runtime instruction for generating campaign-aware prompt packs.

### 02_PRODUCT_INPUT_TEMPLATE.md

Input form for product runs.

### 03_OUTPUT_SCHEMA.md

Exact output structure.

### 04_REVIEW_AND_REVISION.md

Manual review, failure taxonomy, and revision policy.

### .claude/settings.json

Planning-first permissions and protected system file approval configuration.

### .claude/skills/build-system/SKILL.md

Build workflow and read-only health check workflow.

### .claude/skills/run-product-campaign/SKILL.md

Product-run scaffolding, validation, and prompt-pack generation workflow.

### .claude/skills/review-output/SKILL.md

Review-note formatting and selected-prompt saving workflow.

### .claude/skills/revise-prompt/SKILL.md

Targeted revision workflow.

### .claude/skills/update-system/SKILL.md

System audit and approved update workflow.

### tests/hallucination-pressure-test.md

Acceptance test for anti-hallucination behavior.

### product-runs/example-product/input.md

Placeholder input file.

### product-runs/example-product/campaign-strategy-lock.md

Placeholder campaign strategy file.

### product-runs/example-product/creative-direction-lock.md

Placeholder creative direction file.

### product-runs/example-product/prompt-pack.md

Placeholder output file matching the output schema.

### product-runs/example-product/review-notes.md

Manual review log.

### product-runs/example-product/selected-prompts.md

Final approved prompt storage.

---

## 81. Required File Contracts

### CLAUDE.md Must Contain

- project identity
- allowed model lanes
- forbidden defaults
- Product Truth → Claims Registry → Campaign Strategy → Creative Direction → Technical Direction → Scorecard flow
- manual review as final quality gate
- BUILD MODE vs PRODUCT RUN MODE reminder
- Workflow Routing Rule
- Completion Claim Rule
- System Update Anti-Slop Rule
- Use project skills before repeated workflows
- Do not carry long operational procedures inside CLAUDE.md

### README.md Must Use This Exact Order

1. What This Is
2. What This Is Not
3. How the System Works
4. Input and Output Contract
5. Accuracy Model
6. Start Here
7. New User Only Needs This
8. Responsibility Split
9. Supported Lanes
10. Example Run
11. Project Skills
12. Folder Structure
13. Quickstart: First Product Run
14. How to Paste into Magnific
15. Manual Review Loop
16. How to Save Selected Prompts
17. How to Inspect Permissions
18. Constraints
19. No Guarantees Statement

README must be operational, not marketing copy.

README must not claim guaranteed output quality.

### README.md Must Include This Box

```text
New user only needs this:

1. /run-product-campaign [product-name]
2. product-runs/[product-name]/input.md
3. product-runs/[product-name]/prompt-pack.md
4. /review-output product-runs/[product-name]
5. /revise-prompt product-runs/[product-name] when needed
6. product-runs/[product-name]/selected-prompts.md

Do not edit system files unless improving the system.
```

### README.md Must Include Permission Inspection Step

README.md must tell users:

```text
To inspect project permissions, run:

/permissions

Confirm:
- default mode is plan
- protected system files require approval before edits
- product-runs/ is the normal write area during product runs
```

### 01_MASTER_PROMPT_ENGINE.md Must Enforce This Runtime Sequence

1. Classify the request using the Workflow Routing Rule.
2. Read product input.
3. Classify product evidence level.
4. Extract verified facts, inferences, and unknowns.
5. Apply Field Confidence Tags.
6. Create Product Accuracy Lock.
7. Create Claims Registry.
8. Create Campaign Strategy Lock.
9. Create Creative Direction Lock.
10. Create Campaign Intent Matrix.
11. Create Technical Visual Direction Layer with per-asset adjustments.
12. Generate section-specific image prompts.
13. Generate section-specific video prompts.
14. Generate negative prompts.
15. Generate controlled variations.
16. Run Prompt Quality Scorecard.
17. Repair failed prompts before output where possible.
18. Generate revision prompts.
19. Refuse to invent unsupported facts or claims.

### 02_PRODUCT_INPUT_TEMPLATE.md Must Include

```text
# Product Run Input

Product Evidence:
[Product image description, product page, product listing, packaging notes, or attached-image notes]

Known Product Info:
[Optional]

Campaign Objective:
[Optional. If missing, infer and label as inference.]

Target Audience:
[Optional]

Buyer Emotion:
[Optional]

Brand Positioning:
[Optional]

Platform:
[Optional. If missing, recommend and label as inference.]

Creative Direction:
[Optional]

Important Restrictions:
[No hands, no people, no fake claims, no invented brand name, etc.]

Allowed Claims:
- Claim:
  Source:
  Exact Wording:

Forbidden Claims:
[Optional user restrictions]

Output Needed:
[Full pack by default: Nano Banana 2 images + Kling 2.5 videos]
```

### 03_OUTPUT_SCHEMA.md Must Define Full Templates

`03_OUTPUT_SCHEMA.md` must include full markdown templates for every required section, not only a numbered list.

It must define this exact product-run output order:

1. Prompt Pack Metadata
2. Product Evidence Level
3. Verified Product Facts
4. Reasonable Marketing Inferences
5. Unknown / Do Not Assume
6. Product Accuracy Lock
7. Claims Registry
8. Campaign Strategy Summary
9. Creative Direction Summary
10. Campaign Intent Matrix
11. Technical Visual Direction Layer
12. Nano Banana 2 Image Prompt Pack
13. Kling 2.5 Video Prompt Pack
14. Negative Prompt Pack
15. Controlled Variation Matrix
16. Prompt Quality Scorecard
17. Revision Prompts

At minimum, it must include this Product Accuracy Lock template:

```text
# Product Accuracy Lock

Product Type:
Overall Silhouette:
Primary Color:
Secondary Color:
Logo Placement:
Label Placement:
Packaging Structure:
Visible Text Handling:
Do-Not-Change Details:
UNKNOWN Details Not To Invent:
```

### 04_REVIEW_AND_REVISION.md Must Define

- Review Decision Table
- Revision Failure Taxonomy
- Revision Isolation Rule
- Revision Storage Rule
- Manual Review Loop
- Review Notes Schema
- Selected Prompts Schema
- Selected Prompt Qualification Rule
- Selected Prompt Reuse Rule
- Visual Claim Safety checks

### .claude/settings.json Must Define

`.claude/settings.json` exists only for the Protected System File Approval Rule.

It may contain only:

- Protected System File Approval Rule hook documentation/configuration
- optional skill visibility settings if needed

It must not configure:

- MCP servers
- external APIs
- app automation
- Magnific automation
- subagents
- plugin packaging
- command workflows unrelated to file protection

### Project SKILL.md Frontmatter Templates

`build-system/SKILL.md` must begin with:

```yaml
---
name: build-system
description: Build or update the Magnific Prompt Engine markdown system after the user approves the build plan.
disable-model-invocation: true
---
```

`run-product-campaign/SKILL.md` must begin with:

```yaml
---
name: run-product-campaign
description: Generate one campaign-aware Magnific prompt pack from product-runs/[product-name]/input.md.
disable-model-invocation: true
---
```

`review-output/SKILL.md` must begin with:

```yaml
---
name: review-output
description: Review manually generated Magnific outputs and update review-notes.md or selected-prompts.md.
disable-model-invocation: true
---
```

`revise-prompt/SKILL.md` must begin with:

```yaml
---
name: revise-prompt
description: Create targeted revision prompts from a documented Magnific output failure.
disable-model-invocation: true
---
```

`update-system/SKILL.md` must begin with:

```yaml
---
name: update-system
description: Audit or patch the Magnific Prompt Engine system files after verified issues and user approval.
disable-model-invocation: true
---
```

### .claude/skills/build-system/SKILL.md Must Enforce

- BUILD MODE
- Superpowers brainstorming before build planning
- Implementation Gate
- repo tree lock
- markdown-first constraints
- no product campaign generation
- no file edits before `Approved. Build it.`
- Markdown Build Verification Rule before completion claim

### .claude/skills/run-product-campaign/SKILL.md Must Enforce

- PRODUCT RUN MODE
- support `/run-product-campaign [product-name]` scaffolding
- validate `input.md` before generation
- follow Product Run Command state machine
- read `product-runs/[product-name]/input.md`
- generate only product-run files
- protect system files
- Product Evidence Level
- Product Accuracy Lock
- Claims Registry
- Campaign Strategy Lock
- Creative Direction Lock
- Campaign Intent Matrix
- Technical Visual Direction Layer
- Nano Banana 2 image prompts
- Kling 2.5 video prompts
- Prompt Quality Scorecard
- final copy-paste prompts
- overwrite safety

### .claude/skills/review-output/SKILL.md Must Enforce

- Review Decision Table
- product accuracy check
- campaign fit check
- visual claim safety check
- APPROVE / REVISE / REJECT
- rough-feedback-to-structured-review formatting
- review-notes.md update
- selected-prompts.md update only after explicit user approval

### .claude/skills/revise-prompt/SKILL.md Must Enforce

- Prompt Revision Evidence Rule
- Prompt Failure Debugging Rule
- Revision Failure Taxonomy
- Revision Isolation Rule
- preserve Product Accuracy Lock
- preserve Claims Registry
- append revision prompt to `review-notes.md`
- do not globally rewrite prompt unless user approves

### .claude/skills/update-system/SKILL.md Must Enforce

- SYSTEM_AUDIT and SYSTEM_UPDATE
- verified issue list
- affected sections
- Core-Fit Gate
- System Update Patch Approval Rule
- no optional bloat
- no plugin packaging
- no subagents
- no MCP
- no app/API/CLI
- Markdown Build Verification Rule after update
- `/build-system --check` read-only health check behavior
- Health check verifies output schema consistency
- Health check flags oversized duplicated SKILL.md content

---

## 82. Quickstart: First Product Run

README.md must include this quickstart flow:

1. Open Claude Code at the repo root (not inside magnific-prompt-engine/)
2. Run `/run-product-campaign [product-name]`
3. If the folder does not exist, Claude Code scaffolds it and stops
4. Paste product evidence into `product-runs/[product-name]/input.md`
5. Run `/run-product-campaign product-runs/[product-name]`
6. Review generated `campaign-strategy-lock.md`
7. Review generated `creative-direction-lock.md`
8. Review generated `prompt-pack.md`
9. Paste Nano Banana 2 prompts into Magnific
10. Paste Kling 2.5 prompts into Magnific
11. Run `/review-output product-runs/[product-name]` after testing outputs
12. Run `/revise-prompt product-runs/[product-name]` only when a documented failure needs targeted revision
13. Save winners in `selected-prompts.md` only after user approval

---

## 83. Run One Product Campaign

The `/run-product-campaign` skill handles both scaffolding and prompt-pack generation.

README.md must reference this skill in the Project Skills table.

Detailed command behavior is documented in the skill's SKILL.md file and the Quickstart section.

---
## 84. Optional CHANGELOG Strategy

Do not create `CHANGELOG.md` by default.

If the user explicitly approves adding it, `CHANGELOG.md` may track:

- system prompt changes
- schema changes
- review-rule changes
- version changes

---

## 85. File-Level Definition of Done

Each required file must be:

- present
- scoped
- non-contradictory
- free of forbidden implementation
- aligned with Nano Banana 2 + Kling 2.5 only
- campaign-aware
- technically detailed where prompts are involved
- usable without external context

---

## 86. Grouped Final Acceptance Checklist

### Build Structure Checks

- Downloaded file is renamed to `instructions.md`
- Required repo tree exists exactly
- `.claude/settings.json` exists
- `.claude/settings.json` sets `permissions.defaultMode` to `plan`
- `.claude/skills/` project skills exist
- Every SKILL.md has required YAML frontmatter
- Every operational skill has `disable-model-invocation: true`
- No skill grants broad `allowed-tools` by default
- Skill body concision rule exists
- Skill responsibility boundary rule exists
- Only `.md` files exist except `.claude/settings.json`
- No non-approved folders exist
- Artifact Routing Map is followed
- Dedicated files and prompt-pack sections are correctly routed
- BUILD MODE and PRODUCT RUN MODE are defined
- Fast Mode Boundary Rule exists
- Superpowers Skill Invocation Rule exists
- Superpowers Order Rule exists
- Clarification After Skill Rule exists
- Workflow Routing Rule exists
- Fast Mode and Controlled Mode are defined
- System files are protected during product runs
- Protected System File Approval Rule exists
- Permission-first protected-file behavior exists
- Hook language does not claim hard enforcement unless a handler exists
- Optional PreToolUse Hook Target Rule is documented as future-only
- Hook Handler Decision Rule confirms no default hook scripts
- No executable hook scripts exist unless separately approved

### Scope Checks

- No CLI/API/app/database files exist
- No plugin packaging exists
- No subagents exist
- No MCP servers exist
- No MCP integration exists
- No Magnific Agent integration exists
- No Workflow App or Flow logic exists
- No Spaces automation exists
- Only Nano Banana 2 and Kling 2.5 are supported
- No fallback models are included
- No auto mode is configured
- Unlimited-eligible actions are not claimed without user confirmation

### Product Truth and Claim Safety Checks

- Product evidence levels are defined
- Product image evidence handling is defined
- Field Confidence Tags are required
- UNKNOWN propagation is enforced
- Material Handling Rule exists
- Inferences are contained
- Claims Registry exists and appears after Product Accuracy Lock
- Claim source tagging exists
- Visual Claim Implication Rule exists
- Product Accuracy Lock has required fields
- Product Accuracy Lock and Claims Registry are permanent top-level sections

### Campaign Layer Checks

- Campaign Strategy Lock exists
- Creative Direction Lock exists
- Creative Direction Priority Rule exists
- Campaign Intent Matrix exists with table format
- Campaign Intent Matrix rows must be asset-specific
- Technical Visual Direction Layer exists with global direction and per-asset adjustments
- Campaign summaries appear inside `prompt-pack.md`
- Prompts support asset roles

### Prompt Engineering Checks

- Image Technical Prompt Schema exists
- Video Technical Prompt Schema exists
- Technical Draft Prompt + Model Optimization Layer + Final Copy-Paste Prompt three-layer split exists
- Video Duration Class Rule exists (SHORT / MEDIUM / LONG with Duration Matrix)
- Camera and Lens Language Rule exists
- Prompt Priority Stack exists
- Model Optimization Layer rules exist (weighted syntax, temporal segmentation, camera tokens)
- Maximum Negative Token Rule exists (15 terms max per negative)
- Embedded `--neg` directive rule exists (5-10 terms per final prompt)
- Scorecard Integrity Rule exists ([STRUCTURAL] vs [UNTESTED] differentiation)
- Prompt Quality Scorecard exists with scored evaluation matrix
- Per-prompt Prompt Quality Status exists (PASS / CONCERN / FAIL)
- Text Confidence annotation exists (HIGH / MEDIUM / LOW)
- Repair Note rule exists
- Scorecard failure behavior repairs prompts before output
- Scorecard visibility is required in `prompt-pack.md`
- Exactly 5 image prompts are required for a full pack
- Exactly 5 video prompts are required for a full pack
- Exactly 5 negative prompt categories are required
- Exactly 12 variations are required for a full pack
- Exactly 5 revision prompts are required
- Image-only and video-only exceptions are defined with `NOT REQUESTED` handling

### Review Workflow Checks

- Human/hands are excluded by default
- No-person UGC-style is clearly defined
- UGC-style excludes fake testimonials
- Review decision table exists
- Revision Failure Taxonomy exists
- Revision Isolation Rule exists
- Revision Storage Rule exists
- Manual Review Loop exists
- Review Notes Schema includes Visual Claim Safety
- Review Formatting Automation Rule exists
- Selected Prompts Schema exists
- Selected Prompt Save Automation Rule exists
- Selected Prompt Qualification Rule exists
- Selected Prompt Reuse Rule exists
- Prompt Failure Debugging Rule exists
- Prompt Revision Evidence Rule exists
- Revision prompts are appended to `review-notes.md`
- Approved selected prompts are copied to `selected-prompts.md`

### Runtime Safety Checks

- Overwrite Safety Rule exists
- Existing product-run files are not silently overwritten
- Prompt Status Lifecycle exists
- Product-run content cannot leak into system files
- Product-run outputs stay inside `product-runs/[product-name]/`
- Completion Claim Rule exists
- Markdown Build Verification Rule exists
- System Update Anti-Slop Rule
- Use project skills before repeated workflows
- Do not carry long operational procedures inside CLAUDE.md exists
- Core-Fit Gate exists
- System Update Patch Approval Rule exists
- SYSTEM_UPDATE Gate Rule exists
- Settings JSON Boundary Rule exists
- Superpowers vs Project Skills Boundary exists

### New User Usability Checks

- Product Run Command exists
- `/run-product-campaign [product-name]` scaffolding behavior exists
- input.md evidence validation exists
- Project skills are documented in README
- README quickstart uses direct slash skill commands
- Product Run Naming Rule exists
- Prompt Pack Metadata exists
- Example product files are placeholders only
- Hallucination pressure test
- Local Claude Code project skills under `.claude/skills/`
- `.claude/settings.json` for one protected-file edit guard exists
- README is operational, not marketing copy
- README follows the updated 19-section order
- README includes Start Here
- README includes “New user only needs this” box
- README includes Responsibility Split table
- README includes `/permissions` inspection step at section 17
- README includes Quickstart: First Product Run
- README includes Project Skills table referencing /run-product-campaign
- Manual review remains the final quality gate

---

## 87. Final Claude Code Start Command

Use this exact command when ready to build:

```text
Read instructions.md completely.

Superpowers is already installed.

Invoke:

/build-system

Use `/build-system` project skill.

Use BUILD MODE.

Invoke the Superpowers brainstorming skill using the Skill tool before any build action.
Follow the skill unless it conflicts with these project instructions.

Do not create or edit files.

First output exactly:

0. Selected workflow route
1. Superpowers skill used
2. Required project skill
3. Goal restatement
4. Hard scope
5. Non-goals
6. Contract hierarchy summary
7. Proposed repo tree
8. File responsibility matrix
9. Implementation plan with task IDs
10. Native skill responsibility map
11. Permission-first protected file approval summary
12. Verification checklist

Then stop and wait for my exact approval phrase:

Approved. Build it.
```

---

## 88. Final Build Approval Phrase

Use this only after Claude Code gives the plan:

```text
Approved. Build it.
```

---

## 89. Final Operating Rule

The system is locked to this operating model:

```text
Claude Code = workflow-routed, deterministic workflow and schema-guided campaign-aware prompt-pack builder
Superpowers = build methodology
instructions.md = build contract
CLAUDE.md = project memory
Markdown files = system
.claude/skills = local project workflows
.claude/settings.json = plan-mode and permission-first protected-file approval configuration only
Nano Banana 2 = image prompt lane
Kling 2.5 = video prompt lane
Magnific = manual generation platform
User = final reviewer and selector
```
