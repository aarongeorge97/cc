# 20-Agent Script Writing Pipeline

A Claude Code-native implementation of the **20-agent video script writing system** — a structured pipeline where 20 specialized subagents each do one job at a high standard, with quality gates between every step. Built from [this guide](https://docs.google.com/document/d/1LgbuW0EnM20H4qEgLbM8qQk525aOpo8zqbWxEz6EL9k/edit).

The thesis: a single prompt produces generic copy. A pipeline of focused agents — each owning one narrow responsibility, with manager agents that refuse to pass low-quality work — produces scripts that actually convert.

---

## How it works

The pipeline runs in 5 phases:

| Phase | Agents | Output |
|-------|--------|--------|
| **1. Research** | YouTube, Reddit, X researchers + synthesizer | `ammunition-file.md` — the canonical evidence pack |
| **2. Strategy** | Audience profiler, angle selector, brand voice | One specific viewer, one core angle, sentence-level voice rules |
| **3. Writing** | Hook writer ↔ manager, body writer ↔ manager, CTA writer ↔ manager | Each section iterated until 10/10 on every dimension |
| **4. Quality Control** | Novelty scorer, intensity scorer, filler detector, budget enforcer | Line-by-line scoring + exact-length cut |
| **5. Assembly** | Assembler, transition polisher, final reviewer | `final-script.md` with production markup + confidence score |

Manager agents (9, 11, 13) score writer output across multiple dimensions on a 1–10 scale. **Anything below 10 is FAIL**, with explicit rewrite instructions sent back to the writer. The orchestrator caps each writer/manager loop at 3 iterations.

The novelty + intensity scorers (14, 15) form a "weapons check" — every line must hit 10 on **both** to survive.

The budget enforcer (17) cuts to the **exact** target word count. Not approximately. Exactly.

---

## Setup

Nothing to install. The pipeline is shipped as Claude Code subagents and a slash command:

```
.claude/
├── agents/                          # 20 subagent definitions
│   ├── phase1-youtube-researcher.md
│   ├── phase1-reddit-researcher.md
│   ├── phase1-twitter-researcher.md
│   ├── phase1-research-synthesizer.md
│   ├── phase2-audience-profiler.md
│   ├── phase2-angle-selector.md
│   ├── phase2-brand-voice.md
│   ├── phase3-hook-writer.md
│   ├── phase3-hook-manager.md
│   ├── phase3-body-writer.md
│   ├── phase3-body-manager.md
│   ├── phase3-cta-writer.md
│   ├── phase3-cta-manager.md
│   ├── phase4-novelty-scorer.md
│   ├── phase4-intensity-scorer.md
│   ├── phase4-filler-detector.md
│   ├── phase4-budget-enforcer.md
│   ├── phase5-script-assembler.md
│   ├── phase5-transition-polisher.md
│   └── phase5-final-reviewer.md
└── commands/
    └── write-script.md              # /write-script orchestrator
```

Each subagent runs in its own context window — they don't see your conversation history, only the input files in the run directory.

---

## Usage

### 1. Write a Product Brief

Copy `product-brief.example.md` and fill in your own product. The brief must include:

1. **Brand name** and a clear description of what the product does.
2. **Key features** and what makes it different from competitors.
3. **Target audience** — who, what they care about, what they're frustrated with.
4. **Format** — YouTube ad, TikTok, Instagram Reel, product launch, etc.
5. **Target length** — exact word count and seconds (e.g., "60 seconds, 150 words").

### 2. Run the pipeline

```
/write-script your-brief.md
```

The orchestrator will:
- Create `./script-runs/<timestamp>/`, copy your brief in.
- Run Phase 1 research agents in parallel.
- Run Phase 2 strategy agents in sequence.
- Run Phase 3 writer/manager loops (iterating until PASS, max 3 tries each).
- Assemble the draft → run Phase 4 QC → run Phase 5 assembly.
- Print the path to `final-script.md` and the confidence score.

A typical run produces ~25–30 intermediate artifacts in the run directory, all inspectable. Every score, every diagnosis, every rewrite is on disk.

### 3. Inspect, iterate, ship

The run directory contains:
- `ammunition-file.md` — the research distilled
- `audience-profile.md`, `angle.md`, `brand-voice.md` — the strategy decisions
- `hook-draft.md`, `hook-score.md`, `hook.md` — and same for body, CTA
- `qc-novelty.md`, `qc-intensity.md`, `qc-filler.md`, `length-checked.md`
- `assembled.md`, `polished.md`
- `final-script.md` ← the deliverable
- `qc-report.md` — issues found, fixes applied, confidence score (1–10)

If the confidence score is below 9, the report tells you exactly what's blocking it.

---

## Quality Gate Rules

These are non-negotiable. They are what make the system work.

> **Rule 1:** Nothing moves forward until it passes its manager. If the Hook Manager scores a hook 8/10 on any dimension, it goes back to the Hook Writer with specific feedback. No exceptions.
>
> **Rule 2:** Both weapons-check dimensions must hit 10/10. A brilliant idea described in flat language fails. Sharp language about a boring point fails. Both matter equally.
>
> **Rule 3:** Filler gets cut, not rewritten. If a line has no possible high-scoring version, it does not belong in the script. Removing a weak line is always better than trying to polish it.
>
> **Rule 4:** The character budget is a hard ceiling, not a suggestion. If the script is supposed to be 150 words, the final script is 150 words. Not 172. Not "roughly 150." This forces every word to earn its place.
>
> **Rule 5:** The final script must pass the "one watch" test. After one viewing, the audience should be able to tell a friend what the product is, why it matters, and what to do next. If the script fails this, it goes back to Agent 10 for a structural rewrite.

---

## Troubleshooting

**A writer/manager loop hit 3 iterations without passing.** The orchestrator stops and surfaces the manager's last feedback. Read it carefully — usually the angle (Phase 2) is the real problem, not the writer's craft. Re-run with a sharper brief.

**The final word count is off by 1–2 words.** Re-invoke `phase4-budget-enforcer` directly via the Agent tool with the discrepancy noted; it will tighten or pad to exact length.

**The confidence score is 7 or 8.** The QC report lists the blockers with severity. Critical issues should send you back to Phase 3 body writer; moderate issues can usually be fixed by re-running Phase 5 polish + review.

**A research agent couldn't fetch live data.** It marks inferences explicitly. The pipeline still produces a script, but quality drops without real evidence. Consider providing your own scraped quotes in `./script-runs/<run-id>/phase1-reddit.md` before invoking the synthesizer.

---

## Manual operation (no Claude Code)

If you don't have Claude Code, you can run each agent's prompt manually in claude.ai by:
1. Opening a new conversation.
2. Pasting the system prompt from the agent's `.md` file (everything after the frontmatter).
3. Pasting the input files the agent expects to read.
4. Saving the output as the named file in your local run directory.
5. Moving to the next agent.

Slower (1–2 hours vs. ~15–20 minutes automated), same quality.

---

## Credit

System architecture and prompts derived from the publicly-shared 20-agent script writing system. This repo is a Claude Code-native implementation of that design.
