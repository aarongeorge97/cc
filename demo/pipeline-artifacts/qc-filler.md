# QC — Filler Detection (FocusForge / smoketest)

The 3-question test, applied to every line:
1. **Advances the argument?** (Moves the viewer toward "I need this.")
2. **Introduces essential information?** (New, unsaid-yet fact.)
3. **Creates an emotional response?** (Curiosity, sting, urgency, relief.)

A line that fails all three is filler. Marked `[CUT]`. A line that passes is kept.

---

## Annotated draft

### Paragraph 1 — Hook

> **"11 AM. 23 Slack replies. Zero commits. You reach for cmd-tab. Your best four hours are already gone."**

- "11 AM." — KEEP. Sets the indictment frame. Emotional (recognition).
- "23 Slack replies." — KEEP. New info, advances the trap.
- "Zero commits." — KEEP. The verdict. Strong emotional sting.
- "You reach for cmd-tab." — KEEP. Names the gesture; advances the diagnosis.
- "Your best four hours are already gone." — KEEP. Emotional close to the hook (urgency/regret). Novelty QC scored this 7 — true but tropey — but it still passes the 3-question test (creates emotional response). Not filler. Flag to budget enforcer for *rewrite*, not cut.

**No cuts in the hook.**

---

### Paragraph 2 — Body

> **"Your productivity app is the distraction now. FocusForge is one button. Hit Forge — Slack, Twitter, every tab is unreachable for 90 minutes. Kernel-level. No override button to hunt for. No streaks. $39 once. macOS only."**

- "Your productivity app is the distraction now." — KEEP. The diagnosis. Reframes the category.
- "FocusForge is one button." — KEEP. Introduces the product and the core mechanic in one beat.
- "Hit Forge — Slack, Twitter, every tab is unreachable for 90 minutes." — KEEP. Names the verb, the targets, the duration. Advances the argument.
- "Kernel-level." — KEEP. The moat, in two words.
- "No override button to hunt for." — KEEP (see cross-reference below). Indicts the competitor escape hatch — essential differentiator. Both QCs flagged it for *rewrite tightness* ("No override."), not for cut. It still advances the argument and creates a moment of relief ("they actually mean it"). Not filler.
- "No streaks." — KEEP. Differentiator vs Forest/Streaks/Habitica. Essential info.
- "$39 once." — KEEP. Price + anti-subscription stance in one beat.
- "macOS only." — KEEP. Audience-narrowing flex.

**No cuts in the body.**

---

### Paragraph 3 — CTA

> "Link in bio. Forge tomorrow at 8:30. Ship the thing before lunch."

- **`[CUT]` — "Link in bio."**
  - Advances argument? No. The viewer already knows where the link lives; it is platform furniture on every Reel.
  - Introduces essential info? No. Identical CTA to every account on the platform.
  - Creates emotional response? No. It is the most generic CTA on Instagram.
  - **Fails all three. This is filler.** Confirmed by both upstream QCs (novelty 4, intensity 7 — the joint low across both reports).
- "Forge tomorrow at 8:30." — KEEP. Brand-as-verb, specific time, prescriptive. Advances + emotional (commitment).
- "Ship the thing before lunch." — KEEP. The cold close. Native verb, native register.

---

## Cross-reference: lines flagged by both novelty and intensity QCs

The brief instructed me to cross-reference both upstream reports for converging signals. Two lines were called out by both:

### 1. "Link in bio." — novelty=4, intensity=7
**Both reports converge: this is the weakest line in the script on both axes.** Novelty calls it "pure filler CTA." Intensity calls it "generic to every Reel on the platform." It also fails my 3-question test on all three counts.

**Recommendation: CUT outright.** Do not replace with "Forge link in bio." or "Link in bio. Or don't." — those are rewrites the upstream agents proposed, but the cleaner move is removal. Lines 15 and 16 ("Forge tomorrow at 8:30. Ship the thing before lunch.") already carry the close. The CTA is implicit on a Reel; "Link in bio" is structural habit, not argument.

### 2. "No override button to hunt for." — novelty=10, intensity=8
**The two reports diverge.** Novelty scored it 10 (category-defining; "the phrase 'to hunt for' reveals the actual user behavior FocusForge refuses to enable"). Intensity scored it 8 (over-described; the on-brand version is "No override.").

This is a genuine disagreement, not a converging filler signal. The line is not filler — it advances the argument, introduces essential info (the competitor escape hatch), and creates relief. The disagreement is about *tightness*, not *necessity*.

**Recommendation: KEEP the line, but flag the rewrite tension to the budget enforcer.** Two paths:
- **Tight version:** "No override." — saves 4 words, matches the brand-voice cadence, but loses the "to hunt for" verb that names the user behavior (which is what made novelty score it 10).
- **Full version:** "No override button to hunt for." — keeps the novelty-defining phrasing.

Given the script is **9 words under target** (see below), the budget enforcer should keep the full version. The word budget is on our side here; tightness is only a virtue when words are scarce, and they are not.

---

## Recommended cut list

1. **Line 14 — "Link in bio."** (3 words removed)

That is the only cut. Every other line passes the 3-question test.

---

## Word count math

- Current draft: **66 words**
- After cut: 66 − 3 = **63 words**
- Target (per Product Brief): **exactly 75 words**
- **Gap after cuts: 12 words under target.**

---

## Note to budget enforcer — where to add 12 words

The script was already 9 words under target before my cut. After removing "Link in bio," the gap widens to 12 words. The budget enforcer should add words where they will *advance the argument or sting harder*, not where they will pad. Highest-leverage addition sites, ranked:

1. **Line 5 — "Your best four hours are already gone."**
   - Both QC reports flagged this as the weakest non-CTA line (novelty 7). The novelty rewrite suggestion — "The hard problem of the day is still open in tab 14." (11 words vs the current 8) — is +3 words and would lift the line from 7 to ~10.
2. **Line 8 — "Hit Forge — Slack, Twitter, every tab is unreachable for 90 minutes."**
   - Novelty suggested replacing the generic enumeration with a sting that attaches to the kernel-level mechanism (e.g. "Slack is gone. The unread badge stays."). Intensity suggested removing the em-dash and the passive verb. A combined rewrite could add 3–5 words and clear both objections.
3. **Line 11 — "No streaks."**
   - Novelty's suggested expansion — "No streak to break. Nothing to come back to." — is +6 words and tightens the indictment of gamification.

A combination of (1) + (3), or (2) + a small extension on (1), would land the script close to 75 words while *strengthening* the lines that scored weakest, not padding them.

**I am not making the additions — that is the budget enforcer's call.** I am flagging the gap and the highest-leverage sites.

---

## Gate verdict

- **1 line cut** ("Link in bio.").
- **15 lines pass the 3-question test** and should be preserved.
- **Post-cut word count: 63.** Below target by 12 words. **Does not meet the 75-word target on length** — but the deficit is the right kind of problem (room to strengthen, not room to trim).
- Filler-detection gate: **PASS** (no surviving filler in the script after the recommended cut).
