# Demo: 20-Agent Pipeline vs. Single Prompt

**Same brief. Same target length. Same model. Two very different scripts.**

This folder shows what the pipeline actually produces, side-by-side with the naive baseline. Read this if you're deciding whether the pipeline is worth running for your use case.

---

## The brief

A 30-second Instagram Reel for **FocusForge**, a one-button distraction-blocking timer for indie macOS developers. Hard target: **exactly 75 words**. Brief is at [`product-brief.md`](./product-brief.md).

---

## What the baseline produced

Single prompt. Five sentences in a Claude conversation. No research, no audience profile, no manager review.

> Be honest. You opened your laptop at 9 AM to ship something real. It's now 4 PM, and you've been "just checking" Twitter for hours. Streak apps won't save you. Browser blockers won't save you. You'll click "unblock" every single time. FocusForge is one button. Click Forge, and for 90 minutes, Slack, tabs, notifications, even system menus are gone at the kernel level. No streaks. No subscription. macOS only. Thirty-nine bucks, once. Ship today.

75 words. Competent. Hits the differentiators. Probably 7/10.

[Full file →](./baseline-script.md)

---

## What the pipeline produced

Spoken script body (markup stripped):

> 11 AM. 23 Slack replies. Zero commits. You reach for cmd-tab. The one hard problem of the day is still open in tab 14. Your productivity app is the distraction now. FocusForge is one button. Hit Forge. Slack, Twitter, every tab is unreachable for 90 minutes. Kernel-level. No override button to hunt for. No streak to break. Nothing to come back to. $39 once. macOS only. Forge tomorrow at 8:30. Ship the thing before lunch.

75 words. Final QC confidence: **9/10**.

The shippable version with [VISUAL CUE], [EMPHASIS], and [PAUSE] markup, plus 3 alternate hooks and a backup CTA, is in [`final-script.md`](./final-script.md).

---

## What changed, line by line

| Beat | Baseline | Pipeline | Why the pipeline version is sharper |
|---|---|---|---|
| Opening time-cue | "It's now 4 PM, and you've been 'just checking' Twitter for hours." | "11 AM. 23 Slack replies. Zero commits. You reach for cmd-tab." | Five fragments instead of one sentence. Each is a load-bearing unit. The body of the script's audience profile names *11 AM* and *Slack messages by lunch* as the specific moment of self-disgust. Baseline gestures; pipeline names the exact thing. |
| The sting | "You'll click 'unblock' every single time." | "The one hard problem of the day is still open in tab 14." | Baseline is generic. Pipeline names what the viewer was *supposed* to be doing — a specific tab, a specific kind of task — which is the actual sting (the failure to ship), not the failure to focus. |
| The diagnosis | (absent) | "Your productivity app is the distraction now." | This line is the recognition trigger the audience profile says will flip Marcus from "interesting" to "I need this." A single prompt has no reason to put it on its own line as a hard cut. The pipeline knows it should because the profile said so. |
| Mechanism | "for 90 minutes, Slack, tabs, notifications, even system menus are gone at the kernel level" | "Hit Forge. Slack, Twitter, every tab is unreachable for 90 minutes. Kernel-level. No override button to hunt for." | Pipeline broke this into four hard beats with a separate "Kernel-level." sentence — the QC scorer specifically protected that as a high-novelty line. Baseline buries it in a comma list. |
| Anti-streak | "No streaks." | "No streak to break. Nothing to come back to." | Baseline lists a feature. Pipeline names the *trap* — the audience profile's exact frustration ("if you miss a day, you stop using the app entirely"). |
| CTA | "Ship today." | "Forge tomorrow at 8:30. Ship the thing before lunch." | Baseline is generic and immediate. Pipeline closes the loop the hook opened: the hook said "11 AM, four hours wasted"; the CTA says "8:30 tomorrow, shipped before lunch." Specific time, specific outcome, named verb (Forge). |

---

## The mechanism — 4 moments where the system caught what a single prompt wouldn't

### 1. The hook manager rejected 3 of the 4 hooks

The hook writer produced 4 hooks (Bold Claim, Pain Call-out, Contrarian, Story Opener). The hook manager scored them across 5 dimensions on a 1-10 scale. Three FAILed:

- **Hook 1 (Bold Claim) FAILed** — the manager flagged "*The one that held*" as soft metaphor (the brand voice doc bans soft metaphor) and the colon construct ("The one that held: kernel-level") as a writerly punctuation move the brand doesn't use.
- **Hook 2 (Pain Call-out) FAILed** — almost-pass at 49/50. The manager noted it "ends on its third proof-beat without any turn — four nods is not the same as one involuntary 'yes.'"
- **Hook 3 (Contrarian) FAILed** — peaks at sentence 2 ("anxiety with a leaderboard") and tapers into abstract principle in sentence 3.

Hook 4 passed 50/50 and became primary.

A single prompt cannot do this. There's no second pass, no rubric, no specific voice rules to enforce. Read [`pipeline-artifacts/hook-score.md`](./pipeline-artifacts/hook-score.md) — the scoring is granular enough to be auditable.

### 2. The novelty + intensity scorers converged on the same weak line

Phase 4 runs two independent line-by-line scorers (Invention Novelty and Copy Intensity). They scored every one of the 16 lines.

**Both flagged "Link in bio." as weak.** Novelty gave it 4/10 ("pure CTA filler"). Intensity gave it 7/10 ("generic platform-CTA"). The filler detector then formally cut it.

The agents disagreed productively on **"No override button to hunt for."** — novelty gave it 10 (category-defining differentiator), intensity gave it 8 (could be tighter as just "No override."). The filler detector, seeing the disagreement, **kept it** because the disagreement was a tightness signal, not a filler signal.

That kind of cross-check is impossible in a single pass. See [`pipeline-artifacts/qc-novelty.md`](./pipeline-artifacts/qc-novelty.md) and [`pipeline-artifacts/qc-intensity.md`](./pipeline-artifacts/qc-intensity.md).

### 3. The budget enforcer hit *exactly* 75 words

After the filler cut, the script was at 63 words — under target by 12. The budget enforcer didn't pad with filler. It made two surgical decisions:

- Replaced *"Your best four hours are already gone."* (novelty 7 — "Cal-Newport-era trope") with *"The one hard problem of the day is still open in tab 14."* — pulling directly from the audience profile's stated goal of "one hard problem solved per day."
- Replaced *"No streaks."* with *"No streak to break. Nothing to come back to."* — naming the gamification trap.

Final word count: exactly 75. Not 74. Not 76. (Rule 4 from the source doc.)

### 4. The final reviewer caught a brand-voice slip nobody else would

The transition polisher noticed that the brand voice doc bans em-dashes in spoken script. One line had snuck through: *"Hit Forge — Slack, Twitter, every tab is unreachable..."* The polisher swapped the em-dash for a period before the script ever reached production.

The final reviewer also flagged a moderate-severity factual issue: the brief says FocusForge "runs as a system extension," but the script says "Kernel-level." On modern macOS, system extensions run in user space, so "kernel-level" is technically loose. The reviewer documented this honestly in the QC report rather than papering over it. See [`pipeline-artifacts/qc-report.md`](./pipeline-artifacts/qc-report.md).

A single prompt would never do that.

---

## Cost

This run used:

| Phase | Agents called | Approx. tokens | Wall time |
|---|---|---|---|
| Phase 2 (strategy) | 3 (parallel) | ~70k | ~70s |
| Phase 3 (writing) | 6 (sequential) | ~165k | ~6 min |
| Phase 4 (QC) | 4 (2 parallel + 2 sequential) | ~95k | ~4 min |
| Phase 5 (assembly) | 3 (sequential) | ~70k | ~5 min |
| **Total** | **16 agents** (research phase stubbed) | **~400k tokens** | **~16 min** |

A real run would also include Phase 1 (4 research agents hitting WebSearch / WebFetch), bringing the total to ~20 agents and roughly $3-6 in LLM spend at Sonnet pricing.

The single-prompt baseline cost <$0.05 and finished in 16 seconds.

---

## When this is worth it

**Use the pipeline when:**
- The script is for a paid ad spend, a product launch, a high-stakes pitch — anywhere a 7/10 script costs you measurably in conversion.
- You need 4 hooks with scored alternates (the system gives you 3 backups by design).
- The brand has a specific voice and you want it enforced line-by-line, not just "approximately."
- You want every editorial decision auditable on disk — *which* line was cut, *why* it was cut, *what* replaced it.

**Skip the pipeline when:**
- It's an internal video, an experiment, or a thing you'll rewrite next week.
- The product is generic enough that a 7/10 script and a 9/10 script will both convert at the same rate.
- You don't yet know your brand voice — the pipeline enforces a voice; it doesn't discover one for you.

---

## What to read next

- **[`final-script.md`](./final-script.md)** — the shippable script with visual cues, emphasis, alternate hooks.
- **[`pipeline-artifacts/audience-profile.md`](./pipeline-artifacts/audience-profile.md)** — the level of audience specificity downstream agents are working against. This is where most of the sharpness comes from.
- **[`pipeline-artifacts/hook-score.md`](./pipeline-artifacts/hook-score.md)** — three FAILing hooks with specific manager critiques. This is what "10/10 on every dimension or it goes back" actually looks like.
- **[`pipeline-artifacts/qc-report.md`](./pipeline-artifacts/qc-report.md)** — the final reviewer's confidence score with honest reasoning for why it's 9 and not 10.

---

## Reproducing this

This demo was produced by running each agent's prompt against the inputs in `script-runs/smoketest/`. Phase 1 research was stubbed with a hand-written ammunition file (real research would call WebSearch / WebFetch in [`phase1-*.md`](../.claude/agents/) agents).

To run the full pipeline yourself in a fresh Claude Code session, from the repo root:

```
/write-script product-brief.example.md
```

The orchestrator handles run-directory creation, parallel research, manager retry loops, and end-to-end assembly.
