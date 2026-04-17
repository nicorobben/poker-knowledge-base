# Modern Preflop Ranges

> **Doc 2 of the Poker Training Knowledge Base** · Covers solver-derived opening / 3-bet / 4-bet / push-fold / BB-defense ranges for cash (100bb) and MTT (50/30/20/≤15bb) formats, with an explicit comparison to Will Ma's 2016 ranges from Doc 1. · License: CC BY-NC-SA 4.0 (matches Doc 1) · Primary sources in [`sources/02-sources.md`](../sources/02-sources.md).

---

## Coaching agent guide (read this first if you're Claude)

**When this doc is your best source.** A student asks any of: "what should I open from X?", "is this hand a 3-bet or a call?", "at Y bb, should I shove or raise-fold?", "how wide should I defend the BB?", "why do modern charts have me opening so many hands?", or "Will's book says UTG ~6% but everyone online opens way more — who's right?" Default to this doc. For range-vs-range postflop play, c-betting, or blockers on the flop → hand off to Doc 03. For ICM-adjusted ranges at final tables, satellite bubbles, or risk premium → hand off to Doc 04. For structured range drills → Doc 07.

**Default workflow when a student brings a preflop decision.**

1. Start with Doc 1's 7-step hand analysis workflow as the spine — position, effective stack, cards, action so far, ranges, then decision. Doc 1 is the foundation; this doc only specializes the "ranges" step.
2. Name the format first: cash 100bb? MTT 50/30/20bb? Sub-15bb push-fold? The ranges diverge sharply across these, and a student asking about "opening AJo" without a format is asking an underspecified question. Ask.
3. Give the baseline from the solver-aligned published chart (GTO Wizard public ranges, Upswing Preflop Prodigy, or Jonathan Little's free charts), not from memory. Cite the chart. Standing Rule #8: do **not** reproduce paywalled grids — describe in prose, point to the free public source.
4. Name the deviation axis. Modern baselines assume a specific rake and a solver-prepared opponent. If the student is in a 5%+10¢-capped raked live game or facing a recreational pool, the baseline is the *starting point*, not the recommendation. Point to Doc 08 for population adjustments.
5. Stamp any solver or sizing claim with `as of [Month Year]` per Standing Rule #7.
6. Always frame Doc 1 disagreements honestly per Standing Rule #6 — Will Ma's 2016 ranges were correct for his assumptions (3bb opens, Stars rake, that era's pool). They are not wrong. They are an earlier equilibrium.

**Tone and limits.**

- Concrete first, principle second — "BTN opens roughly 50% of hands at 100bb" before "the button's range is the widest because no one has position on you."
- Honest uncertainty. If the student asks whether to open 74s UTG at 50bb, the real answer is "mostly no, but it's a thin mix in some charts and a pure fold in others — the EV swing here is tiny." Say that. Do not manufacture a false crispness.
- Never reproduce a paywalled solver sim or a paid-tool chart verbatim. Describe the shape, cite the source, link the free equivalent.
- Never advise a student to play a range that's outside their bankroll / game security assumptions. If they're playing a $0.05/$0.10 game with rake that eats the BTN's EV, the solver baseline is directionally right but quantitatively meaningless. Redirect to Doc 08 for practical adjustments.

---

## How to use this document as a human reader

This doc specializes one slice of Doc 1's framework: the ranges step in preflop decisions. It assumes you've already read and internalized three things from Doc 1: (a) **thinking in ranges, not hands** (L2 of the levels-of-reasoning model), (b) the **position → effective stack → cards** hierarchy that governs every preflop spot, and (c) **decisions-not-results** as a cultural frame for evaluating whether a range choice was correct. If those don't feel native yet, read the *Mental Framework* section of Doc 1 before this doc. You'll get more out of this if you do.

Each of the ten numbered sections follows the same three-part rhythm: **Key takeaways** (four to six bullets you could teach someone else), then **Detailed notes** (the reasoning, the deltas from Doc 1, the caveats that would otherwise leave you with a chart you don't understand), then **Examples** (one to three concrete hands). Read the takeaways first. If they answer your question, you're done. If you want to know *why*, read the detailed notes. The examples are for calibration — "does my instinct about this spot match what the solver says?"

When this doc has to talk about a range, it will describe the shape in prose and point you to the published chart rather than reproducing a 13×13 grid. That is deliberate: grids lose too much signal in plain text, and the authoritative grids are in GTO Wizard's viewer, Upswing's app, and Jonathan Little's PDFs — all of which render better than any ASCII I could paste here. When the doc says "opens around 16%," you should mentally translate that to "roughly pairs 55+ and 22, suited broadways down to KTs, some suited connectors, AJ+ / KQ offsuit" — that's the shape of a 16% range. Over time you'll see the shape from the percentage.

If you're in a hurry and just want what to do, jump to the **Quick-reference card** near the bottom. It's distilled for fast lookup.

---

## Core thesis: what changed between 2016 and 2026

Three ideas thread through the rest of this doc. They are the reason the ranges you'll see here look different from Will's 2016 charts, and if you hold them in your head the numbers stop feeling arbitrary.

**First: open sizes shrank, and that pulled ranges wider.** In Will's 2016 class the canonical open was 3bb. In the 2026 online environment, the solver-preferred online cash open is closer to 2.0–2.3bb, and the MTT open tends to 2.0–2.25bb chip-stack games and 2.2–2.5bb once antes are in [[6]](../sources/02-sources.md). Smaller opens risk less to win the same pot, which shifts the breakeven fold frequency downward and makes the marginal-hand open (T9s UTG, KJo from the cutoff) profitable where it wasn't at 3bb. Smaller sizes → wider ranges; the two move together.

**Second: the solver-aligned baseline is now directly consumer-accessible, so the baseline itself moved.** In 2016 the "right" range was a reasoned construction from FTOP, combinatorics, and educated guesses at what opponents would do. In 2026, GTO Wizard's public spot viewer, Upswing Poker's Preflop Prodigy app, Jonathan Little's free downloadable charts, and Holdem Resources Calculator's free push-fold generator all give you solver output at zero or near-zero cost [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) [[18]](../sources/02-sources.md) [[8]](../sources/02-sources.md). What changed isn't that poker suddenly has a "right answer" — it's that the right answer got distributed. Good players now have the same baseline sheet.

**Third: the modern frontier is no longer "what is the range?" but "what are the *preconditions* under which this range is the range?"** Rake eats the bottom of every range, and the magnitude is not small — GTO Wizard's raked-solution analysis finds positions facing an opening raise VPIP 25–35% fewer hands in raked games than in unraked ones [[5]](../sources/02-sources.md). Antes widen opening ranges around 4–6% [[4]](../sources/02-sources.md). ICM at a final table changes the entire shape (handled in Doc 04). So when you see a chart that says "BTN opens 50% at 100bb," the claim is "50% at the rake structure, sizing convention, and ICM conditions this solver assumed." Wielding those ranges without that caveat is the most common modern mistake.

Where this departs from Doc 1: Doc 1 taught ranges as a reasoned construction — you build a 6%-ish UTG opening range by combining position, card strength, and the equity you need against callers. That reasoning is still right. What this doc does is substitute the solver output in for the final numbers while keeping Will's reasoning as the scaffold for *understanding* them. Doc 1 gives you the mental model. This doc gives you the calibrated starting points to plug into it.

---

## 1. The opening framework — why ranges are looser than 2016, what changed

**Key takeaways**

- Modern open sizes are 2.0–2.5bb, not 3bb. Every modern range baseline assumes this smaller sizing [[6]](../sources/02-sources.md).
- Modern ranges are wider than Will's 2016 charts, especially from early position. Smaller sizing is the mechanical driver; solver-pure ranges without exploitative tightening is the philosophical one [[17]](../sources/02-sources.md).
- The solver-aligned baseline is now publicly available — you no longer need to reverse-engineer it from principles, but you should still understand the principles [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) [[18]](../sources/02-sources.md).
- The baseline assumes: specific rake structure, specific sizing convention, specific stack depth, no ICM. All four shift the range. Rake alone can shrink a facing-an-open VPIP by 25–35% [[5]](../sources/02-sources.md).
- Exploitative adjustment is a layer *on top of* the baseline, not a replacement for it. Doc 08 handles the exploit layer.

### Detailed notes

The mechanical reason for wider modern opens is straightforward. When you open 3bb into blinds of 1.5bb, you risk 3bb to win 1.5bb — breakeven fold frequency is 3 / (3 + 1.5) = 66.7%. When you open 2.25bb, you risk 2.25 to win 1.5, so breakeven is 2.25 / (2.25 + 1.5) = 60%. That 6.7-point drop in required fold frequency is enormous at the margins. Hands that were unprofitable opens at 3bb because they couldn't generate enough folds pre *and* couldn't realize enough equity post (think Q9s from UTG, 55 from early-middle positions at 9-max) become marginal-to-profitable at 2.25bb. The solver captures this, and so the range widens.

The second driver is how "right" means "solver-GTO" rather than "profitable given this specific opponent pool." Will's 2016 ranges were a product of both GTO reasoning *and* assumptions about what Stars players were doing in 2016 — if everyone 3-bet light from the blinds, his opening range had to tighten to compensate. The modern published ranges assume the opponent also plays solver-approximate strategies, which means fewer exploitative punishments, which means the opener can get away with more marginal hands. GTO Wizard's "Preflop Range Morphology" and Upswing's advanced-solver-ranges methodology page both make this framing explicit [[2]](../sources/02-sources.md) [[17]](../sources/02-sources.md).

The third driver — and the one most often ignored by students staring at a chart — is that solver output is **conditional**. GTO Wizard's raked-solutions analysis, publicly quantified on their blog, finds that in cash games positions facing an open raise VPIP 25–35% fewer hands in raked games compared to unraked simulations [[5]](../sources/02-sources.md). If your live 1/3 game takes a 10%/$6-cap rake from a $80 pot, you are not playing the same game as a 100bb online 500NL solver baseline. The chart is directionally right; the percentages are optimistic for any hand close to the margin. Standing Rule #7 applies — if the recommendation you're about to give a student rides on a solver baseline, stamp the assumptions and name the uncertainty.

The fourth driver is sizing convention drift across formats. Online cash tends to 2.0–2.3bb. Live cash, where stacks are shallower-in-bb and players are looser, tends to 2.5–3bb. MTTs without antes tend to 2.0–2.25bb. MTTs with antes tend to 2.2–2.5bb — antes raise the dead money so the minimum profitable open size bumps up. Each size generates a slightly different solver range; a chart from a 2.0bb sim is not a chart from a 2.5bb sim. When you cite a chart, cite its sizing assumption [[6]](../sources/02-sources.md).

**Named principle — the "conditional baseline" rule:** a solver opening range is always conditional on its *(rake, sizing, stack depth, ICM)* tuple. If any of those four differ in your actual game, the published chart is a starting point for your intuition, not a literal prescription. Expect the bottom 10–20% of the chart's range to be the first casualty of any adverse condition.

### Examples

**Example 1.1 — Why 55 becomes an EP open at 2.25bb but not at 3bb.** At 3bb, opening 55 from UTG in a 6-max game requires you to (a) win the blinds a large fraction of the time and (b) realize enough equity postflop when called to make the open profitable. With 55's 20% equity against a typical calling range (which contains a lot of broadways that outflop you) and 3bb risked, the margin is thin-to-negative. Drop the size to 2.25bb and the EV swings positive: smaller bet pre means more folds and a cheaper postflop dead-money contribution when called. Hence 55 is a standard modern UTG 6-max open [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) (as of April 2026).

**Example 1.2 — Why the chart you're reading matters.** Two charts both claim to show "BTN open at 100bb 6-max." Chart A is from a 2.0bb / unraked / no-ante simulation. Chart B is from a 2.5bb / 5%-capped / no-ante simulation. Chart A has a ~52% BTN opening range; Chart B has a ~44% BTN opening range. The difference (~8 percentage points) is entirely the sizing-plus-rake tuple. The chart you hand a student has to match the game the student is playing, or you're teaching them a range that's quantitatively wrong by a quarter of its hands [[5]](../sources/02-sources.md) [[6]](../sources/02-sources.md).

**Example 1.3 — Where Will Ma's 2016 ~6% UTG range is still right.** A 9-handed live $1/$3 game, 3bb opens standard, heavy rake, pool that 3-bets aggressively. In that game, the modern solver chart's ~13% UTG range would be a disaster — your bottom hands get punished by loose 3-bets pre and heavy rake post. Will's ~6% (a conservative construction of JJ+, AQs+, AKo) is a more defensible practical range. This is the practical value of Standing Rule #6: don't pretend the disagreement doesn't exist; name which context each view is right for.

---

## 2. Cash 100bb open ranges by position

**Key takeaways**

- 6-max 100bb opens at 2.0–2.3bb: roughly UTG 16–18%, HJ 22–24%, CO 28–30%, BTN 48–52%, SB 40–44% (as of April 2026) [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) [[20]](../sources/02-sources.md).
- 9-max 100bb opens at 2.5bb (live-convention): roughly UTG 12–14%, UTG+1 13–15%, MP 14–16%, MP+1 16–18%, HJ 20–22%, CO 25–28%, BTN 43–47%, SB 38–42% (as of April 2026) [[13]](../sources/02-sources.md) [[20]](../sources/02-sources.md).
- Tighten the bottom of each range by 5–15% of its width in heavily raked live games [[5]](../sources/02-sources.md).
- Do not publish or rely on 13×13 ASCII heat-map grids in this doc. Use the published chart viewers. The BUILD_PLAN §2.1 watch-out is explicit on this.
- The BTN is where the largest EV per range-width comes from — if you must memorize one chart, memorize the BTN.

### Detailed notes

The range shapes at 100bb cash are the most thoroughly studied spots in all of poker. GTO Wizard's public cash ranges, Upswing's Preflop Prodigy app's online-cash 6-max module, and BBZ Poker's public GTO charts all agree to within a few percentage points on the shape and percentage per position, with variation driven by the tuple in §1 [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) [[20]](../sources/02-sources.md). I'll describe each position's shape in prose, link the chart for memorization, and note the deviations from Will's 2016 framing.

**6-max UTG (roughly 16–18% at 2.25bb).** All pocket pairs 22+. All suited broadways down to KTs, QTs, JTs, T9s. Suited aces A2s–A5s (blocker/playability), A8s–AKs (strength). Suited kings KJs+ (a little KTs). Off-suit: AQo+, KQo sometimes included as a mix. The expansion from Will's 2016 ~6% range is concentrated in two places: small pairs (22–77 were often folded in Will's range) and suited wheel-aces and low suited connectors (Will's range skewed broadway-heavy). Both additions are mechanically driven by the 2.25bb sizing; at 3bb they were cusp-or-negative, at 2.25bb they're clean opens [[1]](../sources/02-sources.md) [[6]](../sources/02-sources.md).

**6-max HJ (~22%).** UTG range plus: KTs, Q9s (mixed), J9s (mixed), T8s (mixed), some more KQo frequency, some AJo. The "mixed" in this context means the solver opens some combos and folds others of the same hand class — at the margin, solver frequency is fractional, and human simplification rounds to "open always" or "fold always." Upswing's Preflop Prodigy labels these as yellow / partial-colored cells in its grid [[13]](../sources/02-sources.md).

**6-max CO (~28%).** HJ range plus: more suited connectors (76s, 65s as mixes or pure opens), broader off-suit broadway (AJo pure, KJo mixed, QJo mixed), more suited aces. The CO is the position where the "open wide and steal / put pressure on the blinds" principle from Doc 1 starts to dominate over the "open for value" principle.

**6-max BTN (~50%).** CO range dramatically widened: all pocket pairs, all suited hands from about K2s, Q5s, J7s, T7s, 97s, 87s, 76s, 65s, 54s downward-or-similar; all broadway off-suit; many off-suit connectors and one-gappers like KTo, QTo, JTo, T9o, 98o. The BTN range is roughly half the 169-hand matrix. The single most high-leverage chart in all of cash preflop — and the one where Doc 1's ~55% BTN baseline and modern solver ~50% BTN baseline agree within a few points [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md).

**6-max SB (~42%) — with a polarized structure.** The SB cannot flat-call profitably at 100bb cash because the BB then gets a free look from behind with positional disadvantage only against one opponent (SB), and the SB's realization factor OOP is poor. The solver-preferred SB strategy is to raise a polarized range — the top of a 40–45% opening range — and fold the rest, with a small limp frequency in some solves. This is a meaningful structural deviation from Will's 2016 SB framing (which treated SB as "raise moderately, call rarely") and pushes SB strategy closer to the 3-bet-heavy shape described in §8 [[1]](../sources/02-sources.md) [[7]](../sources/02-sources.md).

**9-max opens** are the same shape ideas applied to more positions, with UTG / UTG+1 / MP roles all squeezed tighter because there are more players still to act. The canonical 9-max live-cash open is 2.5bb (rake-and-tendency compensation), and the opening percentages from UTG through MP+1 run roughly 12–18% in a step function. Jonathan Little's free small-stakes cash charts and Upswing's live-cash charts cover this in detail [[18]](../sources/02-sources.md) [[13]](../sources/02-sources.md).

**Live-cash caveats.** Live cash rake is typically higher than online cash rake (5% up to a $6–$10 cap in most rooms), which compresses the bottom of every range. Live-cash pools also 3-bet less and call more; the solver baseline is directionally right but exploitative tightening of the thinnest opens (low suited aces, small off-suit broadways) is usually correct. Doc 08 handles the practical exploits [[5]](../sources/02-sources.md) [[22]](../sources/02-sources.md).

**Chart-format note.** Per BUILD_PLAN §2.1 watch-outs, this doc does not include ASCII 13×13 grids. The shapes above are conceptual descriptions; for the actual combo-by-combo ranges, point a student to (a) GTO Wizard's public spot viewer (no login required for many spots), (b) Upswing's Preflop Prodigy app, or (c) Jonathan Little's free 100bb chart PDF [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md) [[18]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1 gave an UTG range of around 6% at 9-max (roughly 99+, AQ+, sometimes sprinkling in KQs). The modern 9-max baseline at 2.5bb is roughly 12–14% — about double. The reasons are exactly the three in the core thesis: smaller open size (3bb → 2.5bb), solver baseline replacing exploitative-against-pool reasoning, and the assumption that other players also play near-solver strategies. Will's 6% is still correct for the specific environment he was targeting (3bb opens, exploitative 3-bet-heavy Stars pool, 2016 meta). It is not the right number for a 9-max live $5/$10 in 2026 at 2.5bb opens — where 12–14% is the solver-indicated baseline, further tightened 15–25% for live rake and pool tendencies, yielding a practical UTG open around 10–12%.

### Examples

**Example 2.1 — AJo UTG 6-max cash.** Will's 2016 chart: cusp, lean open. Modern solver at 2.25bb: pure open. Why: at smaller size, the "get paid by the BB's defending range" line and the "fold out a lot of marginal off-suit broadways behind" line both profit more per attempt. Net: AJo is a clean UTG 6-max open at modern sizing [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md).

**Example 2.2 — 55 from UTG 9-max at 2.5bb, live $2/$5 with $6-capped rake.** Solver baseline: marginal open in 9-max UTG (it's in some 12-14% charts, out of others). Live-rake adjustment: the rake alone shifts ~55's realized EV negative for the vanilla-open line. Recommendation: fold at the baseline, open as an exploit against a passive pool that calls wide and doesn't 3-bet. This is exactly the "chart is directionally right, quantitatively adjusted by context" pattern from §1 [[5]](../sources/02-sources.md) [[22]](../sources/02-sources.md).

**Example 2.3 — K9s from HJ 6-max cash.** Solver: mixed open (some combos in, some out). Human-simplification: include it as a pure open at the lower end of the HJ range. Will's 2016 framing would have folded K9s from HJ. Both framings "work" — the solver's mixed frequency suggests the EV is near zero either way. This is the kind of spot where the student should be told: pick a line and stick to it; the execution discipline matters more than the marginal EV [[13]](../sources/02-sources.md).

---

## 3. MTT open ranges by stack depth

**Key takeaways**

- At 50bb, opens are similar shape to 100bb with ~1–3 point tightening in early position and slight widening on the BTN (as of April 2026) [[3]](../sources/02-sources.md) [[18]](../sources/02-sources.md).
- At 30bb, opens are noticeably tighter in early position (small pairs and suited gappers get dropped) and the SB starts using more of a 3-bet / fold split instead of an open / limp / fold [[3]](../sources/02-sources.md).
- At 20bb, opens tighten further and the SB transitions to a shove / raise-first-in / fold mix; BTN opens remain wide [[3]](../sources/02-sources.md) [[18]](../sources/02-sources.md).
- MTT open sizes are typically 2.0–2.25bb chipless, 2.2–2.5bb once antes are in [[6]](../sources/02-sources.md).
- Do not conflate MTT ranges with cash ranges. The "same chart for both formats" mistake is one of the most common student leaks.

### Detailed notes

MTT preflop strategy is driven by three moving quantities that cash-100bb strategy barely touches: stack depth in big blinds, presence of antes, and ICM pressure. This section covers the first two. ICM is Doc 04's territory, not this doc's.

**The stack-depth gradient.** At 100bb, positional equity realization in 3-bet pots is high enough that most suited connectors, small pairs, and thin broadways play profitably. At 50bb, those hands lose some of their implied-odds upside (you have less to win if you flop a set with 22 because the effective stack is smaller). At 30bb, the implied-odds hands that depend on stacking opponents on deep runouts are sharply devalued. At 20bb, many of them drop out of the opening range entirely, and the game transitions toward a raise / 3-bet / shove / fold decision tree in which set-mining is a minor part of the value [[3]](../sources/02-sources.md).

**The qualitative picture of stack-depth shifts to opening ranges.**

- **50bb**: UTG 6-max opens ~14–16% (tightened from 100bb's 16–18% by dropping the lowest suited pair and thinnest suited aces). BTN ~48–50% (similar). SB ~38–42% (similar). The overall shape is very close to 100bb.
- **30bb**: UTG ~10–12%. HJ ~14–16%. CO ~22–24%. BTN ~42–46%. SB ~34–38%. The biggest drop is in the thin-implied-odds hands: 22, 33, small suited connectors like 54s, 65s, and thin suited gappers.
- **20bb**: UTG ~8–10%. HJ ~12–14%. CO ~18–22%. BTN ~36–40%. SB transitions — the mixed "raise-first-in / shove / fold" structure starts taking over. A 20bb SB open-raise is still standard with the top of its range, but the shove option crowds in for pairs 55–TT and AJ+ strength-grade hands [[3]](../sources/02-sources.md) [[18]](../sources/02-sources.md).

**Sizing convention.** MTT open sizes without antes: 2.0–2.25bb. MTT open sizes with antes: 2.2–2.5bb. The antes add dead money, which raises the minimum-profitable open size (and also widens the range by roughly 4–6 percentage points — see §9) [[4]](../sources/02-sources.md) [[6]](../sources/02-sources.md).

**Forward reference.** ICM at final tables materially changes these ranges — the 20bb UTG range at a pay-jump bubble is 4–6 percentage points tighter than the chip-EV baseline, and the bottom of the BTN range can drop a similar amount or widen, depending on stack distribution. That's Doc 04's job. This doc gives the chipEV baseline; Doc 04 layers ICM on top.

### Where this departs from Doc 1

Doc 1 has strong coverage of the 15bb-and-below push-fold framework (L3) and the 100bb preflop framework (L4), but the intermediate MTT depths — 50/30/20bb — weren't given a dedicated treatment. Will's pedagogical decision there was reasonable: those depths blend the two end-points and the student benefits more from understanding the boundary cases first. Modern MTT play spends a huge fraction of the tournament at these depths (a typical MTT grinder spends more hands at 20–50bb than at 100bb), so this doc treats them explicitly.

### Examples

**Example 3.1 — 22 from UTG at 50bb vs. 30bb vs. 20bb MTT (6-max).** At 50bb: mixed open, roughly 50% frequency. At 30bb: pure fold in most charts (the implied-odds premium for set-mining evaporates). At 20bb: pure fold. The pair itself didn't get worse; the effective stack behind it got shallower, so the value of flopping a set dropped [[3]](../sources/02-sources.md).

**Example 3.2 — 65s from HJ at 30bb MTT.** Solver-mixed (some combos fold, others open). Human simplification: fold. The small suited connector is a premier implied-odds hand, and at 30bb the implied odds aren't there. Upswing's and Little's 30bb charts align on this call [[13]](../sources/02-sources.md) [[18]](../sources/02-sources.md).

**Example 3.3 — AJo from CO at 20bb MTT with antes.** Pure open at 2.3bb. AJo at 20bb has strong absolute-equity value (fine 5-bet-or-fold decision if 3-bet) and the antes raise the profitable threshold for open raises. The "should I open-shove AJo here?" instinct from cash players is wrong at this depth: 20bb is not short enough for an open-shove, and open-raising captures most of the value [[4]](../sources/02-sources.md) [[3]](../sources/02-sources.md).

---

## 4. Push-fold (≤15bb) — the Nash framework

**Key takeaways**

- At ≤15bb effective, the raise / 3-bet-or-fold dynamic degenerates. Open-shoving becomes the dominant strategy for many hands from most positions [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md).
- Nash-equilibrium push-fold tables for heads-up and for tournament late positions are widely published and free. HRC (free tier), Upswing's public push-fold chart, and Will Ma's Doc 1 L3 coverage all cover the standard SB/BB and three-handed spots.
- At 15bb there is still meaningful raise-fold play for MP/HJ/CO (not pure push-fold). At 10bb and below, nearly every position shifts to push-or-fold or shove-or-raise-fold mixes. At 5bb, ranges are very wide on the shove side [[14]](../sources/02-sources.md).
- Nash tables are chipEV equilibria. ICM at a pay-jump will tighten them meaningfully — Doc 04.
- Standing Rule #8 applies: we do not reproduce paid push-fold grids verbatim. We describe, and point to HRC free tier and Upswing public chart [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md).

### Detailed notes

The push-fold framework is the closest thing poker has to a solved problem, and Doc 1's L3 section handles its *why* — the breakeven-equity arithmetic of "when is a shove +chipEV given the pot odds the caller needs?" This section doesn't replay that math; it specializes the conclusions into the modern Nash-table landscape and adds the practical "what to do at 15, 10, 7, 5 bb" calibration that Doc 1 sketched but didn't fully enumerate.

**The shove-from-position hierarchy.** The tighter the position, the tighter the Nash shove range, because more players act after you. From under-the-gun at a 6-max 20bb table, the Nash shove is roughly the top 8–10% of hands (pairs 88+, AQ+, AJs, KQs as a mix). From the button it's roughly the top 30–40% of hands (all pairs, all suited broadways, most suited connectors, many off-suit broadways). From the small blind it's even wider — 45–55% — because there's only the big blind behind. These percentages come from HRC's and Upswing's published Nash tables at the corresponding stack depth [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md).

**The 15bb boundary — raise-fold still lives.** At 15bb, positions MP through CO still use an open-raise to 2.0–2.2bb as their dominant non-premium action, with open-shove reserved for a narrower premium-or-suited-ace stratum. The key difference from 20–30bb is that the raise-fold continuance (facing a 3-bet, how often you 4-bet-or-fold) collapses to near-pure shove-or-fold. At 15bb you can still open, but if you face a 3-bet you're essentially jamming with QQ+/AK and folding the rest [[3]](../sources/02-sources.md) [[14]](../sources/02-sources.md).

**The 10bb threshold — shove-first-in dominates.** At 10bb effective from the SB facing a fold-through, nearly all non-trash hands are shoves: all pairs, all suited broadways, suited aces, many off-suit broadways, suited connectors down to 65s-ish. From the BTN at 10bb, the solver still mixes some raise-first-in for premium hands (opening to 2.1bb with QQ+/AK looks "weak" and invites 3-bet jams you can call), but shove is the dominant action for the wide-middle of the range. The HU 10bb Nash tables are the canonical reference here [[8]](../sources/02-sources.md).

**The 7bb threshold — nearly pure push-fold.** At 7bb, even BTN opens collapse. The shove ranges widen: SB Nash shove at 7bb is roughly 60%+ of hands (all pairs, all suited hands, most off-suit broadways, many off-suit connectors). BB's Nash calling range vs. a SB 7bb shove is roughly 30–38% — a number worth memorizing. Source: Chen & Ankenman's Nash formalism (Doc 1 reference) plus HRC's and Upswing's modern tables [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md).

**The 5bb threshold — ranges are very wide.** At 5bb, SB shoves most hands and BB calls most hands. The HU Nash calling range at 5bb is about 55–60%. Blind-vs-blind at this depth is roughly a coin flip on range-vs-range equity; positional leverage has collapsed and it's a math-driven all-in contest.

**Standing Rule #8 — no paid grids.** We describe these ranges in prose and point a student to free sources: HRC's free push-fold calculator, Upswing's public tournament push-fold page (which publishes ten hand-grid tables from 2bb through 20bb), and Doc 1's L3 coverage [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md). A student who wants combo-by-combo detail should use those.

### Where this departs from Doc 1

It doesn't. Doc 1's L3 coverage is still correct and canonical for the push-fold framework. This section is an extension, not a disagreement — it adds the stack-depth gradient (15 → 10 → 7 → 5bb) that Doc 1 sketched at a single-depth level. The SB shove at 66.8% and BB call at 38.5% from Will's 15bb Nash example remain pedagogically central.

### Examples

**Example 4.1 — 15bb UTG at a 9-handed MTT table.** Open-raise with QQ+, AK, AQs: standard. Open-shove: only with the premium stratum — QQ+/AKs in most modern charts, AK sometimes mixed as a shove. Fold everything else. Critically, at 15bb UTG you are *not* open-shoving JJ or AQo; you're open-raising and playing postflop or responding to a 3-bet [[3]](../sources/02-sources.md).

**Example 4.2 — 10bb SB, folded to you.** Shove range is roughly 55–65% of hands: all pairs, all suited hands down to around 64s or so, all suited aces, most broadway off-suit (KJo, QJo, JTo mixed), many middle off-suit connectors. The BB calls shove with the top 30–38%. This is the canonical spot where a student should internalize "Nash range, Nash call" [[8]](../sources/02-sources.md).

**Example 4.3 — 7bb HU at a SnG.** SB shoves nearly any two cards. BB calls with the top half-or-more of hands. Edges are tiny; decisions are mechanical. The correct meta-move is to have the Nash tables memorized for the exact depth you're at and execute without deliberation [[8]](../sources/02-sources.md) [[14]](../sources/02-sources.md).

---

## 5. 3-bet construction — polarized vs. linear/merged

**Key takeaways**

- Linear (also called "merged"): contiguous top of range, e.g. TT+/AQ+/KQs. Used when your opponent will not fold to pressure on the top, and when you want postflop playability [[2]](../sources/02-sources.md) [[10]](../sources/02-sources.md).
- Polarized: strong value hands plus designed bluffs (low suited aces for blocker and playability), almost no medium hands. Used when fold equity is high and you want sharp post-flop pressure [[2]](../sources/02-sources.md) [[11]](../sources/02-sources.md).
- Condensed / capped: mostly medium-strong hands with fewer premiums or bluffs. Rare in aggressive modern play; typically a by-product of a call-heavy counter-range [[2]](../sources/02-sources.md).
- Shape choice is driven by position, relative stack depth, opener's position, and who has the capped / uncapped range advantage [[2]](../sources/02-sources.md) [[10]](../sources/02-sources.md).
- 3-bet sizing conventions: in position ~2.5–3.5x the open; out of position ~3.5–4.5x; at shallow stacks (≤30bb) larger as fraction but smaller in absolute bb because open sizing also shrinks [[6]](../sources/02-sources.md) [[3]](../sources/02-sources.md).

### Detailed notes

3-betting is where solver theory diverges most visibly from 2016-era teaching. Will Ma's framing in Doc 1 L4 built up 3-bet ranges as polarized — "strong value, a few bluffs, nothing in the middle" — because that was the solver-aligned prescription given the assumptions of that era's opening ranges and 3-bet sizes. Modern solver work shows that the *shape* of the 3-bet range depends on the confluence of position, opener position, stack depth, and the opener's calling/4-betting patterns, and the linear/merged shape is often preferred in position and against specific opens [[2]](../sources/02-sources.md).

**The four shapes, concretely.**

- **Linear / merged:** QQ+, JJ, TT, AK, AQ, KQs, AJs as a continuous block from the top of your range. Playable postflop in position, robust to 4-bet bluffs (most of the range has strong showdown value), de-prioritizes fold equity.
- **Polarized:** QQ+, AK as the value stratum; A5s–A3s, K5s–K4s, sometimes 75s / 64s as the bluff stratum; very little JJ / TT / AQ — those are calls. Maximizes fold equity and postflop pressure.
- **Condensed:** JJ–99, AQ, AJs, KQs — strong-but-not-premium. A defensive 3-bet range built from hands that dominate the opener's calling range but give up equity to 4-bets.
- **Capped:** a range that has had its top removed. Usually a consequence of other actions (calling with premiums for deception, or 4-betting them), rarely a designed shape.

**Shape selection by spot.** This is where modern solver work has built a map that didn't exist in 2016:

- **IP (BTN or CO) vs. late open (CO or BTN):** linear/merged dominates. The opener's range is wide, you have position, you want hands that play well postflop, and you don't need huge fold equity because your EV when called is positive [[2]](../sources/02-sources.md).
- **OOP (SB or BB) vs. late open:** polarized dominates. OOP equity realization is poor, so you want either (a) value hands that win big pots or (b) bluffs that can either take it down pre or make sharp plays post. The medium-strength condensed shape does badly OOP [[2]](../sources/02-sources.md) [[7]](../sources/02-sources.md).
- **IP vs. early open (UTG):** condensed or linear depending on depth. The opener's range is tight and value-heavy; you need to either dominate (linear) or fold-to-the-top-and-bluff-below (polarized). Mixed in modern solves; stack-depth dependent [[2]](../sources/02-sources.md).
- **OOP vs. early open:** narrow polarized or mostly flat. Fold equity is modest (opener's range is strong) and realization is poor.

**Sizing.** In position 3-bet sizing is typically 2.5–3.5x the open: vs. a 2.25bb BTN open from the SB, the standard 3-bet is to about 8–10bb (~4x OOP) or 6–7bb (~3x IP). Out of position, sizing bumps up because OOP needs more fold equity to compensate for worse realization. At shallower stacks, the sizing in bb is smaller in absolute terms (because the open is smaller and the stack is smaller), but the multiple of the open sometimes nudges down — at 30bb a SB 3-bet from 2.0bb to 6bb is 3x, and the remaining stack-to-pot ratio makes 4x unnecessarily large [[6]](../sources/02-sources.md) [[3]](../sources/02-sources.md).

**Blocker-driven bluffs.** Suited aces (A2s–A5s) and sometimes suited kings (K2s–K4s) appear in modern 3-bet bluff ranges because of blocker effects: holding an ace reduces the opponent's combinations of AA, AK, AQ, and AJ — their strong continuing range — by a meaningful fraction. This blocker reasoning is central to modern polarized construction and was underweight in 2016 teaching [[11]](../sources/02-sources.md) [[10]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1 L4 taught 3-betting as primarily polarized. That was right for the assumptions in 2016, and still right in the OOP-vs-late-open spots where polarized shapes are the modern consensus. Where modern work has moved on is specifically in the IP-vs-late-open spots: there, linear/merged shapes are now preferred because (a) smaller open sizes shift the breakeven fold frequency, (b) in-position equity realization is high enough that the medium-strength block plays well postflop, and (c) polarized IP ranges leave too much EV on the table by 3-betting hands that would profitably call. Will's teaching isn't wrong; its domain has narrowed.

### Examples

**Example 5.1 — BTN opens 2.25bb, SB 3-bets.** SB 3-bet shape: polarized. Value: QQ+/AK (and some AQs). Bluffs: A2s–A5s, K4s–K5s, sometimes 64s / 75s. Size: to ~10bb (≈4.4x). Calls (non-3-bet range): AQ, KQs, JTs, some pairs 77–JJ [[1]](../sources/02-sources.md) [[2]](../sources/02-sources.md).

**Example 5.2 — UTG opens 2.25bb in 6-max, BTN 3-bets.** BTN 3-bet shape: linear/merged. Range: QQ+, JJ, TT (mixed), AK, AQ (mixed), KQs, AJs — about 3–4% of hands as a 3-bet. Size: to ~7bb (≈3.1x, IP). Calls (non-3-bet range): 77–99, AQo (mixed), most suited broadways. The reason it's linear here: UTG's range is tight and value-heavy, so a polarized bluff-heavy 3-bet gets exploited when UTG 4-bets strongly — your bluffs profile as blockers but still run into dominance often [[2]](../sources/02-sources.md).

**Example 5.3 — CO opens 2.25bb, BTN 3-bets.** BTN 3-bet shape: linear/merged but wider than vs. UTG (because CO's opening range is wider). Range: TT+, AQ+, KQs, AJs, and sometimes KJs / QJs / T9s as small frequency adds — about 6–8% of hands. Linear/merged IP is the modern preference here, vs. Will's 2016 lean toward polarized. This is the clearest case of where modern solver output and 2016 construction genuinely differ [[2]](../sources/02-sources.md).

---

## 6. 4-bet construction

**Key takeaways**

- 4-bet ranges are small (typically 2–4% of hands) and strongly bimodal: premium value plus a thin slice of suited-ace bluffs [[2]](../sources/02-sources.md) [[10]](../sources/02-sources.md).
- 4-bet sizing: 2.2–2.5x the 3-bet in position, 2.5–3.0x out of position. At 100bb, a 4-bet to 22–26bb from an 8–10bb 3-bet is standard [[6]](../sources/02-sources.md).
- 4-bet bluff selection is blocker-driven: A5s–A2s (blocks AA/AK combos) are the modern canonical 4-bet bluffs; suited kings (K5s) appear at some frequencies [[10]](../sources/02-sources.md) [[11]](../sources/02-sources.md).
- Facing a 5-bet shove: fold everything except QQ+ in most 100bb spots; at shallower stacks the calling range widens to JJ+ / AK [[3]](../sources/02-sources.md).
- A pure-call range (vs. being 3-bet) exists when deep and in position, containing hands too strong to fold but not quite 4-bet quality (QQ–TT, AK-sometimes-calls). Not all hands that could 4-bet should 4-bet [[10]](../sources/02-sources.md).

### Detailed notes

The 4-bet is the most heavily theorized preflop action because it determines how the 3-bet-er's bluffs get punished, and thus the economy of the whole pre-flop game. Modern construction is tight: value hands that want to get it in (KK+, sometimes QQ), plus a small number of blocker bluffs that are cheap enough to fold to a 5-bet.

**Value composition.** At 100bb, the standard 4-bet-for-value range is KK+/AK — with AA always, KK always, AK at a high frequency, and QQ at a lower frequency that depends on the 3-bet-er's range. If the opponent's 3-bet range is highly polarized (lots of bluffs), QQ 4-bets more; if it's linear (lots of JJ+ and AQ value), QQ mostly calls. AK is a pure mix, not a pure 4-bet — the alternative is to call or flat IP to keep bluffs in your calling range [[2]](../sources/02-sources.md) [[10]](../sources/02-sources.md).

**Bluff composition.** The modern canonical 4-bet bluffs are A2s–A5s. The ace blocks the opponent's AA and AK combinations, reducing the frequency of their "continue with strength" bandwidth. The suit gives postflop playability if the 4-bet gets called. Suited kings (K4s, K5s) appear at partial frequency in some solves; the reasoning is weaker (the king blocks KK and AK less comprehensively than the ace blocks AA/AK), so these are typically lower-frequency bluffs than the suited wheel aces [[11]](../sources/02-sources.md) [[10]](../sources/02-sources.md).

**Sizing.** IP 4-bet size is 2.2–2.5x the 3-bet. Vs. a SB 3-bet to 10bb from a BTN 2.25bb open, the BTN 4-bet is to ~22–24bb. OOP sizes are larger because you need fold equity; a BTN-opens, SB-3-bets, BTN-folds pattern, with the SB later needing to 4-bet from OOP against a BTN 3-bet, would have the SB sizing up to ~26–28bb. At shallower stacks (≤50bb) the sizing ratio compresses because the stack-to-pot ratio after 4-betting is small and a full 2.5x risks committing the stack unnecessarily [[6]](../sources/02-sources.md) [[3]](../sources/02-sources.md).

**The 5-bet decision.** Facing a 5-bet shove at 100bb after having 4-bet, the calling range is roughly the top of your 4-bet value range: QQ+ always, AK usually, KK+ always. The 4-bet bluffs (A5s, A4s) fold to the shove — the whole point of bluffing with them is that they're cheap to fold when 5-bet. At shallower stacks the calling range widens by necessity: at 40bb effective, there's simply not enough fold equity to 4-bet-fold AK, and it becomes a 4-bet-call [[10]](../sources/02-sources.md).

**The pure-call range when deep.** An often-missed piece of modern construction: at 100bb IP, facing a 3-bet from OOP, you should not 4-bet every strong hand. Flatting with QQ / JJ / AK / KQs in position keeps your calling range robust, realizes equity well, and protects against 5-bet shoves that would otherwise punish a 4-bet-fold. The "4-bet with all strong hands" instinct from 2016 is wrong at deep stacks; the "4-bet with some strong hands, call with some, fold weaker" mix is modern [[10]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1's treatment of 4-betting is implicit — it's folded into the L4 polarization teaching and the hand-analysis workflow, but not given a dedicated section. The modern construction above is an extension, not a contradiction. Will's polarization principle ("value + bluff, no middle") still holds at the 4-bet layer. What this doc adds is the specific composition (KK+/AK value + A5s/A4s bluff), the sizing conventions at modern open and 3-bet sizes, and the pure-call-range concept that matters most at deep stacks.

### Examples

**Example 6.1 — BTN opens 2.25bb, SB 3-bets to 10bb, BTN faces the 3-bet.** BTN 4-bet range: KK+ always, QQ mixed, AK mixed, A5s/A4s as bluffs. Calling range: JJ–TT, AQ, KQs, AJs. Folding range: everything else. Size: to 22–24bb. On a 5-bet shove from SB, BTN calls QQ+ and AK, folds the bluffs [[1]](../sources/02-sources.md) [[2]](../sources/02-sources.md).

**Example 6.2 — UTG opens 2.25bb, CO 3-bets, UTG 4-bets.** UTG is much less likely to 4-bet bluff here because its opening range is already tight (KK+/AK value base), so a polarized 4-bet shape has less room for bluffs without the range getting unbalanced. The UTG 4-bet is a near-pure value range; the call-vs-4-bet mix with JJ / AQ is higher than in the BTN-vs-SB spot [[10]](../sources/02-sources.md).

**Example 6.3 — 40bb MTT, CO opens 2.1bb, BTN 3-bets to 5.5bb, CO 4-bets.** Sizing: CO 4-bets to ~13bb (2.4x the 3-bet). Value: KK+, QQ (higher frequency than at 100bb because fold equity is lower), AK. Bluffs: tiny — the stack-to-pot ratio doesn't support a 4-bet-fold line well, so the bluff slice compresses. At this depth, "4-bet with almost-only value" is close to correct [[3]](../sources/02-sources.md).

---

## 7. Big-blind defense

**Key takeaways**

- BB defense frequency is a function of pot odds, rake, and the opener's range. Against a BTN 2.5x open in cash, Upswing's published solver-aligned continuance is approximately 51.7% (defend via call or 3-bet) [[15]](../sources/02-sources.md). Against tighter openers (CO, HJ, UTG), continuance tapers by several percentage points per position — the bands given below are extrapolated from the published BTN figure, not directly published.
- The BB's job is not to defend *maximally* — that's a 2016 framing — but to defend *correctly*: enough frequency that the opener's thin opens don't profit, and no more [[15]](../sources/02-sources.md).
- 3-bet frequency from the BB is typically 8–14% of facing-open situations, with the exact split between 3-bet and call depending on opener's position [[15]](../sources/02-sources.md) [[17]](../sources/02-sources.md).
- Stack depth matters: at 30bb BB defense tightens and 3-bet / shove mixes appear for pair hands; at 100bb the call / 3-bet / fold decision is the full tree [[3]](../sources/02-sources.md).
- Against live recreational pools, BB defense can profitably tighten 5–10 percentage points; the solver baseline assumes a solver-prepared opener [[22]](../sources/02-sources.md).

### Detailed notes

Big-blind defense is the most misunderstood frequency in modern poker. The student-error mode is "I need to defend 40% because I'm getting 3:1 odds" — the first half is roughly right; the second half treats pot odds as the only input when rake and postflop realization also matter. The modern framing is: the BB's break-even defense frequency depends on (a) the opener's sizing, (b) rake effect on postflop pots, (c) realization penalty from playing OOP, and (d) the opener's range strength [[15]](../sources/02-sources.md).

**The headline number: ~50% continuance vs. BTN 2.5x.** Upswing's publicly-quantified BB-vs-BTN example puts the cash-game continuance at 51.7% of hands (combining call and 3-bet) in a $1/$2 spot with the button opening 2.5x [[15]](../sources/02-sources.md). That's much wider than a 2016 pot-odds-only calculation would give, and it's driven by BB realizing more equity than a naïve "OOP is bad" assumption suggests, given that BTN's opening range is weak on average.

**Continuance vs. tighter openers is extrapolated, not published.** Among the Tier-1 and Tier-2 sources in `sources/02-sources.md`, only the BTN 2.5x figure is directly published. The framework for the tapering is MDF-plus-realization: the pot odds offered are roughly the same across opener positions (same sizing, same blinds), so the pot-odds contribution to defense frequency doesn't change. What changes is (a) BB's realized equity against a stronger range and (b) the proportion of BB's own range that retains enough absolute equity to profitably continue. Those two effects move together, but not as fast as raw-equity-vs-range intuition suggests — so BB continuance tapers gently from BTN down through UTG, rather than collapsing. Solver defense vs. the same 2.5x sizing from tighter opens typically falls in these bands (as of April 2026): CO ~46–50%, HJ ~42–46%, UTG ~38–42%. A reader who wants exact numbers should verify in a live solver viewer (GTO Wizard spot viewer, Preflop Prodigy app) [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md).

**Call / 3-bet / fold split.** Against a BTN 2.5x open: roughly 38–40% call, 12–14% 3-bet, 48–50% fold. Against a CO 2.5x open: roughly 36–38% call, 10–12% 3-bet, 50–54% fold. Against an HJ 2.5x open: roughly 32–34% call, 10–12% 3-bet, 54–58% fold. Against an UTG 2.5x open: roughly 30–32% call, 8–10% 3-bet, 58–62% fold. Calls skew toward medium-strength hands that play well postflop (suited connectors, suited broadways, middle pairs). 3-bets skew polarized — AQ+, QQ+, and suited-ace blockers [[15]](../sources/02-sources.md) [[2]](../sources/02-sources.md).

**Stack-depth sensitivity.** At 30bb the call frequency compresses (equity realization IP from OOP worsens as SPRs tighten, and the implied-odds hands lose value); the 3-bet frequency stays similar but its composition shifts toward shove-over-raise for strong pair hands. At 20bb, BB defense becomes a near-binary 3-bet-shove or fold decision for the middle of the range [[3]](../sources/02-sources.md).

**Exploitative adjustment.** Live recreational pools open wider than solver baseline, 3-bet less, and play straightforwardly postflop. BB defense vs. these pools can profitably tighten on the flat-call side (you'll face more c-bets you can't beat) and slightly widen on the 3-bet side (you can value-3-bet wider because villain calls too thin). Doc 08 covers the exploits in depth [[22]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1 discusses defending the BB as a pot-odds question and gives the foundational math (breakeven calling frequency). That math is still correct; the ~52% number against a BTN 2.5x at 100bb is consistent with Will's framework if you plug in modern assumptions. The departure is quantitative, not conceptual: modern solver output gives exact call / 3-bet / fold splits per opener position, where Will's 2016 framing was more abstract. Also, the 3-bet shape choice (polarized from OOP) aligns with Doc 1's L4 polarization teaching; this doc just specifies the OOP-heavy spots where that shape dominates.

### Examples

**Example 7.1 — Facing a BTN 2.5bb open from the BB at 100bb.** Call: suited broadways (KJs, QTs), middle pairs (55–88), suited connectors (76s, 87s, 98s), T9s, J9s, plus wider off-suit broadway and low suited hands including 53o-class hands at the thin margin. 3-bet to 10bb: QQ+, AK, A5s, A4s. Fold: weak off-suit and the most dominated low unsuited hands. Overall continuance ~52% in Upswing's $1/$2 example [[15]](../sources/02-sources.md).

**Example 7.2 — Facing an UTG 2.5bb open from the BB at 100bb.** Call: AJs, KQs, KJs, QJs, AQo, middle pairs (66–TT), some suited connectors (T9s, 98s) and suited-wheel-aces at mix frequency. 3-bet to 10bb: KK+, AK (high frequency), QQ (mixed), A5s (small frequency). Fold: the thinnest off-suit broadway, most low off-suit connectors. Continuance ~38–42% (extrapolated; no primary source publishes this figure directly — verify in a live solver viewer) [[1]](../sources/02-sources.md) [[15]](../sources/02-sources.md).

**Example 7.3 — 30bb MTT, BTN opens 2.1bb, BB faces the open.** Call: tighter than at 100bb — suited broadways and middle pairs only. 3-bet-shove: JJ+, AK, AQs. 3-bet-non-shove: mostly absent at this depth. Fold: everything else. The flat-call range compresses because OOP realization at 30bb SPR is noticeably worse than at 100bb [[3]](../sources/02-sources.md).

---

## 8. Blind-vs-blind (SB-vs-BB)

**Key takeaways**

- The SB's strategy at 100bb is roughly: raise ~40–45% of hands (polarized, top-of-range), limp ~5–15% in some solves, fold the rest [[7]](../sources/02-sources.md) [[19]](../sources/02-sources.md).
- The BB's defense vs. a SB open is very wide — ~80% continuance against a typical 3x SB open — because the price is generous, there's no third player to fear, and BB has position postflop [[16]](../sources/02-sources.md) [[19]](../sources/02-sources.md).
- BvB 3-bet frequency from the BB is among the highest of any spot in the game — ~15–20% of facing a SB open — because BB has position and SB can't easily escape with a 4-bet-fold line [[16]](../sources/02-sources.md).
- The SB limp (re-popularized in modern solves at deep stacks) is not a beginner's limp — it's a structured limp that invites BB's iso-raise, against which SB has a defined calling and 3-betting range [[7]](../sources/02-sources.md).
- BvB is one of the highest-variance spots in the game; understanding the structure is high-leverage [[19]](../sources/02-sources.md).

### Detailed notes

Blind-vs-blind is the only spot in poker where a single player (SB) is both out of position and has invested dead money in the blind. That geometry is unique and drives the entire shape of the BvB game.

**SB strategy structure.** At 100bb, the SB's options are limp, raise, or fold — and the solver preference is a mix of raise and fold with a thin limp slice. The raise range is polarized: the top of the range (strong pairs, strong suited broadways, premium off-suit broadways) plus a thin slice of designed bluffs. The middle of the range either limps or folds. The limp range typically includes medium pairs and playable suited connectors that prefer to see a flop cheaply [[7]](../sources/02-sources.md).

**BB defense vs. SB open.** Against a SB open to 3bb (a common SB size at 100bb, since OOP opens size up), the BB's solver continuance is ~80% of hands. Call: most hands with any playability, including very wide suited ranges. 3-bet: ~15–20% of hands, polarized, to ~10–12bb. Fold: only the true-trash off-suit hands (below Q5o, J5o, etc.) [[16]](../sources/02-sources.md) [[19]](../sources/02-sources.md).

**The SB's role as a 3-bet-heavy position in non-BvB spots.** Separately from the BvB dynamic above, when SB faces an open from LJ, HJ, CO, or BTN, the SB's strategy is 3-bet-or-fold (because calling OOP with a wide range realizes equity poorly and lets BB squeeze). So the SB has a dual personality: tight-opener-limper in BvB, 3-bet-heavy from behind against open-raisers. This is one of the structural shifts from Will's 2016 SB teaching, which was more flat-call-friendly [[1]](../sources/02-sources.md) [[7]](../sources/02-sources.md).

**BB's positional leverage.** In BvB the BB is in position postflop, which is unusual — most BB situations put the BB OOP vs. the opener. That positional advantage is the reason BB's 3-bet frequency is so high: a 3-bet IP in a headsup pot is a high-EV line, and BB can execute it frequently without being exploited [[16]](../sources/02-sources.md).

**Limping mechanics.** The SB limp at deep stacks re-emerged in modern solves because a polarized raise structure leaves a "dead zone" of medium hands that want to see flops cheaply. The solver limps these, invites BB's iso-raise (which BB does ~60–70% of the time), and then has a calling range (the better half of the limp range) and a 3-bet range (the top, which overlaps with hands that could have open-raised). This is structured and not exploitable; attempting it without the full decision tree memorized is a student-level error [[7]](../sources/02-sources.md) [[19]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1 treats blind-vs-blind at the level of the overall framework (positional equity, range dynamics) but does not resolve to a specific strategy split. The modern limp-from-SB structure is a genuine addition — 2016 teaching largely eliminated limping in favor of raise-or-fold, and modern solver work has brought a specific limp slice back at deep stacks in BvB. This is not a contradiction of Will's pedagogy; the limp was eliminated from his framework as a simplification for beginners, and adding it back is a strict expansion for advanced play.

### Examples

**Example 8.1 — 100bb cash, SB-vs-BB, SB action.** SB raises to 3bb with QQ+, AK, AQ, KQs, AJs, KJs (polarized-ish top). SB limps with 22–99, suited connectors 65s–T9s, middle suited broadways like QTs/JTs. SB folds the rest. Against a BB iso-raise after the limp, SB calls the limped-range top and 3-bets with the premium overlap [[7]](../sources/02-sources.md).

**Example 8.2 — BB faces a SB 3bb open at 100bb.** BB continues with ~80% of hands. 3-bet with QQ+, AK, AQ, A5s, A4s, K5s, 75s, 64s (polarized IP). Call with everything playable: all middle pairs, suited broadways, most suited connectors, most off-suit broadways [[16]](../sources/02-sources.md).

**Example 8.3 — 25bb MTT, SB open 2.3bb, BB response.** BB continuance compresses to ~60% at this depth, and the 3-bet becomes a 3-bet-shove with pair and strong-ace hands rather than a non-committing 3-bet. SB's opening range also tightens substantially from the 100bb spot — the limp largely disappears at this stack depth because the structured flatting game requires depth to be profitable [[3]](../sources/02-sources.md).

---

## 9. Antes adjustments

**Key takeaways**

- Antes add dead money to the pot, shifting breakeven open-raise fold frequencies downward and widening opening ranges by approximately 4–6 percentage points across positions [[4]](../sources/02-sources.md).
- Open sizing tends to bump up slightly with antes: 2.0–2.25bb without antes becomes 2.2–2.5bb with antes [[6]](../sources/02-sources.md).
- BB defense widens in lockstep: with a 1bb ante in play, the BB is getting a better price relative to the pot, so the defense frequency rises [[4]](../sources/02-sources.md) [[15]](../sources/02-sources.md).
- The percentage shift is modest, but leverage compounds: a 5-point wider opening range from a 50% base is a meaningful EV shift across an MTT [[4]](../sources/02-sources.md).
- Antes-on blinds (big-blind-ante format, common in modern online MTTs) and per-player-ante formats produce slightly different math, but the net effect on ranges is nearly identical [[4]](../sources/02-sources.md).

### Detailed notes

Antes change the preflop economy in a way that is easy to state but easy to under-weight in practice: they add dead money that doesn't belong to any player, which lowers the break-even fold frequency for every raise and widens every defense range. In chipEV MTT play (non-ICM), the quantified effect is around 4–6% more hands opened per position in solver simulations with antes compared to the chipless base [[4]](../sources/02-sources.md).

**Mechanical reason.** Without antes, an UTG 2.25x open at 100bb risks 2.25bb to win 1.5bb (the two blinds); breakeven fold frequency is 60%. With a 1bb big-blind ante, the same 2.25x open risks 2.25bb to win 2.5bb; breakeven fold frequency is 47.4%. The drop from 60% to 47.4% is a 12.6-percentage-point expansion in the space of profitable steal attempts, which solver output translates to a 4–6% wider opening range once the counter-ranges also update [[4]](../sources/02-sources.md).

**Open-sizing effect.** With antes, the pot is bigger relative to the blinds, so the same multiplier of the blind is a smaller multiplier of the pot. To get the same relative pot build, opens tend to size up slightly (2.25bb → 2.5bb, or 2.0bb → 2.25bb). The size matches the ante structure more than it matches an absolute "bigger or smaller" claim; the right answer is that the size and the range both adjust together [[4]](../sources/02-sources.md) [[6]](../sources/02-sources.md).

**BB defense effect.** BB defense widens under antes, for the same reason: the pot is bigger relative to the call cost, so the price is better. Against a 2.5bb open with a 1bb BB-ante, BB is paying 1.5bb to win 5bb (pre-rake), compared to 1.5bb to win 4bb without antes. Continuance frequency rises by roughly 3–6 percentage points depending on opener position [[15]](../sources/02-sources.md) [[4]](../sources/02-sources.md).

**Small number, big leverage.** The 4–6% range widening looks small on paper, but an MTT grinder plays tens of thousands of hands with antes per year; the EV swing from getting the baseline right is measurable. More important, the ante-widened ranges interact with 3-bet and 4-bet frequencies, and the whole preflop economy shifts together. A player who opens antes-on ranges without widening misses out; a player who widens but keeps the chipless 3-bet frequencies gives too much back [[4]](../sources/02-sources.md).

### Where this departs from Doc 1

Doc 1's L3/L4 coverage assumes antes-on for MTT push-fold work, which is correct. The cash-game coverage is antes-off, which is correct for almost all cash games (the straddle-ante variant exists and is a different animal, handled implicitly by the same logic). The departure is quantitative: Will's framework absorbs the ante-adjustment concept but doesn't put a specific "4–6% wider" number on it. That specificity comes from modern solver output [[4]](../sources/02-sources.md).

### Examples

**Example 9.1 — UTG 6-max MTT open, antes off vs. on.** Antes off at 50bb: UTG opens ~14% at 2.1bb. Antes on (1bb BB-ante) at 50bb: UTG opens ~18–20% at 2.3bb. The extra ~5 percentage points of UTG opens include additional suited connectors and suited-ace hands that weren't quite profitable chipless [[4]](../sources/02-sources.md) [[3]](../sources/02-sources.md).

**Example 9.2 — BB defends a BTN 2.5bb open, antes off vs. on.** Antes off: ~52% continuance (published). Antes on (1bb ante): ~55–58% continuance (extrapolated from the ante-widening math in §9). The extra defense is a mix of wider suited and off-suit broadway calls; the 3-bet frequency barely changes [[15]](../sources/02-sources.md) [[4]](../sources/02-sources.md).

**Example 9.3 — Cash game with straddle (ante-like dynamic).** A live 1/2 with a 4 button-straddle puts dead money in the pot similar to a BB-ante format, and the range-widening logic applies: opens up 3–5 percentage points, defenses wider. Treat the straddled pot as if it had a large ante [[4]](../sources/02-sources.md).

---

## 10. Comparison table — Will Ma 2016 vs. modern solver

**Key takeaways**

- Will's 2016 ranges assumed 3bb opens, Stars online rake, and a pool that 3-bet loosely. Modern solver ranges assume 2.0–2.5bb opens, online-cash rake, and a solver-prepared opponent. Apples and oranges if stripped of context.
- UTG opens widened the most (Doc 1 ~6% → modern ~13% at 9-max). BTN opens widened mildly (Will's 9-max ~45% → modern 9-max ~43–47%; modern 6-max ~48–52%). Middle positions widened modestly at 9-max [[1]](../sources/02-sources.md) [[13]](../sources/02-sources.md).
- Push-fold framework (Doc 1 L3) is essentially unchanged in the modern era — Nash equilibrium at ≤15bb is a solved problem and Doc 1's numbers are still canonical [[8]](../sources/02-sources.md).
- 3-bet shape: Doc 1 taught polarized; modern prefers linear/merged IP and polarized OOP. Not a contradiction — context-dependent [[2]](../sources/02-sources.md).
- SB structure: Doc 1 taught raise-or-fold; modern solves bring back a structured limp at deep stacks in BvB [[7]](../sources/02-sources.md).

### Modern 6-max opens at 100bb cash

Doc 1 publishes Will Ma's 9-max opening ranges but not a 6-max table, so a direct 6-max-to-6-max comparison is not available. The modern 6-max figures are included here on their own for completeness; the cross-era comparison that follows operates on the 9-max data, where Will's numbers are published.

| Position | Modern solver (2.25bb opens, GTO-base) |
|---|---|
| UTG | ~16–18% |
| HJ | ~22–24% |
| CO | ~28–30% |
| BTN | ~48–52% |
| SB | ~40–44% (polarized raise-or-fold) |

### Side-by-side: 9-max opens at 100bb

| Position | Will Ma 2016 | Modern solver | Delta |
|---|---|---|---|
| UTG | ~6% | ~12–14% | +6–8 pts |
| UTG+1 | ~7% | ~13–15% | +6–8 pts |
| MP | ~9% | ~14–16% | +5–7 pts |
| MP+1 | ~12% | ~16–18% | +4–6 pts |
| HJ | ~15% | ~20–22% | +5–7 pts |
| CO | ~22% | ~25–28% | +3–6 pts |
| BTN | ~45% | ~43–47% | ≈0 |
| SB | ~30% | ~38–42% | +8–12 pts; shape changed |

### Side-by-side: ~25bb MTT opens (chip-EV, no ICM)

| Position | Will Ma 2016 (approx, where addressed) | Modern solver (antes on) | Delta |
|---|---|---|---|
| UTG | ~7–9% | ~10–12% | +2–4 pts |
| HJ | ~12–15% | ~14–17% | +2–4 pts |
| CO | ~18–22% | ~20–24% | +2–4 pts |
| BTN | ~35–42% | ~38–42% | ≈0 |
| SB | ~30–35% (raise-or-fold, shove mix) | ~32–38% (raise-or-fold, shove mix expanded) | +2–5 pts |

### Where this departs from Doc 1

Doc 1's 2016 framing is **not wrong** — it's right for the assumptions it made. The three places where modern theory most visibly differs are:

1. **Early-position cash opens**. Doc 1 UTG 9-max ~6% vs. modern ~13% is the largest single delta. Driver: sizing (3bb → 2.25bb) plus solver-base vs. exploit-aware construction.
2. **3-bet shape in position**. Doc 1 L4 taught polarized across the board; modern solves show linear/merged is correct IP, polarized is correct OOP. Contextualize, don't generalize.
3. **SB structure**. Doc 1 treated SB as a traditional raise-or-fold position; modern BvB solves bring back a structured limp at deep stacks, and treat SB as 3-bet-heavy when facing late opens.

In all three cases, Standing Rule #6 applies: frame as right-for-context, not as correction. Will's teaching remains the conceptual foundation. This doc layers solver-calibrated specifics on top [[1]](../sources/02-sources.md) [[2]](../sources/02-sources.md) [[13]](../sources/02-sources.md).

---

## Quick-reference card (1-page printable)

**Sizing conventions (as of April 2026)**

| Action | Online cash | Live cash | MTT chipless | MTT antes-on |
|---|---|---|---|---|
| Open | 2.0–2.3bb | 2.5–3bb | 2.0–2.25bb | 2.2–2.5bb |
| 3-bet IP | 2.5–3.5x open | 3x open | 2.5–3x open | 2.5–3x open |
| 3-bet OOP | 3.5–4.5x open | 3.5–4x open | 3.5–4x open | 3.5–4x open |
| 4-bet IP | 2.2–2.5x 3-bet | 2.2–2.5x 3-bet | tighter at ≤50bb | tighter at ≤50bb |
| 4-bet OOP | 2.5–3x 3-bet | 2.5–3x 3-bet | tighter at ≤50bb | tighter at ≤50bb |

**Open-range percentages, 100bb 6-max cash (as of April 2026)**

| Position | Modern baseline (2.25bb open, unraked sim) |
|---|---|
| UTG | 16–18% |
| HJ | 22–24% |
| CO | 28–30% |
| BTN | 48–52% |
| SB | 40–44% (polarized raise-or-fold, no flat) |

Rake adjustment: tighten each by 5–15% of its width in raked games.

**BB continuance frequencies, 100bb cash (as of April 2026)**

| Facing (at 2.5x) | Call | 3-bet | Total continuance |
|---|---|---|---|
| BTN | ~38–40% | ~12–14% | ~50–52% (published) |
| CO | ~36–38% | ~10–12% | ~46–50% (extrapolated) |
| HJ | ~32–34% | ~10–12% | ~42–46% (extrapolated) |
| UTG | ~30–32% | ~8–10% | ~38–42% (extrapolated) |
| SB 3x (BvB) | ~60% | ~18% | ~78–80% |

*Only the BTN figure is from a primary source; the CO / HJ / UTG bands are extrapolated per §7. Verify in a live solver viewer if the exact number matters.*

**Push-fold landmarks (chipEV, no ICM) (as of April 2026)**

| Stack | SB shove width | BB call width |
|---|---|---|
| 15bb | ~30–35% | ~22–28% |
| 10bb | ~55–60% | ~30–38% |
| 7bb | ~65–70% | ~38–44% |
| 5bb | ~75–80% | ~50–60% |

**3-bet shape by spot — one-line rule**

- IP vs. late open → linear/merged
- OOP vs. late open → polarized
- IP vs. early open → narrow linear or mixed
- OOP vs. early open → narrow polarized or flat-fold

**Antes adjustment — one-line rule**

Add 4–6 percentage points to each opening range; bump sizing 0.2–0.3bb; widen BB defense 3–6 percentage points.

**Decision frame for any preflop spot**

1. Format? (cash 100bb / MTT 50 / 30 / 20bb / ≤15bb push-fold)
2. Sizing convention? (establishes which solver chart)
3. My position / opener's position?
4. My rake / ICM / pool tendencies? (exploits layer)
5. Range before hand: what's the full shape?
6. My hand within that range: its role (value / bluff / call)?
7. Decision: the action that matches the role.

---

## Anti-patterns — what to redirect

| Student error | Diagnosis | Corrective |
|---|---|---|
| "I open 3bb because that's what my book says." | Using 2016 sizing with 2026 ranges. | If your ranges come from a modern chart, use modern sizing (2.0–2.5bb). Mixing them decorrelates the math. Stamp the chart's sizing assumption before using it [[6]](../sources/02-sources.md). |
| "I defend the BB 40% because pot odds." | Pot-odds-only framing ignores rake and realization. | Use the solver continuance per opener position (§7). ~50–52% vs. BTN 2.5x (published); ~38–42% vs. UTG (extrapolated). The number depends on who opened, not just the price [[15]](../sources/02-sources.md). |
| "I 3-bet polarized from every position." | Importing 2016 polarization teaching without context. | IP vs. late open → linear/merged. OOP vs. late open → polarized. The shape depends on position and opener's range [[2]](../sources/02-sources.md). |
| "I flat-call in the SB with QQ to trap." | Misusing the SB's structural OOP position. | SB at 100bb vs. a late open has no profitable flat. 3-bet or fold. Flatting OOP allows the BB to squeeze with impunity [[7]](../sources/02-sources.md). |
| "I shove 15bb with AJo from UTG." | Collapsing raise-fold into shove before the depth demands it. | At 15bb UTG, raise-fold is still correct with AJo. Shove ranges at 15bb are premium-only (QQ+/AK) from early position. The stack still has raise-room [[3]](../sources/02-sources.md). |
| "I play the same range for cash 100bb and MTT 30bb." | Ignoring the stack-depth gradient. | Small pairs, suited gappers, and thin implied-odds hands drop sharply as depth shortens. A 30bb range is 4–6 percentage points tighter in early position than the 100bb range [[3]](../sources/02-sources.md). |
| "I memorize one BB-defense frequency (~50%) and use it everywhere." | Generalizing the BTN-open number to all openers. | ~50–52% is specifically vs. BTN at 2.5x (published). The rate tapers to ~46–50% vs. CO, ~42–46% vs. HJ, ~38–42% vs. UTG (extrapolated) because their ranges are stronger [[15]](../sources/02-sources.md). |
| "I 4-bet with every hand I'd 3-bet for value IP." | Missing the pure-call range when deep. | At 100bb IP, QQ/JJ/AK flat some of the time in a balanced mix. 4-betting everything strong unbalances your calling range and lets 5-bet bluffs run wild [[10]](../sources/02-sources.md). |
| "I limp from the SB in BvB because the solver does." | Attempting the structured limp without the decision tree. | The SB limp is only correct if you have the post-limp call / 3-bet / fold tree memorized. If you don't, raise-or-fold is simpler and barely loses EV [[7]](../sources/02-sources.md). |
| "Solver says open AJo UTG, so I open AJo UTG in my $1/$3 live game." | Ignoring the conditional-baseline rule. | The solver's sizing and rake assumption don't match your game. The thin UTG opens get punished by live rake + pool tightness. Tighten 15–25% [[5]](../sources/02-sources.md) [[22]](../sources/02-sources.md). |

---

## Glossary (additions to Doc 1)

Only terms introduced in this doc, not already covered by Doc 1's glossary.

- **Linear / merged range.** A 3-bet or 4-bet range composed of the contiguous top of a player's hand range (e.g. TT+/AQ+/KQs), without designed bluffs. Distinct from polarized. See §5.
- **Polarized range.** A 3-bet or 4-bet range composed of strong value hands plus designed bluffs (commonly low suited aces for blocker value), with few-to-no medium-strength hands. See Doc 1 L4 for foundational intro; §5 for modern usage.
- **Condensed range.** A 3-bet range composed primarily of medium-strength hands (e.g. JJ–99, AQ, AJs), without premium value or designed bluffs. A defensive shape, uncommon in aggressive modern play. See §5.
- **Capped range.** A range from which the top has been removed, typically as a consequence of other actions (e.g. flatting premiums or 4-betting them). A vulnerability, not a shape you construct deliberately. See §5.
- **Conditional baseline.** The framing that a solver-derived range is always conditional on a (rake, sizing, stack depth, ICM) tuple; changing any of the four shifts the correct range. The central §1 principle.
- **Equity realization (preflop-framed).** The fraction of a hand's raw equity that is actually captured postflop, given position, stack depth, and opponents' tendencies. High realization in position → wider opening ranges; low realization OOP → tighter defense. See §§1, 7.
- **Solver-prepared opponent.** An opponent whose strategy is close enough to GTO that exploitative deviations cost you more than they gain. The default assumption baked into every published solver range.
- **Exploitative deviation.** A deliberate departure from the GTO baseline to take advantage of a specific opponent-pool tendency. See Doc 08 for the practical library.
- **Push-fold threshold.** The stack depth below which raise-fold strategies degenerate to open-shove or open-fold. Typically ~10bb; 15bb is the soft boundary. See §4.
- **Open-shove.** An all-in first-in raise, bypassing the raise-call / raise-3-bet tree. Standard at ≤10bb for wide ranges; rare at 15bb except with premium hands. See §4.
- **BB continuance.** The total frequency (call + 3-bet) with which the big blind defends against an open. ~50–52% vs. BTN 2.5x in 100bb cash (Upswing published figure); extrapolated bands of ~46–50% vs. CO, ~42–46% vs. HJ, and ~38–42% vs. UTG at the same sizing. See §7.
- **Frontier — reconfirm.** A marker used in this doc when a specific numeric claim depends on a published source that could shift as solver methodology or vendor charts update. Treat any `[frontier — reconfirm]`-flagged number as directionally right but worth re-verifying against the linked source before use.

---

## Resources & links

**Free solver / chart sources (primary):**

- [GTO Wizard — main site and free spot viewer](https://gtowizard.com/)
- [GTO Wizard blog — Preflop Range Morphology](https://blog.gtowizard.com/preflop-range-morphology/)
- [GTO Wizard blog — How Stack Sizes Change Your Range](https://blog.gtowizard.com/how-stack-sizes-change-your-range/)
- [GTO Wizard blog — How to Crush Ante Cash Games](https://blog.gtowizard.com/how_to_crush_ante_cash_games/)
- [GTO Wizard blog — Customizable Raked Solutions](https://blog.gtowizard.com/customizable-raked-solutions-with-gto-wizard-ai/)
- [GTO Wizard blog — Preflop Raise Sizing](https://blog.gtowizard.com/preflop-raise-sizing-examining-2-key-factors/)
- [GTO Wizard blog — ICM and Blind Battles (Big Blind)](https://blog.gtowizard.com/icm-and-blind-battles-the-big-blind/)
- [Holdem Resources Calculator (HRC) — free tools](https://www.holdemresources.net/free-tools)
- [Upswing Poker — Preflop Prodigy (free charts)](https://upswingpoker.com/preflop/)
- [Upswing Poker — Push-Fold Tournament Charts](https://upswingpoker.com/push-fold-tournament-strategy-charts/)
- [Upswing Poker — BB Defense Strategy](https://upswingpoker.com/big-blind-defend-strategy-mtt-vs-cash/)
- [Upswing Poker — Defend BB vs. SB](https://upswingpoker.com/defend-big-blind-vs-small-blind/)
- [PokerCoaching (Jonathan Little) — free preflop charts](https://pokercoaching.com/preflop-charts)
- [BBZ Poker — GTO Charts & Preflop Ranges](https://bbzpoker.com/poker-charts/)
- [BBZ Poker — BvB Complete Guide](https://bbzpoker.com/blind-vs-blind-guide/)

**Books (Tier 2):**

- Acevedo, *Modern Poker Theory* (D&B, 2019) — canonical modern GTO textbook.
- Janda, *Applications of No-Limit Hold'em* (D&B, 2013) — pre-solver range-based reasoning.
- Chen & Ankenman, *The Mathematics of Poker* (ConJelCo, 2006) — Nash equilibrium intuition.

**Practitioner writing (Tier 4):**

- [SplitSuit — Understanding 3-Bet Ranges In 2026](https://www.splitsuit.com/understanding-3-bet-ranges)
- [Red Chip Poker — Preflop Poker Charts](https://redchippoker.com/preflop-poker-charts/)

**Full annotated bibliography:** [`sources/02-sources.md`](../sources/02-sources.md).

---

## Where this fits in the knowledge base

- **Predecessor:** [Doc 1, L1](./01-mit-15s50-foundations.md) (opening-range framework), [Doc 1, L3](./01-mit-15s50-foundations.md) (push-fold Nash), [Doc 1, L4](./01-mit-15s50-foundations.md) (3-bet polarization). The *Mental Framework* and *Hand Analysis Workflow* sections at the top of Doc 1 are the conceptual foundation this doc specializes.
- **Follow-ons:**
  - Doc 03 (postflop solver concepts) — range-vs-range play in 3-bet pots, c-bet construction, blockers, overbets. This doc's 3-bet and 4-bet construction sets the range shapes that Doc 03 plays.
  - Doc 04 (ICM deep-dive) — ICM adjustments to every range in this doc at final tables, bubbles, and satellites. This doc gives the chipEV baseline; Doc 04 layers ICM on top.
  - Doc 07 (drill library) — range drills, push-fold drills, BB-defense drills. This doc's principles are the content of those drills.
  - Doc 08 (modern training resources) — the exploit layer, population-adjustment templates, solver / chart / training-site landscape.

---
