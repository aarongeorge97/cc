---
description: Run the 20-agent script writing pipeline end-to-end. Pass the path to a product brief, e.g. /write-script product-brief.example.md
argument-hint: <path-to-product-brief>
allowed-tools: Bash, Read, Write, Edit, Agent
---

You are the **orchestrator** for a 20-agent video script writing pipeline. Your job is to invoke each phase's subagents in the right order, enforce quality gates, and produce a final production-ready script.

## Run input

The user invoked: `/write-script $ARGUMENTS`

If `$ARGUMENTS` is empty, default to `product-brief.example.md` in the repo root and tell the user that's what you're doing.

## Step 0 — Set up the run directory

1. Generate a run id: `RUN_ID=$(date -u +%Y%m%dT%H%M%SZ)`. Hold this value and use it everywhere below — every subagent prompt must reference the concrete path `./script-runs/<RUN_ID>/`.
2. `mkdir -p ./script-runs/$RUN_ID`
3. Copy the product brief into the run directory: `cp "$ARGUMENTS" ./script-runs/$RUN_ID/product-brief.md` (resolve `$ARGUMENTS` as a relative or absolute path; if it doesn't exist, error out).
4. Read the product brief once yourself so you know the **target word count** — you'll need it for the loop caps and the budget enforcer.
5. Tell the user: "Run id: <RUN_ID>. Working directory: ./script-runs/<RUN_ID>/. Starting Phase 1 (research, 3 agents in parallel)..."

## Phase 1 — Research (parallel, then synthesize)

Send a single message with **three Agent tool calls in parallel**:
- `phase1-youtube-researcher` → tell it the run id and that the product brief is at `./script-runs/<RUN_ID>/product-brief.md`.
- `phase1-reddit-researcher` → same.
- `phase1-twitter-researcher` → same.

Wait for all three to finish. Verify each wrote its expected output file:
- `./script-runs/<RUN_ID>/phase1-youtube.md`
- `./script-runs/<RUN_ID>/phase1-reddit.md`
- `./script-runs/<RUN_ID>/phase1-twitter.md`

Then invoke `phase1-research-synthesizer` to write `./script-runs/<RUN_ID>/ammunition-file.md`.

Report progress to the user: "Phase 1 done. Starting Phase 2..."

## Phase 2 — Strategy (sequential)

Invoke in order, waiting for each output before starting the next:
1. `phase2-audience-profiler` → `audience-profile.md`
2. `phase2-angle-selector` → `angle.md`
3. `phase2-brand-voice` → `brand-voice.md`

Report: "Phase 2 done. Starting Phase 3 writing..."

## Phase 3 — Writing with manager gates

For each of the three writer/manager pairs below, run this loop **up to 3 iterations**. If you reach iteration 3 without a PASS, stop the pipeline and surface the latest manager feedback to the user.

### 3a. Hook loop
1. Invoke `phase3-hook-writer` → produces `hook-draft.md`.
2. Invoke `phase3-hook-manager` → produces `hook-score.md` and (on FAIL) `hook-feedback.md`.
3. If any hook scored < 10 on any dimension: delete (or ignore) the previous draft, leave `hook-feedback.md` in place, and re-invoke `phase3-hook-writer` for another iteration.
4. When the manager marks at least the **PRIMARY** hook as PASS (all 10s), extract its text from the writer's draft and write it to `./script-runs/<RUN_ID>/hook.md` using the Write tool.

### 3b. Body loop
Same shape, with `phase3-body-writer` ↔ `phase3-body-manager`. On PASS, extract the final draft body and write to `./script-runs/<RUN_ID>/body.md`.

### 3c. CTA loop
Same shape, with `phase3-cta-writer` ↔ `phase3-cta-manager`. On PASS, extract the primary CTA and write to `./script-runs/<RUN_ID>/cta.md`.

Report: "Phase 3 done. Hook + body + CTA approved. Starting Phase 4 quality control..."

## Step 3.5 — Assemble draft script

Concatenate `hook.md` + blank line + `body.md` + blank line + `cta.md` into `./script-runs/<RUN_ID>/draft-script.md`. Use the Write tool. This is the input to Phase 4.

## Phase 4 — Quality control (sequential)

Invoke in order:
1. `phase4-novelty-scorer` → `qc-novelty.md`
2. `phase4-intensity-scorer` → `qc-intensity.md`
3. `phase4-filler-detector` → `qc-filler.md`
4. `phase4-budget-enforcer` → `length-checked.md` (must be exact target word count)

Sanity-check `length-checked.md`'s word count against the target. If off by more than 5%, re-invoke `phase4-budget-enforcer` once with feedback noting the discrepancy.

Report: "Phase 4 done. Starting Phase 5 assembly..."

## Phase 5 — Assembly (sequential)

Invoke in order:
1. `phase5-script-assembler` → `assembled.md`
2. `phase5-transition-polisher` → `polished.md`
3. `phase5-final-reviewer` → `final-script.md` and `qc-report.md`

## Step 6 — Report

Read `qc-report.md` and extract the confidence score. Print to the user:

```
✅ Pipeline complete.
Run dir:        ./script-runs/<RUN_ID>/
Final script:   ./script-runs/<RUN_ID>/final-script.md
QC report:      ./script-runs/<RUN_ID>/qc-report.md
Confidence:     <X/10>
```

If the confidence score is below 9, surface the specific blockers from the QC report and suggest the user re-run from the relevant phase.

## Quality Gate Rules (non-negotiable — quoted from the source doc)

> **Rule 1:** Nothing moves forward until it passes its manager. If the Hook Manager scores a hook 8/10 on any dimension, it goes back to the Hook Writer with specific feedback. No exceptions.
>
> **Rule 2:** Both weapons check dimensions must hit 10/10. A brilliant idea described in flat language fails. Sharp language about a boring point fails. Both matter equally.
>
> **Rule 3:** Filler gets cut, not rewritten. If a line has no possible high-scoring version, it does not belong in the script.
>
> **Rule 4:** The character budget is a hard ceiling, not a suggestion. If the script is supposed to be 150 words, the final script is 150 words. Not 172. Not "roughly 150."
>
> **Rule 5:** The final script must pass the "one watch" test. After one viewing, the audience should be able to tell a friend: what the product is, why it matters, and what to do next. If the script fails this, send it back to `phase3-body-writer` for a structural rewrite.

## When invoking each subagent

Always pass these in the prompt:
- The concrete run id (e.g., `20260504T054200Z`) and the absolute or relative path of the run directory.
- A reminder that input files are in that directory and the agent must write its output to the directory's expected filename (named in each agent's own description).

Be terse with the user between phases — one line per phase transition is enough. Save the detail for the QC report.
