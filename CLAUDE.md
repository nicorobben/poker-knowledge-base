# CLAUDE.md — Standing instructions for any Claude Code session

This file is for Claude Code sessions working in this repo. Read it at the start of every session.

**All build instructions live in [BUILD_PLAN.md](./BUILD_PLAN.md). Read it in full before doing anything.**

---

## Per-session kickoff checklist

Before starting any doc work:

1. Read this file (CLAUDE.md).
2. Read [README.md](./README.md) for current repo status.
3. Read [BUILD_PLAN.md](./BUILD_PLAN.md) in full.
4. Read [`docs/01-mit-15s50-foundations.md`](./docs/01-mit-15s50-foundations.md) — it is the conceptual foundation for everything else.
5. Find the per-doc brief for your assigned doc in BUILD_PLAN.md Part 3.
6. Check out the correct branch per the naming convention (`doc/NN-slug`), creating from `main` if it doesn't exist.
7. Confirm `git status` is clean.
8. Begin Phase 1.

---

## Standing rules (non-negotiable)

1. **One doc per branch. One author at a time.** Never edit a sibling doc on this branch beyond resolving cross-references during Phase 5.
2. **Phase gates are non-negotiable.** Don't start Phase 3 until Phase 2's gate has been met. Every gate in BUILD_PLAN.md Part 3 is self-checkable — verify before advancing.
3. **Sourcing discipline.** Every non-obvious claim is sourced. `[unsourced]` flags are temporary; they must all be resolved before Phase 3's gate passes.
4. **Voice consistency.** When in doubt, re-read Doc 1's *"How Will Ma teaches"* section. Concrete first, principle second. Math-grounded. Honest uncertainty. Direct — cut filler.
5. **Scope discipline.** If a topic feels relevant but belongs to another doc, write a forward cross-ref and move on. Do not partially treat it.
6. **Handle disagreements with Doc 1 honestly.** When modern theory genuinely differs from Will Ma's 2016 framing (e.g., donk-betting in Doc 03; opening ranges in Doc 02), name the disagreement explicitly in a subsection called *"Where this departs from Doc 1."* Frame both views as right-for-their-context: Will's pedagogical model is correct for beginners building intuition; modern theory is correct for solver-prepared opponents. Don't pretend the disagreement doesn't exist, and don't claim Will was "wrong."
7. **Date-stamp anything time-sensitive.** Solver outputs, prices, tool recommendations — anything that could age. Format: `(as of [Month Year])`.
8. **Never reproduce paywalled content.** Solver outputs from paid tools (PioSolver, paid GTO Wizard tiers, paid training site videos) are proprietary. Cite and link, but do not reproduce the charts or sim content. Use only freely-available equivalents.
9. **Get stuck → stop.** Three attempts, then WIP commit (`git commit -m "wip(NN): stuck on [description]"`) and wait for human review. Do not paper over confusion with plausible-sounding fabrication.

---

## Commit conventions

[Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/). Scope = doc number.

- Phase completion: `docs(NN): phase N complete — [phase name]`
- Regular work: `docs(NN): [description]`
- Work in progress (stuck): `wip(NN): stuck on [description]`
- Bootstrap: `chore: [description]`
- Closing tasks / integration: `chore(integration): [description]`
- Hotfix after merge: `fix(NN): [description]`

One phase = one commit at minimum. More-granular commits within a phase are fine.

---

## File ownership — what not to touch

- **Sibling docs.** One branch, one doc. You can *read* sibling docs for cross-ref context; you cannot edit them.
- **Master README.md TOC / status table.** Updated only by Closing Tasks (BUILD_PLAN.md Part 5). Don't change the status of docs other than your own.
- **Master `glossary.md`** (at repo root, built in Closing Tasks). Per-doc glossaries go in the doc itself. The master is composed only at the end.
- **BUILD_PLAN.md.** Treat as read-only unless you are explicitly updating the plan itself (rare — gets its own branch/commit).

---

## Per-doc files YOU own (for doc NN)

When building Doc NN you create and edit:

- `docs/NN-[slug].md` — the doc itself
- `sources/NN-sources.md` — annotated bibliography
- `coaching-agent/test-questions/NN-test-questions.md` — acceptance-test questions
- `coaching-agent/test-answers/NN-test-answers.md` — drafted answers for self-check

These paths are designed so multiple Claude Code sessions working on different docs in parallel (Wave 1, Wave 3 in BUILD_PLAN.md) never touch the same files.

---

*End of standing rules. Specifics of what to build for each doc live in BUILD_PLAN.md.*
