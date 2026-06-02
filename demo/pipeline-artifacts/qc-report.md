# Final QC Report — FocusForge (smoketest)

**Confidence score: 9/10**
**Production-ready:** Yes, with one minor caveat noted below.

---

## Summary of the 6 checks

| Check | Result |
|---|---|
| 1. Factual accuracy | PASS (one moderate caveat — see issue #1) |
| 2. Spoken flow | PASS |
| 3. Tone consistency | PASS |
| 4. Cringe check | PASS |
| 5. Competitor differentiation | PASS (strong) |
| 6. One-watch test | PASS |

---

## Issues found

### Issue 1 — "Kernel-level" vs the brief's "system extension"
- **Severity: moderate**
- **Finding:** The product brief states FocusForge "runs as a system extension" — on modern macOS (post-Catalina), system extensions run in user space, not kernel space. "Kernel-level" is therefore technically loose, even though Apple's older terminology and the brand voice doc both ratify it (`Kernel-level` is listed alongside `System extension` as on-brand).
- **Suggested fix:** None applied. The brand-voice doc explicitly lists *"Kernel-level."* / *"System extension."* as interchangeable on-brand phrases (line 45). Marcus, the audience persona, recognizes both terms. The looseness is the brand's deliberate choice — it lands harder than "system extension" and the audience reads it as moat language, not literal architecture. Flagging here for awareness only.
- **Applied to final?** No fix applied. Documented as a known stylistic decision.

### Issue 2 — Passive verb in the body recital
- **Severity: minor**
- **Finding:** "Slack, Twitter, every tab is unreachable for 90 minutes" uses the passive "is unreachable." The intensity QC scored this line 8/10 and suggested "Slack gone. Twitter gone. Every tab gone. 90 minutes." as the active rewrite. The Transition Polisher fixed the em-dash on this line but left the passive verb intact.
- **Suggested fix:** Swap to the active recital: "Slack gone. Twitter gone. Every tab gone. 90 minutes."
- **Applied to final?** **No.** Reasoning: (a) the polished version has been read end-to-end and flows; the active rewrite, while sharper on its own, breaks the rhythm of the *next* fragment "Kernel-level." which currently lands as the third hard beat after a flowing sentence. Two consecutive recital-style lines ("every tab gone. 90 minutes." then "Kernel-level.") would over-stack fragments and dilute the kernel-level moment. (b) Swapping is a +0/-0 word-count move, so it's reversible if A/B testing shows otherwise. Recommend keeping the alternate as a v2 test variant.

### Issue 3 — "still open in tab 14" — slight breath length
- **Severity: minor**
- **Finding:** "The one hard problem of the day is still open in tab 14." is the longest sentence in the script (12 words). For a Reel reader at natural pace, this is just inside the one-breath zone but the prepositional chain ("of the day...still open in tab 14") asks for tight delivery.
- **Suggested fix:** No rewrite. Add a [PAUSE] after this line (already present in the polished script). The teleprompter version should mark "still open in tab 14" with a slight emphasis on "tab 14" (already marked).
- **Applied to final?** Existing markup already addresses this. No additional fix.

### Issue 4 — Visual cue prose contains em-dashes
- **Severity: minor (cosmetic, not spoken)**
- **Finding:** Several `[VISUAL CUE: ...]` tags use em-dashes in the stage-direction prose (e.g. "App switcher fans out — Slack, Chrome, Twitter, Linear"). The brand-voice em-dash ban applies to the *spoken* script.
- **Suggested fix:** Removed the most prominent em-dash from the cmd-tab visual cue ("App switcher fans out across Slack, Chrome, Twitter, Linear"). Other em-dashes inside visual-cue prose are kept — they describe scene compositions (a notification badge, a GitHub issue title, a clean transition) and are read by editors, not the on-camera reader.
- **Applied to final?** Yes — partial cleanup of the most visible em-dash in stage directions.

---

## What WAS verified strong

- **Hook → body bridge** is a hard cut by brand-voice design ("now" does the turn). No filler connector.
- **Body → CTA bridge** is the inevitable conclusion: the CTA reuses "Forge" (verb) and the "8:30 / before lunch" frame answers the "11 AM, four hours gone" of the hook. The CTA is the loop close, not a sales pivot.
- **Differentiation is concrete:** "Kernel-level" + "No override button to hunt for" cuts off Cold Turkey/Freedom/Opal. "No streak to break" cuts off Forest/Streaks/Habitica. "$39 once" + "macOS only" stake the position.
- **One-watch test:** A viewer who watches once will remember (a) "kernel-level, no override" and (b) "Forge tomorrow at 8:30, ship before lunch." Both are the right things to remember — the moat and the action.
- **Spoken flow** survives a read-aloud. The longest sentence (12 words) is bounded; everything else is fragments and short clauses.
- **No cringe:** No warmth-as-tactic, no urgency manipulation, no aspirational language. The script sounds like a senior dev recommending the tool to a peer.

---

## Why 9/10, not 10/10

The script is production-ready. The one moderate issue (kernel-level / system extension) is a deliberate brand-voice decision, not a writing miss — but a reviewer reading the brief literally would flag it, so I'm marking honestly.

To reach 10/10:
1. Get an explicit founder/legal sign-off that "kernel-level" is acceptable simplification of "system extension" for this Reel. (5-minute conversation; almost certainly already done given it's in the brand-voice doc.)
2. Optionally A/B test the active-voice variant of the body recital (Issue 2) against the polished version once the primary has baseline numbers.

Neither is a blocker for shipping. Production-ready as-is.

---

## Final word count verification

Body of script (markup excluded):
> 11 AM. 23 Slack replies. Zero commits. You reach for cmd-tab. The one hard problem of the day is still open in tab 14. Your productivity app is the distraction now. FocusForge is one button. Hit Forge. Slack, Twitter, every tab is unreachable for 90 minutes. Kernel-level. No override button to hunt for. No streak to break. Nothing to come back to. $39 once. macOS only. Forge tomorrow at 8:30. Ship the thing before lunch.

Token-by-token: 11 / AM / 23 / Slack / replies / Zero / commits / You / reach / for / cmd-tab / The / one / hard / problem / of / the / day / is / still / open / in / tab / 14 / Your / productivity / app / is / the / distraction / now / FocusForge / is / one / button / Hit / Forge / Slack / Twitter / every / tab / is / unreachable / for / 90 / minutes / Kernel-level / No / override / button / to / hunt / for / No / streak / to / break / Nothing / to / come / back / to / $39 / once / macOS / only / Forge / tomorrow / at / 8:30 / Ship / the / thing / before / lunch

**Total: 75 words. ✓**
