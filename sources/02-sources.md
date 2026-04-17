# Doc 02 — Modern Preflop Ranges · Annotated bibliography

> Phase 1 output. Every source used in `docs/02-modern-preflop-ranges.md` is listed here with a URL, an accessed-date, a tier rating (per BUILD_PLAN.md §2.3), and a one-line scope note. Sources are grouped by role in the doc.

**Sourcing tiers** (from BUILD_PLAN.md §2.3):
- **Tier 1:** solver output (GTO Wizard, PioSolver, MonkerSolver, HRC) — primary for ranges, frequencies, sizings.
- **Tier 2:** books / papers by recognized authorities.
- **Tier 3:** training-site content from established pros.
- **Tier 4:** practitioner blogs, videos.
- **Tier 5:** forum / community consensus (sanity-check only).

All URLs accessed 2026-04-16 unless noted otherwise.

---

## Tier 1 — Solver outputs and solver-vendor explanations

### 1. GTO Wizard — main site and free tier
- **URL:** <https://gtowizard.com/>
- **Tier:** 1
- **Scope:** Solver-derived preflop and postflop ranges across cash (up to 100bb, multiple rake structures, with/without straddle), MTT (21 stack depths from 2bb to 100bb), and live-cash formats. The free tier exposes many spot viewers without download. *Canonical Tier-1 reference for this doc.*
- **How it's used:** All "modern solver baseline" claims for opening, 3-bet, 4-bet, BB defense, and blind-vs-blind at 100bb and at MTT stack depths anchor to GTO Wizard's public ranges. Per Standing Rule #8, no paywalled chart is reproduced verbatim — specific hand grids are described in prose or linked back to GTO Wizard's viewer.

### 2. GTO Wizard blog — *Preflop Range Morphology*
- **URL:** <https://blog.gtowizard.com/preflop-range-morphology/>
- **Tier:** 1 (vendor-authored explanation of solver output)
- **Scope:** Defines linear, polarized, merged, and condensed range shapes and shows which shapes apply to opens vs. 3-bets vs. 4-bets. Grounds the "polarized vs. linear/merged" 3-bet decision in §5 of the doc.

### 3. GTO Wizard blog — *How Stack Sizes Change Your Range*
- **URL:** <https://blog.gtowizard.com/how-stack-sizes-change-your-range/>
- **Tier:** 1
- **Scope:** How opening / 3-bet / 4-bet ranges shift from 100bb → 50bb → 30bb → 20bb. Source for the MTT stack-depth section.

### 4. GTO Wizard blog — *How to Crush Ante Cash Games*
- **URL:** <https://blog.gtowizard.com/how_to_crush_ante_cash_games/>
- **Tier:** 1
- **Scope:** Quantifies the ante widening effect on opening ranges ("equivalent positions open-raise around 4–6% more often in the ante simulation compared to classic charts"). Source for the antes-on-vs-off section.

### 5. GTO Wizard blog — *Customizable Raked Solutions With GTO Wizard AI*
- **URL:** <https://blog.gtowizard.com/customizable-raked-solutions-with-gto-wizard-ai/>
- **Tier:** 1
- **Scope:** Shows the magnitude of rake's effect on preflop ranges in cash games ("positions facing an opening raise VPIP 25%–35% fewer hands in raked games compared to unraked"). Source for the "deltas depend on rake" caveat in §1 and §10.

### 6. GTO Wizard blog — *Preflop Raise Sizing: Examining 2 Key Factors*
- **URL:** <https://blog.gtowizard.com/preflop-raise-sizing-examining-2-key-factors/>
- **Tier:** 1
- **Scope:** Why modern open sizes have shrunk from 3bb to 2.0–2.5bb in online cash, and how sizing interacts with range width. Used in §1 (framework) and the 2016-vs-modern comparison table.

### 7. GTO Wizard blog — *ICM and Blind Battles: The Big Blind* / *The Small Blind*
- **URLs:**
  - <https://blog.gtowizard.com/icm-and-blind-battles-the-big-blind/>
  - <https://blog.gtowizard.com/icm-and-blind-battles-the-small-blind/>
- **Tier:** 1
- **Scope:** Solver output for blind-vs-blind dynamics with chipEV vs. ICM adjustments. Used in §8 (Blind-vs-blind) and §9 (antes adjustments) and referenced by the brief cross-ref to Doc 04.

### 8. Holdem Resources Calculator (HRC) — free Nash push-fold tool
- **URL:** <https://www.holdemresources.net/free-tools>
- **Home:** <https://www.holdemresources.net/>
- **Tier:** 1
- **Scope:** Industry-standard Nash equilibrium solver for short-stack tournament push-fold. The free tools page includes classic HU Nash tables and a light push-fold generator. *Primary source for §4 (Push-fold ≤15bb).*

### 9. MonkerSolver — public documentation
- **URL:** <https://www.monkerguy.com/>
- **Tier:** 1
- **Scope:** Reference for multiway and ICM preflop solver methodology. Used as a secondary corroborator to GTO Wizard for 3-bet / 4-bet construction.

---

## Tier 2 — Published books / papers

### 10. Acevedo, Michael — *Modern Poker Theory: Building an unbeatable strategy based on GTO principles* (D&B Publishing, 2019)
- **URL (publisher / Google Books):** <https://books.google.com/books/about/Modern_Poker_Theory.html?id=fQ6oDwAAQBAJ>
- **Tier:** 2
- **Scope:** The canonical modern textbook on GTO-based range construction. Chapter *The Theory of Pre-flop Play* covers playing-first-in, limping, open-push, pre-flop bet sizing, and playing vs. 3-bets. Grounds the conceptual framing in §1 and §5.

### 11. Janda, Will — *Applications of No-Limit Hold'em* (D&B Publishing, 2013)
- **URL (publisher):** <https://dandbpoker.com/products/applications-of-no-limit-hold-em-a-guide-to-understanding-theoretically-sound-poker>
- **Tier:** 2
- **Scope:** Pre-solver foundational text on range-based reasoning, 3-bet / 4-bet polarization math, and sizing. Used to cross-check the intuitions behind the modern solver output.

### 12. Chen, Bill & Ankenman, Jerrod — *The Mathematics of Poker* (ConJelCo, 2006)
- **URL (publisher):** <https://www.conjelco.com/mathofpoker.html>
- **Tier:** 2
- **Scope:** Source for the Nash-equilibrium intuition in §4 (push-fold) and the "iterated best response" framing that Will Ma also uses. Already referenced from Doc 1.

---

## Tier 3 — Training-site content (free-tier only)

### 13. Upswing Poker — *Preflop Prodigy* (free preflop-chart app)
- **URL:** <https://upswingpoker.com/preflop/>
- **Catalog:** <https://upswingpoker.com/charts/>
- **Tier:** 3
- **Scope:** Free solver-derived preflop charts for Online Cash (6-max), Live Cash (9-handed), and Tournament (3 stack depths). Solver-pure ranges with minor simplifications for human use. *Primary source for §2 (cash 100bb opens) and §7 (BB defense).*

### 14. Upswing Poker — *10 Push Fold Charts for Poker Tournaments*
- **URL:** <https://upswingpoker.com/push-fold-tournament-strategy-charts/>
- **Tier:** 3
- **Scope:** Freely available push-fold tables from 2bb through 20bb. Cross-check against HRC output in §4.

### 15. Upswing Poker — *Big Blind Defense Strategy 101: Tournaments vs Cash*
- **URL:** <https://upswingpoker.com/big-blind-defend-strategy-mtt-vs-cash/>
- **Tier:** 3
- **Scope:** Calibrates BB defense frequency by format. Quantitative hook: Upswing's published $1/$2 cash example gives BB continuance of 51.7% vs. a BTN 2.5x open. Used in §7.

### 16. Upswing Poker — *How to Defend Big Blind Vs a Small Blind Open*
- **URL:** <https://upswingpoker.com/defend-big-blind-vs-small-blind/>
- **Tier:** 3
- **Scope:** SB-vs-BB specifics for §8 (blind-vs-blind).

### 17. Upswing Poker — *Master Preflop Play with the New Advanced Solver Ranges*
- **URL:** <https://upswingpoker.com/advanced-solver-ranges/>
- **Tier:** 3
- **Scope:** Upswing's published solver methodology and chart structure — useful for the "why ranges are looser than 2016" framing in §1.

### 18. PokerCoaching (Jonathan Little) — free downloadable preflop charts
- **URL:** <https://pokercoaching.com/preflop-charts>
- **100bb charts:** <https://pages.pokercoaching.com/100bb-charts>
- **Small-stakes cash charts:** <https://jonathanlittlepoker.com/smallcashcharts/>
- **Tier:** 3
- **Scope:** Jonathan Little's public preflop charts (100bb cash plus MTT at multiple depths). *Primary secondary source for §3 (MTT opens by depth) and the 2016-vs-modern comparison.*

### 19. BBZ Poker — *Blind vs Blind Strategy: The Complete Guide to BvB Play in MTTs*
- **URL:** <https://bbzpoker.com/blind-vs-blind-guide/>
- **Tier:** 3
- **Scope:** Blind-vs-blind strategy at multiple stack depths with solver-derived frequencies. Used in §8.

### 20. BBZ Poker — *GTO Poker Charts & Preflop Ranges for Every Position*
- **URL:** <https://bbzpoker.com/poker-charts/>
- **Tier:** 3
- **Scope:** Cross-check for §2 and §3 opening ranges. BBZ's charts cover both tournament and cash.

---

## Tier 4 — Practitioner content

### 21. SplitSuit (James Sweeney) — *Understanding 3-Bet Ranges In 2026*
- **URL:** <https://www.splitsuit.com/understanding-3-bet-ranges>
- **Tier:** 4
- **Scope:** Accessible practitioner writing on 3-bet construction against typical opponent pools. Useful for framing the exploitative-deviation side of §5.

### 22. Red Chip Poker — *Preflop Poker Charts*
- **URL:** <https://redchippoker.com/preflop-poker-charts/>
- **Tier:** 4
- **Scope:** Pool-tendency adjustments to solver baselines, referenced only for the "exploitative deviation" framing in §1 and the cheat sheet.

---

## Tier 5 — Community / consensus (sanity-check only, never load-bearing)

### 23. PokerStrategy forum — *How does preflop rake affect GTO ranges* (community discussion)
- **URL:** <https://www.pokerstrategy.com/forum/thread.php?threadid=513744>
- **Tier:** 5
- **Scope:** Corroborator only for the "ranges tighten with rake" point made authoritatively by GTO Wizard (source 5). Not cited alone.

---

## Dataset tiering summary

| Tier | Count | Sources |
|---|---|---|
| 1 (solver output / vendor explainer) | 9 | 1, 2, 3, 4, 5, 6, 7, 8, 9 |
| 2 (books) | 3 | 10, 11, 12 |
| 3 (training sites) | 8 | 13, 14, 15, 16, 17, 18, 19, 20 |
| 4 (practitioners) | 2 | 21, 22 |
| 5 (community) | 1 | 23 |
| **Total** | **23** | |

**Distinct authors / orgs:** GTO Wizard, HoldemResources / Kim Lee, MonkerSolver, Michael Acevedo, Will Janda, Chen & Ankenman, Upswing Poker, Jonathan Little / PokerCoaching, BBZ Poker, SplitSuit / Red Chip Poker, PokerStrategy forum → **11 distinct authors/orgs.**

---

## Gate check (Phase 1, per BUILD_PLAN.md §3 template)

- [x] ≥ 6 sources across ≥ 3 different authors/orgs (23 sources, 11 authors/orgs)
- [x] Every source has URL, accessed-date (2026-04-16 default), tier rating, 1-line scope note
- [x] At least one Tier 1 or Tier 2 source present (9 Tier-1, 3 Tier-2)

Phase 1 gate met.
