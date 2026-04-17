# Poker Coaching Knowledge Base — Build Plan

**Status:** Draft v1
**Repo:** `poker-knowledge-base`
**Doc 1 (MIT 15.S50 Foundations):** Source content exists as `MIT_15_S50_Poker_Knowledge_Base.md` (currently in project knowledge / will be in repo after bootstrap). Repo Bootstrap (Part 0.5) imports it as `docs/01-mit-15s50-foundations.md` before any other work begins.
**Docs to build:** 7 confirmed + 1 proposed
**Recommended total effort:** ~25–40 hours of autonomous Claude Code work, parallelizable into 4 waves
**Required Claude Code capabilities:** filesystem access, `git`, web search + web fetch (for source assembly)

---

## How to use this document

This file is the single source of truth for building out the rest of the knowledge base. Claude Code reads this at session start and executes one doc at a time, phase by phase. Each per-doc brief is self-contained: source list, required structure, definition of done, and watch-outs are all spelled out. No decision should require returning to chat.

If you (the operator) want to run multiple Claude Code sessions in parallel, see **Part 4 — Build Order** for which docs can be built simultaneously without merge conflicts or content overlap.

**If GitHub repo context is provided to the session** (operator may attach the repo URL or push it as project knowledge): start by running `git status` and reading `README.md` to confirm the bootstrap state. If the repo is empty or the bootstrap commit isn't present, run Part 0.5 first.

---

## Part 0 — Project Context

### The North Star

This is a knowledge base for a **dual-purpose audience**:

1. **Human readers** studying poker — students who want a structured, sourced curriculum.
2. **An AI coaching agent** (built on top of the KB) that uses these docs as its operational reference when teaching students.

Every doc must serve both. The pattern from Doc 1 is canonical: a "coaching agent guide" up front (how the agent should use this doc when teaching), then the human-readable curriculum, then named principles, anti-pattern tables, glossary, and resources. **All new docs must mirror this dual-purpose structure.**

### What's done

- **Doc 1** — *MIT 15.S50: How to Win at Texas Hold'em Poker* — full synthesis of the MIT OCW course taught by Will Ma in January 2016. Includes coaching agent guide, hand analysis workflow, all 6 recorded lectures (1, 2, 3, 4, 6, 7), problem sets, and quick-reference cheat sheet. **Content is complete.** The doc currently lives as `MIT_15_S50_Poker_Knowledge_Base.md` in project knowledge; Part 0.5 (Repo Bootstrap) moves it into the repo as `docs/01-mit-15s50-foundations.md`. This doc is the **conceptual foundation** every other doc builds on or extends — every Claude Code session must read it before drafting.

### What's planned (the backlog)

| Doc | Title | Why it exists | Priority |
|---|---|---|---|
| 02 | Modern Preflop Ranges | Will's 2016 ranges are intentionally tight; modern solver ranges are looser | High |
| 03 | Postflop Solver Concepts | Doc 1 L2/L4 give the pedagogical basics; modern GTO is more nuanced | High |
| 04 | ICM Deep-Dive | Doc 1 L6 introduces ICM at concept level; need full final-table treatment | Medium |
| 05 | Mental Game & Tilt | Doc 1 L7 gives ~5 min; this is a major skill area | Medium |
| 06 | Hand History Review Template | Students need a structured workflow for converting played hands into improvement | High (pairs with all theory docs) |
| 07 | Drill Library | Theory needs practice; concrete exercises tied to each concept | Medium |
| 08 | Modern Training Resources | Will's 2016 list is stale (CardRunners, 2+2 forums); landscape changed dramatically | Low (ages fast — build last) |
| 09 | *(Proposed)* Opponent Typing & Population Reads | Will's course is solo-theory; the agent needs population tendencies for exploitative advice | Optional |

---

## Part 0.5 — Repo Bootstrap (one-time, runs before any doc work)

**Trigger:** First Claude Code session against this repo. Skip if `docs/01-mit-15s50-foundations.md` already exists and the folder structure below is in place.

**Goal:** Stand up the repo so that all subsequent per-doc sessions have a deterministic environment. This is its own branch (`bootstrap/repo-init`) and its own commit; not part of any doc's branch.

**Tasks (in order):**

1. **Verify environment.** Confirm working dir is the cloned `poker-knowledge-base` repo and `git status` is clean.
2. **Create folder structure** matching the tree in Part 1: `docs/`, `sources/`, `coaching-agent/test-questions/`, `coaching-agent/test-answers/`, `plans/`. Add `.gitkeep` files where needed.
3. **Import Doc 1.** The source content is `MIT_15_S50_Poker_Knowledge_Base.md` (provided as project knowledge or pasted into chat). Save it as `docs/01-mit-15s50-foundations.md` verbatim. Do not edit the content.
4. **Create `CLAUDE.md`** at repo root containing the standing rules from Part 7 of this document, plus a one-line pointer: "All build instructions live in `BUILD_PLAN.md`. Read it in full before doing anything."
5. **Create `README.md` skeleton** at repo root with: project name, one-paragraph description, link to BUILD_PLAN.md, link to Doc 1, "Status" table showing which docs are built (only Doc 1 ✅ at this point) vs. planned.
6. **Create `.gitignore`** with at minimum: `plans/*` (except `.gitkeep`), `.DS_Store`, `*.swp`, `node_modules/` (just in case), `.env`.
7. **Save BUILD_PLAN.md** to repo root (this file).
8. **Commit and push.** `git add -A && git commit -m "chore: bootstrap repo structure and import Doc 1"` then `git push origin bootstrap/repo-init`.
9. **Open a PR to main and merge** (or merge directly if solo). All subsequent doc branches are created from main.

**Definition of done:**
- [ ] All folders in Part 1's tree exist
- [ ] `docs/01-mit-15s50-foundations.md` exists and matches the project-knowledge source byte-for-byte
- [ ] `README.md`, `CLAUDE.md`, `BUILD_PLAN.md`, `.gitignore` all present at repo root
- [ ] `git log` on main shows the bootstrap commit
- [ ] `git status` is clean

**Watch-outs:**
- Do not edit Doc 1's content during bootstrap. Even small style normalizations risk drift from the canonical source.
- Do not start any Wave 1 doc work in the same session as bootstrap. Bootstrap commits and exits; doc work begins in a new session on a new branch.

---

```
poker-knowledge-base/
├── README.md                              # Project overview, master TOC, quickstart
├── BUILD_PLAN.md                          # This file
├── CLAUDE.md                              # Standing instructions for any Claude Code session
├── .gitignore                             # ignore plans/scratch, .DS_Store, etc.
├── docs/                                  # The KB documents
│   ├── 01-mit-15s50-foundations.md       # ✅ Content done; bootstrapped from project knowledge
│   ├── 02-modern-preflop-ranges.md
│   ├── 03-postflop-solver-concepts.md
│   ├── 04-icm-deep-dive.md
│   ├── 05-mental-game-and-tilt.md
│   ├── 06-hand-history-review-template.md
│   ├── 07-drill-library.md
│   ├── 08-modern-training-resources.md
│   └── 09-opponent-typing.md             # (if approved)
├── sources/                               # Per-doc annotated bibliographies
│   ├── 02-sources.md
│   ├── 03-sources.md
│   └── ...
├── coaching-agent/                        # Agent operational config
│   ├── system-prompt.md                  # Composed from doc front-matter (built in Closing Tasks)
│   ├── test-questions/                   # Per-doc test questions (avoids parallel-write conflicts)
│   │   ├── 02-test-questions.md
│   │   ├── 03-test-questions.md
│   │   └── ...
│   └── test-answers/                     # Drafted answers for self-check (Phase 4 output)
│       ├── 02-test-answers.md
│       └── ...
└── plans/                                 # Phase-level scratch — gitignored; not for shared use
    └── .gitkeep
```

### Naming conventions

- **Doc files:** `NN-kebab-case-slug.md` where NN is the two-digit doc number.
- **Branches:** `doc/NN-short-slug` (e.g., `doc/02-preflop-ranges`). Bootstrap branch is `bootstrap/repo-init`. Final integration branch is `integration/final-pass`.
- **Commits:** [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/). Use scope = doc number, e.g., `docs(02): draft section on 3-bet construction`. Phase-completion commits use `docs(02): phase N complete — [phase name]`. Bootstrap and integration use scope `chore`.

### File ownership rule

One doc per branch, one author (one Claude Code session) at a time. If two docs are being built in parallel, they live on separate branches and never touch each other's files until merged.

---

## Part 2 — House Style (applies to every doc)

Every doc must conform to this style. The "Quality Pass" phase explicitly checks compliance.

### 2.1 — Document anatomy

Every doc has these sections, in this order:

1. **Title + Doc N of N + Source attribution + License** (top of file)
2. **Coaching agent guide** — "read this first if you're Claude" — how the agent should use this doc when teaching, what mistakes to redirect, what tone to take, what limits to honor.
3. **How to use this document as a human reader** — orientation for the student.
4. **Mental framework / core thesis** (where applicable) — the 2–3 ideas that thread through the rest.
5. **Main body** — concept sections in pedagogical order. Each major section opens with a **Key Takeaways** block (memorize-able rules), then **Detailed Notes** (the reasoning), then **Examples** (concrete hands or cases).
6. **Quick-reference cheat sheet** — distilled named principles for fast lookup mid-conversation.
7. **Anti-patterns / common mistakes table** — what to redirect, with named diagnoses.
8. **Glossary** — every term defined. Add to it as you draft.
9. **Resources & links** — every URL referenced in the doc, organized by category.
10. **Where this fits in the knowledge base** — link to predecessor docs, link to follow-on docs.

### 2.2 — Voice and tone

Mirror Will Ma's pedagogy from Doc 1:

- **Concrete first, principle second.** Lead with a hand example or specific case; then name the principle. Never the other way around.
- **Math-grounded.** Show the EV calculation, the combo count, the equity number. Don't hand-wave.
- **Honest uncertainty.** When the answer is "it depends" or "no one really knows," say so. Don't manufacture confidence.
- **Named principles.** Give every concept a memorable name so the agent can reference it ("This is reverse implied odds"). Re-use Doc 1's named concepts where they apply; coin new ones where the doc covers new ground.
- **Anti-results-oriented.** Always evaluate decisions, not outcomes. Make this a verbal pattern.
- **Direct.** Will is not chatty. Cut filler. Say the thing.

### 2.3 — Sourcing rules

- **Every non-obvious claim is sourced** in-line with a link or footnote. "Opening 22% of hands from CO is solver-standard at 100bb cash" — needs a source.
- **Authoritative source hierarchy** (use the highest-tier source available):
  - Tier 1: solver outputs (GTO Wizard, PioSolver, MonkerSolver) — for ranges, frequencies, sizings.
  - Tier 2: published books and papers by recognized authorities (Tendler, Janda, Sklansky, Chen).
  - Tier 3: training site content from established pros (Upswing, Run It Once, Raise Your Edge).
  - Tier 4: practitioner blogs and videos with named authors.
  - Tier 5: forum consensus (2+2, Reddit r/poker) — only for population tendencies, never for theory.
- **Date stamp every claim that could age.** Solver outputs change with rake structure, antes, and software updates. Always note "as of [date], using [ruleset]."
- **Flag the modern frontier.** When a claim depends on the latest solver work and may shift, mark it: `[frontier — reconfirm Q[N] [year]]`.
- **Never invent quotes.** If you attribute a sentence to a person, link the source. Doc 1's verbatim Will Ma quotes are the model.

### 2.4 — Coaching agent integration patterns

Every doc must include these agent-facing elements:

- **A "How the agent should use this doc" front-matter section.** What kinds of student questions does this doc answer? What's the agent's default workflow when invoking content from this doc?
- **A named-principles block** the agent can reference verbally. ("That's the equity-realization adjustment from Doc 3.")
- **An anti-pattern table** mapping student errors to the relevant lecture concept and the corrective response.
- **5+ sample student questions** (in `coaching-agent/agent-test-questions.md`) that the agent should be able to answer using only this doc + Doc 1. These are the doc's acceptance test.

### 2.5 — Cross-referencing convention

- **Backward refs to Doc 1:** Every concept that extends a Will Ma lecture must link back. Format: `(Doc 1, L2 — Will Ma's FTOP)` or inline `(see Doc 1, "Bluffing Epiphany #2")`.
- **Sibling doc refs:** When a concept is treated more deeply elsewhere in the KB, link forward. Format: `→ Doc 03, "Equity realization"`.
- **Forward placeholders:** If a doc that doesn't exist yet would be the right home for something, leave a `TODO(Doc NN): ...` comment. The Quality Pass phase resolves these.
- **Don't duplicate.** If a topic is covered in another doc, link to it instead of re-explaining. Brief reminders are OK; full re-treatments are not.

### 2.6 — Length and scope discipline

- **Target length per doc: 8,000–15,000 words.** Doc 1 is ~25,000 because it covers 6 lectures; new docs are narrower.
- **If a section grows past ~3,000 words, consider splitting** that section into its own follow-on doc and replacing it with a summary + forward link.
- **Stay in your lane.** Each per-doc brief in Part 3 has explicit "Scope OUT" — those topics get punted to their owning doc, not partially treated here.

---

## Part 3 — Per-Doc Briefs

Each brief below is a complete spec. A Claude Code session should be able to build the doc using only its brief + Doc 1 + Part 2 (house style).

### Per-doc phase template

Every doc follows the same five phases. Specifics are in each brief; the structure is constant. **All gates are self-checkable** — Claude Code can verify them without human input. Optional human review checkpoints are flagged separately; they pause execution but do not block autonomous runs.

| Phase | Name | Output | Self-checkable gate to advance |
|---|---|---|---|
| 1 | **Source assembly** | `sources/NN-sources.md` — annotated bibliography with URLs, ratings, scope notes | (a) ≥6 sources listed across at least 3 different authors/orgs; (b) every source has URL, accessed-date, tier rating (per §2.3), and 1-line scope note; (c) at least one Tier 1 or Tier 2 source present |
| 2 | **Outline** | Section-level outline as a comment block at top of `docs/NN-*.md` | (a) Outline contains every required anatomy section (§2.1); (b) section titles match required outline in this doc's brief; (c) no section name overlaps with a sibling doc's Scope IN |
| 3 | **Draft** | Full prose draft of the doc body | (a) Word count in 8,000–15,000 range (or brief's target); (b) zero `[unsourced — needs review]` markers (all replaced with sourced claims or removed); (c) every claim that depends on solver/tool output has an `as of [date]` stamp |
| 4 | **Coaching integration** | Coaching agent guide front-matter added; named principles named; anti-pattern table built; 5 test questions added to `coaching-agent/test-questions/NN-test-questions.md`; drafted answers in `coaching-agent/test-answers/NN-test-answers.md` | (a) All 5 test questions have drafted answers in `test-answers/NN-test-answers.md`; (b) every answer cites which section of this doc + which lecture of Doc 1 it draws from; (c) no answer requires content outside this doc + Doc 1 |
| 5 | **Quality pass** | Internal links audited; glossary section finalized; sibling-doc cross-refs added (forward placeholders only — sibling docs are updated by their own owners or Closing Tasks); `[TODO]` markers resolved or escalated to "future work" section | (a) `grep -r "TODO" docs/NN-*.md` returns zero unintentional TODOs (planned future work is OK if labeled); (b) every URL in the doc returns 200 (use web_fetch to spot-check 5 random URLs); (c) every `(Doc 1, ...)` reference resolves to a real section heading in `docs/01-mit-15s50-foundations.md`; (d) glossary contains every bolded term used in the doc body |

**Note on README.md and master glossary:** Per-doc Phase 5 does NOT update the master `README.md` TOC or the master `glossary.md`. Those are touched only by Closing Tasks (Part 5) to avoid parallel-write conflicts when multiple docs are being built concurrently.

**Optional human-review checkpoints** (flagged but not blocking):
- After Phase 1: operator can sanity-check the source list before drafting begins. If skipped, drafting proceeds.
- After Phase 4: operator can read the drafted test answers as a quality signal. If skipped, Phase 5 proceeds.

If Claude Code gets stuck on any phase after 3 attempts → commit WIP with `git commit -m "wip(NN): stuck on [description]"` and stop. Wait for human review.

---

### Doc 02 — Modern Preflop Ranges

**Slug:** `02-modern-preflop-ranges`
**Branch:** `doc/02-preflop-ranges`
**Why it exists:** Will Ma's 2016 opening ranges (Doc 1, L1) are deliberately tight — easier to err tight as a beginner. Modern solver-derived ranges are meaningfully looser, especially from late position and in 3-bet construction. The agent currently can't give a student a current-standard preflop chart, which is table-stakes for any coaching tool.

**Scope IN:**
- Open-raise (RFI) ranges by position, for cash 100bb and MTT stack depths (50bb, 30bb, 20bb)
- Push-fold ranges (≤15bb) — replace Doc 1 L3's Nash sketch with full charts
- 3-bet ranges (value + bluff construction) by position pair and stack depth
- 4-bet ranges (value + bluff)
- BB defense vs. open ranges
- SB strategy (open vs. limp vs. fold) — modern view
- Blind-vs-blind dynamics
- Antes-on vs. antes-off adjustments
- Comparison table: Will Ma's 2016 ranges vs. modern solver ranges (so students can see the delta)

**Scope OUT:**
- Detailed solver theory and methodology → Doc 03
- Final-table-specific ICM preflop adjustments → Doc 04 (mention briefly + link)
- Drilling and quizzing on ranges → Doc 07
- Comparing solver products → Doc 08

**Source list (build during Phase 1):**
- GTO Wizard public free ranges (gtowizard.com — the free preflop solutions)
- Upswing Poker free preflop charts (upswingpoker.com)
- Jonathan Little's MTT charts (jonathanlittlepoker.com / pokercoaching.com free content)
- Holdem Resources Calculator (HRC) — for push-fold Nash baselines
- Daniel Negreanu MasterClass charts (cite carefully — they're conservative)
- Modern reg-pool consensus charts from 2+2 / Reddit (Tier 5 — only as sanity check)

**Required outline:**
1. The opening framework — why ranges are looser than 2016, what changed
2. Cash 100bb open ranges by position (full 6-max + 9-max tables)
3. MTT open ranges by stack depth (50/30/20bb)
4. Push-fold (≤15bb) — full Nash tables for each position vs. each remaining player count
5. 3-bet construction — the modern polarized vs. linear/merged decision
6. 4-bet construction
7. BB defense
8. Blind-vs-blind
9. Antes adjustments
10. Comparison table: Will Ma 2016 vs. modern (deltas highlighted)
11. Quick-reference card (1-page printable)
12. Glossary additions, resources, cross-refs

**Cross-refs:**
- Doc 1, L1 (opening ranges, position hierarchy)
- Doc 1, L3 (push-fold, Nash equilibrium intuition)
- Doc 1, L4 (3-bet polarization theory)
- → Doc 03 (postflop play in 3-bet pots)
- → Doc 04 (ICM-aware adjustments at final tables)

**Coaching integration:**
The agent must be able to:
- Give a specific opening range for any (position, stack depth, format) combo
- Distinguish "solver baseline" from "exploitative deviation" and state which it's giving
- Explain *why* a modern range differs from Will's 2016 chart in concrete terms (rake structure, ante effect, theoretical refinement)

**5 test questions for this doc:**
1. "What should I open from the cutoff at 100bb cash?"
2. "I have AKo on the button at 25bb in an MTT — what's my play if UTG opens to 2.2bb?"
3. "How wide should I 3-bet from the BB vs. a CO open at 100bb?"
4. "When antes kick in, how much should my UTG range widen?"
5. "Will Ma says open 6% from UTG; modern charts say ~12%. Why the gap?"

**Watch-outs:**
- Solver outputs vary by **rake structure** and **ante size**. Always specify which dataset a chart is from.
- Don't claim a single "correct" cash range — it depends on the pool's tendencies and the rake.
- Push-fold Nash is mostly stable; postflop-relevant ranges are where the modern frontier moves.
- **Frame deltas vs. Doc 1 honestly** (per Standing Rule #6). Add a "Where this departs from Doc 1" sub-section explaining that Will's ranges were pedagogically tight on purpose; modern solver ranges are not a correction of Will but an evolution for a different opponent pool.
- **Chart rendering.** Markdown can't render the visual 13×13 hand-grid heatmap that solvers produce. Use plain markdown tables with annotated cells (e.g., `R` raise / `C` call / `F` fold, or `R/C 50/50` for mixed strategies). For each chart, include a link to the original solver source so readers can see the visual version. Do NOT attempt ASCII art grids — they break readability on mobile.
- **Copyright on solver outputs.** Per Standing Rule #8: cite paid solver products but never reproduce their charts verbatim. Use only freely-available outputs (free GTO Wizard tier, Upswing free charts, public Nash equilibrium tables from HRC).

---

### Doc 03 — Postflop Solver Concepts

**Slug:** `03-postflop-solver-concepts`
**Branch:** `doc/03-postflop-solver`
**Why it exists:** Doc 1 L2 (Will Ma's FTOP, c-bet basics) and L4 (3-bet pots) give pedagogically clean rules. Modern postflop GTO is meaningfully more nuanced — small c-bets at high frequency, range vs. range thinking, equity realization, blocker effects, mixed strategies, overbet theory. The agent currently can't reason about postflop spots at the level a student getting their feet wet with a solver expects.

**Scope IN:**
- Range vs. range as the unit of analysis (vs. hand vs. range from Doc 1 L1)
- Equity realization (R%) — why a hand's equity ≠ its EV
- Board texture taxonomy (dry/wet, paired, monotone, connected, high/middle/low, dynamic vs. static)
- C-bet sizing matrix by texture and position
- Multi-street barrel construction (turn card categorization, river decision tree)
- Polarization vs. linear vs. merged vs. condensed ranges (postflop)
- Blocker theory (for value, for bluffs, for bluff-catching)
- Modern view of donk-betting (when solvers actually like it)
- Overbet theory (when, with what range, what to defend with)
- Common solver insights that contradict folk wisdom (small c-bets, big rivers, mixed strategies, defending wider than intuition suggests)

**Scope OUT:**
- Preflop ranges → Doc 02
- ICM-adjusted postflop play → Doc 04
- Drilling postflop spots → Doc 07
- Specific solver software comparisons → Doc 08
- Opponent-specific exploitative play → Doc 09 (if approved)

**Source list:**
- GTO Wizard free postflop solutions (gtowizard.com)
- Upswing Poker postflop content (free articles + course descriptions)
- "Modern Poker Theory" by Michael Acevedo (book — primary modern textbook)
- "Play Optimal Poker" 1 & 2 by Andrew Brokos (book)
- Run It Once free content (Phil Galfond, Patrick Leonard)
- BBZ Poker public content
- Doug Polk YouTube content (cite specific video URLs)

**Required outline:**
1. The mental model shift: range vs. range, not hand vs. range
2. Equity realization — what it is, why it matters
3. Board texture framework (with classification table)
4. Flop c-bet sizing matrix (texture × position × range type)
5. Turn play — card categorization (good/bad/neutral for each player)
6. River decision framework — value, bluff, bluff-catch
7. Range polarization (revisited from Doc 1 L4 with postflop nuance)
8. Blocker theory — full treatment
9. Donk-betting — the modern reversal
10. Overbet theory
11. "Solver insights that contradict folk wisdom" — a section that calls out the deltas vs. Doc 1
12. Quick-reference cheat sheet
13. Glossary, resources, cross-refs

**Cross-refs:**
- Doc 1, L2 (Will's FTOP, basic c-bet, bluffing epiphanies)
- Doc 1, L4 (preflop polarization → postflop polarization)
- Doc 1, L7 (combinatorial analysis — extends naturally into blocker theory)
- → Doc 02 (preflop ranges feeding into postflop)

**Coaching integration:**
The agent must be able to:
- Take a (board texture + range matchup) and recommend a sizing + frequency
- Explain blocker effects on a specific decision
- Identify when a solver mixed strategy applies and what it means for the student's choice
- Differentiate "GTO baseline" from "exploitative deviation"

**5 test questions:**
1. "I have AK on a K72 rainbow flop in a SRP from BTN vs. BB — should I c-bet, and how much?"
2. "What's the blocker effect of holding A♠ on a monotone spade river when considering a bluff?"
3. "Why do solvers like small c-bets on high-card dry boards?"
4. "On a 9♠8♠7♥ flop, what's the difference between a polarized and a merged range?"
5. "Will Ma says don't donk-bet. When do solvers say it's actually correct?"

**Watch-outs:**
- Mixed strategies are confusing for students. Always present the **frequency**, then the **principle behind the frequency**, then the **practical recommendation** (e.g., "default to the higher-frequency action unless you have a specific reason").
- Solver outputs are baselines, not exploits. Be explicit when crossing from theory to practice.
- Don't contradict Doc 1's pedagogical model. Frame this as *adding nuance* to Will's rules, not replacing them.

---

### Doc 04 — ICM Deep-Dive

**Slug:** `04-icm-deep-dive`
**Branch:** `doc/04-icm-deep-dive`
**Why it exists:** Doc 1 L6 introduces ICM at the conceptual level with a 3-player example. Modern tournament play requires fluency with bubble factors, risk premiums, FGS (future game simulation), satellite strategy, and pay-jump-driven preflop adjustments. This doc takes a student from "I get the idea" to "I can actually play a final table without burning EV."

**Scope IN:**
- ICM math refresher (formula, intuition, when it kicks in)
- Bubble factor — what it is, how to estimate it
- Risk premium — calculating the chip-EV-vs-money-EV gap for any spot
- Big stack adjustments at final tables
- Medium stack tightening
- Short stack play — survival vs. ladder vs. accumulate
- Satellite strategy (heavy ICM, fold-AA-on-the-bubble math)
- Pay jump exploitation
- Deal-making theory (chip chop vs. ICM chop vs. negotiated)
- FGS (Future Game Simulation) introduction — what it adds beyond ICM, when to care
- ICM-aware preflop ranges at final tables (defer detail to Doc 02 cross-ref)

**Scope OUT:**
- Cash game theory entirely → Docs 02/03
- Mental game of bubble pressure → Doc 05
- Specific ICM tools (ICMIZER, HRC) feature comparison → Doc 08

**Source list:**
- ICMIZER documentation and free tutorials (icmpoker.com)
- Holdem Resources Calculator docs (holdemresources.net)
- Nick Petrangelo final-table content (training site previews + interviews)
- "Kill Everyone" by Nelson, Steib, Heston, Hachem, Grospellier (Doc 1 already cites this)
- Modern MTT training content from Raise Your Edge (free portions)
- Snowie / DTO Poker content for FGS

**Required outline:**
1. ICM math — full refresher with worked examples
2. Bubble factor — concept and computation
3. Risk premium — the operational unit of ICM decisions
4. Stack-size strategy: big/medium/short
5. Satellite strategy — the special case
6. Pay jump dynamics
7. Deal-making theory
8. FGS — what it is, when it matters
9. Common ICM mistakes (anti-pattern table)
10. Quick-reference cheat sheet (bubble factor estimation, fold-equity adjustments)
11. Glossary, resources, cross-refs

**Cross-refs:**
- Doc 1, L6 (ICM intro — assume this as background)
- Doc 1, L3 (push-fold — adjusted for ICM here)
- → Doc 02 (preflop ranges, ICM-adjusted)
- → Doc 05 (mental game on the bubble)

**Coaching integration:**
The agent must be able to:
- Take (chip stacks, payout structure, hand, position) and recommend an ICM-aware action
- Estimate bubble factor without running a calculator (rough)
- Explain *why* a chip-EV+ play is money-EV− in a specific spot
- Recognize when ICM is and isn't relevant (early MTT vs. final table vs. cash)

**5 test questions:**
1. "I'm on the bubble of a satellite, dealt AA in the BB, and a big stack jams from UTG covering me. What's the play?"
2. "Final table, 5 left, I'm 2nd in chips. Chip leader covers me by 2x. CO opens, I have AKo in the SB. Call, 3-bet, or fold?"
3. "What's the difference between bubble factor and risk premium?"
4. "When does ICM start mattering in a tournament?"
5. "My 3 opponents and I want to chop. What's the difference between a chip chop and an ICM chop?"

**Watch-outs:**
- ICM math is computationally hard. Be honest that the agent should recommend tools (ICMIZER, HRC) for precise spots — its job is to teach the *reasoning*, not crunch the numbers in real time.
- Satellite strategy is genuinely different from regular MTT ICM — call this out explicitly so students don't conflate them.
- Doc 1 already covers the concept; this doc *operationalizes* it. Don't re-prove that ICM matters; assume the student is past that.

---

### Doc 05 — Mental Game & Tilt

**Slug:** `05-mental-game-and-tilt`
**Branch:** `doc/05-mental-game`
**Why it exists:** Doc 1 L7 closes with "four reasons there's money in poker," and two of them (overconfidence, gambling self-control) are mental game. Will gives ~5 minutes of treatment. For most students, mental game is the largest leak — bigger than any technical hole. The agent needs a real framework for diagnosing and addressing it.

**Scope IN:**
- Tilt taxonomy (Tendler's seven tilt profiles)
- A-game / C-game model
- The "inchworm" — moving your B-game forward, shrinking the gap
- Bankroll management — guidelines + the psychology behind them
- Variance acceptance — emotional, not just intellectual
- Downswing management
- Upswing management (overlooked, but important — overconfidence creep)
- Session structure — length, breaks, environment
- Pre-session and post-session routines
- Study/play balance
- Ego calibration and confidence management
- Moving up in stakes — psychological dimension
- Recognizing when a student's "technical" question is actually a mental game question

**Scope OUT:**
- Pure technique → other docs
- Specific bankroll *numbers* by stake — those go in Doc 08 alongside the tools that calculate them

**Source list:**
- Jared Tendler — "The Mental Game of Poker" 1 & 2 (canonical references)
- Tommy Angelo — "Elements of Poker" (especially the "reciprocality" and tilt-control sections)
- Elliot Roe — public content (his Primed Mind app, podcast appearances)
- Ed Miller — "Poker's 1%" (motivation + study habits framing)
- The "Thinking Poker" podcast back catalog (named episodes)

**Required outline:**
1. Why mental game is the biggest leak for smart students
2. Tilt taxonomy — the seven types with diagnostic questions for each
3. A-game vs. C-game — the inchworm model
4. Bankroll management — psychology before numbers
5. Variance — emotional acceptance, not just intellectual
6. Downswing playbook
7. Upswing playbook (and why this exists)
8. Session structure
9. Pre/post session routines
10. Study habits
11. Ego and confidence calibration
12. Moving up — when, how, what to expect emotionally
13. Diagnostic: when a "technical" question is really a mental question
14. Anti-pattern table
15. Glossary, resources, cross-refs

**Cross-refs:**
- Doc 1, L1 (decision mentality, results-orientedness)
- Doc 1, L7 (overconfidence, gambling self-control, "joy of making good decisions")
- → Doc 06 (study habits feed the review template)
- → Doc 08 (mindset coaches and apps as resources)

**Coaching integration:**
The agent must be able to:
- Recognize when a student's question is mental rather than technical (e.g., "I keep losing to bad players" is often tilt, not strategy)
- Walk a student through diagnosing their tilt type
- Recommend specific routines (not generic "stay calm" advice)
- Talk a student through a downswing without rationalizing or moralizing

**5 test questions:**
1. "I just lost three buy-ins in two hours. Should I keep playing to get unstuck?"
2. "How do I stop tilting when fish suck out on me?"
3. "I'm winning at 5NL — when should I move up to 10NL?"
4. "I've been studying 10 hours a week for 6 months and I'm still breakeven. What's wrong?"
5. "How big should my bankroll be for [stake]?"

**Watch-outs:**
- This is the doc where moralizing is most tempting. **Don't.** Ground every recommendation in a specific framework (Tendler, Angelo, etc.) with attribution.
- Some students will be in genuine distress (gambling addiction signals). The agent's job is to recognize this and recommend professional help — see the user-wellbeing section in any standing system prompt; this doc must include explicit guidance on the boundary.
- Don't conflate mental game with motivational fluff. The Tendler / Angelo work is rigorous; treat it as such.

---

### Doc 06 — Hand History Review Template

**Slug:** `06-hand-history-review-template`
**Branch:** `doc/06-hand-review-template`
**Why it exists:** Doc 1 gives the analytical framework (the 7-step hand analysis workflow) but no operational process for systematically reviewing a played session and converting leaks into improvement. This doc is what turns Docs 1–5 from a curriculum into a *practice*.

**Scope IN:**
- Review philosophy — what makes review effective vs. ritualistic
- When to review (timing, frequency)
- Hand selection criteria — which hands to review, which to skip
- The full 7-step workflow (extends Doc 1's hand analysis workflow into a session-review structure)
- Leak categorization (preflop / postflop / mental / ICM)
- Leak-to-drill conversion (which leak → which drill in Doc 07)
- Session journal template
- Weekly leak review process
- Monthly leak audit
- Using HUD stats for self-review (basic — defer tool details to Doc 08)
- Solo review vs. group/coach review

**Scope OUT:**
- Specific drills → Doc 07
- HUD/tracking software comparisons → Doc 08
- Mental game routines → Doc 05 (cross-ref)

**Source list:**
- Doc 1's hand analysis workflow (foundational — extend, don't duplicate)
- Tommy Angelo's review content
- Run It Once review videos (Galfond's review methodology — public excerpts)
- Upswing Lab review templates (where publicly described)
- Modern coaching practitioners (Jonathan Little, Matt Affleck) on review

**Required outline:**
1. Review philosophy — process over product
2. Review timing and frequency
3. Hand selection — the "interesting hand" filter
4. The session review workflow (7 steps, extended from Doc 1)
5. Leak categorization framework
6. Leak-to-drill conversion table
7. Session journal template (printable + markdown version)
8. Weekly review process
9. Monthly leak audit
10. HUD-assisted review (basics)
11. Solo vs. group review
12. Anti-pattern table (e.g., "results-oriented review", "only reviewing losers")
13. Glossary, resources, cross-refs

**Cross-refs:**
- Doc 1, hand analysis workflow (extend and operationalize)
- Doc 1, L7 (combinatorial analysis as the deepest review move)
- → Docs 02, 03, 04, 05 (leak categories map back to these)
- → Doc 07 (leak-to-drill conversion)

**Coaching integration:**
The agent must be able to:
- Walk a student through a session review in real time
- Take a described hand and apply the 7-step workflow
- Diagnose a leak from a described pattern and recommend specific drills (cross-ref to Doc 07)
- Help a student build a session journal habit

**5 test questions:**
1. "I just played 200 hands. How do I review the session?"
2. "I keep getting it in bad on the river. How do I diagnose what's actually going wrong?"
3. "What's the difference between reviewing a hand because I lost and reviewing it because the decision was hard?"
4. "Should I review my biggest losing hand of the day?"
5. "How often should I be reviewing?"

**Watch-outs:**
- Easy to make this feel mechanical. Emphasize the *principle* behind each step (from Doc 1) — the workflow is the structure, the principles are the content.
- Don't make review a chore. The doc should help students *want* to review, not just give them a checklist.

---

### Doc 07 — Drill Library

**Slug:** `07-drill-library`
**Branch:** `doc/07-drill-library`
**Why it exists:** Theory needs practice. Students consistently say they "understand" concepts but can't apply them at the table. This doc is the bridge — concrete, repeatable exercises tied to each major skill.

**Scope IN:**
- Equity quizzes (preflop hand vs. range, flop equity given outs)
- Range vs. range battles (compute the matchup, predict the EV split)
- Combinatorial counting drills (combo counting from board + range)
- Push-fold drills (see a hand + stack, decide instantly)
- Hand reading exercises (street-by-street range narrowing)
- Board texture classification drills
- Bet sizing drills (see board + range, name the size)
- ICM spots (decision under pressure)
- Mental game drills (visualization, breath work, pre-session ritual practice)
- Session-length / focus drills
- Daily / weekly / monthly drill plan templates
- Beginner / intermediate / advanced progression
- Scoring and tracking

**Scope OUT:**
- Theory itself → Docs 01–05
- Software for running drills → Doc 08

**Source list:**
- Common drill formats from training sites (GTO Wizard "Trainer," DTO Poker, Solver+)
- Custom drill construction based on Doc 1 examples
- Andrew Brokos / Carlos Welch — drill-style content from training sites
- Mental drills from Tendler / Angelo

**Required outline:**
1. Drill philosophy — why deliberate practice beats just playing
2. Drill index by skill area (with difficulty rating + time estimate)
3. Equity drills (with answer keys)
4. Combo counting drills (with answer keys)
5. Push-fold drills (with answer keys)
6. Hand reading drills (with answer keys)
7. Board texture drills
8. Bet sizing drills
9. ICM drills
10. Mental drills
11. Daily/weekly/monthly plan templates
12. Progression levels (beginner / intermediate / advanced) with recommended drill mix
13. Scoring + tracking
14. Glossary, resources, cross-refs

**Cross-refs:**
- All other docs (every drill tags back to a concept doc)
- Especially Doc 06 (review identifies leaks → drills address them)

**Coaching integration:**
The agent must be able to:
- Take a diagnosed leak and recommend 1–3 specific drills with frequency
- Walk a student through a drill in real time
- Adjust difficulty based on student level

**5 test questions:**
1. "I'm bad at counting combos. What drill should I do?"
2. "Give me a hand-reading drill for a SRP, BTN vs. BB."
3. "What's a good 30-minute daily practice routine?"
4. "I keep mis-sizing my c-bets. What drills will help?"
5. "I get nervous at the final table. Are there mental drills for that?"

**Watch-outs:**
- Drills age. Rotate. Build with a refresh cadence.
- Don't make every drill computational. Mental and routine drills matter equally.
- Difficulty progression is everything. A drill too easy is a waste; too hard is demoralizing.

---

### Doc 08 — Modern Training Resources

**Slug:** `08-modern-training-resources`
**Branch:** `doc/08-training-resources`
**Why it exists:** Doc 1 L7 closes with a 2016 list (CardRunners, 2+2 forums) that is meaningfully outdated. The training landscape is now solver tools (PioSolver, GTO Wizard, MonkerSolver), training sites (Run It Once, Upswing, Raise Your Edge, BBZ Poker), study tools (HRC, ICMIZER, Flopzilla), HUD software (PT4, HM3), and a long tail of YouTube/Twitch content. Students need a sober map.

**Scope IN:**
- Solver landscape (Pio, GTOW, Monker, Solver+, DTO) with strengths/use-cases
- Training site landscape (RIO, Upswing, RYE, BBZ, PokerCoaching)
- Study tools (HRC, ICMIZER, Flopzilla, Equilab)
- HUD/tracking software (PT4, HM3)
- Free vs. paid content
- Recommended stack by budget tier
- Recommended stack by skill level
- Recommended stack by goal (cash, MTT, satellites)
- Study time allocation guide
- Common pitfalls (over-collecting tools, under-using them)

**Scope OUT:**
- Theory → other docs
- Drills themselves → Doc 07

**Source list:**
- Direct from current product sites (verify pricing and features at time of writing)
- Practitioner reviews (specific named reviewers — link to source)
- Run a web search for "[tool name] review 2026" during Phase 1 to surface recent comparisons

**Required outline:**
1. The landscape — high-level map
2. Solver tools (with comparison table)
3. Training sites (with comparison table)
4. Study tools (with comparison table)
5. HUD/tracking
6. Free content sources (YouTube channels, podcasts, blogs — with specific names + URLs)
7. Recommended stack by budget
8. Recommended stack by skill level
9. Recommended stack by goal
10. Study time allocation
11. Common pitfalls
12. **Date stamp prominently at top of doc.** "As of [Q1 2026] — review quarterly."
13. Glossary, resources, cross-refs

**Cross-refs:**
- Doc 1, L7 (the 2016 list — link to it for historical reference)
- All other docs (tools support specific skills)

**Coaching integration:**
The agent must be able to:
- Recommend specific tools based on student goal + budget + skill level
- Be honest about tool overlap and "good enough" alternatives
- Flag when its own info may be stale ("As of [date] — verify current pricing")

**5 test questions:**
1. "I'm a beginner with $50/month to spend on poker study. What should I get?"
2. "What's the difference between PioSolver and GTO Wizard?"
3. "Do I need a HUD to win at micro stakes?"
4. "What's the best free YouTube channel for MTT learning?"
5. "I'm an MTT player — should I subscribe to RIO or Raise Your Edge?"

**Watch-outs:**
- **This doc ages fastest.** Build a review reminder into the doc itself — explicit "next review due" date.
- **Pricing and feature info is volatile.** Use language like "as of [date]" everywhere. Don't claim a tool "currently costs $X" without verifying recently.
- **Avoid affiliate-style language** even unintentionally. The agent's job is honest recommendation, not marketing.

---

### Doc 09 — Opponent Typing & Population Reads *(Proposed — operator decides)*

**Slug:** `09-opponent-typing`
**Branch:** `doc/09-opponent-typing`
**Why it exists (if approved):** Doc 1 is solo-theory. The agent currently can't give exploitative advice ("vs. the typical low-stakes nit, you should…") because it has no model of poker populations. This doc fills that gap.

**Scope IN:**
- Player taxonomy (LAG, TAG, fish, calling station, nit, maniac) with HUD-stat fingerprints
- Population tendencies by stake (micro, small, mid, high)
- Population tendencies by format (cash, MTT, SnG, satellite)
- Live vs. online population differences
- How to identify opponent type quickly (first 20 hands)
- Standard exploits per type (per street)
- When to deviate from GTO toward exploitation (and how far)
- Reciprocality (Tommy Angelo concept) — the meta-game

**Scope OUT:**
- GTO baselines → Docs 02, 03
- Mental game of opponent profiling → Doc 05

**Decision needed:** Does the operator want this? If yes, build after Doc 03 (it depends on understanding the GTO baseline to recommend deviations). If no, fold a small "exploitative deviations" subsection into Doc 03 instead.

---

## Part 4 — Build Order, Parallelization, and Sequencing

### Dependency graph

```
                 Doc 01 (DONE)
                      │
          ┌───────────┼───────────┬──────────────┐
          ▼           ▼           ▼              ▼
        Doc 02      Doc 04      Doc 05        Doc 09 (proposed)
          │           │           │              ▲
          ▼           │           │              │
        Doc 03 ───────┼───────────┼──────────────┘
          │           │           │
          └─────┬─────┴─────┬─────┘
                ▼           ▼
              Doc 06      Doc 07
                            ▲
                            │
                          Doc 08
```

**Hard dependencies** (must build B before A):
- Doc 03 depends on Doc 02 (postflop range play assumes modern preflop ranges as input)
- Doc 06 depends on Docs 02, 03, 04, 05 (review categorizes leaks into these doc areas)
- Doc 07 depends on Docs 02, 03, 04, 05 (drills reinforce these doc concepts)
- Doc 09 (if approved) depends on Doc 03 (exploits deviate from GTO baseline)

**Soft dependencies** (nice to have but not blocking):
- Doc 08 references all other docs but doesn't structurally need them done first

### Recommended build order — wave-based

**Wave 1 — Foundations (parallel-safe)**
- Doc 02 (Modern Preflop Ranges)
- Doc 04 (ICM Deep-Dive)
- Doc 05 (Mental Game)

These three have no cross-dependencies and only depend on Doc 1, which is done. They can be built in **three concurrent Claude Code sessions** if you want to compress wall-clock time. Each session runs on its own branch (`doc/02-preflop-ranges`, `doc/04-icm-deep-dive`, `doc/05-mental-game`) and merges independently to main.

> **Parallelization note:** "Concurrent" here means "operator runs three Claude Code sessions side-by-side in separate terminals." A single Claude Code session executes one doc at a time. The branches are designed to never touch the same files, so merge conflicts should only occur on the master `README.md` TOC update — handle that one merge manually after all three Wave 1 docs land.

**Wave 2 — Postflop**
- Doc 03 (Postflop Solver Concepts)

Build this after Doc 02 lands (postflop ranges in 3-bet and SRP pots reference the preflop ranges from Doc 02). Single session.

**Wave 3 — Practice infrastructure (parallel-safe)**
- Doc 06 (Hand History Review Template)
- Doc 07 (Drill Library)

These have overlapping dependencies (both need Docs 02–05 done) but don't depend on each other. Two concurrent sessions OK. They will both want to update Doc 06 ↔ Doc 07 cross-references — resolve that in the Quality Pass phase of whichever lands second.

**Wave 4 — Resources (last)**
- Doc 08 (Modern Training Resources)

Build last because it ages fastest and references the other docs. Single session.

**Optional — Wave 2.5**
- Doc 09 (Opponent Typing) if approved — slot between Wave 2 and Wave 3.

### Effort estimates per doc

| Doc | Estimated phase hours | Total |
|---|---|---|
| 02 | Sources 1h + Outline 1h + Draft 4h + Coaching 1h + QA 1h | **~8h** |
| 03 | Sources 1h + Outline 1h + Draft 5h + Coaching 1h + QA 1h | **~9h** |
| 04 | Sources 1h + Outline 1h + Draft 4h + Coaching 1h + QA 1h | **~8h** |
| 05 | Sources 1h + Outline 1h + Draft 3h + Coaching 1h + QA 1h | **~7h** |
| 06 | Sources 0.5h + Outline 1h + Draft 3h + Coaching 1h + QA 1h | **~6.5h** |
| 07 | Sources 0.5h + Outline 1h + Draft 4h + Coaching 1h + QA 1h | **~7.5h** |
| 08 | Sources 2h (lots of web research) + Outline 1h + Draft 3h + Coaching 0.5h + QA 1h | **~7.5h** |
| 09 (optional) | ~7h |

**Total:** 25–35 hours sequential. With Wave 1 + Wave 3 parallelized → ~18–22 hours wall-clock for the operator running 3 sessions in parallel during the parallel waves.

---

## Part 5 — Closing Tasks (after all docs)

When the last doc's Phase 5 is complete, run these one-time tasks on a final integration branch (`integration/final-pass`):

1. **Master README write-up** — full project overview, TOC linking every doc, quickstart for human readers, quickstart for the AI agent. Replace the bootstrap-skeleton README from Part 0.5.
2. **Cross-reference audit** — every `(Doc NN, ...)` reference resolves correctly to a real section heading. Every `→ Doc NN` forward link points to a real doc. No orphan `TODO(Doc NN)` markers remain. Use `grep -r "TODO(Doc" docs/` and `grep -r "→ Doc" docs/` to drive this — each result must verify against `docs/0N-*.md`.
3. **Glossary merge** — consolidate per-doc glossary sections into a master `glossary.md` at repo root. Each per-doc glossary section gains a top-link: `[See master glossary](../glossary.md)`. Resolve duplicate definitions; the most recent doc's definition wins, but flag any conflicts inline.
4. **Test-question consolidation** — merge `coaching-agent/test-questions/*.md` into a single `coaching-agent/agent-test-questions.md` (preserving per-doc grouping). Same for `test-answers/*.md` → `agent-test-answers.md`. Per-doc files remain in place as the source of truth.
5. **Coaching agent system prompt** — write `coaching-agent/system-prompt.md`. Composition rules: (a) Treat Doc 1 as foundational. (b) Use Docs 02–08 for current-frontier content. (c) Always cite the doc + section when sourcing a claim. (d) Honor the limits noted in each doc (esp. Doc 08's date-stamps and Doc 05's mental-health boundary). (e) Default to the workflow in Doc 1's "Hand analysis workflow" section for any hand a student brings.
6. **Acceptance test pass** — for each doc, re-read `test-answers/[NN]-test-answers.md` and verify each answer (a) draws only from the named doc + Doc 1, (b) cites specific sections, (c) demonstrates the named principle. Any failures → file as bugs against the relevant doc, fix on a hotfix branch, re-merge before final.
7. **Final commit on main** — `chore: knowledge base v1.0 complete` with a release-note commit body summarizing what's in v1 and what's planned for v2 (the Doc 09 decision, any deferred sections, etc.).

---

## Part 6 — Claude Code Kickoff Prompts

### Bootstrap kickoff (run first, exactly once)

Use this for the very first session against the empty repo:

```
You are bootstrapping the poker-knowledge-base repo.

Required capabilities check: confirm you have filesystem write, git, and the ability 
to read project knowledge / paste-in content. If any are missing, stop.

Read BUILD_PLAN.md (provided in this session). Execute Part 0.5 (Repo Bootstrap) 
exactly as specified. Do not start any doc work in this session — bootstrap commits 
and exits.

Doc 1 source content (`MIT_15_S50_Poker_Knowledge_Base.md`) will be provided as 
either project knowledge attachment or pasted text. Save it verbatim as 
`docs/01-mit-15s50-foundations.md`. Do not edit.

When Part 0.5's Definition of Done is met, commit, push, and stop.
```

### Generic per-doc kickoff prompt

Use this template when starting a new Claude Code session to build a doc. Replace `[NN]` and `[slug]`:

```
Required capabilities: filesystem, git, web_search, web_fetch.
If any are missing, stop and report which.

Read CLAUDE.md, README.md, and BUILD_PLAN.md first. Then read 
docs/01-mit-15s50-foundations.md in full — it is the conceptual foundation 
for everything you will write.

Verify Repo Bootstrap (Part 0.5 of BUILD_PLAN.md) is complete. If not, stop 
and run bootstrap first.

Check out branch `doc/[NN]-[slug]` from main (create if it doesn't exist).

Find the per-doc brief for Doc [NN] in BUILD_PLAN.md, Part 3. This is your spec.

Execute the 5 phases (Source assembly → Outline → Draft → Coaching integration → 
Quality pass) in order. Every gate is self-checkable — verify before advancing. 
Do not skip phases. Do not advance with failing gates.

After each phase, commit with `docs([NN]): phase N complete — [phase name]`.

If you get stuck on any phase after 3 attempts, stop, commit with 
`git commit -m "wip([NN]): stuck on [description]"`, and wait for human review. 
Do not paper over confusion with plausible-sounding fabrication (Standing Rule #9).

Constraints:
- Stay strictly within the Scope IN / Scope OUT for this doc (Part 3 brief).
- Conform to the house style in BUILD_PLAN.md, Part 2.
- Every claim needs a source. `[unsourced]` flags are allowed during Phase 3 drafting 
  but must all be resolved before Phase 3's gate passes.
- Do NOT update master README.md or master glossary.md — those are touched only by 
  Closing Tasks to avoid parallel-write conflicts.
- Per-doc test questions go in `coaching-agent/test-questions/[NN]-test-questions.md`. 
  Drafted answers go in `coaching-agent/test-answers/[NN]-test-answers.md`.

Start with Phase 1.
```

### Wave 1 parallel kickoff (operator-side)

To build Wave 1 in parallel: confirm bootstrap is merged to main first, then open three terminals and run the generic per-doc prompt above in each, with NN values 02, 04, and 05 respectively. Verify each session is on its own branch before letting any session run free. Because each doc writes to its own files (per-doc sources, per-doc test-questions, per-doc test-answers, the doc itself), there should be zero merge conflicts at PR time. The master README.md and master glossary.md are not touched by per-doc work — Closing Tasks handle those.

### Final integration kickoff

```
Required capabilities: filesystem, git, web_fetch (for link audit).

Read CLAUDE.md and BUILD_PLAN.md.

Verify all per-doc branches in scope have been merged to main. If any are 
outstanding, stop and report.

Check out branch `integration/final-pass` from main.

Execute Part 5 (Closing Tasks) of BUILD_PLAN.md in order. Each numbered task 
has a clear output. Do not skip.

Commit after each task with `chore(integration): [task description]`.

When all 6 tasks are complete, open a PR to main titled "Knowledge base v1.0".
```

---

## Part 7 — Standing rules for any Claude Code session

These rules apply to every session, every doc. They will also be copied into `CLAUDE.md` at repo root for redundancy.

1. **One doc per branch. One author at a time.** Never edit a sibling doc on this branch beyond resolving cross-references during Phase 5.
2. **Phase gates are non-negotiable.** Don't start Phase 3 until Phase 2's gate has been met.
3. **Sourcing discipline.** Every non-obvious claim is sourced. `[unsourced]` flags are temporary, not permanent — they must all be resolved before Phase 3's gate passes.
4. **Voice consistency.** When in doubt, re-read Doc 1's "How Will Ma teaches" section.
5. **Scope discipline.** If a topic feels relevant but is in another doc's scope, write a forward cross-ref and move on. Do not partially treat it.
6. **Handle disagreements with Doc 1 honestly.** When modern theory genuinely differs from Will Ma's framing (e.g., donk-betting in Doc 03; opening ranges in Doc 02), name the disagreement explicitly in a sub-section called something like *"Where this departs from Doc 1"*. Frame both views as right-for-their-context: Will's pedagogical model is correct for beginners building intuition; modern theory is correct for solver-prepared opponents. Don't pretend the disagreement doesn't exist, and don't claim Will was "wrong."
7. **Date-stamp anything time-sensitive.** Solver outputs, prices, tool recommendations, anything that could age. Format: `(as of [Month Year])`.
8. **Never reproduce paywalled content.** Solver outputs from paid tools (PioSolver, paid GTO Wizard tiers, paid training site videos) are proprietary. Cite the source and link to the product, but do not reproduce the actual chart/sim content. Use only freely-available equivalents.
9. **Get stuck → stop.** Three attempts, then WIP commit and wait for review. Don't paper over confusion with plausible-sounding fabrication.

---

*End of build plan v1. Update this doc as the project evolves; treat it as living infrastructure, not a one-shot spec.*
