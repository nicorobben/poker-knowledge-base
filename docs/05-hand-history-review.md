# Hand History Review Template

> **Doc 5 of the Poker Training Knowledge Base** · An operational workflow for converting played sessions into measurable improvement — extending Doc 1's *Hand analysis workflow* from "how to analyze one hand" to "how to run a session, a week, and a month of review." · License: CC BY-NC-SA 4.0 (matches Doc 1) · Primary sources in [`sources/05-sources.md`](../sources/05-sources.md).

<!--
================================================================================
Outline / structural map (Phase 2 output, retained through Phase 3 drafting).

House-style anatomy (BUILD_PLAN §2.1):
  A. Title + source attribution + license   (above)
  B. Coaching agent guide
  C. How to use this document as a human reader
  D. Core thesis
  E. Main body sections 1–12
  F. Quick-reference cheat sheet
  G. Anti-patterns table (consolidated in §12)
  H. Glossary
  I. Resources and links
  J. Where this fits in the knowledge base

Main body:
   1. Review philosophy — process over product
   2. Review timing and frequency
   3. Hand selection — the "interesting hand" filter
   4. The session review workflow (7 steps, extended from Doc 1)
   5. Leak categorization framework
   6. Leak-to-drill conversion
   7. Session journal template
   8. Weekly review process
   9. Monthly leak audit
  10. HUD-assisted review — basics
  11. Solo vs. group / coached review
  12. Anti-pattern table (consolidated)

Cross-ref numbering note: Docs 02 and 01 use BUILD_PLAN's original numbering
for forward references. This doc uses the branch-name-implied renumbering
in which Doc 04 = Mental Game and Doc 05 = Hand History Review. Where the
number is unstable (Docs 03 and 06 may swap between Postflop and ICM),
cross-refs include the topic in parentheses so Closing Tasks' cross-ref
audit can update the number without changing meaning.
================================================================================
-->

---

## Coaching agent guide (read this first if you're Claude)

**When this doc is your best source.** A student says any of the following and this doc is the default: "how do I review a session?", "I played for two hours last night — what should I do now?", "I keep making the same mistakes, how do I actually fix them?", "should I review my biggest losing hand?", "I just want to know if I played this hand right" (often a review-philosophy issue, not a hand-specific question), "I've been studying for months and I'm stuck", or any question that describes a *pattern* across multiple hands rather than a single spot. If the question is really about one hand, use Doc 1's hand analysis workflow and return. If the question is mental-game-flavored ("I tilt after bad beats, how do I review those without spiraling?"), hand off to Doc 04 — Mental Game & Tilt but use this doc's §5 to name the leak category.

**Default workflow when a student asks "help me review."**

1. **Establish the session context first** — format, stakes, duration, hand count, rough win/loss. Don't skip this. It's the difference between a useful review and a generic "here are some tips." §4 step 0 of this doc covers the exact questions.
2. **Filter before you analyze.** Review is not about re-playing every hand. It's about picking the right ~10–20% of hands that teach something and ignoring the rest. §3 (hand-selection filter) is the gate.
3. **Run Doc 1's 7-step hand analysis workflow on each filtered hand.** That workflow is the spine. This doc's §4 adds three session-review steps around it (pre-filter, categorize-the-leak, extract-the-habit).
4. **Categorize every identified leak into one of the five buckets** in §5 (preflop / postflop / ICM / mental / execution). Do this even if the leak is obvious — the categorization is what drives the drill recommendation in §6.
5. **Close the loop.** The student should leave the review with *one* specific drill (§6 cross-refs to Doc 07 — Drill Library) and *one* line in their session journal (§7 template). Not five. One.

**Tone and limits.**

- Concrete first, principle second. Don't say "review is about finding your leaks"; say "you called a river bet closing action with a bluff-catcher on a board that completed two draws, and a similar spot appeared three more times in the session — that's a pattern, and the pattern is the leak. The principle is that you're not weighting the frequencies of Villain's value combos correctly when draws complete." Name the spot, *then* the principle.
- Honest uncertainty. When a student asks "was this call right?", the correct answer is often "given the range you built and the pot odds, yes; given a different range assumption, no — and the range assumption is where you should spend the review time, not on the call itself." Doc 1's *decisions-not-results* framing applies every time.
- Never moralize. "You should have reviewed earlier" or "you're not studying enough" is useless feedback even if it's true. Redirect to §2's cadence guidance without judgment.
- Respect the mental-game boundary. If a review turns up tilt patterns (time-of-night losses, after-beat aggression spikes, session-extension after losses), acknowledge the pattern and hand off to Doc 04 for the routines that address it. This doc identifies mental leaks in §5; it does not treat them. Standing Rule #6 in CLAUDE.md applies: the diagnosis lives here, the treatment lives in the Mental Game doc.
- No drill bloat. The temptation is to end every review with "here are seven drills that might help." Don't. §6 is explicit about one drill per leak, rotated weekly.

**Pedagogical mirrors from Doc 1's *How Will Ma teaches* section to use consistently.**

- *Concrete first, principle second* — show the specific hand, then name the leak type, then generalize.
- *Audience Q&A as the engine* — when a student describes a hand, ask them what they think Villain's range was before you say what you think. The review is their work; you're the coach, not the solver.
- *Honest uncertainty* — if the spot is close, say so. Don't invent a crisp verdict to perform confidence.
- *Callbacks* — "this is the same pattern as the Macau A-T hand from Doc 1 L1" beats reinventing the concept.
- *Negative-space arguments* — if a student insists a hand was fine, ask "what would Villain have to do differently for this to be wrong?" The answer reveals the range assumption they were relying on.

---

## How to use this document as a human reader

This doc assumes you already have Doc 1's *Hand analysis workflow* — the 7-step sequence from "establish context" through "translate the conclusion into a habit" — loaded into your head. If you don't, read that section first. It's the spine of everything here. This doc's job is to wrap that workflow in a session-review loop, a week-review loop, and a month-review loop, with filters and categorization tools in front of each.

Each of the twelve numbered sections follows the same rhythm: **Key takeaways** (four to six memorize-able bullets), then **Detailed notes** (the reasoning and the caveats), then **Examples** (one or two concrete review sessions described end-to-end). Read the takeaways first; go into the details only if you want the *why*.

Two sections are templates you can copy and paste: §7 (session journal) and §6 (leak-to-drill conversion). Everything else is conceptual.

If you are picking this doc up cold and only have 20 minutes, read the Quick-reference cheat sheet at the bottom. It is the compressed one-page version.

---

## Core thesis: review is the feedback step of deliberate practice

Three ideas thread through the rest of the doc. If you hold these, the operational details stop feeling like a checklist.

**First: practice without review is not practice.** Anders Ericsson's 1993 paper on deliberate practice specifies four conditions under which practice builds expertise: a well-defined task with appropriate difficulty, *informative feedback*, opportunities for repetition and correction, and a motivated learner [[9]](../sources/05-sources.md). Of the four, the feedback condition is where poker goes wrong most often. A session played without review has no feedback step — the "result" (the stack movement) is noise at any reasonable sample size, and Doc 1's whole *decisions-not-results* framing is built around the fact that the stack can't teach you anything about whether a specific decision was right. Review is what substitutes for the feedback absent from the result. That's its function. Everything operational in this doc is downstream of this.

The caveat worth naming: deliberate practice is a contributor to expert performance, not a full explanation. Macnamara and Hambrick's 2020 review documents that deliberate practice accounts for roughly a quarter of the variance in performance across studied domains, with genetics, starting age, and environment explaining the rest [[23]](../sources/05-sources.md). In poker the range of variance explanation for practice is genuinely unknown. *Don't promise a student that review alone will make them great.* Do commit to the weaker claim: review is the feedback mechanism without which every hour of play teaches less than it should.

**Second: the unit of review is a pattern, not a hand.** Doc 1's hand-analysis workflow is correct on a single hand. But if you apply it 150 times per session, you produce 150 unconnected verdicts and no learning. The unit that teaches is the *pattern across hands*: "you open QJo from UTG three times across the session, and all three are close-to-losing under any reasonable live-pool rake assumption." That's a leak. The individual hands are symptoms; the leak is the diagnosis. GTO Wizard's hand-review piece is explicit on this: *"I'm using them as an impetus to discover some element of strategy I do not yet understand"* — the job of a reviewed hand is to seed an investigation into a broader principle, not to produce a hand-specific verdict [[1]](../sources/05-sources.md). This is why §3 (filtering) and §5 (categorization) matter more than §4 (per-hand analysis): they are what turn the 150 hands into, say, three identified leaks.

**Third: review has to close.** The end of a session review is not a page of notes. It's a single specific commitment: "for the next 72 hours, I drill combo-counting on draw-heavy boards for ten minutes before each session" (cross-refs Doc 07 — Drill Library). Peter Clarke's *Grinder's Manual* makes this explicit with a tag-driven loop: hands tagged during play, reviewed against specific chapter material, converted into a targeted study block, and then re-tagged in subsequent sessions to check whether the leak re-appears [[8]](../sources/05-sources.md). The loop has to close, or the review becomes a ritual that makes the player feel like they're working without changing any frequency at the table. This is the single highest-leverage difference between effective and ritual review, and §6 (leak-to-drill conversion) is the operational move that enforces it.

**Where this departs from Doc 1.** Doc 1 gives you a 7-step workflow for analyzing *a* hand. It says less about when to trigger that workflow, which hands deserve it, how to turn a verdict into a study plan, or how to run the workflow across a week or a month. That's this doc's contribution. Doc 1 is correct on the *what*; this doc adds the *when, which, and how often*.

---

## 1. Review philosophy — process over product

**Key takeaways**

- The job of review is to *produce a diagnosis*, not to replay the session. A good review ends with one named leak and one next action. A bad review ends with a page of bullet points.
- Separate the decision from the result on every hand you review. If you catch yourself saying "and then I *lost*, so it must have been wrong," stop and reframe. This is Doc 1's single most-violated rule in practice.
- Review the decisions you're least sure about, not the ones that hurt most. Confidence, not stack-impact, is the selection signal.
- Marking hands for review during play is part of the philosophy — not a HUD convenience. It buys you focus at the table and a review queue that reflects your in-session uncertainty rather than your post-session hindsight bias [[1]](../sources/05-sources.md) [[21]](../sources/05-sources.md).
- Reciprocality is the frame. Every leak you fix that your opponents don't widens the gap between your A-game and theirs, regardless of absolute skill level [[7]](../sources/05-sources.md).

### Detailed notes

The process-over-product frame starts with a concrete contrast. Player A finishes a 200-hand session down three buy-ins. She opens her tracker, sorts by biggest pot lost, and spends ninety minutes reviewing the two hands that bled the most chips. She comes away with a verdict on those two hands ("I should have folded the turn") and a vague sense that she ran badly. Player B finishes the same session and opens her in-session hand-marking list — four hands she tagged while playing, none of them the biggest pots. She spends ninety minutes asking *why she was uncertain* on each of the four, identifies that three of them share the pattern "floated OOP with a backdoor draw and no plan for the turn," and commits to ten minutes of turn-card-categorization drill before her next session. Player A has done a session review. Player B has done a leak review. Only Player B's work affects her next session's frequencies.

The difference is the selection rule. GTO Wizard's review guidance is explicit: mark hands during play "prevents rumination and creates commitment to yourself to review it later," and the hands worth reviewing are "surprising results that prompt deeper investigation" — not the hands where the solver agrees with you and not necessarily the ones where you bled money [[1]](../sources/05-sources.md). The selection signal is *prediction error*: hands where your in-the-moment confidence and the retrospective assessment diverge. Prediction error is where the learning is, because by definition you were wrong about something you thought you knew.

This is also why Tommy Angelo's reciprocality framing matters operationally, not just philosophically. Angelo's definition — *"reciprocality is any difference between you and your opponents that affects your bottom line"* [[7]](../sources/05-sources.md) — tells you what's worth fixing. It's not "everything you do wrong." It's "everything you do wrong that your opponents do right, or everything you do right that your opponents do wrong." A leak that the entire pool shares is free EV no one collects. A leak that only you have is EV your opponents collect from you. Review should prioritize the second category, which maps to leaks you learned from a specific coach or training site that happened to be wrong, or leaks that are unique to your player type.

**The anti-results trap.** Doc 1 names it; this doc's philosophy section underlines it. The temptation to review the biggest losing pot is nearly irresistible — it's emotionally weighted, it's at the top of any loss-sorted list, and it feels like the place where the most went wrong. It usually isn't. Big losing pots are concentrated in high-variance spots (stack-off with top pair, set over set, river all-ins for stacks) where the decision quality is either obvious (call with nuts, fold to jam) or genuinely thin in a way that doesn't generalize. The leaks that move your winrate live in small-pot decisions: bet-or-check turns with second pair, 2.5bb 3-bet defends with offsuit broadways, flop c-bet sizing on dry boards. Those don't sort to the top of any loss ladder. You have to pick them on purpose.

**The "interesting hand" criterion.** The one-line version of the selection rule is *a hand is interesting if you'd like to see the same situation play out again*. If you would, it means there's something about the situation you haven't resolved — you want another data point. That's the review candidate. If you wouldn't (because you'd know exactly what to do next time), it's not a review candidate even if it was the biggest pot of the session. §3 operationalizes this into a filter.

### Examples

**Example 1.1 — Review as diagnosis, not autopsy.** A 200nl 6-max cash player posts a losing session. The biggest pot lost: AA vs. set of deuces all-in on a K♦7♣2♠ flop. Review-instinct: "what could I have done differently?" Review-reality: *nothing*. AA is a value set-mine cooler and a decision the player will make the same way every time. Time spent reviewing: zero. The right candidate from that same session: a hand where the player c-bet K92 rainbow for 33% pot, got raised, and folded — *and wasn't sure at the table whether the fold was right*. That uncertainty is the signal. The diagnosis from reviewing it is likely "my c-bet range is too wide on K-high static boards, so my check-raise-fold frequency is too high" — a leak that shows up in 30-40% of my sessions. Fix that and ten buy-ins shift.

**Example 1.2 — Prediction error vs. result size.** Same session. Player flats a BTN 2.3bb open with 55 from the BB, flops 6♠5♦3♣, check-calls twice, gets it in on the river for stacks on a paired turn-river board, scoops. Biggest winner of the session. Review candidate? No. The hand played itself — the in-session uncertainty was zero. Review candidate from the same session: a hand where the player *checked* a mid-strength value bet in a 3-bet pot on a river because they "didn't know if it was ahead of the range," and the hand showed down a check. That hand cost two big blinds or nothing. The prediction error — "I wasn't sure if I was ahead of the call range" — is the diagnostic data.

---

## 2. Review timing and frequency

**Key takeaways**

- Review within 24 hours of playing, ideally within 12. Memory of in-session context decays faster than most players realize [[11]](../sources/05-sources.md).
- A realistic serious-study cadence is 1:1 to 1:2 study:play hours. Clarke's public recommendation is 2:1 *play:study* early in development (playing more than you study) and shifting toward 1:1 when you're actively leak-hunting [[18]](../sources/05-sources.md).
- Session reviews are short — 15–45 minutes. Weekly reviews are 60–90 minutes. Monthly audits are 2–3 hours and come out of your normal study time, not on top of it [[11]](../sources/05-sources.md).
- Never review a session you just lost in while still emotionally activated. The review will be wrong. Wait until the next day.
- Review cadence is a commitment, not a mood. Block the time on the calendar the same way you would a session.

### Detailed notes

The timing rule is cognitive, not moral. When you're at the table, you're carrying context that isn't in the hand history — what Villain looked like at his webcam, how the table was playing in the preceding orbits, what your own fatigue level was, what you noticed about a specific Villain's sizing pattern four hands earlier. That context evaporates on a timescale of hours. Reviewing the next morning recovers maybe 70% of it; the next week, 20%; the next month, essentially none. Jonathan Little's *PokerCoaching* workflow piece recommends review within the 24-hour window for exactly this reason [[11]](../sources/05-sources.md), and all the review-methodology interviews with serious grinders repeat the point [[18]](../sources/05-sources.md).

The study-to-play ratio question is more contested. A common myth in training content is "study 1 hour for every hour you play." In practice, what serious grinders do and what coaches recommend are closer to:

- **Early-stage (first 6-12 months of serious study) — play more than you study.** Clarke's recommendation of 2:1 play:study reflects the fact that early-stage players need volume and pattern-exposure more than they need leak-hunting [[18]](../sources/05-sources.md). At this stage, review is about *building the habit of reviewing* and getting fluent with the session-review workflow — not about finding sophisticated leaks.
- **Mid-stage (actively leak-hunting a specific technical issue) — 1:1.** When you have an identified leak and you're working to close it, the time balance shifts. You're using play sessions as leak-exposure reps and study sessions as diagnosis and drilling. A 200-hand play session can easily yield a 45-minute targeted review plus a 30-minute drill session — roughly matching the play time.
- **Advanced (professional-adjacent) — highly variable.** Professional cash grinders with established leak-tracking systems often run 3:1 or 4:1 play:study during stable periods and flip to 1:2 or 1:3 during deliberate skill-acquisition periods. The number isn't generalizable.

**The "review within 24 hours" rule has two exceptions.**

- *Emotional activation.* If you just ended a session tilted, on a downswing, or after a beat that's still live in your head, wait. Tilted review produces tilt-flavored diagnoses ("that guy always sucks out, I should have jammed harder") and misses the actual leak. Doc 04's pre-review check-in routine is the cross-ref. Wait until the activation has cleared.
- *Multi-day tournament days.* If you played a two-day MTT and day 1 ended at 2 AM, don't review at 2 AM. Sleep. Review the next morning before day 2 starts — the deeper-run pattern recognition you'll do on day 2 benefits from the review.

**Weekly and monthly cadences.** A weekly review (§8) takes the leaks identified in that week's session reviews and asks: *which of these repeated?* A monthly audit (§9) takes three or four weeks of data and asks: *which leaks are chronic vs. episodic?* Neither of these can substitute for per-session review — they're additions to it, not replacements. Attempting to batch a week of sessions into a single review is the most common modern mistake, and the reason: by the time you review session 1 at the end of the week, the in-session context is gone and you're effectively reviewing blind.

### Examples

**Example 2.1 — The morning-after cadence.** A 20-hour-per-week recreational player plays Tuesday, Thursday, and Saturday evenings. Her review schedule: 20-30 minutes Wednesday morning before work (Tuesday's review), 20-30 minutes Friday morning (Thursday's review), 30-45 minutes Sunday morning (Saturday's review, larger session). Weekly review: 60-90 minutes Sunday afternoon, pulling leaks from all three. Monthly audit: 2-3 hours the first Sunday of each month, taken out of the usual Sunday weekly-review block (that week has no weekly review). Total review time per week: ~2-3 hours against ~15 hours play. Ratio: roughly 1:5 study:play, plus drill time. Appropriate for a recreational player with limited weekly hours.

**Example 2.2 — The emotional-activation rule in practice.** A serious grinder finishes a six-hour session down four buy-ins, including two set-over-set coolers. His first instinct is to open the tracker. The better move: close the laptop, eat, sleep. Review the next day, when the stack-movement memory has dissipated to the point where he can separate the coolers (noise; no review needed) from the c-bet sizing spot he was uncertain about in hour three (signal; review candidate). Twelve hours of delay is a small cost for a review that finds the actual leak instead of the emotionally weighted pseudo-leak.

---

## 3. Hand selection — the "interesting hand" filter

**Key takeaways**

- Review ~5–15% of hands played, not all of them. A 200-hand session yields 10–30 review candidates, not 200.
- The primary selection filter is *in-session uncertainty* — hands you tagged at the table, hands where you paused for longer than your norm, hands where you'd genuinely like to know what the solver says [[1]](../sources/05-sources.md).
- Secondary filters: (a) any hand where a solver or tracker flags an EV loss above a threshold you set [[2]](../sources/05-sources.md) [[3]](../sources/05-sources.md); (b) any hand where your decision tree included an option you didn't take but considered; (c) any hand that seemed to play itself but ended badly — worth a single pass to verify the "played itself" assessment.
- Skip: hands you're confident you played correctly and the result matched; hands where the villain action left you no decision; hands with obvious coolers (set over set, AA vs KK all-in preflop).
- If the filter produces zero candidates, you're probably filtering too conservatively. Aim for at least 5% of hands played even in "autopilot" sessions — the minimum yield prevents the review from becoming vestigial.

### Detailed notes

Selection is the lever. A typical 200-hand 6-max online cash session produces roughly 50–80 hands where the player made any nontrivial decision (VPIPed or faced a bet). Of those, perhaps 10–30 have enough decision-content to be worth the review workflow. The rest are either automatic folds, automatic calls with nutted hands, or the preflop all-in coolers that have no postflop to examine. The job of filtering is to find the 10–30, not to visit the full 50–80.

**Primary filter — in-session uncertainty tagging.** PokerTracker's in-session hand-tagging tool is designed for this exact purpose [[21]](../sources/05-sources.md). Hand2Note and modern Holdem Manager provide similar functionality [[19]](../sources/05-sources.md) [[20]](../sources/05-sources.md). The workflow:

1. Configure a "Review" tag with a distinctive color (yellow or orange are conventional).
2. Tag *during* play any hand where you felt non-trivial uncertainty at the decision point. The tag takes under a second; the cost is negligible and the signal is strong.
3. At the end of the session, your tagged list is your first-pass review queue.

The reason this works is that in-session uncertainty is noisy at the table (you might tag a hand that turns out to have an obvious answer) but not systematically biased toward big pots or losing hands the way a post-session sort is. The tagged list is closer to your actual distribution of decision difficulty than any retrospective sort will produce.

**Secondary filter — EV loss flags from the solver-backed analyzer.** GTO Wizard's Analyzer produces an EV-loss estimate per decision against its solver baseline [[2]](../sources/05-sources.md) [[3]](../sources/05-sources.md). Using it as a *secondary* filter is useful: take your tagged list first, then run the session through the Analyzer and add any hand with an EV loss above your threshold (a practical starting threshold is 0.5bb per decision for cash, 1bb per decision for MTT). Using it as the *primary* filter is a mistake: you'll review every marginal mixed-strategy spot where the solver estimates a tiny loss against the equilibrium baseline, which trains you to memorize frequencies rather than diagnose patterns. GTO Wizard's own review guidance makes the same point: *don't review every hand the solver flags red — review hands that reveal bigger strategic patterns you don't yet understand* [[1]](../sources/05-sources.md).

**Tertiary filter — recurring-spot recognition.** After a few sessions of this workflow, you'll notice spots that keep showing up in your review queue across sessions. That repetition is itself a signal: when a situation appears in your queue three weeks in a row, it's a chronic leak, and §9 (monthly audit) is where you consolidate them.

**What to skip, explicitly.**

- *Played-itself hands.* You called preflop with AA, flopped top set, stacked off against KK-on-K-flop. No review. You didn't make any interesting decisions.
- *Coolers.* AA vs KK all-in preflop is a rake-paying formality, not a decision. Same for set-over-set all-ins on flop, straight-over-flush rivers, and nut-flush-over-nut-flush runouts. The result is meaningful for variance-tracking purposes but is unreviewable.
- *Auto-fold / auto-call preflop.* 72o UTG fold is not a decision. AKs UTG open is not a decision. Skip.
- *Obvious villain mistakes.* If villain limp-called UTG+1 and then jammed over your 3-bet with 64s, your call with KK is not a review candidate. You made the correct decision against an opponent whose decision was so far off the map that the review would be about *them* and there's no learning for you.

### Examples

**Example 3.1 — 200-hand cash session, realistic filter output.** Player plays 200 hands of 25NL online 6-max, winning 4bb overall. Hand-tagging during play yielded 14 yellow-tagged hands. Post-session Analyzer sweep added 6 more with EV loss ≥ 0.7bb/decision. Total first-pass: 20 hands. Second pass removes 4 coolers (flopped top two into opponent's top set; AA < KK all-in pre; two river flush-over-flush spots where I was on the losing end) and 2 trivial-decision hands. Second-pass total: 14 hands. Review time at ~3 minutes per hand with notes: 45 minutes. Yield: 3 pattern-level leaks identified (over-3-betting from the blinds; too-wide flop c-bet on middle-card dry boards; river bluff-catcher frequency too high with A-high) and 3 concrete drill assignments for the week.

**Example 3.2 — The tagged hand that played out fine.** A mid-stakes grinder tags a hand at the table: held J♠T♠ on a 8♠7♠2♥ flop as the BB vs. BTN SRP, check-called a 33% pot c-bet, turn K♦ checked through, river 4♣, BB checked, BTN bet 75% pot, BB tanked for 15 seconds and called. BTN showed K♥T♥ for top pair-second kicker. BB won the pot. The result is fine. The tag is not about the result — it's about the 15-second tank on the river. Review candidate. The review reveals the BB was considering a check-raise on the turn when the K hit and talked himself out of it; the solver baseline shows check-raise is the higher-frequency line because BB's range has the nut-flush draw and a chunk of two-pair combos while BTN's range on the turn is capped. The diagnosis is *missed turn check-raise on scare cards that favor my range*. Leak: turn aggression on range-shift cards. Drill: node-locked turn-card-categorization for this spot.

**Example 3.3 — When to not review the biggest losing hand.** A tournament player busts a $109 MTT in 80th place when he 3-bet-jammed 77 for 18bb from the BB over a CO 2.2bb open, got called by JJ, and lost. Biggest chip loss of the tournament. Review? Probably not. A 18bb 3-bet-jam with 77 in the BB vs. a CO open is a standard mixed-strategy spot near the solver baseline; the result was the variance realization of a roughly 20% equity hand getting called by a cover. The review is unlikely to produce actionable information beyond "that's standard and sometimes loses." Better review candidate from the same tournament: a level 4 hand where the same player flat-called a 3-bet out of position with A9s at 45bb and had no plan for any turn card. That hand cost less in chips but is a leak that generalizes to dozens of spots.

---

## 4. The session review workflow — 7 steps extended from Doc 1

**Key takeaways**

- The core is Doc 1's 7-step hand analysis workflow. This doc adds a pre-step (establish session context), wraps each hand's analysis in a categorize-and-extract step, and closes with a session-level synthesis.
- Do the steps in order. Skipping step 0 (context) is the single most common failure mode in self-review.
- Speak the reasoning out loud, even alone. Verbalizing forces you to complete the reasoning you'd otherwise shortcut [[11]](../sources/05-sources.md) [[12]](../sources/05-sources.md).
- Every review hand ends with two outputs: a named leak (from §5's taxonomy) and a one-sentence habit/rule to extract. Not three paragraphs of notes — one sentence.
- The session ends with a synthesis: up to three leaks across the session that re-appeared, ranked by frequency.

### Detailed notes

Doc 1's hand-analysis workflow — Steps 0 through 7, ending with *"translate the conclusion into a habit"* — is the spine of per-hand analysis. It is not reproduced here. Read Doc 1's workflow if it isn't loaded. This section assumes it is.

What this section adds is the session-review wrapper. The wrapper has three parts: a pre-step (step 0 of the session review, distinct from step 0 of the per-hand workflow), a per-hand loop (where Doc 1's 7 steps run), and a post-step (the synthesis).

**Session review step 0 — establish the session context.** Before you open any hand:

- Format, stakes, site, table type.
- Total hands played, total duration at the keyboard.
- Overall win/loss in bb/100 or chips.
- Start energy level and end energy level (rate 1-10). Did fatigue affect late-session decisions?
- Any external factors: distractions, multi-tabling load, game selection issues, bankroll context.
- Any mental-game events: a bad beat that lingered, a tilt moment, a rush of confidence after a win.

This information frames every subsequent hand review. A turn decision made in hour 4 of a 7-hour session with 8 tables running is not the same decision as the same spot in hour 1 with 2 tables. Skipping this step is how self-review produces pristine-spherical-cow verdicts that don't transfer to real play.

**Session review step 1 — select the review queue.** Use §3's filter. Produce a list of 5–15% of session hands with rough ordering by expected insight value (yellow-tagged first, then solver-flagged, then anything else).

**Session review step 2 — for each hand in the queue, run Doc 1's 7-step workflow.** No modifications. The one addition: *speak it out loud* even if alone. Jonathan Little's *A Little Coffee* format models this — the entire value of the format is Little narrating his reasoning on camera rather than thinking silently [[12]](../sources/05-sources.md). Verbalization makes you complete the reasoning instead of eliding the hard part. You'll notice where your thinking is thin because the words stop flowing. That's the signal to slow down on that step.

**Session review step 3 — for each analyzed hand, categorize the leak.** Use §5's five-bucket taxonomy (preflop / postflop / ICM / mental / execution). Be specific: "preflop — 3-bet range construction from the BB vs. CO" is categorizable; "preflop" alone is not. If a hand has multiple decision errors, categorize each separately.

**Session review step 4 — for each categorized leak, extract a one-sentence habit.** "When I'm IP on a dry board with a wide preflop range lead, default to 33% c-bet rather than 66%." "When SB flats BTN 2.5x with a merged medium range, I should 3-bet QJs instead of flatting." One sentence. The sentence is what you read before your next session.

**Session review step 5 — session synthesis.** At the end of the queue, look at the leak-categorization results. If a category repeats — two or more hands with leaks in the same subcategory — that's a session-level leak. Write it in a sentence at the top of the journal entry (§7). If no category repeats, the session's leaks were scattered; the review's output is per-hand insights with no session-level theme, which is also a valid result.

**Session review step 6 — convert the session-level leaks (or the scattered leaks, if no theme) into drill assignments.** §6 is the conversion table. The rule: one drill per session-level leak, ten minutes per drill per next-session, maximum two drills. More drills dilutes the focus; fewer is fine.

**Session review step 7 — journal and close.** Write the session journal entry (§7 template), file it, close the review. Do not carry the review into the rest of your day mentally. This is the same discipline Doc 04 prescribes for post-session: the closing of the book is part of the practice.

### Anchor back to Doc 1

Every step of this session-review workflow maps to a Doc 1 concept:

- Session step 0 (context) ↔ Doc 1's hand-analysis step 0 (position / stack / antes), elevated to the session level.
- Session step 2 (run Doc 1's workflow) ↔ directly Doc 1.
- Session step 3 (categorize) ↔ Doc 1's step 7 ("translate the conclusion into a habit") — this doc just operationalizes the naming.
- Session step 4 (extract a sentence) ↔ Doc 1's step 7 again, enforced to one sentence.
- Session step 5 (synthesize) is the piece Doc 1 doesn't have — Doc 1 is scoped to one hand, and this doc adds the session-level pattern recognition on top.

### Examples

**Example 4.1 — A 45-minute session review, step by step.**

*Context (step 0):* 250NL online 6-max, 210 hands, 2.5 hours, two tables, down 2.1 buy-ins. Start energy 8/10, end energy 6/10. No mental-game events; one minor tilt-spike on a river bluff-catcher fold but recovered. No external distractions.

*Queue (step 1):* 11 yellow-tagged in session, 4 added from Analyzer EV-loss sweep, 2 removed as coolers. Final queue: 13 hands.

*Analysis (step 2):* 13 × ~2.5 minutes = ~32 minutes of hand-by-hand workflow, verbalizing each.

*Categorization (step 3):* 4 postflop leaks (2 on flop sizing, 1 on turn barrel selection, 1 on river bluff-catch), 3 preflop leaks (all BB defense), 1 execution leak (misclicked a 3-bet size on the BTN), 5 hands clean / no leak identified after review.

*Habit extraction (step 4):* 7 sentences written, one per leak.

*Synthesis (step 5):* Theme of the session = BB defense and flop sizing. 3 of the preflop leaks are BB defense spots against CO/BTN; 2 of the postflop leaks are flop c-bet sizing that cascaded from wide BB-defense ranges. These connect: my BB defense range is slightly too wide, and as a consequence my flop play OOP with a weak range is expensive.

*Drill (step 6):* Two drills assigned for the week. (1) 15 minutes of BB-defense-range recitation against CO and BTN 2.5x opens at 100bb, three times across the week. (2) 10 minutes of flop-c-bet-sizing drill on dry middle-card boards, once before each session.

*Journal (step 7):* 5-sentence entry in the session journal (§7 template). Close the laptop.

**Example 4.2 — A review that finds nothing actionable.** Sometimes the output of the workflow is "I played close to solver baseline across the queue." That's a valid outcome. The journal entry for that session is short: "Queue of 8, all close to baseline, no pattern-level leak. Session-level verdict: solid play, normal variance." This is rare but real. When it happens, do not manufacture leaks to justify the review time. The review's job is diagnostic; absence of pathology is a finding.

---

## 5. Leak categorization framework

**Key takeaways**

- Five buckets: **preflop**, **postflop**, **ICM**, **mental**, **execution**. Every leak fits into exactly one.
- Each bucket has 3–6 subcategories. The subcategory is what maps to a drill in §6.
- Categorize by *root cause*, not by *symptom*. If the symptom is "lost a big pot on the river" but the root cause is "3-bet bluff construction is too light from the BB," the category is preflop, not postflop.
- The categorization is the bridge between review and drilling. Without it, the loop from §1's *review must close* doesn't.
- Forward to Doc 04 for mental leaks: this doc identifies them; the Mental Game doc treats them.

### Detailed notes

The taxonomy is designed to be exhaustive within the scope of cash and MTT hand review. It is loosely aligned with Red Chip Poker's review categorization [[14]](../sources/05-sources.md) and with the topic structure of Clarke's *Grinder's Manual* [[8]](../sources/05-sources.md), but simplified to five top-level buckets for operational use.

**Bucket 1: Preflop leaks.** Anything that happened before the flop.

Subcategories:
- *Opening range.* Hands you open that you shouldn't, or hands you fold that you should open. Cross-ref: Doc 02 §§1–3.
- *3-bet construction.* Value/bluff balance, polarization vs. merged/linear shape, position-specific frequencies. Cross-ref: Doc 02 §5.
- *4-bet / 5-bet.* Including 4-bet bluff frequency and 5-bet-shove thresholds.
- *BB/SB defense.* Continuance vs. specific opens, call/3-bet/fold splits. Cross-ref: Doc 02 §§7–8.
- *Push-fold (≤15bb MTT).* Cross-ref: Doc 02 §4.
- *Stack-depth mismatch.* Playing a 100bb range at 30bb or vice versa. Cross-ref: Doc 02 §3.

**Bucket 2: Postflop leaks.** Anything that happened on the flop, turn, or river.

Subcategories:
- *Flop c-bet sizing.* Includes c-bet frequency and sizing as IP/OOP preflop aggressor. Cross-ref: Doc 03 (Postflop Solver Concepts) — flop c-bet sizing matrix.
- *Turn play.* Barrel selection, turn card categorization, turn check-raise frequencies.
- *River play.* Value bet sizing, bluff-catch frequencies, blocker effects on bluffs. Cross-ref: Doc 03 blocker theory.
- *Hand-reading accuracy.* Street-by-street range-narrowing errors. Cross-ref: Doc 1, Step 6 of the hand-analysis workflow, and Doc 03's range-vs-range framing.
- *Bet sizing.* Any sizing choice not caught by the c-bet/turn/river subcategories. Usually means "I sized wrong for the texture and position."
- *Equity realization.* Playing hands whose equity doesn't translate to EV, especially OOP in 3-bet pots and with small pairs and non-suited connectors. Cross-ref: Doc 03 equity realization.

**Bucket 3: ICM leaks.** Tournament-only, and only at stages where ICM pressure is live (final tables, satellite bubbles, significant pay-jump proximity).

Subcategories:
- *Big-stack over-cautious.* Failing to apply ICM pressure when covering. Cross-ref: Doc 06 — ICM Deep-Dive (topic: big-stack strategy).
- *Medium-stack miscalibration.* Playing too loose or too tight relative to the bubble factor.
- *Short-stack ladder vs. accumulate miscall.* Shoving too wide when survival dominates, folding too tight when accumulation dominates.
- *Satellite-specific.* Folding AA pre on a satellite bubble, or failing to recognize the satellite math at all. Cross-ref: Doc 06 — satellite strategy.

**Bucket 4: Mental leaks.** Decisions affected by the player's state rather than the spot.

Subcategories:
- *Tilt-reactive.* Aggression spikes after beats; frequency drift after losses. Cross-ref: Doc 04 — tilt taxonomy.
- *Fatigue.* Late-session decision quality decay. Cross-ref: Doc 04 — session structure.
- *Overconfidence.* Frequency inflation after wins; moving up prematurely. Cross-ref: Doc 04 — upswing management.
- *Avoidance.* Skipping marginal EV+ spots because they're uncomfortable. Distinct from tight play — this is refusing spots that the player knows are EV+.
- *Results-orientation.* Changing frequencies based on recent outcomes rather than decision quality. This is the Doc 1 anti-pattern surfacing in review data.

The diagnostic for mental leaks is *the same spot played differently on different days*. If your 3-bet frequency from the BB swings from 11% to 22% across sessions with no change in player-pool or stack depth, that's a mental-leak signal. The fix is in Doc 04, not here.

**Bucket 5: Execution leaks.** Mechanical / interface errors, not decision errors.

Subcategories:
- *Misclicks.* Wrong button; wrong sizing slider.
- *Table-management.* Sitting with insufficient buy-in; staying in too long; game-selection drift.
- *Note/HUD issues.* Playing without notes you should have; ignoring notes you do have.
- *Time-bank mismanagement.* Running out of time in spots that needed thinking.

Execution leaks are easy to dismiss ("I misclicked once, no big deal") but over a month's sample can account for multiple bb/100 in lost EV. The monthly audit (§9) is where they get surfaced.

**Categorization rule: root cause over symptom.** The single most important rule in this section. A hand where you "lost a big pot on the river" categorizes by what the actual error was, not by when the money went in. If you opened too wide preflop and everything cascaded from there, the category is preflop. If you 3-bet the right shape but picked the wrong bluff combo, the category is preflop (3-bet construction), not postflop. If you played the postflop correctly given a reasonable preflop range but the hand was unwinnable because the range was wrong, the category is preflop. Getting this right is what makes §6 (leak-to-drill) work: drilling postflop c-bet sizing does nothing for a preflop-range leak.

### Examples

**Example 5.1 — Root-cause vs. symptom.** Player open-raises K9o UTG at 100bb 6-max cash, gets 3-bet by BB, calls, flops K72r, faces a 33% pot c-bet, calls, turn is 5c, BB bets 75%, hero folds. Turn fold cost the pot; symptom location = turn. But the leak is preflop: K9o UTG is a fold in modern solver charts (Doc 02 §2) and the hand was losing EV from the moment it entered the pot. Category: preflop, subcategory = opening range.

**Example 5.2 — Mental leak surfaced via frequency swing.** Across four consecutive sessions, a player's BB defense-vs-BTN frequency is 44%, 42%, 58%, 51%. The 58% session lines up with a session that followed a large downswing day. Root-cause categorization: mental, subcategory = tilt-reactive. Fix lives in Doc 04 (emotional-state routines pre-session and in-session checks). The review here flags the leak; it doesn't treat it.

**Example 5.3 — Execution leak that looks strategic.** Player routinely opens 2.5bb on the BTN in an online 100bb cash game where the site's one-click sizing slider default is 2.5bb. In the same player's live 9-max game, the click sequence produces a 3bb open. Player's online BTN winrate is 8bb/100; live BTN winrate is 2bb/100. After review, the culprit isn't strategy — it's that online-calibrated BTN ranges are quantitatively wrong for the 3bb live open size (Doc 02 §1's conditional-baseline point). Category: execution, subcategory = table-management (failing to adjust sizing across formats), not strategy.

---

## 6. Leak-to-drill conversion

**Key takeaways**

- Every categorized leak maps to one or two drills in the Drill Library (Doc 07).
- The conversion table below is the operational bridge. One leak → one drill as the default; two drills only for chronic leaks surfaced by the monthly audit (§9).
- Drill duration: 10–20 minutes per session, before the session starts. Not after.
- If no drill exists in Doc 07 for an identified leak, either (a) the leak is novel and warrants a new drill proposal for the Drill Library, or (b) the leak is mental and lives in Doc 04's routines, not in a drill format.
- Rotate drills weekly. Drilling the same thing for four weeks stops producing gains; the effective range of a single drill focus is ~5–10 sessions.

### Conversion table

The table below uses the five-bucket taxonomy from §5. Cells map a subcategory to a drill in Doc 07. Drill names follow Doc 07's naming convention; forward references are placeholders until that doc lands.

| Leak category | Subcategory | Primary drill (Doc 07) | Secondary, if chronic |
|---|---|---|---|
| Preflop | Opening range | Position-by-position range recitation | Range-vs-action quiz |
| Preflop | 3-bet construction | Polarized-vs-linear shape drill | 3-bet combo selection |
| Preflop | 4-bet / 5-bet | 4-bet-or-fold threshold drill | — |
| Preflop | BB/SB defense | Defense-frequency-by-opener drill | BB 3-bet-vs-call selection |
| Preflop | Push-fold (≤15bb) | Nash push-fold flash drill | ICM-adjusted push-fold (see ICM bucket) |
| Preflop | Stack-depth mismatch | Depth-recognition drill | — |
| Postflop | Flop c-bet sizing | Texture-to-sizing mapping drill | C-bet frequency quiz |
| Postflop | Turn play | Turn card categorization drill | Turn check-raise spots |
| Postflop | River play | River value-vs-bluff-catch drill | Blocker selection drill |
| Postflop | Hand-reading | Street-by-street range-narrowing drill | Combo-counting drill |
| Postflop | Bet sizing | Sizing-by-texture drill | — |
| Postflop | Equity realization | R% intuition drill | Small-pair implied-odds quiz |
| ICM | Big-stack over-cautious | Risk-premium estimation drill | — |
| ICM | Medium-stack miscalibration | Bubble-factor quick-estimation | — |
| ICM | Short-stack ladder/accumulate | Ladder-vs-accumulate scenario drill | — |
| ICM | Satellite-specific | Satellite-math quick drill | — |
| Mental | Tilt-reactive | *(no drill — see Doc 04 tilt routines)* | — |
| Mental | Fatigue | *(no drill — see Doc 04 session-structure routines)* | — |
| Mental | Overconfidence | *(no drill — see Doc 04 confidence calibration)* | — |
| Mental | Avoidance | *(no drill — see Doc 04)* | — |
| Mental | Results-orientation | Decision-quality rubric drill | Doc 04 routines |
| Execution | Misclicks | Table-interface-reset checklist | — |
| Execution | Table-management | Pre-session game-selection checklist | — |
| Execution | Note/HUD issues | HUD-layout audit drill (see Doc 08) | — |
| Execution | Time-bank | Time-bank discipline self-check | — |

### Detailed notes

The conversion table is deliberately conservative about "secondary" drills. A common mistake in self-directed study is to drill five related things at once; the return is diminishing because the session-to-session reinforcement gets spread across too much surface area. Single-drill focus produces measurable improvement faster, even if it feels less ambitious.

The *no drill* cells under Mental are not omissions — they're deliberate. Mental leaks do not respond to technical drilling. Drilling tilt-recovery is drilling the wrong thing; the treatment is the pre-session and in-session routines in Doc 04. The only mental subcategory with an operational drill is *results-orientation*, and that drill is really a meta-skill drill (rating decisions on a rubric without reference to the outcome) rather than a technical one.

**Rotation and retirement.** A drill earns its place by producing identifiable frequency change in play. Run a drill for 5–10 sessions. If the leak category appears less often in the review queue, the drill is working — keep it another 2–3 sessions, then retire it and rotate to the next queued leak. If the leak category appears the same or more often, the drill is wrong — reconsider whether the root-cause categorization was correct (§5) before re-drilling. Ericsson's feedback-informed practice framework applies directly here: a drill without measurable feedback on the behavior it targets is just busywork [[9]](../sources/05-sources.md).

### Examples

**Example 6.1 — Single-leak single-drill flow.** Session review produces one theme: BB defense frequency is too loose vs. CO. Category: preflop, subcategory = BB/SB defense. Primary drill (per table): defense-frequency-by-opener drill. Assigned: 15 minutes before each of the next 5 sessions, BB-defense range recitation vs. each position's 2.5x open at 100bb. After 5 sessions, review the week's data — if BB-vs-CO defense frequency has moved from 54% toward the solver baseline of ~49%, drill is working; continue for 3 more sessions, then rotate.

**Example 6.2 — Two drills for a chronic leak.** Monthly audit surfaces turn play as a leak showing up in 3 of 4 weeks. Category: postflop, subcategory = turn play. This is chronic, not episodic, so both drills from the table apply: turn-card-categorization drill and turn-check-raise-spots drill. Allocation: 10 minutes each, three sessions per week each, for 3 weeks. Measure re-appearance rate at the next monthly audit.

---

## 7. Session journal template

**Key takeaways**

- The journal is the artifact of every session review. No journal entry = no review closure.
- Format: short and structured. 5–10 sentences plus the leak table. Never more than one page.
- The journal serves two purposes: (a) forces the synthesis in §4 step 7; (b) becomes the input to the weekly review (§8) and the monthly audit (§9).
- Use a dated-filename convention (`2026-04-16-session.md` or similar) so chronological sorting is automatic.
- Write in present tense when describing leaks ("I over-defend the BB vs. CO"), not past tense. Present tense signals it's a current tendency to fix; past tense lets you rationalize it as a one-time event.

### The template

Copy this into a new file at the end of every session. Replace the bracketed fields. Keep the structure; adjust the length as honest reporting requires.

```markdown
# Session review — [YYYY-MM-DD]

## Context

- Format: [cash / MTT / SNG / satellite] · [stakes] · [site]
- Duration: [N hours] · Hands: [N] · Tables: [N]
- Result: [+/− N bb/100 or chips] · Variance notes: [coolers or runouts worth flagging]
- Start energy [1–10] → End energy [1–10]
- Mental-game events: [tilt moment? bad-beat lingering? confidence rush? "none" is a valid answer]
- External factors: [distractions, game-selection issues, bankroll context]

## Queue

- Yellow-tagged during play: [N]
- Analyzer-flagged (EV loss ≥ threshold): [N]
- After filter: [N hands reviewed]

## Leaks identified

| # | Hand description (one line) | Category | Subcategory | Habit extracted (one sentence) |
|---|---|---|---|---|
| 1 | [e.g., BB flat vs CO 2.5x with J9s, no plan for turn] | Preflop | BB defense | [e.g., "I don't flat low suited connectors OOP against CO without a defined turn plan."] |
| 2 | | | | |

## Session-level synthesis

[One paragraph, 2–4 sentences. If a leak category repeated across multiple hands, that's the session theme — name it. If not, note that the session's leaks were scattered.]

## Drill assignment for the week

- Drill: [name from §6 conversion table]
- Duration: [N minutes per session]
- Frequency: [N sessions per week]
- Start date: [YYYY-MM-DD]

## Followups / open questions

[If a hand review surfaced a question you couldn't resolve alone — solver shape you don't understand, range assumption you're not sure about — log it here. Resolve at the weekly review or in a dedicated study block.]
```

### Detailed notes

**Why the template is rigid.** Every field serves a downstream purpose. Context establishes the frame for the weekly review. The queue counts feed the monthly audit's filter-calibration analysis ("am I over- or under-filtering?"). The leak table is the input to §5 and §6. The synthesis is what Doc 1 would call the *translated habit* at the session level. The drill assignment is the loop-closer from §1's philosophy. Each field's absence breaks a specific downstream step.

**Why one-sentence habits.** A habit you can recite in one sentence is a habit you can run at the table. A three-paragraph analysis is a habit you can't retrieve under decision pressure. The constraint is not aesthetic — it's operational.

**Why present tense.** Present-tense leak-description ("I over-defend") is a statement about tendency. Past-tense ("I over-defended") is a statement about a single hand, which lets you rationalize the leak as an exception. Tense is a small thing with a large effect on whether the review changes next session's play.

### Example

**Example 7.1 — Filled template from a realistic session.**

```markdown
# Session review — 2026-04-15

## Context

- Format: cash · 100NL 6-max · site X
- Duration: 2.5 hours · Hands: 215 · Tables: 3
- Result: −2.1 buy-ins. Variance: one flopped set-over-set (~1.3 buy-ins); otherwise no major coolers.
- Start energy 8/10 → End energy 6/10
- Mental-game events: one minor tilt-spike hour 2 after a river bluff-catcher fold shown down as correct but still felt wrong for ~15 minutes. Recovered.
- External: partner asked me to help with groceries mid-session — 10 min break at hour 1.5. No other distraction.

## Queue

- Yellow-tagged during play: 11
- Analyzer-flagged (EV ≥ 0.5bb): 6
- After filter: 13 hands reviewed (2 removed as coolers, 2 as trivial)

## Leaks identified

| # | Hand | Category | Subcategory | Habit |
|---|---|---|---|---|
| 1 | BB flat vs CO 2.5x, J9s, no turn plan | Preflop | BB defense | I don't flat low suited connectors from BB OOP vs. CO without a defined turn plan. |
| 2 | c-bet 2/3 pot on K92r from BTN vs BB | Postflop | Flop c-bet sizing | On dry K-high boards IP vs. a capped BB range, I c-bet 33% not 66%. |
| 3 | c-bet 2/3 pot on 974tt from BTN vs BB | Postflop | Flop c-bet sizing | Same — on dry low-card boards IP vs. capped range, 33% not 66%. |
| 4 | 3-bet bluff AJo from SB vs BTN 2.5x | Preflop | 3-bet construction | I don't 3-bet AJo from SB vs. BTN — it plays worse than flatting in the linear range. |
| 5 | River bluff-catcher fold with A♠2♠ on K-Q-7-4-A♠ | Postflop | River play | On a board where a flush arrives on the river as a 3-card monotone, my bluff-catcher is too weak against the opponent's range. |

## Synthesis

Session theme: flop c-bet sizing. Two of five identified leaks are variants of the same pattern — I default to 66% on dry boards IP in position where the solver-baseline is 33%. The BB-defense leak (hand 1) is a known recurring issue that the BB defense drill from week 3 hasn't fully closed; second-order issue this week.

## Drill assignment

- Drill: Texture-to-sizing mapping drill (Doc 07).
- Duration: 15 minutes per session.
- Frequency: 3 sessions this week.
- Start date: 2026-04-17.

## Followups

- Hand 5 (river fold on monotone). Want to check the solver's overall bluff-catch frequency on 3-card-monotone rivers in this spot against a capped range. Log for weekend study block.
```

---

## 8. Weekly review process

**Key takeaways**

- The weekly review takes the week's session journal entries as input and produces a list of *repeated* leaks — the ones that showed up in two or more sessions.
- Duration: 60–90 minutes, typically a weekend morning.
- The output is one to three prioritized drill assignments for the next week. Same one-drill-per-leak rule as per-session, applied at the weekly level.
- The weekly review is also where "followups" from per-session journals get resolved — hands where you weren't sure, solver outputs you wanted to check, range assumptions to verify.
- Without the weekly review, per-session reviews fragment. Session-level leaks never consolidate into week-level patterns, and the drill assignments stay scattered.

### Detailed notes

The workflow:

1. **Aggregate.** Open all session journals from the past 7 days. For most players this is 2–5 entries. List every leak (row) from every entry's leak table into one combined list.
2. **Group by subcategory.** Using §5's subcategories, group leaks that share a subcategory. "BB defense" from Monday's session and "BB defense" from Thursday's session go together.
3. **Find the repeats.** Any subcategory with ≥2 entries across the week is a *weekly leak*. Any subcategory with 1 entry is an isolated observation — note it but don't drill it yet. Wait to see if it repeats next week.
4. **Prioritize.** If you have more than three weekly leaks, pick the three with the highest EV impact (usually preflop and flop-c-bet leaks — they touch the most hands). The remaining leaks roll to next week's data.
5. **Resolve followups.** Each session journal's followups section goes into a targeted 15–30 minute study block now. Solver checks, range-verification queries, anything you flagged in-week as "need to think about."
6. **Assign drills.** One drill per weekly leak from §6's conversion table. The drill assignment overrides whatever per-session drills were assigned that week — the weekly view wins.
7. **Write the weekly summary.** One-paragraph entry noting the weekly leaks, the drills, and any trend from prior weeks (carry-over leaks vs. new leaks vs. retired leaks).

**The trend view.** The second time you run a weekly review, you have the previous week to compare against. A subcategory that appeared in week N-1 and again in week N is escalating toward *chronic leak* status (§9's domain). A subcategory that appeared in week N-1 but not in week N is evidence the drill is working — worth one more week of drilling then rotate. A subcategory that appears in week N for the first time is new data — one more week of observation before committing drill resources.

**The "followups" resolution block.** Many per-session followups are solver-check questions — "what's the actual c-bet frequency on T-high monotone flops from CO vs. BB?" — that take 5–10 minutes to resolve with a solver query. Batching them into a weekly block is cheaper than resolving each mid-session. The pattern makes the per-session review short (because unresolved questions are deferred, not investigated) and concentrates solver time into one focused block, which also matches deliberate-practice theory's repetition-with-feedback requirement [[9]](../sources/05-sources.md).

### Examples

**Example 8.1 — A typical weekly review.** 4 sessions that week, 4 journal entries. Aggregated leak list: 12 leaks total. Grouped: flop c-bet sizing (×3), BB defense (×3), turn barrel selection (×2), river play (×2), one-off misclick (×1), one-off 3-bet bluff selection (×1). Weekly leaks: c-bet sizing, BB defense, turn barrel. Prioritization: c-bet sizing is highest-frequency (touches every SRP I play as the preflop aggressor); drill that. BB defense has a drill running from two weeks ago; keep it. Turn barrel is new to this week but clearly a weekly leak already; add as second drill. Followups (4 total): solver-check on 3-card-monotone-river bluff-catch frequencies (hand 5 from 04-15), solver-check on OOP c-bet frequency in 3-bet pots on dry boards, re-run BB defense range memorization once, and a quick push-fold Nash verification for one MTT hand.

---

## 9. Monthly leak audit

**Key takeaways**

- The monthly audit takes the past 3–5 weekly summaries and identifies *chronic* leaks — ones that appeared in 3 or more weeks.
- Chronic leaks get more intensive treatment: dedicated study blocks, possibly a coach session (§11), possibly a temporary reduction in play volume to create study space.
- The monthly audit also retires solved leaks, archives drills that have finished their cycle, and resets the priority list for the next month.
- Duration: 2–3 hours, typically the first weekend of the month. Takes the place of that weekend's weekly review.
- This is also where execution leaks (§5 bucket 5) usually surface — individual misclicks and table-management issues are easy to dismiss in a per-session review but add up visibly over 4 weeks.

### Detailed notes

The 4-week view exposes patterns that weekly reviews can miss. A subcategory that appeared in 1 of 4 weeks is episodic — probably a mental-state event or a variance cluster. A subcategory that appeared in 3+ of 4 weeks is chronic, and chronic leaks do not fix themselves with per-session drills. They need concentrated study time or external input.

The audit workflow:

1. **Aggregate the weekly summaries.** Usually 4 summaries per month.
2. **Count subcategory occurrences across weeks.** A table with subcategory rows and week columns; mark an X in the column if that subcategory was a weekly leak that week.
3. **Classify each subcategory.**
   - *Chronic* (3-4 weeks): priority leaks. These drive next month's primary drill rotation.
   - *Persistent* (2 weeks): keep the drill running; monitor.
   - *Episodic* (1 week): no action; watch next month.
   - *Retired* (was chronic or persistent in the prior month but hasn't appeared this month): remove from drill rotation, confirm fix has stuck.
4. **Check execution leaks.** Even single-session execution-leak events, aggregated across a month, show patterns: 4 misclicks in 4 weeks suggests a table-interface issue; 2 bankroll-stretch sessions in 4 weeks suggests a game-selection drift. Flag these separately from decision leaks.
5. **Assign the next month's drill rotation.** 1–2 drills on chronic leaks (top priority), 1 drill on persistent leaks, any new-hire drills as they emerge during the next month.
6. **Consider coach involvement (§11).** Chronic leaks that haven't responded to 4 weeks of self-directed drilling are candidates for a coaching session. Coaches catch leaks in your reasoning that you can't catch alone because the blind spot is, by definition, something you can't see [[10]](../sources/05-sources.md).
7. **Write the monthly audit summary.** One page. The chronic list, the retired list, the next-month drill plan, any coach-consideration decisions.

**Deliberate-practice cross-check.** The monthly audit is also where you verify that your study is meeting deliberate-practice conditions. A check:

- Are the drills you're running producing measurable change (leak frequency in the review queue)? If not, the feedback condition is failing.
- Is the difficulty appropriately set? Drilling BB defense on 100bb cash when your leaks are all at 30bb MTT is difficulty-mismatched; fix the drill selection.
- Are you actually running them, not just assigning them? Self-report in the monthly audit whether the drills happened.
- Is the motivation still there? A month of missed drills often signals a mental-game issue, not a discipline failure. Doc 04.

### Example

**Example 9.1 — A monthly audit.** 4 weekly summaries. Subcategory counts: flop c-bet sizing (4/4 weeks) — **chronic**. BB defense (3/4) — **chronic**. Turn play (2/4) — **persistent**. River play (1/4) — **episodic**. 3-bet construction (3/4 two months ago, 0/4 this month) — **retired**. Execution leaks: 3 misclicks across the month, all on the same software; flag as interface issue. 1 late-night session with clear fatigue-driven frequency drift; flag as session-structure issue (→ Doc 04).

Next month's drill rotation: primary — texture-to-sizing drill (chronic c-bet sizing). Secondary — BB defense range drill (chronic, carryover). Maintenance — turn card categorization drill once per week (persistent).

Coach involvement decision: c-bet sizing has been chronic for two months. Book one coach session to review the chronic spots and get a second-opinion diagnosis of the root cause.

Execution fix: reconfigure software sizing buttons to eliminate the misclick source.

---

## 10. HUD-assisted review — basics

**Key takeaways**

- A HUD and tracker are *review tools*, not play tools. Their primary value is the database they build — the database is what makes §3's filtering and §9's chronic-leak tracking possible.
- Modern trackers (PokerTracker 4, Hand2Note, Holdem Manager 3) all provide: hand tagging with colors, filter-by-position / stack / action, EV loss (when coupled with a solver-backed analyzer), session-level stats, and long-run leak-finders [[19]](../sources/05-sources.md) [[20]](../sources/05-sources.md) [[21]](../sources/05-sources.md).
- This doc takes a tool-agnostic position on which tracker to use. Tool comparisons live in Doc 08 — Modern Training Resources.
- At minimum, configure: (a) a "Review" color tag for in-session marking, (b) an EV-loss sort for sessions, (c) a filter for position × action combinations you want to monitor.
- HUD-assisted review at the micro stakes is usually *over*-applied. Below 25NL online cash, most leaks are behavioral (tilt, game selection) or mechanical (sizing defaults) and don't need the tracker to surface them.

### Detailed notes

The review-tool value proposition is modest and specific. A tracker is extremely good at answering questions like: "What's my VPIP from the BB vs. a CO 2.5x open across 10,000 hands?" It's mediocre at answering questions like: "What's my reasoning error on a specific turn barrel decision?" The first class of questions is where the tracker earns its place; the second is where the per-hand review workflow (§4) does the work.

**Minimum configuration — operational list.**

- *Color tags.* Four is enough: yellow for "review later," orange for "definitely a leak," red for "egregious," and green for "well-played, want to remember the reasoning." PokerTracker's tag documentation describes the mechanics [[21]](../sources/05-sources.md).
- *Filters.* Build filters for your most-played position-action combinations: "BTN open and got 3-bet," "BB defended vs. CO 2.5x," "OOP in 3-bet pot," "SB open-raise." These become the queries for the weekly review's trend view.
- *EV-loss sort.* When paired with a solver-backed analyzer (GTO Wizard's Analyzer is the mainstream version in 2026), the tracker can surface hands where your decision lost a specified amount of EV against the solver baseline [[2]](../sources/05-sources.md) [[3]](../sources/05-sources.md). Use this as the secondary filter in §3.
- *Session stats.* Configure a dashboard showing per-session: hands played, bb/100, VPIP, PFR, 3-bet%, fold-to-c-bet, and one or two leak-specific stats (BB defense, for example). The session-stats view is useful in §4 step 0 — it gives you a factual baseline about the session that your memory might distort.

**The over-application caveat.** Below 25NL online cash (or equivalent live-stake buy-ins), the HUD-tracker's leak surfacing is a lower priority than behavior: game selection, tilt management, session length discipline, bankroll adherence. A player at those stakes who's spending 30% of their study time on tracker filters is usually procrastinating on the mental-game leaks that are larger in bb/100. Doc 04 handles the behavior side; this doc's §5 mental-leak bucket is the redirect path. The tracker is a tool that becomes more valuable as stakes go up, not the reverse.

**Tool selection.** PokerTracker 4, Hand2Note, Holdem Manager 3, and smaller tools each have feature and pricing trade-offs; comparisons live in Doc 08 and are deliberately out of scope here. The review workflow in §§4–9 is tool-agnostic and works with any of them. If you don't have a tracker yet, use a spreadsheet — the session journal template in §7 is a paper-and-pencil equivalent of what a tracker would produce, and it's better than no review at all.

### Examples

**Example 10.1 — A modern review setup.** PokerTracker 4 with the four-tag scheme; GTO Wizard's Analyzer on auto-upload so hands queue to the Analyzer as played [[2]](../sources/05-sources.md); custom filters saved for the five position-action combinations the player is currently leak-hunting. Weekly review workflow: open PT4, filter by yellow tag for the week, work through in chronological order using the §4 workflow; then open GTO Wizard Analyzer, pull the EV-loss > 0.5bb list for the same week, add any not already reviewed; sum the leak categorizations into the weekly summary (§8). Tooling time: ~15 minutes for setup and filtering; ~70 minutes for the actual review workflow.

**Example 10.2 — The micro-stakes overuse pattern.** 5NL player reports playing 40 hours of hands per week and studying 10 hours per week, with 7 of those 10 hours going to tracker filters and HUD leak-finders. Identified leaks from the tracker: 3-bet frequency from BTN is 4% lower than solver baseline; BB defense frequency is 6% lower than solver baseline. Monthly winrate: -1.8bb/100. The diagnosis: the tracker-flagged leaks are real but small; the actual problem is that 8 of 40 weekly play hours are happening after 11pm with visible fatigue (bb/100 in those hours is -9bb vs. +2bb in earlier hours). Redirect: 70% of study time should shift to session-structure and game-selection work (Doc 04), not tracker filtering.

---

## 11. Solo vs. group / coached review

**Key takeaways**

- Solo review is the default. It has to be learned first, and it's the foundation of any other review format.
- Group review (peer-reviewed hand histories, study group with shared sessions) adds *external perspective* on reasoning you can't see alone.
- Coached review — 1:1 with someone visibly stronger than you — is the highest-leverage format per hour, but only when the coach can diagnose leaks you haven't yet identified [[13]](../sources/05-sources.md).
- Ericsson's deliberate-practice literature finds that coached practice outperforms solo practice by roughly 2-3x in most studied domains, but only when the coach can see deficiencies the practitioner cannot see yet [[10]](../sources/05-sources.md).
- Don't hire a coach for leaks you can fix yourself. Coach time is expensive; reserve it for leaks that have been chronic across 4+ weeks of self-review.

### Detailed notes

**When to bring in a second set of eyes.** The useful operational test: if your monthly audit shows a leak that has been chronic for 8+ weeks and hasn't responded to targeted drilling, you have a blind spot. Blind spots are called that for a reason — you can't see them by looking harder. Another person can, either because they recognize the pattern from their own development or because your reasoning-out-loud exposes the step where your thinking is going wrong.

**Group review.** Free, accessible, usually via a study group or an online community like a discord, a 2+2 post with a hand history, or a subreddit review thread. Benefits: exposure to other players' reasoning, diverse perspectives, cheap ongoing access. Limits: the average strength of group reviewers is roughly the average strength of the group, which is usually your stakes-peer group. You're more likely to find a diagnosis you already suspected than a diagnosis you didn't. Useful for checking specific spots; insufficient as a sole review format.

**Coached review.** A 1:1 session with a paid coach working through hand histories you've pre-selected. Benefits: the coach sees blind spots, asks diagnostic questions you wouldn't ask yourself, and calibrates difficulty to your level. Jonathan Little's Platinum Coaching Series is a public example of the hand-history-review coaching format; the 15-video progression is structured around student-input review of specific hands [[13]](../sources/05-sources.md). Limits: cost (hundreds to low-thousands of dollars per hour at top-tier), scheduling friction, and the tendency of some students to substitute coach time for their own review practice.

**How to prep for a coached session.** Select 5–10 hands you've already reviewed solo and flagged as either (a) you don't understand the solver recommendation, or (b) you believe you played correctly but have a chronic leak pattern in that spot. Don't show up with 30 random hands from the session — that wastes the first 45 minutes on context. Show up with a pre-selected queue and a specific question. Best coached sessions come from "I'm not sure why the solver prefers X here" questions; least useful come from "did I play this right?" questions.

**The deliberate-practice angle.** Ericsson's 2008 synthesis is explicit that coached practice is not universally better than solo practice — it depends on whether the coach can identify leaks the student cannot see [[10]](../sources/05-sources.md). A coach who only confirms the student's own diagnosis is not adding much. A coach who reveals a blind spot is worth the rate. Before hiring, ask what they'll specifically look for that you haven't been looking for.

### Examples

**Example 11.1 — Group review gets the diagnosis right.** A 100NL grinder posts a chronic-leak pattern (c-bet sizing on middle-card dry boards) in a study group. A peer who has worked the same spot points out the grinder is sizing for the solver baseline against a merged BB range but playing against a pool that has a wider, more polarized call-range, which makes 66% over-sized against the actual population. Fix: 50% on those boards for population adjustment. This is a diagnosis the grinder wasn't going to produce alone; a peer produced it for free. Net value: high, low cost.

**Example 11.2 — Coached session for a chronic blind spot.** Same grinder has a chronic leak that has resisted 8 weeks of drilling: out-of-position 3-bet-pot river play against specific villain types. Books a 90-minute session with a coach at 200NL+ experience. Pre-sends 6 selected hands. Coach identifies in the first 20 minutes that the grinder is calling too many bluff-catchers without a planned escape — the problem isn't the river decision, it's the flop check-call that committed the grinder to a river decision tree with too few folds. Diagnosis was not on the grinder's radar. Fix: flop check-raise frequency in that spot. Net value: diagnosis that was chronic for 8 weeks resolved in one session. Cost: coach's hourly rate. EV justification: the leak was bleeding ~2bb/100 across relevant sessions; projected annual EV recovery substantially exceeds the session cost.

**Example 11.3 — When not to hire a coach.** A 25NL player with a 3-month track record, no journaling practice, and no tracker. First priority is not a coach — it's getting a basic review workflow running (this doc's §§1–7) and 4 weeks of solo data. Most of the leaks at 25NL resolve with structured solo review. Spend coach budget later, once the solo practice has surfaced the blind spots that actually need external help.

---

## 12. Anti-pattern table — consolidated

Anti-patterns that show up in self-review. Each one is diagnosed here; most link back to a section of this doc or a sibling doc for the fix.

| The anti-pattern | Why it happens | The fix |
|---|---|---|
| **Reviewing the biggest losing pot** | Emotional weighting; easier to rationalize study time after a loss. | §1 and §3. Review by in-session uncertainty, not by stack-impact. |
| **Reviewing every hand** | Completeness bias; belief that more-is-better in study. | §3. Filter to 5–15% of hands. Reviewing 200 hands produces 200 shallow passes, not 200 deep diagnoses. |
| **"Was this hand right?" framing** | Single-hand verdicts feel satisfying. | §1 core thesis. The unit of review is a *pattern* across hands, not a per-hand verdict. |
| **Batching a week of sessions into one review** | "I'll do it all Sunday." In-session context has decayed by then. | §2. Review within 24 hours of playing. Weekly review is additive, not a substitute. |
| **Reviewing tilted** | Emotional activation demands action. | §2 exception. Wait until the activation has cleared. Doc 04 for the pre-review check-in routine. |
| **Categorizing by symptom, not root cause** | "Lost on the river → postflop leak." | §5. Categorize by the decision that caused the cascade, not by when the money went in. |
| **Drilling everything at once** | Ambition; wanting to fix all leaks simultaneously. | §6. One drill per leak. Rotate weekly. Drilling five things produces diffuse reinforcement on all five. |
| **No journal** | Feels bureaucratic; review notes stay in head. | §7. Without the journal artifact, weekly and monthly reviews have no input and sessions fragment. |
| **Skipping the session context step** | "I know the session, why re-state it?" | §4 step 0. Context frames every subsequent decision; memory distorts the frame faster than expected. |
| **Past-tense leak descriptions** | "I over-defended" reads as a one-time event. | §7. Use present tense ("I over-defend") to signal the leak is a current tendency. |
| **Drilling leaks that never re-appear** | Drill rotation too slow. | §6 and §9. Retire a drill when the leak frequency drops. Chronic leaks earn the drill; episodic ones don't. |
| **Tracker-filtering as substitute for thinking** | Tool use feels productive without being productive. | §10. The tracker surfaces filterable questions; the review workflow does the thinking. |
| **Hiring a coach for leaks you haven't diagnosed yourself** | Shortcutting solo practice. | §11. Build the solo workflow first; coach time is for blind spots, not for leaks already visible in the journal. |
| **Reviewing to feel better** | Review as self-soothing after a loss. | §1 philosophy; Angelo's reciprocality frame [[7]](../sources/05-sources.md). The goal is diagnosis, not reassurance. |
| **Moralizing instead of diagnosing** | "I'm just undisciplined." Vague, unactionable. | Name a specific leak category (§5). Every vague self-critique is actually a specific pattern; find the pattern. |
| **Judging decisions by results** | The Doc 1 anti-pattern surfacing in review data. | Doc 1 *decisions-not-results*. Every leak row in §7's table is about the decision given the information available — never about the outcome. |

---

## Quick-reference cheat sheet

### When a student says "help me review," run this sequence

1. *Context.* Format, stakes, duration, hands, result, energy, mental-game events. (§4 step 0)
2. *Filter.* Yellow-tagged first; Analyzer-flagged second; skip coolers and auto-decisions. Target 5–15% of hands. (§3)
3. *Per-hand.* Run Doc 1's 7-step workflow. Verbalize. (§4 step 2)
4. *Categorize.* Preflop / postflop / ICM / mental / execution. Root cause, not symptom. (§5)
5. *Extract.* One-sentence habit per leak. Present tense. (§4 step 4)
6. *Synthesize.* Look for the session theme — 2+ leaks in one subcategory. (§4 step 5)
7. *Drill.* One drill per theme, from §6's table. 10–20 minutes per session, 3–5 sessions. (§6)
8. *Journal.* §7 template. Dated filename. Close the review. (§7)

### Key rules

- **Review within 24 hours.** Not later.
- **Never while tilted.** Wait.
- **Present tense in leak descriptions.** "I over-defend," not "I over-defended."
- **One drill per leak.** Rotate weekly.
- **Followups go to the weekly review.** Not into the session review.
- **The biggest losing pot is usually not the best review candidate.** Filter by uncertainty, not by stack-impact.

### Cadences

- Session review: 15–45 min, within 24 hours.
- Weekly review: 60–90 min, weekend morning.
- Monthly audit: 2–3 hours, first weekend of the month.

### Five leak categories

1. **Preflop** — ranges, 3-bet/4-bet, defense, push-fold, depth.
2. **Postflop** — c-bet, turn, river, hand-reading, sizing, R%.
3. **ICM** — big / medium / short stacks, satellites.
4. **Mental** — tilt, fatigue, overconfidence, avoidance, results-orientation. (Fixes live in Doc 04.)
5. **Execution** — misclicks, table-management, HUD, time-bank.

### Three highest-leverage habits

- Mark hands during play. Never trust retrospective hand selection.
- Write the journal, every session. Without the artifact, no downstream review works.
- Close the loop. One drill, one sentence, then stop.

---

## Glossary

- **A-game / C-game.** The distribution of quality-of-play across sessions. Range between your best and worst play. Narrow the gap. (Originates with Tendler — full treatment in Doc 04.)
- **Analyzer.** A solver-backed tool (e.g. GTO Wizard's Analyzer) that evaluates played decisions against a solver baseline and reports per-decision EV loss [[2]](../sources/05-sources.md) [[3]](../sources/05-sources.md).
- **Blind spot.** A leak that you cannot diagnose alone because recognizing it requires seeing something your current mental model excludes. Coached review is the standard treatment. (§11.)
- **Chronic leak.** A leak category that appears in 3 or more weeks out of 4 during the monthly audit. Earns dedicated drill resources. (§9.)
- **Deliberate practice.** Practice structured with a well-defined task, informative feedback, opportunities for repetition and correction, and a motivated learner [[9]](../sources/05-sources.md). Review is the feedback step for poker. (Core thesis.)
- **Episodic leak.** A leak that appears in 1 week out of 4. Monitored but not drilled. Often a mental-state event. (§9.)
- **Execution leak.** A mechanical or interface error — misclick, wrong sizing default, sitting with a short buy-in — rather than a decision error. (§5 bucket 5.)
- **Filter, in-session uncertainty.** Marking hands during play based on your in-the-moment uncertainty about the decision. The primary selection signal for review. [[1]](../sources/05-sources.md) [[21]](../sources/05-sources.md) (§3.)
- **Followup.** A solver check or range-verification question logged during a per-session review but deferred to the weekly review's resolution block. (§7 template, §8.)
- **Habit, extracted.** A one-sentence rule written at the end of a per-hand review that captures what the player should do next time. Present tense. (§4 step 4, §7.)
- **Leak.** A pattern of EV-negative decisions across hands. The unit of diagnosis. Distinct from a single wrong decision. (Core thesis; §5.)
- **Leak-to-drill conversion.** The operational bridge from a diagnosed leak to a specific Doc 07 drill. Enforces the "review must close" requirement. (§6.)
- **Persistent leak.** A leak category that appears in 2 weeks out of 4. Drill continues; watch. (§9.)
- **Reciprocality.** Tommy Angelo's concept: any difference between you and your opponents that affects your bottom line [[7]](../sources/05-sources.md). Frames review as gap-widening, not absolute improvement. (§1.)
- **Review queue.** The filtered subset of a session's hands that are worth per-hand analysis. Typically 5–15% of hands. (§3.)
- **Retired leak.** A previously chronic or persistent leak that hasn't appeared for an audit period. Removed from drill rotation. (§9.)
- **Session theme.** The leak category, if any, that two or more hands from a session's review share. Drives the drill assignment. (§4 step 5, §7.)
- **Tag (color).** A tracker-assigned marker (yellow, orange, red, green) applied in-session or during review. Mechanism for filtering and queue construction [[21]](../sources/05-sources.md). (§10.)

---

## Resources and links

### Primary sources (full bibliographic details in [`sources/05-sources.md`](../sources/05-sources.md))

**Tools and vendor-authored methodology (Tier 1)**

- [GTO Wizard — How To Get the Most out of Your Hand Reviews](https://blog.gtowizard.com/how-to-get-the-most-out-of-your-hand-reviews/) [[1]](../sources/05-sources.md)
- [GTO Wizard — Redesigned Analyzer (2026)](https://blog.gtowizard.com/redesigned_analyzer_and_upgraded_gto_reports/) [[2]](../sources/05-sources.md)
- [GTO Wizard — Analyze Mode guide](https://help.gtowizard.com/analyze-mode-guide/) [[3]](../sources/05-sources.md)
- [Holdem Resources Calculator — free tools](https://www.holdemresources.net/free-tools) [[6]](../sources/05-sources.md)

**Canonical books and papers (Tier 2)**

- [Tommy Angelo — *Elements of Poker*](https://www.tommyangelo.com/elements-of-poker/) [[7]](../sources/05-sources.md)
- [Peter Clarke — *The Grinder's Manual*](https://smartpokerstudy.com/interview-peter-clarke-carroters-author-grinders-manual-100-hands-174/) [[8]](../sources/05-sources.md)
- [Ericsson, Krampe, Tesch-Römer — *The Role of Deliberate Practice in the Acquisition of Expert Performance* (1993)](https://www.ida.liu.se/~nilda08/Anders_Ericsson/Ericsson_delib_pract.pdf) [[9]](../sources/05-sources.md)

**Training sites with public review content (Tier 3)**

- [PokerCoaching (Jonathan Little) — How to Effectively Review a Hand History](https://pokercoaching.com/blog/how-to-effectively-review-a-hand-history/) [[11]](../sources/05-sources.md)
- [PokerCoaching — *A Little Coffee* hand-history series (exemplar)](https://jonathanlittlepoker.com/) [[12]](../sources/05-sources.md)
- [Red Chip Poker — 6-Max Hand History Analysis](https://redchippoker.com/6-max-hand-history-analysis/) [[14]](../sources/05-sources.md)
- [Run It Once — Phil Galfond's *Foundations* and *Simplifying Solvers*](https://www.runitonce.com/courses/foundations/) [[15]](../sources/05-sources.md) [[16]](../sources/05-sources.md)

**Tracker and HUD documentation**

- [PokerTracker — Marking Hands for Review](https://www.pokertracker.com/guides/pt3/tutorials/marking-hands-for-review) [[21]](../sources/05-sources.md)
- [Hand2Note — feature comparison](https://hand2note.com/Help/hand2note-vs-other-tools) [[20]](../sources/05-sources.md)

### Forward cross-references

- **Doc 1 — MIT 15.S50 Foundations** (foundational throughout; specifically the *Hand analysis workflow* section and L1/L2/L4/L6/L7 concepts this doc's categorization extends).
- **Doc 02 — Modern Preflop Ranges** (leak category: preflop subcategories).
- **Doc 03 — Postflop Solver Concepts** (leak category: postflop subcategories — flop c-bet sizing, turn, river, equity realization).
- **Doc 04 — Mental Game & Tilt** (leak category: mental subcategories — all mental-leak fixes live there, not here).
- **Doc 06 — ICM Deep-Dive** (leak category: ICM subcategories). *Note: numbering may shift at Closing Tasks' cross-ref audit.*
- **Doc 07 — Drill Library** (every leak subcategory in §5 maps to a drill in Doc 07 per §6's table).
- **Doc 08 — Modern Training Resources** (tracker and tool comparisons; HUD configuration; coach-selection resources for §11).

### External pointers outside the knowledge base

- [Deliberate Practice critique — Macnamara & Hambrick, 2020](https://pmc.ncbi.nlm.nih.gov/articles/PMC7461852/) [[23]](../sources/05-sources.md) (caveat on §1's core-thesis claim).
- [Thinking Poker (Andrew Brokos & Nate Meyvis) — review of *Elements of Poker*](https://www.thinkingpoker.net/poker-book-reviews/elements-of-poker/) [[22]](../sources/05-sources.md).

---

## Where this fits in the knowledge base

This doc is the **practice infrastructure** for the theoretical content in Docs 01–04 and Doc 06. Reading Doc 1 gives you the hand-analysis framework; reading Doc 02 gives you modern preflop ranges; reading Doc 03 gives you postflop solver concepts; reading Doc 04 gives you the mental-game framework; reading Doc 06 gives you ICM. *Using any of them in practice* requires running the workflow in this doc across your actual played sessions. Theory without review is decorative.

Pair this doc with Doc 07 — Drill Library. §6's leak-to-drill conversion table is the operational link: review diagnoses the leak, drills close it, re-review verifies the close. The loop is what turns a static curriculum into a practice.

Downstream, the monthly audit in §9 is the input to Doc 08 — Modern Training Resources. When a chronic leak hasn't responded to 8+ weeks of drilling, the monthly audit's "consider coach involvement" decision (§11) routes through Doc 08's coach-selection content.

Upstream, Doc 1's 7-step hand-analysis workflow is the spine of §4. This doc's contribution is the session-level, week-level, and month-level wrappers around it. The per-hand workflow is not re-treated here — read Doc 1 for it — but every session review invokes it.

If the curriculum had to collapse to two documents, they would be Doc 1 and this one: Doc 1 for the framework, this doc for the practice that turns the framework into improvement.

---

*End of Doc 05 — Hand History Review Template.*
