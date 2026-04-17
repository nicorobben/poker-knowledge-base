# Doc 02 — Drafted acceptance-test answers

> Drafted answers to the five acceptance-test questions, each citing the specific Doc 02 section and the Doc 1 lecture it builds on. Every claim here is drawn from Doc 02 + Doc 1 alone — no external material is introduced. This file is the self-check for whether the doc actually answers its target questions.

---

### A1 — UTG 6% vs. 13%: which is right?

Neither is wrong; they're answers to different questions.

Will Ma's 2016 UTG ~6% at 9-max is the correct range under a specific set of assumptions: 3bb opens, Stars online rake in 2016, and a pool that 3-bet loosely enough that thin opens from UTG got punished. Under those conditions, tightening UTG to a value-heavy ~6% is a defensible reasoned construction — exactly what Doc 1's L1 preflop framework would produce if you plug Will's assumptions in.

Modern solver baselines at ~13% for UTG 9-max are the correct range under a different set of assumptions: 2.25bb opens, online-cash rake assumptions, and a solver-prepared opponent that does not over-3-bet the thin top of your range. Under those conditions, the smaller open size lowers the break-even fold frequency from 66.7% (at 3bb) to 60% (at 2.25bb), and that 6.7-percentage-point drop pulls hands like 55, A5s, and KJs from cusp-or-negative into clearly-profitable territory. Doc 02 §1 calls this the **conditional baseline** — a solver range is always conditional on its (rake, sizing, stack depth, ICM) tuple.

The practical translation for a student: if you're playing 2.25bb opens online at 100bb and the pool is near solver-pool behavior, the ~13% range is your baseline. If you're playing 3bb opens live with heavy rake and a 3-bet-happy pool, Will's tighter ~6% range is still the right answer. Both framings are live; the question is which assumption set matches your game.

(Doc 02 §§1, 10; Doc 1 L1 opening-range framework and L4 polarization teaching.)

---

### A2 — BB defense vs. BTN 2.5bb at 100bb cash

Overall continuance is approximately 50–52% of hands at $1/$2 cash (Doc 02 §7, from Upswing's solver-aligned BB-vs-BTN analysis, which publishes 51.7% in its worked cash example). That splits roughly:

- Call: ~38–40% of hands — middle pairs (55–88), suited broadways (KJs, QTs, JTs), suited connectors (76s, 87s, 98s, T9s), one-gappers (J9s, T8s), wider off-suit broadway and some thin low-suited and off-suit hands at the margin.
- 3-bet: ~12–14% of hands, polarized — QQ+ and AK as value; A5s/A4s as blocker bluffs, plus occasional suited-king or low suited-connector bluffs.
- Fold: ~48–50% — the weakest off-suit and most dominated low unsuited hands.

The critical piece for the student: 51.7% is specific to vs. the button at 2.5x and is the only figure published by a primary source. Against tighter openers, the continuance tapers because their ranges are stronger and BB's realized equity drops — but the taper is gentler than raw-equity intuition suggests, because the pot odds offered don't change with the opener's position. Doc 02 §7 gives extrapolated bands per opener position at 100bb at the same 2.5x sizing: ~50–52% vs. BTN (published), ~46–50% vs. CO, ~42–46% vs. HJ, ~38–42% vs. UTG. A student who memorizes "50%" and applies it vs. an UTG open is defending ~8–10 percentage points too loose — meaningful, but not catastrophic. The exact non-BTN numbers should be verified in a live solver viewer.

The reasoning connects back to Doc 1's pot-odds framework (L1) — the break-even calling frequency calculation still holds — but specialized by the modern understanding that realization and opener-range-strength change the equation per position, not just the price.

(Doc 02 §7; Doc 1 L1 pot-odds framework, L4 polarized 3-betting.)

---

### A3 — 12bb BTN, folded to me: raise or shove?

Open-raise, not shove. The 15bb → 10bb boundary (Doc 02 §4) is the relevant landmark: at 15bb effective, raise-fold still dominates for most positions; at 10bb, shove-first-in takes over. 12bb sits between, and on the button specifically, the solver still prefers a raise-first-in for the top of the range (which would otherwise invite easy shoves from the blinds against pure shove ranges).

The correct structure at 12bb BTN:

- Open-raise to ~2.1bb with a wide range (similar in shape to 15bb BTN, roughly 35–42% of hands: all pairs, suited broadways, most suited aces and connectors, broader off-suit broadways).
- Against a 3-bet, the response collapses to near-pure 4-bet-shove (QQ+, AK) or fold. The raise-call line disappears because the stack-to-pot ratio after calling a 3-bet doesn't support postflop play well.
- Open-shove with a narrower premium-weighted slice in some charts (QQ+, AKs), but most solvers keep these as raise-first-in because the raise captures value against the blinds' weaker continues.

The student-level error is collapsing 12bb into "push-fold territory" and jamming a hand like AJo from the button. That's a 10bb-or-less move. At 12bb you still have raise-room, and the raise is higher EV than the shove with the middle and top of your range.

(Doc 02 §4 push-fold framework and 15bb/10bb boundary; Doc 1 L3 push-fold Nash — conceptually still the governing model, specialized by stack-depth gradient in Doc 02.)

---

### A4 — CO opens 2.25bb, BTN 3-bets: polarized or linear?

Linear/merged. Doc 02 §5 is explicit on this: in position vs. a late open (CO or BTN), the modern solver preference is linear/merged construction — TT+, AQ+, KQs, AJs as a contiguous block at the top of the range, roughly 6–8% of hands as a 3-bet.

The reasoning: CO's opening range is already wide enough that a polarized bluff-heavy 3-bet doesn't gain much incremental fold equity, while the medium-strength hands in a linear shape (TT, JJ, AQ, KQs) realize equity very well in position postflop. 3-betting with all the strong hands and flatting only the marginal hands leaves too much EV on the table — specifically, you miss out on the EV of value-3-betting hands that dominate CO's calling range.

This is the most visible place where Doc 1's 2016 polarization teaching (L4) has been specialized rather than contradicted. Polarization is still correct from out of position — for example, SB vs. BTN (Doc 02 §5 Example 5.1) is a classic polarized shape with A5s/A4s blocker bluffs. But IP vs. a late open, the shape flips to linear/merged. The rule of thumb in the quick-reference card distills this: **IP vs. late open → linear/merged; OOP vs. late open → polarized**.

Where this departs from Doc 1: L4 taught polarized as the default 3-bet shape. That's still right for OOP-vs-late-open spots. Modern work narrows the scope of "always polarized" to the OOP cases where it's genuinely optimal, and replaces it with linear/merged in the IP cases where the solver prefers that shape. Will's teaching is foundational; Doc 02 §5 specializes it.

(Doc 02 §5 3-bet construction, Quick-reference card; Doc 1 L4 polarization.)

---

### A5 — Cash ranges for antes-on MTTs: same or different?

Different, and in two distinct ways.

**First, the antes adjustment itself.** Doc 02 §9 quantifies this: antes add dead money, which lowers the break-even fold frequency for every open-raise and widens opening ranges by approximately 4–6 percentage points across positions. Open sizes also bump up slightly — from 2.0–2.25bb chipless to 2.2–2.5bb with antes — to maintain the same relative pot build. And BB defense widens in lockstep by roughly 3–6 percentage points because the better price pulls more hands into profitable defense.

**Second — and the student probably didn't ask, but needs to hear — the stack-depth question that's larger than the antes question.** Doc 02 §3 covers this: MTT stack depths run the gamut from 50bb down to sub-15bb, and the ranges shift substantially across that range. At 50bb the opens are shape-similar to 100bb cash (with antes layered on). At 30bb, small pairs and thin implied-odds hands start dropping from early-position ranges. At 20bb, early-position ranges tighten further and SB transitions toward raise-first-in vs. shove mixes. At 15bb and below, the push-fold framework of Doc 02 §4 and Doc 1 L3 takes over. A cash player who applies the cash 100bb range at 25bb MTT will be opening 4–6 percentage points too wide from early position simply from ignoring the stack-depth gradient.

The practical translation: (a) widen cash-style ranges by ~5 percentage points for antes-on, (b) tighten early-position ranges separately by ~3–5 percentage points per major stack-depth step below 100bb, and (c) the net answer at 25bb antes-on is often *tighter* from UTG than the 100bb cash baseline, once both adjustments apply. The antes and the shallower stack pull in opposite directions.

Forward reference: ICM layers on top of this at final tables and bubbles. That's Doc 04. This doc's ranges are chipEV, not ICM. A student at a final table with pay jumps needs both this doc and Doc 04.

(Doc 02 §§3, 9; Doc 1 L1 opening-range framework, L3 push-fold, L4 3-betting — all of which extend conceptually into MTT play.)

---

## Self-check

- [x] Every answer cites the specific Doc 02 section.
- [x] Every answer cites the specific Doc 1 lecture it builds on.
- [x] No external material introduced beyond Doc 02 + Doc 1.
- [x] Every numeric claim is traceable to a sourced claim in Doc 02.
- [x] Answers respect Standing Rule #6 framing of Doc 1 disagreements as right-for-context.
- [x] Answers respect Standing Rule #8 (no paywalled grid reproduction) — all describe in prose and point to §§ of the doc.

---
