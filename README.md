# Poker Knowledge Base

A structured, sourced curriculum for no-limit Texas Hold'em — built as both a **human-readable study guide** and the **operational knowledge source for an AI poker coaching agent**.

Grounded in MIT 15.S50 (Will Ma, 2016). Expanding into modern preflop ranges, postflop solver concepts, ICM, mental game, session review, drills, and tools.

---

## Status

| # | Doc | Scope | Status |
|---|---|---|---|
| 01 | MIT 15.S50 Foundations | Will Ma's full course synthesis — EV, levels of reasoning, preflop, postflop, ICM intro, combinatorics | ✅ Complete |
| 02 | Modern Preflop Ranges | Solver-derived opening / 3-bet / 4-bet / push-fold ranges; 2016 vs. modern deltas | ⏳ Planned |
| 03 | Postflop Solver Concepts | Range vs. range, equity realization, board textures, modern c-bet theory, blockers, overbets | ⏳ Planned |
| 04 | ICM Deep-Dive | Bubble factor, risk premium, satellites, FGS, pay-jump dynamics | ⏳ Planned |
| 05 | Mental Game & Tilt | Tendler taxonomy, A/C-game, bankroll psychology, downswing playbook | ⏳ Planned |
| 06 | Hand History Review Template | Session review workflow, leak categorization, leak-to-drill conversion | ⏳ Planned |
| 07 | Drill Library | Equity, combos, push-fold, hand reading, board texture, sizing, ICM, mental drills | ⏳ Planned |
| 08 | Modern Training Resources | Solver / training site / study tool / HUD landscape — refreshed quarterly | ⏳ Planned |
| 09 | Opponent Typing & Population Reads | Player taxonomy, population tendencies, exploit templates | 🟡 Proposed |

All planned work is specified in [BUILD_PLAN.md](./BUILD_PLAN.md).

---

## Why this exists

Most poker study material sits in one of two failure modes. The free end is scattered YouTube videos and forum threads with no continuity — every concept gets explained from scratch, poorly, by someone new. The paid end is solver output dressed up as instruction, with heavy copyright and no pedagogical frame. Both are hard to learn from.

This knowledge base is different in two ways. First, it's structured: each doc has a coaching guide up front, a key-takeaways block per section, detailed reasoning underneath, concrete hand examples, and a quick-reference cheat sheet at the end. Same anatomy every time. Second, it's dual-purpose: every doc is written so a human student *and* a Claude-based coaching agent can both use it — the human reads prose, the agent reads the named principles and anti-pattern tables.

Doc 1 is the foundation — a full synthesis of Will Ma's MIT course. Every other doc extends it. When modern theory genuinely disagrees with Will's 2016 framing, the doc names the disagreement explicitly in a *"Where this departs from Doc 1"* subsection. We don't pretend Will was wrong, and we don't pretend the frontier hasn't moved.

---

## For human readers

Read the docs in `docs/` in order, or jump to whatever matches your weakest area.

**Start here:** [`docs/01-mit-15s50-foundations.md`](./docs/01-mit-15s50-foundations.md). The *Mental Framework* and *Hand Analysis Workflow* sections at the top are the single highest-leverage pages in the whole KB. Read those carefully before anything else.

**Then:** pick based on what's slowing you down.
- Preflop feels fuzzy → Doc 02
- You get it in bad postflop → Doc 03
- You bust at final tables → Doc 04
- You tilt / you play when you shouldn't → Doc 05
- You want to actually improve from sessions, not just play → Doc 06 + Doc 07
- You don't know which tool to buy → Doc 08

**When you're ready to practice:** pair Doc 06 (Review Template) with Doc 07 (Drill Library). Review a session, identify a leak, run the matching drill. That's the improvement loop.

---

## For the coaching agent

The composed system prompt will live in [`coaching-agent/system-prompt.md`](./coaching-agent/system-prompt.md) once Closing Tasks run. Per-doc test questions and drafted answers live in `coaching-agent/test-questions/` and `coaching-agent/test-answers/` as each doc lands.

Agent operational defaults (details in each doc's front-matter):

- **Treat Doc 1 as foundational.** For any hand a student brings, default to the 7-step hand analysis workflow in Doc 1.
- **Always think in ranges, never a single hand.** The Level-1 → Level-2 upgrade is the single highest-value habit.
- **Separate decisions from results.** If a student says "I called and lost, was it wrong?" — evaluate the decision given available information first.
- **Cite sources.** Every recommendation links back to a specific doc section.
- **Honor limits.** Doc 08 ages fast (date stamps). Doc 05 has a mental-health boundary. Solver content is cited, not reproduced.

---

## Project structure

```
poker-knowledge-base/
├── README.md                  this file
├── BUILD_PLAN.md              master build plan — single source of truth for unfinished work
├── CLAUDE.md                  standing rules for any Claude Code session in this repo
├── .gitignore
├── docs/                      the KB documents
│   ├── 01-mit-15s50-foundations.md
│   └── 02..08 (planned)
├── sources/                   per-doc annotated bibliographies
├── coaching-agent/            agent system prompt + acceptance tests
│   ├── system-prompt.md       (built by Closing Tasks)
│   ├── test-questions/
│   └── test-answers/
└── plans/                     scratch (gitignored)
```

---

## Building the rest

All unfinished work is specified in [BUILD_PLAN.md](./BUILD_PLAN.md). It contains:

- Per-doc briefs (scope IN/OUT, required outline, source list, coaching integration, acceptance-test questions, watch-outs) for Docs 02 through 08 (+09 proposed)
- Five-phase workflow (Source assembly → Outline → Draft → Coaching integration → Quality pass) with self-checkable gates
- Wave-based build order with parallelization safety
- Claude Code kickoff prompts
- Closing tasks (cross-ref audit, glossary merge, acceptance-test pass, master README + system prompt write-up)

If you are picking this up cold, read `BUILD_PLAN.md` in full before touching anything.

---

## Standing principles

The full rules live in [CLAUDE.md](./CLAUDE.md). Highlights:

1. **Dual-purpose design.** Every doc serves both human readers and the coaching agent.
2. **Every non-obvious claim is sourced.** Unsupported assertions are bugs.
3. **Honor Doc 1 as the conceptual foundation.** Disagreements named explicitly and framed as right-for-their-context, not as corrections.
4. **Judge decisions, not results.** The anti-results-oriented frame is the cultural throughline of the whole project.
5. **Honest uncertainty over manufactured confidence.** When the answer is "it depends" or "no one really knows," say so.
6. **Never reproduce paywalled solver outputs.** Cite and link; use freely-available equivalents.
7. **Date-stamp anything time-sensitive.**

---

## Sources & provenance

**Doc 1** is a structured synthesis of [MIT OpenCourseWare 15.S50 — *How to Win at Texas Hold'em Poker* (January IAP 2016)](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/), taught by Will Ma. Source materials are CC BY-NC-SA 4.0.

Subsequent docs draw from solver outputs (GTO Wizard free tier, Holdem Resources Calculator, ICMIZER), training-site free content (Run It Once, Upswing Poker, Raise Your Edge, BBZ Poker), and canonical books (Tendler, Angelo, Brokos, Acevedo, Chen & Ankenman, Sklansky/Miller/Malmuth, Harrington). Per-doc annotated bibliographies live in `sources/`.

---

## License

Synthesis work in this repo is released under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) to match the Doc 1 source license. Original quotes from Will Ma, published books, and solver output are the property of their respective authors and are cited, not reproduced.

---

## Acknowledgments

Will Ma (MIT 15.S50 instructor, 2016 IAP) — primary source for Doc 1. Jennifer Shahade and Bill Chen (guest lecturers for Lectures 5 and 8 — unrecorded but referenced). The broader poker study community whose public writing, streaming, and analysis make a sourced curriculum like this possible.
