# Doc 05 — Drafted acceptance-test answers

> Drafted answers to the five acceptance-test questions, each citing the specific Doc 05 section and the Doc 1 lecture it builds on. Every claim here is drawn from Doc 05 + Doc 1 alone — no external material is introduced. This file is the self-check for whether the doc actually answers its target questions.

---

### A1 — Reviewing every hand vs. selecting hands

No. Reviewing every hand is the single most common beginner mistake, and Doc 05 §3 is explicit that it's actively counterproductive for two reasons: (a) attention is finite, and spreading it across 400 hands means you spend 30 seconds on each instead of 10 minutes on the hands that actually matter, and (b) the uninteresting hands — the ones where you open-raised, c-bet, got called, and gave up on the turn — are almost always correctly played, and "reviewing" them trains you to second-guess rather than to learn.

The correct approach is the **"interesting hand" filter** (§3). An interesting hand is one that meets at least one of four criteria:

1. **You were uncertain at decision time.** The feeling of "I don't know what the right play is here" is the single strongest signal. Mark these in-session if your site allows it.
2. **You made a nonstandard choice.** Any hand where you deviated from your default — 4-bet bluffed, called a river overbet, min-raised preflop — is worth reviewing regardless of result.
3. **A large pot.** Hands where the pot got to >40bb deserve attention because the EV swing is large enough that small mistakes compound.
4. **Your opponent made a nonstandard choice.** If they 4-bet from the BB when that's rare in the pool, that hand teaches you something about the population.

Most sessions have 5–15 interesting hands. That's the review queue. The other 385 hands don't need your time.

The Doc 1 framing (L1's decision-quality focus) still governs — you're reviewing the decisions that had meaningful EV attached — but Doc 05 adds the session-level scaffolding that Doc 1 didn't: *how do you find those decisions in a pile of 400 hands?*

(Doc 05 §§1, 3; Doc 1 L1 decision-quality framework.)

---

### A2 — Review timing: post-session vs. next-day

These are two different reviews, and you should do both.

**Immediately post-session** (Doc 05 §2) — do a short journaling pass. 10–15 minutes. Dump the context (stakes, duration, mental state, result), flag the interesting hands while memory of them is still warm, write down any hypotheses you had during play ("I think villain in seat 4 was overfolding turns"). This is *capture*, not analysis. The goal is to not lose the session's signal to sleep.

**The next day** (Doc 05 §2) — do the deep review. This is where you actually go through the flagged hands, run solver checks, categorize leaks, and assign drills. The next-day timing is deliberate: it gives cognitive consolidation a chance to work, and it prevents the review from being colored by how the session *felt* (a breakeven session after a bad cooler feels like a losing session; a winning session off a hot run feels like skill).

The most common failure modes are collapsing these into one session — either doing the deep review immediately (colored by emotion, tired brain, no consolidation) or skipping the immediate journal and losing the flagged hands by next day (you'll remember you had an interesting hand, but not which one). Separate the two moments; keep each short.

This extends rather than contradicts Doc 1. Will Ma didn't address session-review timing directly — his L1 framework is about how to analyze a single hand well, not when in the week to do that analysis. Doc 05 §2 adds the cadence scaffolding.

(Doc 05 §2; Doc 1 L1 framework extended with session-level timing.)

---

### A3 — After finding a leak: converting it to a drill

"Play better next time" is exactly the failure mode — and it's why most students who review still don't improve. Finding a leak is only half the work; Doc 05 §6 calls the second half **leak-to-drill conversion**, and the distinction between students who improve and students who plateau is whether they do this step or skip it.

A drill is a specific, repeatable, measurable action you will take before your next session. Not "play better." Not "think about it more." A drill.

For your specific leak (calling down with ace-high on a board where you should have folded), the §6 conversion table gives a clear path:

1. **Name the decision class.** This is a **river bluffcatching leak** — specifically, calling too wide with bluffcatchers on rivers where the opponent's range is weighted toward value.
2. **Identify the underlying miscalibration.** Ace-high is a bluffcatcher; to call profitably you need the opponent to be bluffing at a rate that clears the pot-odds bar. You over-estimated their bluff frequency.
3. **Pick a concrete drill.** Examples from §6: (a) run 10 similar river spots through a solver and log the minimum defense frequency for each, (b) do a 15-minute PokerSnowie or GTO Wizard trainer session focused on river bluffcatching, (c) write out the opponent's value range and bluff range explicitly before any future river call for the next 3 sessions.
4. **Set a completion criterion.** "Complete the solver drill by Friday before your next session" — not "work on it."
5. **Add it to your session journal's drill-assignment slot** (Doc 05 §7) so it's in front of you when you sit down to play.

The Doc 1 connection: L1 taught the pot-odds math for river decisions. You already know the math. What Doc 05 §6 adds is the behavioral bridge from "I know the math and I still called" to "next session, this exact decision type will be pre-loaded in my attention because I spent 15 minutes on it this week."

(Doc 05 §§6, 7; Doc 1 L1 pot-odds and river bluffcatching math.)

---

### A4 — Categorizing a preflop leak

This is a **preflop leak**, specifically a **range construction leak** — but the categorization is more interesting than "you shouldn't have opened."

Doc 05 §5 gives the five-bucket taxonomy: preflop, postflop, ICM, mental, execution. Your hand is preflop because the decision was made before any community cards. Within preflop, §5 breaks down further into (a) range construction (which hands are you opening from which position?), (b) sizing, and (c) response to 3-bets. Yours is (a).

Here's where it gets nuanced, though: the assumption that "I open-raised KJo from UTG so it was wrong" is itself conditional. Doc 02's conditional-baseline principle applies here. **Whether KJo is in UTG's opening range depends on your stakes, rake structure, sizing, and pool tendencies.** A modern solver baseline at 2.25bb opens online has KJo comfortably in UTG's 9-max range; Will Ma's 2016 UTG 6% did not. If you're playing live 3bb with heavy rake in a 3-bet-happy pool, folding KJo is defensible; if you're playing online 2.25bb, opening is the baseline.

So the categorization sequence is:

1. **Preflop? Yes** — decision happened before the flop.
2. **Which sub-bucket? Range construction.**
3. **Is it actually a leak?** Check: what's my sizing, what's the pool, what's my assumed baseline? If KJo is in the solver range for your specific conditions, the leak isn't "opening KJo" — it's possibly "continuing vs. a 3-bet incorrectly" (which is a separate preflop sub-leak: response to 3-bets), or possibly no leak at all.
4. **Doc 1 connection:** L1's pot-odds framework still governs the 3-bet response decision. You folded, which is one of three correct outcomes (fold, call, 4-bet) depending on price, ranges, and stack depth.

The discipline here — the thing Doc 05 §5 is trying to install — is *categorize before you diagnose*. The student who says "I played it badly" has already skipped the categorization step and is about to prescribe the wrong fix. The student who says "this is preflop → range construction → and actually, given my conditions, I need to check whether it's a leak at all" is doing review correctly.

(Doc 05 §5; Doc 02 §1 conditional-baseline principle; Doc 1 L1 pot-odds framework for the 3-bet response decision.)

---

### A5 — Doc 1's 7-step workflow vs. Doc 05's 7-step workflow

Use both. They're nested, not competing.

Doc 1's 7 steps are a **single-hand analysis workflow** — when you've picked one hand to review, how do you think through it? Will Ma's L1 teaching walks through: identify villain's range, identify your range, work out the equities, apply pot odds, identify the decision point, consider alternative lines, select the highest-EV action.

Doc 05's 7 steps are a **session review workflow** — when you've just finished a 4-hour session, what do you do before you've even picked a hand to analyze? Doc 05 §4 walks through: (1) session capture, (2) hand selection with the interesting-hand filter, (3) prioritization by EV magnitude and uncertainty, (4) per-hand analysis, (5) leak categorization, (6) leak-to-drill conversion, (7) journal update.

**Step 4 of Doc 05 — "analyze the hand" — is where Doc 1's entire 7-step workflow lives.** When you're at that step, you execute Will Ma's sequence. Doc 05 doesn't replace it; it wraps it in the session-level scaffolding that Doc 1 didn't cover: how you got to "now I'm analyzing this hand," and what happens after you've finished the analysis.

This is an extension-not-replacement case, per Standing Rule #6. Will Ma's 2016 teaching focused on the single-hand skill — correctly, because that's the core skill. Modern practitioners (Clarke, Angelo, the training-site curriculum distilled in §4) added the session-level and longitudinal scaffolding: what do you do across hands, across sessions, across weeks? Doc 05 §4 is honest about this: the session workflow is *new*, not a correction. Doc 1's per-hand workflow remains correct and is explicitly referenced as the content of step 4.

Practically: if you have one hand in front of you, use Doc 1's 7 steps. If you have a session in front of you, use Doc 05's 7 steps — and when you hit step 4, you're running Doc 1's 7 steps on each selected hand. The two workflows are compatible because they operate at different scales.

(Doc 05 §4; Doc 1 L1 single-hand analysis workflow; Standing Rule #6 extension-not-replacement framing.)

---

## Self-check

- [x] Every answer cites the specific Doc 05 section.
- [x] Every answer cites the specific Doc 1 lecture it builds on.
- [x] No external material introduced beyond Doc 05 + Doc 1 (A4 references Doc 02 only as a legitimate cross-doc cross-reference already present in Doc 05).
- [x] Every factual claim is traceable to a sourced claim in Doc 05.
- [x] Answers respect Standing Rule #6 framing of Doc 1 extensions as right-for-context, not corrections.
- [x] Answers respect Standing Rule #8 — no paywalled content reproduced.

---
