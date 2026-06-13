# Graph Report - /Users/vusek/Documents/System/magnific-prompt-engine  (2026-06-12)

## Corpus Check
- cluster-only mode — file stats not available

## Summary
- 91 nodes · 147 edges · 12 communities (10 shown, 2 thin omitted)
- Extraction: 87% EXTRACTED · 13% INFERRED · 0% AMBIGUOUS · INFERRED: 19 edges (avg confidence: 0.82)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `1bb30fcc`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- [[_COMMUNITY_Campaign Strategy & Claims|Campaign Strategy & Claims]]
- [[_COMMUNITY_Build System & Review|Build System & Review]]
- [[_COMMUNITY_Product Assets & Videos|Product Assets & Videos]]
- [[_COMMUNITY_Campaign Constraints & Rules|Campaign Constraints & Rules]]
- [[_COMMUNITY_Creative Direction & Aesthetics|Creative Direction & Aesthetics]]
- [[_COMMUNITY_Prompt Pack & Verified Facts|Prompt Pack & Verified Facts]]
- [[_COMMUNITY_Example Product Templates|Example Product Templates]]
- [[_COMMUNITY_Technical Visual & Video|Technical Visual & Video]]
- [[_COMMUNITY_Hallucination & Evidence Rules|Hallucination & Evidence Rules]]
- [[_COMMUNITY_Review & Prompt Selection|Review & Prompt Selection]]
- [[_COMMUNITY_Test Criteria & Procedure|Test Criteria & Procedure]]
- [[_COMMUNITY_Selected Prompts|Selected Prompts]]

## God Nodes (most connected - your core abstractions)
1. `Prompt Pack` - 18 edges
2. `BIONA Hypochlorous Spray Prompt Pack` - 16 edges
3. `BIONA Pure Hypochlorous Acid Spray 0.018%` - 14 edges
4. `Technical Visual Direction` - 11 edges
5. `Creative Direction Lock` - 8 edges
6. `Campaign Strategy Lock` - 6 edges
7. `Input` - 6 edges
8. `No People Constraint` - 5 edges
9. `Example Product Input` - 4 edges
10. `No Hands Constraint` - 4 edges

## Surprising Connections (you probably didn't know these)
- `campaign-strategy-lock.md (biona-hypochlorous-spray)` --references--> `Campaign Strategy Summary`  [INFERRED]
  product-runs/biona-hypochlorous-spray/campaign-strategy-lock.md → 03_OUTPUT_SCHEMA.md
- `creative-direction-lock.md (biona-hypochlorous-spray)` --references--> `Creative Direction Summary`  [INFERRED]
  product-runs/biona-hypochlorous-spray/creative-direction-lock.md → 03_OUTPUT_SCHEMA.md
- `Hallucination Pressure Test` --references--> `Prompt Pack`  [EXTRACTED]
  tests/hallucination-pressure-test.md → product-runs/hallucination-pressure-test/prompt-pack.md
- `Hallucination Pressure Test` --references--> `Review Notes`  [INFERRED]
  tests/hallucination-pressure-test.md → product-runs/hallucination-pressure-test/review-notes.md
- `Hallucination Pressure Test` --references--> `Selected Prompts`  [INFERRED]
  tests/hallucination-pressure-test.md → product-runs/hallucination-pressure-test/selected-prompts.md

## Import Cycles
- None detected.

## Communities (12 total, 2 thin omitted)

### Community 0 - "Campaign Strategy & Claims"
Cohesion: 0.12
Nodes (19): campaign-strategy-lock.md (biona-hypochlorous-spray), creative-direction-lock.md (biona-hypochlorous-spray), input.md (biona-hypochlorous-spray), BIONA Pure Hypochlorous Acid Spray, Campaign Intent Matrix, Campaign Strategy, Campaign Strategy Summary, Claims Registry (+11 more)

### Community 1 - "Build System & Review"
Cohesion: 0.23
Nodes (9): build-system SKILL.md, Completion Claim Rule, review-output SKILL.md, revise-prompt SKILL.md, Revision Failure Taxonomy, run-product-campaign SKILL.md, update-system SKILL.md, Visual Claim Safety (+1 more)

### Community 2 - "Product Assets & Videos"
Cohesion: 0.28
Nodes (13): BIONA Pure Hypochlorous Acid Spray 0.018%, Honeydew Labs, Macro / Detail Image, BIONA Hypochlorous Spray Prompt Pack, Clean E-commerce Image, Kling 2.5, Lifestyle Use-Case Video, Nano Banana 2 (+5 more)

### Community 3 - "Campaign Constraints & Rules"
Cohesion: 0.29
Nodes (11): All Claims Forbidden, Campaign Strategy Lock, Hallucination Pressure Test, Input, No Fake Claims Constraint, No Hands Constraint, No Invented Brand Name Constraint, No People Constraint (+3 more)

### Community 4 - "Creative Direction & Aesthetics"
Cohesion: 0.38
Nodes (7): Clean Studio Aesthetic, Creative Direction Lock, Gentle Slow Reveal Motion, Neutral Color Palette, No Props Policy, Product-Centered Framing, Soft Studio Lighting

### Community 5 - "Prompt Pack & Verified Facts"
Cohesion: 0.47
Nodes (6): Campaign Intent Matrix, Claims Registry, Macro/Detail Image, Product Accuracy Lock, Prompt Pack, Verified Product Facts

### Community 6 - "Example Product Templates"
Cohesion: 0.60
Nodes (5): Example Product Campaign Strategy Lock, Example Product Creative Direction Lock, Example Product Input, Example Product Prompt Pack, Example Product Review Notes

### Community 7 - "Technical Visual & Video"
Cohesion: 0.40
Nodes (5): Lifestyle Product Image, Paid Social Ad Base Image, Premium Cinematic Product Video, Product Hero Image, Technical Visual Direction

### Community 8 - "Hallucination & Evidence Rules"
Cohesion: 0.67
Nodes (3): Forbidden Hallucinations, Product Evidence, Verified Facts

### Community 9 - "Review & Prompt Selection"
Cohesion: 0.67
Nodes (3): Hallucination Pressure Test, Review Notes, Selected Prompts

## Knowledge Gaps
- **19 isolated node(s):** `BIONA Pure Hypochlorous Acid Spray`, `Runtime Sequence`, `Field Confidence Tags`, `Product Evidence Levels`, `Contract Hierarchy` (+14 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Prompt Pack` connect `Prompt Pack & Verified Facts` to `Review & Prompt Selection`, `Product Assets & Videos`, `Technical Visual & Video`?**
  _High betweenness centrality (0.045) - this node is a cross-community bridge._
- **Why does `Creative Direction Lock` connect `Creative Direction & Aesthetics` to `Campaign Constraints & Rules`?**
  _High betweenness centrality (0.020) - this node is a cross-community bridge._
- **Why does `BIONA Hypochlorous Spray Prompt Pack` connect `Product Assets & Videos` to `Technical Visual & Video`?**
  _High betweenness centrality (0.018) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `BIONA Hypochlorous Spray Prompt Pack` (e.g. with `BIONA Hypochlorous Spray Review Notes` and `BIONA Hypochlorous Spray Selected Prompts`) actually correct?**
  _`BIONA Hypochlorous Spray Prompt Pack` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `BIONA Pure Hypochlorous Acid Spray`, `Runtime Sequence`, `Field Confidence Tags` to the rest of the system?**
  _24 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Campaign Strategy & Claims` be split into smaller, more focused modules?**
  _Cohesion score 0.12380952380952381 - nodes in this community are weakly interconnected._