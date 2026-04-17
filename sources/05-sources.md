# Doc 05 — Hand History Review Template · Annotated bibliography

> Phase 1 output. Every source used in `docs/05-hand-history-review.md` is listed here with a URL, an accessed-date, a tier rating (per BUILD_PLAN.md §2.3), and a one-line scope note. Sources are grouped by role in the doc.

**Sourcing tiers** (from BUILD_PLAN.md §2.3):
- **Tier 1:** solver output / vendor explanations (GTO Wizard, PioSolver, HRC) — primary for range and frequency claims.
- **Tier 2:** books / papers by recognized authorities.
- **Tier 3:** training-site content from established pros.
- **Tier 4:** practitioner blogs, podcasts, videos.
- **Tier 5:** community / forum consensus (sanity-check only).

All URLs accessed 2026-04-16 unless noted.

---

## Tier 1 — Solver outputs and tool vendor explanations

### 1. GTO Wizard blog — *How To Get the Most out of Your Hand Reviews*
- **URL:** <https://blog.gtowizard.com/how-to-get-the-most-out-of-your-hand-reviews/>
- **Tier:** 1
- **Scope:** Vendor-authored methodology piece. Argues for selective review over exhaustive review, treats mismatches with the solver as prompts to investigate *principles* rather than memorize *fixes*, and explicitly recommends marking hands during play to defer rumination. Primary source for §§1, 3, and 5 of the doc.

### 2. GTO Wizard — *Redesigned Analyzer & Upgraded GTO Reports*
- **URL:** <https://blog.gtowizard.com/redesigned_analyzer_and_upgraded_gto_reports/>
- **Tier:** 1
- **Scope:** Describes the current (2025-2026) Analyzer workflow: auto-upload, filtering by EV loss, one-click jumps from a played hand to a solver study. Grounds the HUD-assisted and tool-assisted parts of §10.

### 3. GTO Wizard help — *Analyze Mode guide*
- **URL:** <https://help.gtowizard.com/analyze-mode-guide/>
- **Tier:** 1
- **Scope:** Operational documentation for the Analyzer: hand-filtering by EV loss, position, action, and tags. Used in §10 (tool-assisted review).

### 4. GTO Wizard — *How to Use the Hand History Analyzer*
- **URL:** <https://help.gtowizard.com/how-to-use-the-hand-history-analyzer/>
- **Tier:** 1
- **Scope:** Step-by-step workflow documentation. Used as a concrete reference implementation of the review process described in §4.

### 5. GTO Wizard blog — *How to Become a GTO Wizard*
- **URL:** <https://blog.gtowizard.com/how-to-become-a-gto-wizard/>
- **Tier:** 1
- **Scope:** Explains the study → practice → analyze loop that underpins the platform's approach. Used as cross-check for the study-habits framing in §1.

### 6. Holdem Resources Calculator — free tools
- **URL:** <https://www.holdemresources.net/free-tools>
- **Tier:** 1
- **Scope:** Short-stack ICM / Nash push-fold verification tool. Mentioned in §10 as the review tool for ≤15bb decisions — the same tool Doc 02 §4 anchors push-fold claims to.

---

## Tier 2 — Published books / papers by recognized authorities

### 7. Angelo, Tommy — *Elements of Poker* (self-published, 2007; ongoing editions)
- **URL (author site):** <https://www.tommyangelo.com/elements-of-poker/>
- **Reciprocality essay:** <https://www.tommyangelo.com/reciprocality/>
- **Tilt essay:** <https://www.tommyangelo.com/on-tilt/>
- **Tier:** 2
- **Scope:** Canonical reference for the *reciprocality* concept (any difference between you and your opponents that affects your bottom line) and a more operational definition of tilt ("any deviation from your A-game and your A-mindset, however slight or fleeting"). Source for the philosophical framing in §1 (review as EV captured vs. EV left on the table) and the anti-pattern in §12 (reviewing to feel better vs. reviewing to learn).

### 8. Clarke, Peter — *The Grinder's Manual: A Complete Course in Online No Limit Hold'em 6-Max Cash Games* (self-published, 2016)
- **URL (author interview — methodology):** <https://smartpokerstudy.com/interview-peter-clarke-carroters-author-grinders-manual-100-hands-174/>
- **URL (Amazon):** <https://www.amazon.com/Grinders-Manual-Complete-Course-Online-ebook/dp/B01GBFF890>
- **Tier:** 2
- **Scope:** Contains an explicit prescription for tagging hands against chapter topics during a session and reviewing the tagged subset against the material covered. Primary source for the tag-driven review loop in §§3, 8, and 9. Will's Doc 1 hand-analysis workflow is the "how to analyze one hand"; Clarke's tag-drive-review is the "how to analyze a whole session."

### 9. Ericsson, K. Anders; Krampe, Ralf Th.; Tesch-Römer, Clemens — *The Role of Deliberate Practice in the Acquisition of Expert Performance* (Psychological Review, 1993)
- **URL (full PDF):** <https://www.ida.liu.se/~nilda08/Anders_Ericsson/Ericsson_delib_pract.pdf>
- **Alternate (journal):** <https://psycnet.apa.org/record/1993-40718-001>
- **Tier:** 2
- **Scope:** The original "deliberate practice" paper. Specifies the four conditions under which practice builds expertise: (a) well-defined task with appropriate difficulty, (b) informative feedback, (c) opportunities for repetition and correction, (d) motivated learner. Grounds §1's claim that *review is the feedback step* of deliberate practice — without it, play is just repetition. Used as the theoretical scaffold for review's value proposition.

### 10. Ericsson, K. Anders — *Deliberate Practice and Acquisition of Expert Performance: A General Overview* (Academic Emergency Medicine, 2008)
- **URL:** <https://onlinelibrary.wiley.com/doi/10.1111/j.1553-2712.2008.00227.x>
- **Tier:** 2
- **Scope:** Follow-up synthesis on deliberate practice. Used in §1 as secondary support for the feedback requirement and in §11 for the coach-feedback premium (coached practice typically outperforms solo practice by a factor of 2-3x across domains when the coach can identify leaks the student cannot see yet).

---

## Tier 3 — Training-site content (free-tier only)

### 11. PokerCoaching (Jonathan Little) — *How to Effectively Review a Hand History*
- **URL:** <https://pokercoaching.com/blog/how-to-effectively-review-a-hand-history/>
- **Tier:** 3
- **Scope:** Practitioner-authored workflow: preflop first (Equilab/chart check), then push-fold (HRC), then postflop (solver), then node-lock for exploits. Explicit recommendation of 2-3 hours per week minimum. Source for the review-cadence claim in §2, the preflop-first pass in §4, and the leak-categorization structure in §5.

### 12. PokerCoaching (Jonathan Little) — *A Little Coffee* hand history review series
- **URLs (examples of the format):**
  - <https://jonathanlittlepoker.com/150-buy-in-2nd-place-hand-history-review-a-little-coffee-with-jonathan-little-4-15-2020/>
  - <https://jonathanlittlepoker.com/a-little-coffee-with-jonathan-little-11-8-2019/>
  - <https://jonathanlittlepoker.com/sit-n-go-hand-history-review-sng-strategy-a-little-coffee-with-jonathan-little-8-5-2020/>
- **Tier:** 3
- **Scope:** Long-running free video series in which Little reviews a session or a deep-run hand-by-hand in real time, modeling the out-loud reasoning the doc prescribes in §4 (step 0 — verbalize the context). Cited as an exemplar of the workflow rather than as a claim anchor.

### 13. PokerCoaching — *Platinum Coaching Series* overview
- **URL (external review):** <https://cardplayerlifestyle.com/poker-courses/jonathan-littles-25k-platinum-coaching-series-a-thorough-review/>
- **Tier:** 3
- **Scope:** Describes a 15-video progression of coached hand history breakdowns with student input. Used as a third-party-described example in §11 of the coach-involved review structure. Per Standing Rule #8 we do not reproduce the paid course content — only describe the methodology from the external review.

### 14. Red Chip Poker — *6-Max Hand History Analysis*
- **URL:** <https://redchippoker.com/6-max-hand-history-analysis/>
- **Tier:** 3
- **Scope:** Publicly accessible course-framework description for 6-max cash review. Used as a cross-check on the leak-category taxonomy in §5. The categorization pattern Red Chip uses (preflop / flop c-bet / turn barrel / river spots / mental) is the taxonomy this doc formalizes.

### 15. Run It Once — *Foundations* by Phil Galfond (course description)
- **URL:** <https://www.runitonce.com/courses/foundations/>
- **External review (methodology described):** <https://cardplayerlifestyle.com/poker-courses/foundations-by-phil-galfond-review/>
- **Tier:** 3
- **Scope:** Describes Galfond's "value-first" study framework and the BRAIN heuristic (Board coverage, Range & equity, Assets & gaps, Incentives, Nevermind-and-move-on). Cited in §4 step 4 — when you've classified a bet as value or bluff per Doc 1's FTOP, Galfond's value-first frame is a useful next question. Content of the paid course is not reproduced per Standing Rule #8.

### 16. Run It Once — *Simplifying Solvers* by Phil Galfond (course description)
- **URL:** <https://www.runitonce.com/courses/simplifying-solvers/>
- **External reference (methodology):** <https://pokerfuse.com/latest-news/2025/11/phil-galfonds-new-poker-course-teaches-you-how/>
- **Tier:** 3
- **Scope:** Describes a study methodology that works from river decisions backward, aligning with §4 step 6 of this doc (replay-from-Villain's-seat). The methodology is publicly described; the course content is not reproduced.

### 17. Upswing Poker — *WSOP Hand History* / review-framework posts
- **URL:** <https://upswingpoker.com/world-series-of-poker-wsop-hands/>
- **Tier:** 3
- **Scope:** Practitioner-led hand reviews showing the "narrate the decision tree out loud" pattern referenced in §4. Used as an exemplar, not as a claim source.

---

## Tier 4 — Practitioner content

### 18. Sky Matsuhashi / Smart Poker Study — interview with Peter Clarke on review methodology
- **URL:** <https://smartpokerstudy.com/interview-peter-clarke-carroters-author-grinders-manual-100-hands-174/>
- **Tier:** 4
- **Scope:** Podcast interview in which Clarke describes the tag-driven review loop from the book, including his recommendation of 2:1 play:study ratios early in development and 1:1 for serious improvement work. Source for the time-allocation claims in §2.

### 19. BlackRain79 — *PokerTracker vs. Holdem Manager, DriveHUD, Hand2Note, Poker Copilot*
- **URL:** <https://www.blackrain79.com/2020/08/pokertracker-vs-holdem-manager.html>
- **Tier:** 4
- **Scope:** Practitioner comparison of the four major tracking tools. Used in §10 (HUD-assisted review) as a sanity-check source for which tool offers which review filter. Purely operational, not strategic.

### 20. Hand2Note — *vs. Holdem Manager 3 and PokerTracker 4* comparison
- **URL:** <https://hand2note.com/Help/hand2note-vs-other-tools>
- **Tier:** 4 (vendor-authored; used for feature enumeration only)
- **Scope:** Vendor-side feature comparison. Used only to enumerate filter types available in modern trackers in §10 — no strategic claim rests on it.

### 21. PokerTracker — *Marking Hands for Review* tutorial
- **URL:** <https://www.pokertracker.com/guides/pt3/tutorials/marking-hands-for-review>
- **Tier:** 4 (vendor-authored; operational only)
- **Scope:** Operational documentation for the mark-and-tag workflow in §3 and §8. Color-tag schema described here is what the doc translates into the leak-category color scheme.

### 22. Thinking Poker (Andrew Brokos & Nate Meyvis) — book review of *Elements of Poker*
- **URL:** <https://www.thinkingpoker.net/poker-book-reviews/elements-of-poker/>
- **Tier:** 4
- **Scope:** Third-party evaluation of Angelo's framework from a training-podcast angle. Used only as corroboration that the reciprocality concept is taken seriously by modern training voices — not as a primary claim.

### 23. Ericsson critique — *Is the Deliberate Practice View Defensible?* (Macnamara & Hambrick, 2020)
- **URL:** <https://pmc.ncbi.nlm.nih.gov/articles/PMC7461852/>
- **Tier:** 4 (peer-reviewed, but the field is contested)
- **Scope:** Critical review of deliberate-practice theory. Used in §1 for the caveat that deliberate practice is neither necessary nor sufficient for expert performance — only one of several contributors. Prevents §1 from over-claiming that review alone builds a poker career.

---

## Tier 5 — Community (sanity-check only)

### 24. Run It Once chatter — *Doug Polk Hand Analysis on Reddit*
- **URL:** <https://www.runitonce.com/chatter/doug-polk-hand-analysis-on-reddit/>
- **Tier:** 5
- **Scope:** Community discussion referenced only as context-setting for the kind of community-review environment §11 describes. No strategic claim rests on it.

---

## Cross-references to Doc 01 (canonical)

The foundation of this doc is Doc 01's *Hand analysis workflow* (Steps 0 through 7). These are referenced throughout but not re-listed here because they are not external sources — they are canonical prior art from the same knowledge base.

Relevant Doc 01 anchors:
- Hand analysis workflow (the 7 steps) — §4 of this doc extends it into a session-review loop.
- L1 — position / stack / cards hierarchy — used in §4 step 0 (context establishment).
- L2 — Bluffing Epiphanies #1 and #2 — referenced in §4 step 4 (story-check).
- L4 — polarization — referenced in §5 when categorizing 3-bet-pot leaks.
- L6 — ICM — referenced in §5 when categorizing tournament-specific leaks (and forwarded to Doc 04 for the deep treatment).
- L7 — combinatorial analysis — referenced in §4 step 6 (the post-hand replay-from-Villain's-seat move).

---

## Dataset tiering summary

| Tier | Count | Sources |
|---|---|---|
| 1 (solver output / vendor explainer) | 6 | 1, 2, 3, 4, 5, 6 |
| 2 (books / papers) | 4 | 7, 8, 9, 10 |
| 3 (training sites) | 7 | 11, 12, 13, 14, 15, 16, 17 |
| 4 (practitioners) | 6 | 18, 19, 20, 21, 22, 23 |
| 5 (community) | 1 | 24 |
| **Total** | **24** | |

**Distinct authors / orgs:** GTO Wizard, HoldemResources, Tommy Angelo, Peter Clarke, Anders Ericsson et al., Macnamara & Hambrick, PokerCoaching / Jonathan Little, Cardplayer Lifestyle (third-party review), Red Chip Poker, Phil Galfond / Run It Once, Upswing Poker, Sky Matsuhashi / Smart Poker Study, BlackRain79, Hand2Note, PokerTracker, Thinking Poker (Brokos/Meyvis), Run It Once chatter → **17 distinct authors/orgs.**

---

## Gate check (Phase 1, per BUILD_PLAN.md §3 template)

- [x] ≥ 6 sources across ≥ 3 different authors/orgs (24 sources, 17 authors/orgs)
- [x] Every source has URL, accessed-date (2026-04-16 default), tier rating, 1-line scope note
- [x] At least one Tier 1 or Tier 2 source present (6 Tier-1, 4 Tier-2)

Phase 1 gate met.
