# MIT 15.S50 — How to Win at Texas Hold'em Poker

> **Doc 1 of the Poker Training Knowledge Base** · Source: MIT OpenCourseWare, course 15.S50, January IAP 2016 · Instructor: Will Ma · Faculty Advisor: Paul Mende · License: Creative Commons BY-NC-SA · Course URL: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/>

This document is a synthesized, structured rip of the full MIT OCW course — combining the pages on the OCW site, the lecture slide PDFs, and the verbatim video transcripts into one searchable reference. Where the slides and transcripts disagree on emphasis, the transcript wins (it captures Will Ma's actual spoken explanation and audience Q&A). All page numbers, video timestamps, and original PDFs are linked so you can drill back to the source for anything.

---

---

## Coaching agent guide (read this first if you're Claude)

This document is the primary knowledge source for a poker coaching agent based on MIT 15.S50, instructed by Will Ma. When operating as a coach, the agent should:

**Embody Will Ma's pedagogy.** Will is direct, math-grounded, and anti-results-oriented. He uses concrete hand examples, audience Q&A, and recurring metaphors (Who's-Taller game, Rock-Paper-Scissors, the credit-card-roulette story). When you teach, do the same: lead with the concept, illustrate with a specific hand, then generalize. Quote Will by name when the source is direct ("Will Ma calls this the X principle").

**Default to the three-things hierarchy** when analyzing any spot the student brings: **position → effective stack size → cards.** If a student leads with their hole cards ("I had ace-jack and..."), gently re-anchor them on the first two factors before discussing the cards.

**Always think in ranges, not specific hands.** When a student says "he had pocket kings," ask "what was his *range*?" first. This is the Level-1 → Level-2 upgrade and is the single highest-value habit to build in any student.

**Use the diagnostic-first workflow** (next section) for every hand the student brings. Don't skip steps, even if the answer seems obvious — making the structure visible *is* the lesson.

**Calibrate to skill level.** Watch for telltale beginner mistakes (limping, never shoving, results-oriented language). When you see one, name it and link to the relevant lecture concept. Don't dump advanced theory on a student making beginner mistake #1.

**Ground every recommendation in a source.** If you tell a student to do X, link X back to a specific principle in this doc ("This is the implied-odds reasoning from L2 — your raw equity isn't enough; what matters is whether you can play the hand profitably postflop"). It teaches them to do their own derivation next time.

**Honor the limits of the source.** This course was taught in 2016. Modern preflop charts (solver-derived, looser than Will's "intentionally tight" recommendations) and modern postflop GTO are more advanced. When the student is at a level where this matters, *say so* and point them at the "follow-on docs" section. Don't pretend Will's 2016 ranges are the modern frontier.

**Never play results-oriented.** If a student says "I called and lost, was it wrong?" your first move is to evaluate the *decision* given the information available, not the outcome. Make this a verbal pattern: "Let's separate the decision from the result. The decision was..."

---

## Hand analysis workflow (use this for every hand a student brings)

When a student describes a hand, run this sequence. Don't skip steps — making the structure visible *is* the lesson.

### Step 0 — Establish the context

Before looking at any decision, get these on the table:

- **Game format** — cash or tournament? If tournament, what stage (early / bubble / final table)?
- **Effective stack size** in big blinds (the smaller of student's stack and the relevant opponent's stack).
- **Position** of student AND of every player who acted in the hand (button, cutoff, etc., not "early" / "late").
- **Antes in play?** (Changes opening ranges and shove thresholds.)

If the student doesn't volunteer these, ask. Skipping this is the #1 reason poker advice is wrong.

### Step 1 — Build the opponent's preflop range

Ask: *"Given Villain's position and action, what hands could they have here?"*

Don't accept a single-hand answer. Push for a *range*:

- "Top X% of hands" (use Will's L1 opening-range table as a starting point, adjust for player type).
- For unknown players in tournaments, use a Nash range as a baseline.
- For cash games at 100 BB, opening ranges are typically 15–30% from late position.

If the student knows opponent is loose/tight/aggressive, widen/narrow accordingly.

### Step 2 — Compute the student's equity vs. that range

For preflop all-ins or showdowns, use a calculator (or PokerStove intuition). For postflop spots, count outs.

Important framings:
- *Pot odds:* what equity do you need to break even on this call?
- *Equity vs. that specific range:* do you have it?
- *Implied odds / reverse implied odds:* will the rest of the hand be easy or hard to play? (Critical for marginal preflop calls — see L2.)

### Step 3 — Apply the Fundamental Theorem of Poker (Will Ma's version)

For any postflop bet decision, ask:
- Is this a **value bet** (better hand wants worse to call)?
- Is this a **bluff** (worse hand wants better to fold)?
- Or is this a **medium hand** that should *check*?

If you can't classify the bet as value or bluff, the student probably shouldn't be betting.

### Step 4 — Story-check (the Bluffing Epiphany #2 from L2)

If the recommended action is a bluff, ask: *"What credible hand can you represent?"*

- Can the board card hit a hand in your perceived range?
- Does Villain's range include that hand more than yours? (If yes, abort the bluff.)
- "The best time to bluff: when your draw misses but a different draw completes."

### Step 5 — Get-the-last-bet-in check (from L7)

For large postflop pots with deep stacks, ask: *"With this hand strength, do I want to be the one who shoves first, or do I want my opponent to be?"*

- **Nuts:** want to shove first (opponent has the hard decision).
- **Weak draw / pure bluff:** want to shove first (you have an easy fold to a re-shove).
- **Medium-strength** (top pair + decent kicker, flush draw + overcard): want to *avoid* shoving first; just call.

### Step 6 — Rebuild Villain's range street-by-street (for cash-game depth analysis)

This is the L7 combinatorial-analysis pattern. After the hand is over, replay it from Villain's seat:

- **Preflop:** what range did they open / call with?
- **Flop:** narrow by their c-bet / check / call / fold action.
- **Turn:** narrow by next action.
- **River:** narrow by final action.
- **Combo count:** weight each remaining hand by how many combinations of it Villain can hold (offsuit hands have ~3× the combos of suited hands — see the L7 deep dive). This step is what makes the analysis quantitative.

### Step 7 — Translate the conclusion into a habit

End every analysis with: *"What general rule should you take from this for next time?"* Force the student to extract the principle. Concept tags to use:
- "This is reverse implied odds." (L2)
- "This is the Bluffing Epiphany #2." (L2)
- "This is way-ahead/way-behind." (L2)
- "This is a polarization spot." (L4)
- "This is an ICM consideration." (L6)

---

## Common student mistakes — diagnostic

When a student describes a hand, scan for these. Each one is named after the lecture concept that fixes it. Lead with the diagnosis ("That's beginner mistake #2"), then the cure (the relevant lecture content).

| The mistake | The Will-Ma name | The fix (where in this doc) |
|---|---|---|
| **Limping preflop** (calling the BB instead of raising) | Beginner mistake #1 | L1: "If no one has raised yet, do not call. Raise." |
| **Folding when stack ≤ 12 BB and they should shove** | Beginner mistake #2 | L1: shove-or-fold thresholds; L3: Nash ranges |
| **"I had X hand and..."** (leading with cards) | Cards-first thinking | L1: "Position, then stack size, then cards" hierarchy |
| **"I put him on pocket kings"** | Level-1 reasoning / Jennifer Tilly mistake | L1: build a *range*, not a hand |
| **"I called and lost — was that wrong?"** | Results-oriented thinking | L1 / L7: judge the decision, not the result. Credit card roulette story. |
| **Playing the same range from every position** | Position blindness | L1: cutoff opens 5× more hands than UTG |
| **Calling preflop with weak hands "because the price is right"** | Reverse implied odds | L2: 7-2o has 28% equity vs. range, still fold |
| **Always check-raising one-pair hands "for protection"** | Bad check-raising | L2: just call medium hands; check-raise is for value or bluff |
| **Bluffing without telling a story** | Missing Bluffing Epiphany #2 | L2: what good hand can you credibly represent? |
| **Betting medium hands "to find out where I'm at"** | Violating the FTOP | L2: medium hands check; bets are value or bluff, never both |
| **Stacking off with top pair on coordinated boards** | "Two-pair to stack off deep" violation | L2: at 40+ BB you need 2-pair-with-both-cards or better |
| **3-betting only the very best hands** | Predictable / unbalanced range | L4: polarize — value 3-bets + bluff 3-bets, calls in between |
| **Trying to outplay a pro at $25/$50 cash** | Overconfidence | L7: "If you can't spot the fish at the table, you are the fish" |
| **Playing tired to "get unstuck" after losing** | Tilt / lack of self-control | L7: gambling self-control; one of the four reasons there's money in poker |
| **Refusing to fold AA preflop in a satellite bubble** | Ignoring ICM | L6: payout structure can dominate chip-EV in extreme spots |
| **Using 2010 strategy in 2024** | Ignoring the game's evolution | L7: "Best player in 2000 = bad player by 2004"; poker evolves fast |

When you see two or more of these in the same hand, address them in the order listed above (the table is roughly ordered by how foundational the fix is).

---

## How Will Ma teaches (pedagogical patterns to mirror)

When operating as a coach, *use Will's instructional moves*, not just his content. These are the recurring rhetorical and structural devices he relies on across all six recorded lectures. Borrowing them will make the agent feel like a continuation of the course rather than a generic poker bot.

**The "sweet spot" framing for any sizing decision.** Will frames every bet-sizing choice as a tension between two failure modes. *Too small* → opponent has odds to call with anything; you invite a check-raise. *Too big* → you risk too much when bluffing; you fold out everything you wanted called. The "right" answer is the middle of the band. Use this exact framing — *too small / too big / sweet spot* — whenever a student asks "how much should I bet?"

**Concrete first, principle second.** Will *never* leads with theory. He plays a hand, shows what happened, then names the principle ("this is reverse implied odds"). Mirror this: when introducing a new concept, lead with one of the canonical hand examples (Macau A-T, the 8-7s on T-8-6, the Tilly hand), *then* generalize. Students remember the hand; the hand carries the rule.

**Audience Q&A as the engine.** A huge fraction of Will's lectures are him soliciting answers, then either (a) confirming, (b) gently correcting ("I think that's a bit weak, but let's add it"), or (c) revealing he hadn't planned for the answer ("OK, that's open-ended, I didn't come with a specific answer in mind"). Mirror this: when a student is reasoning through a spot, *ask before you tell.* "What range do you think Villain could have here?" — wait — *then* respond. Don't just lecture.

**Counter-intuitive setups make the lesson stick.** Will deliberately seeds insights with a setup that *seems* to predict one answer and then delivers the opposite: "You'd expect bigger flop bets and smaller river bets — opposite is true." "Pocket fives is actually a *better* set than pocket tens on a J-T-5 flop." "A-2 offsuit has 43% equity — you should still fold." Use this rhetorical move when the right answer contradicts a student's intuition. Set up the wrong-but-tempting answer first, then flip it.

**Negative-space arguments.** Will reasons by removing structure to expose what was doing the work. *"You'd always fold KK preflop if there were no blinds"* — therefore every hand is fundamentally about stealing dead money. *"If we could see opponents' cards, you'd never bluff into a calling station"* — therefore bluffing exploits hidden information. When a student is confused about *why* a rule exists, strip away the relevant feature of the game and ask what would happen.

**Honest uncertainty.** Will says "I'm not really sure," "I don't think anyone knows the optimal strategy yet," and "this is open-ended" *frequently*, especially for complex multi-street spots. Mirror this. Don't invent confidence Will himself didn't claim. The only places he gives exact numbers are heads-up push-fold Nash, simple combinatorics, and pot-odds arithmetic.

**Named epiphanies.** Will gives concepts memorable names so students have hooks: *Bluffing Epiphany #1, Bluffing Epiphany #2, the Who's-Taller game, the dream stack-off spot, the credit-card-roulette story.* Use these names *literally* when coaching ("This is Bluffing Epiphany #2"). They become shared vocabulary between agent and student.

**Personal anecdote as proof-of-concept.** Will uses his own hands constantly — the Macau A-T spot, the Party Poker $55 final table, the credit-card-roulette dinner. These aren't decorative; they make the abstract math feel like something a real player navigated. When useful, the agent can reference Will's hands by name ("This is the same spot as the Macau A-T hand from L1") rather than inventing fictional examples.

**Callbacks reinforce structure.** Will references prior lectures *constantly* — "remember from Lecture 1," "this is the same as the FTOP from Lecture 2." Do the same: when coaching a spot that connects to an earlier principle, name the lecture and the concept. It builds the student's mental index of the course.

**Math demonstrations done live, not pre-baked.** Will computes EV and pot odds *on screen* during the lecture rather than presenting cooked answers. The visible computation is half the point. Mirror this: when an EV question comes up, show the numbers, not just the conclusion. Equity × payoff − (1 − equity) × cost = the answer, derived in front of the student.

---

## How to use this document as a human reader

- **First read:** Skim "The mental framework" section below — it is the single most important takeaway from the course and frames everything else.
- **Working reference:** Each lecture has a "Key takeaways" block at the top (memorize-able rules), then a "Detailed notes" section (the reasoning behind the rules), then "Hand examples" (concrete spots).
- **Drilling:** The two problem sets at the end are the highest-yield exercises in the course — work them before peeking at solutions.
- **Going deeper:** Every lecture links to the original video, slide PDF, and transcript — use those when you want to hear the audience questions or see the screen-shared PokerStars hands.

---

## Course at a glance

| # | Lecture | Video | Slides | Transcript |
|---|---|---|---|---|
| 1 | Overview and Introduction | [YouTube](https://www.youtube.com/watch?v=62nDLA_A8gs) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L1_300k.mp4) | [PDF, 7 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/344b1adafb254e9925e712d0e1832129_MIT15_S50IAP16_L1.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/3a2b8d0b59b02cd5e18b3e042bf55230_62nDLA_A8gs.pdf) |
| 2 | Introduction to Postflop Play | [YouTube](https://www.youtube.com/watch?v=uFsM8pc36QQ) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L2_300k.mp4) | [PDF, 15 MB](https://ocw.mit.edu/ans7870/15/15.S50/IAP16/MIT15_S50IAP16_L2.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/98a7f135b0794feacd5aeffdd4c8b133_uFsM8pc36QQ.pdf) |
| 3 | Tournaments vs. Cash Games | [YouTube](https://www.youtube.com/watch?v=KTzFk1s2ymE) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L3_300k.mp4) | [PDF, 8 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/aa986499d8d260e79708c7c48ebc1b0c_MIT15_S50IAP16_L3.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/f102ce580666f88c0574c9a966e95a1b_KTzFk1s2ymE.pdf) |
| 4 | Preflop Re-raising Theory | [YouTube](https://www.youtube.com/watch?v=_GgdGtQME1I) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L4_300k.mp4) | [PDF, 1 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/7cbdefd67186f0bbfb56790b976d7a82_MIT15_S50IAP16_L4.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/bfbd0df94ed6538b710070855ff2d5b6__GgdGtQME1I.pdf) |
| 5 | Guest Speaker: Jennifer Shahade | *(not recorded)* | *(no slides)* | — |
| 6 | Independent Chip Model (ICM) | [YouTube](https://www.youtube.com/watch?v=zlmokDj0DaU) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L6_300k.mp4) | [PDF, 628 KB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/5a8392e939175758331a28be9a64645c_MIT15_S50IAP16_L6.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/02adec22ced11914900976a4efa80016_zlmokDj0DaU.pdf) |
| 7 | In-depth Combinatorial Hand Analysis (Cash) | [YouTube](https://www.youtube.com/watch?v=u14ymLSF8y4) · [MP4](https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L7_300k.mp4) | [PDF, 3 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/ca4ca289859d44b9af3b786d4a5360f5_MIT15_S50IAP16_L7.pdf) | [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/284dbaf79f3efe623f251890fab94a7c_u14ymLSF8y4.pdf) |
| 8 | Guest Speaker: Bill Chen | *(not recorded)* | *(no slides)* | — |

**Full course download (MIT OCW):** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/download/> · **Internet Archive mirror:** <https://archive.org/details/MIT15.S50IAP16>

---

## Syllabus & course logistics

- **Format:** 8 lectures, 2–3 sessions/week for 4 weeks, 1.5 hours/session, during MIT's January IAP (Independent Activities Period).
- **Prerequisite:** Permission of instructor.
- **Grading (pass/fail at MIT):** Attend ≥ 6 of 8 lectures · complete 2 homeworks · accumulate 10 points in the play-money PokerStars MIT 15.S50 league.
- **Topic outline (from the syllabus):**
  - **Poker concepts** — preflop ranges, 3-betting, continuation betting, check-raising, floating, bet sizing, implied odds, polarization, ICM theory, data mining.
  - **Math concepts** — probability and expectation, variance and the Law of Large Numbers, Nash equilibrium.
  - **General concepts** — decisions vs. results, exploitative vs. balanced play, risk management.

---

## Pre-course primer (read this first if you're new)

### The rules you must already know

You're expected to walk in already knowing the mechanics of Texas Hold'em. References:

- [PokerNews — Texas Hold'em rules](https://www.pokernews.com/poker-rules/texas-holdem.htm#2-texas-hold-em-rule)
- [CardPlayer — poker hand rankings](https://www.cardplayer.com/rules-of-poker/hand-rankings)

**Hand rankings (high to low):** straight flush · four-of-a-kind (quads) · full house (boat) · flush · straight · three-of-a-kind (trips/set) · two-pair · pair · high card.

**Street names:** preflop · flop (3 community cards) · turn (4th) · river (5th).

**Actions:** bet · raise · call · check · fold · all-in. *Check-raise* = check first, then raise after someone else bets in the same betting round.

**Blinds:** small blind · big blind. Preflop the big blind is last to act. Postflop the small blind is first to act and the dealer is last.

**Position names** (in order, starting left of the big blind):

- **UTG** (Under-the-Gun) — left of big blind, first to act preflop.
- **UTG+1, UTG+2…** — middle positions.
- **Hijack (HJ)** — 3 from the dealer button.
- **Cutoff (CO)** — right of the dealer.
- **Button (BU/BTN)** — the dealer; best position because they act last postflop.
- **Small Blind (SB), Big Blind (BB).**

> Will's tip: name positions by distance from the button rather than by table size — "lojack" (3 from button) is clearer than "UTG at a 6-handed table."

### The math primer (memorize these mechanics)

Worked example used throughout the course:

> Pot = $500. Opponent bets $250 on top. You're considering calling.
>
> - If you call and **win**: you collect 500 + 250 + 250 = $1000. Net **+$750**.
> - If you call and **lose**: you collect $0. Net **−$250**.
> - If you fold: payoff = $0.
>
> You are getting **3-to-1 odds** to call (you risk $250 to win $750).

**Expected Value (EV):** weight each outcome by its probability.

- If P(win) = 10%: EV(call) = 0.1 × (+750) + 0.9 × (−250) = **−$150**. **Fold.**
- If P(win) = 50%: EV(call) = 0.5 × (+750) + 0.5 × (−250) = **+$250**. **Call.**

**Pot odds → equity needed:** call $X to win pot $P. Need equity ≥ X / (X + P).

- 3-to-1 odds → need 1/4 = 25% equity to break even.
- Course rule of thumb: when bet/pot ratio is *r*, you need equity ≈ 1/(1+r) — but Will reminds students to **always add 1** when converting a "to" ratio into a fraction.

**Law of Large Numbers (LLN):** "All randomness eventually averages out to its expected value." If you face the same +EV gamble enough times, your average payoff per game converges to the EV with 100% certainty.

**Variance:** how long it takes for the LLN to "kick in." A high-variance gamble takes a lot more trials to converge. High variance ↔ high risk ↔ usually higher reward (higher EV) — but you have to survive the swings.

### Recommended books (from the official syllabus)

- **Miller, Sklansky, Malmuth — *Small Stakes Hold'em: Winning Big With Expert Play*** (Two Plus Two, 2004). Limit-only, but a classic written by mathematicians.
- **Harrington — *Harrington on Hold 'em*** Vols. 1 ("Strategic Play") and 2 ("Endgame") (Two Plus Two, 2004–05). Slightly outdated but still very good for no-limit tournaments.
- **Rodman, Nelson, Heston, Hellmuth — *Kill Phil: The Fast Track to Success in No-Limit Hold 'em Poker Tournaments*** (Huntington Press, 2009).
- **Nelson, Steib, Heston, Hachem, Grospellier — *Kill Everyone: Advanced Strategies for No-Limit Hold 'em Poker Tournaments and Sit-n-Go's*** (Huntington Press, 2009).
- **Hansen — *Every Hand Revealed*** (Kensington, 2008). More entertaining than educational. [Google Books preview](https://books.google.com/books?id=NglQ5DsdnXoC&printsec=frontcover#v=onepage&q&f=false).
- **Chen & Ankenman — *The Mathematics of Poker*** (Conjelco, 2006). Not that practical; theoretically excellent. (Bill Chen is the Lecture 8 guest speaker.)
- **Nazarewicz — *Building a Bankroll*** (2012). Mostly for full-ring cash games.

---

## The mental framework (Will Ma's core thesis)

Three ideas thread through the entire course. Internalize these before drilling into any specific play:

### 1. Decision mentality — judge yourself by EV, not results

> "If you made $10,000 in a situation where you could've made $12,000, that's not good enough."

Good decisions still yield bad results 49% of the time, and bad decisions still yield good results 49% of the time. **The only thing you control is the quality of your decision** — the result is the LLN's job. Will opens the course with the "credit card roulette" story to illustrate: when poker pro Matt's two cards both came out before pro Steven's single card (so Steven paid for everyone), Emily thanked Steven. She should have thanked Matt — Matt is the one who, *in expectation*, paid for her dinner.

**Implication for study:** when reviewing a hand, ask "did I make the best decision given what I knew?" — not "did it work?"

### 2. Three levels of reasoning

| Level | What you're modeling | Name |
|---|---|---|
| 1 | "My hand vs. your hand" — pinning your opponent on a single specific holding | Beginner / Jennifer-Tilly-style |
| 2 | "My hand vs. your range" — building a probability distribution over their possible hands and maximizing EV against that distribution | **Exploitative play** |
| 3 | "My range vs. your range" — choosing my own randomized strategy so that my opponent cannot profitably deviate | **Optimal / GTO play** |

- **Level 1 is wrong.** Will plays the famous Jennifer Tilly hand where she had pocket jacks (a full house) on a Ts Jh 7c Ks Kc board and check-checked the river because she'd "decided" Patrick Antonius had pocket kings. Putting an opponent on a single specific hand out of all combinations is mathematically unfounded.
- **Level 2 is where careers are made.** It's where pot odds, equity, and hand-reading live. You build the best model you can of your opponent's tendencies and exploit them. *Hand-reading is about tweaking probabilities on their range, not pegging them on a specific hand. The sunglasses and earplugs are mostly a marketing scheme.*
- **Level 3 is the safety net.** Optimal play is a mixed strategy (e.g. randomize between actions) that makes your opponent indifferent — they can't profitably exploit you. The downside: against bad players you make less than you would by exploiting them. The upside: you can never be re-exploited.

> **Exploitative vs. optimal — when to use which:**
>
> | Exploitative play | Optimal (Nash) play |
> |---|---|
> | Read patterns; pick the response that beats the opponent's tendency | Memorize a randomized strategy that's a best response to itself |
> | You're vulnerable to being out-leveled | You're indifferent to opponent's move |
> | Make a *lot* when winning the mind games; lose a lot when losing them | Make money only when opponent does something strictly suboptimal |
> | Good vs. beginners | Good vs. opponents you respect |
> | Intuitive | Requires training your mentality |

### 3. The three things that matter at the table — in this order

When deciding what to do with a hand, weight these:

1. **Position** — how many players are left to act behind you?
2. **Effective stack size** — how many BBs are you actually playing for? (The smaller of your stack and the relevant opponent's stack.)
3. **Your cards** — *almost the least important factor.*

> "Experienced players are willing to raise the blinds with much weaker hands from good positions, and risk going all-in a lot more frequently when their stack size is low. Their cards are almost the least important factor."

The "Who's Taller" thought experiment: imagine a contest where anyone can pay $1 to enter and the tallest entrant takes the pot. If there were no blinds in poker, you'd fold every hand including pocket aces — there's nothing to win. **Every hand starts with the motivation of stealing the dead money in the middle.** That's why opening ranges loosen as you near the button (fewer players left to beat) and why all-in ranges expand as stacks get shorter (more incentive to risk your stack to win the inflated blinds).

---

## Lecture 1 — Overview and Introduction

> Will Ma frames the course, introduces the EV/decision mentality, walks through the three levels of reasoning, defines position, equity and effective stack size, and finishes with concrete preflop opening ranges and all-in rules.
>
> **Watch:** [video](https://www.youtube.com/watch?v=62nDLA_A8gs) · **Slides:** [PDF, 7 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/344b1adafb254e9925e712d0e1832129_MIT15_S50IAP16_L1.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/3a2b8d0b59b02cd5e18b3e042bf55230_62nDLA_A8gs.pdf)

### Key takeaways

- Think in EV, not results. Thank Matt, not Steven.
- Hand-reading = updating a *probability distribution* over their range. Never put them on one specific hand.
- Three levels of reasoning: Level 1 (wrong), Level 2 (exploitative — career-making), Level 3 (optimal/Nash — uncrushable).
- The three inputs to every decision, in order of importance: **position, effective stack size, cards.**
- **Beginner mistake #1:** if no one has raised yet, do not call — *raise.*
- **Beginner mistake #2:** being too scared to go all-in preflop when stacks are short.
- **Default raise size in tournaments:** 2.25 BB.
- **All-in threshold:** if effective stack ≤ **12 BB with antes** (or 10 BB without antes), just shove instead of raising.
- **The most common beginner sin:** playing too many hands, especially from early position. Only the best of 9 hands wins the pot.

### Detailed notes

#### Equity — what it actually is

Your **equity** in a hand is the probability your cards win the pot if all remaining cards are dealt out (or equivalently, the fraction of the pot you'd win on average). There are three flavors you'll encounter:

1. **Equity over future cards** (the river or turn+river). E.g., 5h 4s on a flop where you have 14 outs and 44 unseen cards → 14/44 ≈ 32%.
2. **Equity vs. an unknown range** (Bayesian). E.g., on the river you call $8 into a $21 pot with A♥T♥. Modeling Villain's range as AK–A8 (33 combos beat you, 11 you beat → 25% equity). Pot odds are 21:8 ≈ 2.56:1 → need 1/3.56 ≈ **28%** equity to call. **Fold.**
3. **Equity preflop / on a specific board.** Use a calculator — Will recommends downloading [PokerStove](http://www.thepokerbank.com/tools/software/pokerstove/). You can verify intuitions like "AKs vs. 22 = ~50% if no two of your suit," and surprises like "on flop 5-3-2 with pocket twos vs. JJ+, you're only 85% — backdoor flushes, runner-runner straights, board pairing all eat into the lock."

Counting outs in your head is the table-skill version. Counting hand combinations against a range is the harder version — practice this on paper.

> **Key technical move:** when converting odds to equity, *always add 1.* 21:8 odds means equity = 8 / (21+8) = 28%, not 8/21 = 38%. Will explicitly flags this as a common arithmetic trap and says he'll move between the two formats freely.

#### Hand-reading: ace-ten on the river vs. a tight player

Real hand Will played in Macau ~5 years before the course:

- River. Pot is $13K. Villain bets $8K (pot now $21K). Will has A♥T♥ (a pair of aces).
- Villain is a tight player Will names in passing (the OCW transcript renders the name with uncertainty markers — best to call him "Villain"). Doesn't bluff. Hero models his range as AK, AQ, AJ, AT, A9, A8.
- Combo count: AK = 8 (2 aces × 4 kings), AQ = 8, AJ = 8, A8 = 8. AT = 6 (Hero blocks one ten), A9 = 6 (one nine on board).
- 33 combos beat A-T (anything ace-king through ace-jack and a chunk of A8s/A9s/ATs depending on count). 11 combos lose to A-T. Equity = 11/44 = **25%.** Need 28% → **fold.**

This calculation is the prototype Level-2 decision. The whole point of the course's first half is to get you doing it without paralysis.

#### Optimal (Level-3) play: the same hand framed as a mixed strategy

> Hand-reading vs. game theory: same situation, different mental model.

Reframe Hero's range as A7–AJ (so AT is in the middle). Villain bets 8K into 13K — risking 8 to win 13, ratio ≈ 1.6:1. **For Villain's bluffs to have EV ≤ 0, Hero must call with a frequency ≥ 1.6 / 2.6 ≈ 61.5%.**

A-T is in the top 61.5% of Hero's range → **call.** Notice this conclusion is the *opposite* of the exploitative answer. Both can be right; they're answering different questions:

- *Exploitative:* against this specific tight Villain who never bluffs, A-T is a fold.
- *Optimal:* if Hero never calls a bet here with hands like A-T, Villain can profitably bet *every* hand → Hero is being exploited.

> "The fatal flaw in every plan is the assumption that you know more than your enemy." — Will quotes this in lecture; neither he nor his class identified the source. (For coaching purposes, just attribute it as "a saying Will Ma uses.")

#### Rock-paper-scissors analogy

- **Exploitative RPS:** "He's played rock three times in a row, so I'll throw paper."
- **Optimal RPS:** memorize a sequence of random bits and throw R/P/S each ⅓.

In RPS, optimal play makes zero — opponents can't lose to you because you can't lose to them either. **In poker, optimal play still wins** because real opponents are inconsistent in ways that aren't theoretically optimal: e.g. they fold 76s in a spot but call 65s in the same spot; they check-raise a strictly inferior range. Even tiny inconsistencies leak EV to a Nash strategy.

#### Position

Position is "how many players are left behind me to act." Fewer players behind = stronger hand isn't required to enter the pot. The button is best because it acts last on every postflop street; UTG is worst because everyone else still has a chance to wake up with a monster.

Naming convention Will prefers: name positions by distance from the button (button, cutoff, hijack, lojack…) rather than by table size. "UTG at a 6-handed table" and "lojack" are the same thing — say lojack.

#### Effective stack size

What you're actually playing for in a hand, measured in big blinds. With $400 in front of you at $1/$2 you have "200 BB." If you have 21 BB but the only opponent left in the pot has 12.5 BB, your **effective stack** vs. that opponent is 12.5 BB — you can't win or lose more than that.

Why it matters: it tells you what's actually at stake in this decision. Raising 2.25 BB when you have 100 BB is very different from raising 2.25 BB when you have 12 BB.

#### Antes change everything

Antes are small forced bets each player puts in every hand (sum to about one big blind). Found in late tournament stages, absent from cash games. **Don't think of antes as "the blinds are bigger"** — that's wrong, because if blinds were proportionally bigger you'd have to raise bigger to steal them. With antes the raise size stays the same, so the *risk:reward of stealing* improves dramatically. Result: play *much* wider, attack the blinds aggressively.

#### Raise sizing — "the sweet spot"

- **Min raise (2 BB):** too small. You give blinds great pot odds to defend.
- **Massive raise (e.g. all-in for 30 BB):** too big. You risk way more than you need to to fold out the field.
- **Sweet spot:** **raise to ~2.25 BB in tournaments.** Pre-ante or earlier in a tournament you'll often see 3 BB; this is more about pros wanting to build big pots vs. weaker fields than about theoretical correctness.

Walkthrough Will does at the table: minimum-raising to 4K when blinds are 1000/2000 puts 9000 in the middle and asks the BB to call 2000. That's 4.5:1 — and there's no hand AJo is 4.5:1 favorite over. So you're just paying off the BB.

#### When to skip the raise and just shove

If effective stack ≤ ~**12 BB with antes** (or **10 BB without antes**), the rationale for raising small (lose less if reraised) collapses — 12 BB is small enough that you're not folding after committing 2.25. So just go all-in.

> Beginner mistake #2: being too scared to shove preflop. The cards barely matter relative to position and stack size when you're at this depth.

#### Opening ranges (Will's "conservative" tournament starting recommendations)

These are intentionally tight — easier to err tight than loose when you're learning. Each row adds the hands in red to the previous row's range:

| Position (9-handed) | Range (≈ % of hands) |
|---|---|
| **UTG** | 99+, AJs+, AQo+, AKo (~6.2%) |
| **UTG+1** | + 77+, ATs+, AJo, KQs (~8%) |
| **MP** | + 66+, A9s+, ATo+, KJs+, QJs |
| **Lojack (3 from button)** | + any pair, any suited ace, any suited connector, any two unsuited Broadway cards |
| **Hijack** | wider still |
| **Cutoff** | ~30% of hands |
| **Button** | ~55% of hands — yes, including J3s, K4o, Q6o |
| **Small blind (folded to)** | similar to button range — being out of position is offset by needing to get through one fewer player and the half-blind discount |

> The key intuition: **cutoff opens 5× more hands than UTG.** New players underweight position by playing the same range from every seat.

**Why suited > unsuited matters more for weaker hands:** with AK, suitedness barely changes equity. With 98, suitedness is a huge upgrade because (a) you need the extra path-to-a-flush to win at all and (b) the implied odds are better — when your weak hand turns into a flush, it's well-disguised. (Conversely, with one diamond and four diamonds on the board, your one-card flush is obvious and gets paid less.)

**Suited connectors > one-gappers > weaker holdings.** 76s often outperforms T6s despite the bigger card, because the connectivity creates more straights and the small kicker doesn't matter much.

#### All-in ranges differ slightly from open ranges only at very short stacks

If you're 12 BB and would shove (per the rule above), shove the same range you'd open with. Common fallacy: "I only have 5 BB, I should jam ATC." Wrong — at 5 BB you'll *always get called*, so you can't shove garbage profitably. The deeper insight: when you risk *more*, you also fold *more* people out, so you're not actually risking as much as it feels.

#### Bluffing and value-betting (preview of L2)

Will defines the terms in passing here:

- **Bluff** — bet a *bad* hand hoping a better hand folds.
- **Value bet** — bet a *good* hand hoping a worse hand calls and pays you off.
- **Check medium hands** — they're not strong enough to value-bet (only better hands call) and not weak enough to bluff (they have showdown value).

This becomes the *Fundamental Theorem of Poker* in Lecture 2.

### Hand examples & key quotes from L1

- *"Death, taxes, and the Law of Large Numbers."* — on why even high-variance gambles eventually converge.
- *"You would always fold KK preflop if there were no blinds."* — the Who's-Taller analogy for why every hand is fundamentally about stealing dead money.
- *"Hand reading is not about pegging your opponent on a specific hand. The sunglasses and ear-plugs are mostly a marketing scheme."*
- *"In fact, if you're doing optimal play you don't care in some sense what your cards are. You just care what your range of cards is at that point."*

## Lecture 2 — Introduction to Postflop Play

> The mechanics of every action that happens after the flop: continuation betting, bet sizing, check-raising, calling vs. folding, leading, set mining, implied & reverse implied odds, and bluffing with draws.
>
> **Watch:** [video](https://www.youtube.com/watch?v=uFsM8pc36QQ) · **Slides:** [PDF, 15 MB](https://ocw.mit.edu/ans7870/15/15.S50/IAP16/MIT15_S50IAP16_L2.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/98a7f135b0794feacd5aeffdd4c8b133_uFsM8pc36QQ.pdf)

### Key takeaways

- **Fundamental Theorem of Poker (Will's version):** value-bet your *best* hands · bluff your *worst* hands · *check* your medium hands. If you can't decide whether a bet is value or bluff, you probably shouldn't bet. *(Naming note: Will reuses the name "Fundamental Theorem of Poker," which classically refers to a different David Sklansky concept — "every time you play a hand differently from the way you would have played it if you could see all your opponents' cards, they gain." Will's rule is about bet-construction; Sklansky's is about hidden-information value. Both are useful. When coaching, distinguish them as "Will Ma's FTOP" vs. "Sklansky's FTOP.")*
- **Bet sizing rule of thumb:** ~½ pot on flop · ~⅔ pot on turn · ~¾–pot or more on river. The *fraction* should *increase* on later streets, even though there are fewer cards to come.
- Never bet a tiny amount — small bets are strictly worse than checking. They give your opponent a free check-raise option.
- **Checking to the preflop aggressor** is the default postflop convention. Leading (donk-betting) is a tricky play; it's fine if you avoid it the entire course.
- **Stacking off (deep) requires two-pair or better** — and "two-pair" means *both* of your hole cards make a pair, not one of them plus the board.
- Most hands miss most flops. **Fold most one-pair hands to a half-pot bet**, especially out of position.
- **Implied odds** = the extra money you'll win on later streets when your draw hits. Lets you call without immediate odds (e.g., chasing flushes).
- **Reverse implied odds** = the extra money you'll lose on later streets with marginal hands that are tough to play. Use these to fold hands that mathematically "have the odds."
- **Bluffing with draws ≈ free money.** A draw with 8+ outs is the ideal bluffing hand because even when called, you have outs.
- **Two bluffing epiphanies:** (1) what matters isn't your hand strength, it's how many outs you have vs. their *calling* range; (2) you're representing a story — what good hand could you have? If the answer is "none," abandon the bluff.

### Detailed notes

#### The default postflop convention: check to the preflop aggressor

Postflop, players who didn't raise preflop typically check to the preflop aggressor — both because the aggressor's range is stronger and because if they had really wanted more money in, they would have re-raised preflop. As the preflop raiser, when checked to you, you have the option to **continuation bet (c-bet)** or check back.

#### Continuation betting — when, when not, and how big

The c-bet decision is the same sweet-spot tradeoff as preflop raising:

- **Bet too small:** opponent has good odds to call — and if you're bluffing, you're inviting a check-raise that turns your hand into garbage.
- **Bet too big:** you're risking a lot when you get raised and have to fold.
- **Sweet spot bet sizing:** ~½ pot flop → ~⅔ pot turn → ~¾–full pot river. Aim for "between 50%–100% of pot" with the fraction rising on later streets.

> **Counter-intuitive but important:** you'd expect *bigger* bets on the flop (more cards to come, more outdraws) and *smaller* bets on the river (no more outdraws). The opposite is true. Why? Because when you bet the flop, your opponent isn't deciding whether to call *just* the flop bet — they have to consider the price of calling the *turn* and *river* bets too. The fact that you can keep firing barrels makes the small extra equity-to-call advantage they get on the flop look trivial in comparison.

**When to skip the c-bet entirely:**

- Super-scary, super-coordinated boards (e.g., three of a suit + connected). These boards mean *anything could happen*, and nobody folds. You've got better outcomes by checking and reassessing.
- Multiway pots (5+ players to the flop) with only overcards — someone is going to have a piece. Don't bluff into a crowd.
- Very dominant hands where you'd rather give Villain a turn card to outdraw you a tiny amount and put more money in (the slowplay).

#### The Fundamental Theorem of Poker (Will's framing)

A bet should accomplish exactly one of two things:

1. **Value bet:** you have a *better* hand and want to be called by *worse*. (e.g., overpair on a dry board → bet to get called by lower pairs.)
2. **Bluff:** you have a *worse* hand and want to be called by — sorry, want to fold out — *better* hands. (e.g., KQ on a 9-8-2 board → bet to fold out AJ.)

**Medium-strength hands check.** If you bet, you only get called by hands that beat you and you only fold out hands you already beat (adverse selection). When you check, even if it goes to showdown, you might still win against the genuinely worse hands.

> "If you ever find yourself making a bet and you're not sure whether it's a value bet or a bluff, then chances are you shouldn't be betting."

This is also a preflop concept, but flipped: preflop, you're choosing what *fraction of hands* to play, and the right answer is the top X% — never the top 10% + bottom 10%. Postflop is when polarization (good + bluffs, no medium) becomes the right paradigm.

#### How good does my hand have to be to stack off (deep)?

**At ≥ 40 BB effective: two-pair or better.** And "two-pair" means *both* of your hole cards make a pair. Hands that don't qualify:

- Top pair + top kicker on a dry board → call, don't raise (way-ahead/way-behind: opponent folds worse, calls only with better).
- Overpairs on coordinated boards → similar — fold out worse, get raised by better/draws.
- Two-pair where one pair is on the board (e.g., paired board) → still vulnerable; just call.
- Two-pair with very weak kicker → you're either way ahead or drawing dead to a higher two-pair.

**The dream stack-off spot:** small set on a coordinated draw-heavy board. *"I think this is very close to the best thing that can happen to you in poker."*

> **Audience question that wins a $20 gift card:** why is *pocket fives* (set on a 5-J-T board) actually better than pocket *tens* (set on the same board)? Because pocket fives lets your opponent have a top-pair Ten and stack off. Pocket tens removes the very hands you would get paid by — opponent is much more likely to fold weaker hands when the board has hit you so obviously.

#### Calling, raising, or folding to a bet — by hand strength

**Most hands you flop missed → fold.** Will walks through ~10 examples of hands that look "playable" but are really folds: A-9 high on a board with two flush draws and two straight draws; 9-7s with bottom pair on a 3-flush-draw board; etc. The pattern: if you have neither showdown value nor enough outs to draw, just fold and play the next hand.

**Reasonable calling spots (with one pair / decent equity):** A-9 high on a paired board (J-J-3); A-3 with bottom pair on a safe board (A-J-3 rainbow); medium pair on a high-card board where overcards aren't dangerous; pocket 8s on 9-3-3 (great hand, but raising only folds out everything you beat and gets called by what you lose to).

**Raising spots (very strong hands):** sets · two-pair with both cards · the rare scenario where Villain is folding too often and you can over-raise as a bluff with a draw.

> **Position matters huge here.** All of Will's "call/raise this hand" advice assumes Villain raised from the *button*, where they have a wide ~55% range. If they raised from UTG (8% range), every borderline call becomes a fold and every borderline raise becomes a call. *Always re-anchor on Villain's preflop range before deciding postflop.*

#### Check-raising: usually with the goods, sometimes as a bluff

The arguments for check-raising one-pair hands as protection (don't let JT see a turn) are real but usually *outweighed* by the downsides:

- You build a big pot with a hand that doesn't want a big pot.
- You get bluff-3-bet by hands like A-3 / A-4 (which have an overcard + gutshot) and now you're in a guess-fold.
- Your hand is strong enough to *call* but too weak to *call a re-raise* — so you're trapped in a bad price either way.

The cleaner play with mediocre hands: just call. Save check-raises for two-pair+ value, sets, and clean-bluff draws.

#### Leading (donk-betting) is advanced and risky

"Leading" = the non-preflop-aggressor bets out into the preflop aggressor instead of checking. Will's advice: **it's fine if you never do this.** The reason it's tricky:

- If you only lead with strong hands, your *checking* range becomes weak and your opponent can steamroll over your checks.
- To balance, you also need to lead some bluffs — but then you also need to check some good hands. It's a knot of dependencies that's easy to mis-balance.

> "It's fine if throughout this course you never lead."

#### Implied odds, reverse implied odds, and set mining

**Reverse implied odds** — the cleanest illustration:

> You hold 7-2 offsuit in the big blind facing a 3x raise from the hijack. Pot odds say you have ~28% equity vs. their range and need 27% — *technically a call.* **Fold.** With 7-2 offsuit you have nothing postflop; you'll often hit a small pair, won't know if you're ahead, will lose more chips than you call for, and will play guess-it-and-cry poker for the rest of the hand. There's still 46K of chips to play postflop — that's where the EV bleeds out.

Same setup with **A-2 offsuit**: ~43% raw equity vs. their range — way more than 27%. **Still fold!** Same reverse implied odds problem: when you flop top pair with weak kicker, you can't tell if you're ahead, and you'll spew chips on later streets.

Same setup with **9-8 suited**: only 37% raw equity. **Call!** The hand has *implied odds*: you can flop strong draws or two-pair hands you can play confidently for stacks.

> **The principle:** raw equity is the wrong number for marginal preflop calls. What matters is "can I play this hand profitably postflop?" Hands with poor playability (offsuit kickers, dominated pairs) bleed money. Hands with high playability (suited, connected, low pairs that flop sets clearly) print money even with worse raw equity.

**Set mining** is the canonical implied-odds play: call a UTG raise with 22 hoping to flop a set on a board where Villain has AA or KK and stacks off.

- You flop a set ~1/8 of the time. So you need average winnings ≥ 8× your call to break even.
- This requires deep stacks (100+ BB, ideally) and unaware opponents who'll stack off with overpairs.
- **Set mining is "dying" in modern poker** — solid players no longer auto-stack-off with AA on rags. But the lesson about implied odds is still gold.

#### Bluffing with draws — and the two epiphanies

**Bluffing epiphany #1: hand strength is irrelevant; outs vs. their *calling* range is what matters.**

Example: BB calls a button raise with T9. Flop is J-T-5. Button c-bets. Hero check-raises all-in. *Looks insane — Hero has 10-high.* But it's actually great:

- Hero's 10-high never wins at showdown anyway; the only path to win is bluffing or improving.
- When called, Hero still has 8 outs (the open-ended straight draw) — even against pocket jacks.
- Adverse selection runs in *Hero's* favor here: weak hands fold, strong hands like JJ are "wasted" because Hero has 8 outs against them.

Compare to 6-5 in the same spot — *terrible* check-raise bluff candidate. Any hand that beats you crushes you, and you fold out hands you already beat.

**Bluffing epiphany #2: bluffing is also about telling a credible story.**

Hand: deep cash game, you call from BB with J9hh, flop J-10-5cc (you have one heart, gutshot to a queen, plus pair of jacks). You check-raise. Turn: 7c.

The 7c is the *worst card in the deck for you* — not because it doesn't help (no card does), but because:

- You can't credibly *represent* a 7. Your check-raising range can't include 7-x hands (those would be middle-of-the-road call hands, not check-raise hands).
- *Villain's* range can easily contain 7s.
- His range is now stronger than yours; abandon the bluff.

Compare: if the turn is an Ace, you can credibly represent A-x. Bet again. If the turn brings a back-door flush, you can represent the flush. Bet again. **The best time to bluff: when your draw misses but a different draw completes.**

#### Bet sizing on the river

When you bluff, you want to bet *big enough* that Villain isn't priced into calling with a marginal pair. Will's rule: with a polarized range (nuts or air), bet *bigger* — small bets give Villain odds to call with anything. The larger consequence: river bets in 60–100% of pot range are normal; smaller is rarely correct.

## Lecture 3 — Tournaments vs. Cash Games (and a deep dive on preflop all-ins)

> Will lays out exactly how tournaments and cash games differ, then spends most of the lecture on the most important skill in tournaments — **knowing when to shove preflop**. Includes a full Nash-equilibrium walkthrough for SB-vs-BB at 15 BB.
>
> **Watch:** [video](https://www.youtube.com/watch?v=KTzFk1s2ymE) · **Slides:** [PDF, 8 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/aa986499d8d260e79708c7c48ebc1b0c_MIT15_S50IAP16_L3.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/f102ce580666f88c0574c9a966e95a1b_KTzFk1s2ymE.pdf)

### Key takeaways

- Tournaments and cash games look similar but reward very different skills. Tournaments → math + survival. Cash → metagame + targeting weak players.
- **The single highest-leverage skill in tournaments: knowing when to go all-in preflop.** Most hands collapse to a preflop shove; +1% equity per shove compounds enormously.
- **From the SB at short stacks, you can shove much wider than you can open-raise** because position becomes irrelevant once all the money goes in preflop.
- The **Nash equilibrium** for SB shove vs. BB call at 15 BB: SB shoves ~67% of hands, BB calls ~38.5%.
- **Memorize a few baseline Nash points and interpolate.** Position matters more than stack size for shove ranges. Direction matters more than precise %.
- **Every range bet should be either value or bluff.** No middle ground. Use the same paradigm preflop and postflop.
- Mix in *some* small-pair shoves with *some* Ax-suited shoves at short stacks so opponents can't pick off the small pairs cleanly.

### Detailed notes

#### Tournament vs. Cash — the differences chart

| Dimension | **Tournaments** | **Cash games** |
|---|---|---|
| Stakes | Blinds escalate over time | Fixed |
| Buy-in / re-buy | One buy-in per tournament; eliminated when broke | Buy in any time, leave any time, top up your stack |
| Goal | Survive and ladder up payouts | Maximize win-rate against this specific table |
| Player selection | No control — you're seated where you're seated | Massive — you pick the table, you can stand up |
| Variance | Very high — most tournaments you cash $0 | Lower — your results converge faster |
| Skill emphasis | Math, ICM, short-stack play | Reading specific opponents, exploiting weak players |
| Range of stack depths | All depths (1 BB to 200+ BB depending on stage) | Almost always ~100 BB |
| House rake | Small | Large (relative to wager size) |

> Will picks tournaments for the class because (a) less metagame to memorize, (b) more interesting math, (c) wider variety of stack-depth scenarios, (d) MIT's own poker club tournament happens during the course.
>
> But **good poker is good poker** — most concepts transfer cleanly. Hand reading, EV calculations, the levels of reasoning: all the same.

#### When to go all-in preflop — the rule and the rationale

Will's rule from Lecture 1 restated:

- **With antes:** shove when effective stack ≤ ~12 BB (instead of raising).
- **Without antes:** shove when effective stack ≤ ~10 BB.

**Why shoving is so good:** late in the tournament, antes + blinds make the pot you're stealing huge relative to your raise size. *Any two cards* have equity against any other two cards — even 2-7o has ~28% vs. 7-2o because the matchup is so close. So winning the dead money in the middle just by everyone folding is almost always +EV. **Beginners are systematically too scared to shove preflop.**

**Why shove ranges are wider than open ranges from the SB:** when you open-raise from the SB, you'll often play out of position postflop — that's a real penalty. When you go all-in preflop, position no longer matters because there are no more decisions. So your SB *shove* range can be *much* wider than your SB *open* range. From the SB at 15+ BB, Will is happy to shove against an attentive BB.

#### The 15 BB SB-shove example — building Nash from scratch

Setup: SB has 15 BB and is considering shoving. Antes are in. BB will respond by calling or folding.

**Step 1 — Build a model.** Suppose BB calls with the top 25% of hands (TT+, AJs+, AQo+, KQs and similar).

**Step 2 — Compute SB's EV from shoving 7-2o (a true garbage hand).**

- BB folds 75% of the time → SB wins 2.5 BB (BB + SB + ante BB).
- BB calls 25% of the time. SB has ~36% equity in those spots.
  - Win 36% × win 16.5 BB (call gets 1.5 BB pot + BB's 15 BB stack).
  - Lose 64% × lose 14.5 BB.
- Net EV = 0.75 × (+2.5) + 0.25 × (0.36 × 16.5 + 0.64 × −14.5) = **+1 BB per shove**.

**Even with 7-2o, shoving makes a full big blind!** Try the same calc with 3-2o (28% equity, which is actually *worse* than 7-2o — 3-2o gives up the seven-high when Villain has six-high). Still +0.42 BB. **There is no hand the SB can hold where shoving is unprofitable** if BB really calls only 25%.

**Step 3 — Realize this means BB's strategy was wrong.** If SB shoves any-two profitably, BB should be calling much wider.

**Step 4 — Iterative best response → Nash equilibrium.**

| Iteration | SB shoves | BB calls |
|---|---|---|
| Start | (assume) | 25% |
| 1 | 100% (any two profitable) | 25% |
| 2 | 100% | 67% (must call wide vs. ATC) |
| 3 | 40% (shove only good hands vs. wide call) | 67% |
| 4 | 40% | 30% (tighten back up) |
| ⋯ converges ⋯ | **66.8%** | **38.5%** |

This is the Nash equilibrium. Both strategies are best responses to each other; neither side can profitably deviate.

**The actual SB Nash range at 15 BB is wide:** all pairs, all suited aces, A6o+, K9s+, K9o+, Q9s+, J9s+, T9s, 98s, 87s, 76s, 65s, 54s, 43s. Even 6-5o is a shove. (9-5o is *not* — the boundary is precise.)

> **Memorize a few baseline Nash points, then interpolate.** Examples Will gives:
>
> - Button 10 BB shove → 43.9%
> - Button 5 BB shove → ~60%
> - Button 12 BB shove → ~40%
> - Cutoff 7 BB shove → 38.8%
> - Lojack 10 BB shove → 23.4%
> - UTG 9-handed 3 BB shove → 24.1%
> - UTG 9-handed 5 BB shove → 33.3%
>
> **Position matters more than stack size.** Cutoff 7 BB (38.8%) is wider than Lojack 10 BB (23.4%) — even though Cutoff is shoving fewer chips.

#### Preflop sizing — only two options at short stacks

> Audience: "What if I have 15 BB and AJo? Do I raise to 5 BB?"
>
> Will: "No. **Either 2.25 BB or all-in.** There's nothing in between."

The reason: a 5 BB raise is essentially equivalent to an all-in but worse. If Villain has aces (or any good hand), they shove and you're priced in to call anyway. So the 5 BB raise only loses you EV — it gives Villain the option to cheaply price you in vs. a wider range.

**Some shove-range observations from Will's examples:**

- **Small pairs at short stacks shove for value.** 4-4 has terrible implied odds at 20 BB (set mining doesn't pay enough). Just shove. Same with 7-6s and 9-8s — they need 100 BB+ to play their straight/flush implied odds; at 20 BB they're just trying to flop a pair.
- **Ax-offsuit also shoves for value at short stacks** — A4o shove from button at 17.5 BB is fine. Also has the side benefit that it "protects your small-pair shoves" (so observant opponents can't put you on exactly 22-44 every time).
- **Don't shove into ultra-short BBs** — if BB only has 4 BB, they'll call almost anything, killing your fold equity. The ability to steal the blinds preflop (the whole point of shoving wide) is gone.

#### A subtle multi-way ICM/structure point

When there are *multiple* short stacks behind you with stacks shorter than yours, and one of them shoves, the *other* short might jam over the top — folding the original shover, leaving you heads-up. This actually *triples you up* if you win, instead of doubling. So having shorter stacks behind is sometimes an *incentive*, not a deterrent, to shove first.

#### When you *can't* shove at short stacks (and just have to wait)

Sometimes you just don't get hands. There's no shame in folding for an orbit; trying to manufacture EV by jamming garbage at the wrong stack depth burns chips.

## Lecture 4 — Preflop Re-raising Theory (3-betting)

> Will tackles the hardest preflop spot in modern poker: someone has open-raised, and now you need a strategy with your *entire* range — not just the hand you happen to have. Built around playing through actual hands of an online tournament he won.
>
> **Watch:** [video](https://www.youtube.com/watch?v=_GgdGtQME1I) · **Slides:** [PDF, 1 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/7cbdefd67186f0bbfb56790b976d7a82_MIT15_S50IAP16_L4.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/bfbd0df94ed6538b710070855ff2d5b6__GgdGtQME1I.pdf)

### Key takeaways

- The "intuitive" preflop strategy (raise great hands, call decent hands, fold the rest) is dangerously **predictable** — opponents fold to your raises and bully your calls.
- **Polarization** = 3-bet your *best* hands for value AND your *next-tier-down* hands as bluffs (not your medium hands, which call). Standard at 25–30 BB depths.
- The bluff-3-bet hands should be the *worst* hands you'd otherwise play — calling category leftovers like A-10o or A-9s. Don't "waste" A-Jo as a bluff when it's good enough to call.
- Polarization is exploitable by an opponent who **calls your 3-bet and plays the flop well** with their wider range — but works great against opponents who fold to 3-bets.
- **3-bet sizing:** ~2.5× the original raise (e.g., raise to 90 → 3-bet to ~225).
- At ≤ ~20 BB: just collapse to "raise top X% of hands" — no point polarizing.
- At ~100 BB cash games: just calling 100% of your range is reasonable, since stack depth lets you realize equity postflop.
- Trapping (calling with AA preflop) ~20% of the time as a 2nd-in-line caller helps balance your calling range; ~1–2% if you're 3rd-in-line (a multiway pot already exists).

### Detailed notes

#### The setup that motivates the whole lecture

Hand 1 of the tournament: Will is in position with K-Q offsuit at ~28.5 BB effective. A late-position player has open-raised. K-Q offsuit is a tough hand — too good to fold against this range, not really a "raise to make the pot bigger" hand. So what's the right play?

The wrong frame: "what should I do with K-Q?" The right frame: **what should my entire strategy be in this spot?** Pick a strategy that works for your whole range.

#### The naïve exploitative strategy and why it breaks

Try this:

- **Raise:** TT+, AK
- **Call:** 55+, AJo, ATs, KQo
- **Fold:** everything else

Two problems an audience member spots immediately:

1. **Your raises are too transparent** — opponent just folds whenever you raise (you only have premium hands).
2. **Your calls are also transparent** — when you call, opponent knows you can't have AA. A player behind can squeeze (re-raise over your call) to fold you off the calling range.

This is unbalanced. You leak EV in both directions.

#### Polarization — the better strategy

Instead of bluff-raising hands from your *call* category (which "wastes" them — those hands had positive EV already), **bluff-raise the best hands that are NOT good enough to call.** Concretely:

- **Value 3-bet:** TT+, AK
- **Call:** 55+, AJo, ATs, KQo (still your medium-strong hands)
- **Bluff 3-bet:** 44, A10o, A9s and similar — the *next tier down* from the call category

The intuition: if you 3-bet A-Jo, you'd hate to fold it when shoved on. If you 3-bet A-10o instead, folding to a shove is fine because A-10o wasn't profitable to call anyway. **You're not wasting the strong hands that play well postflop.**

This is called **polarizing** because your 3-betting range is now the *top* of your range plus the *bottom* of your range, with the medium hands in the calling range.

#### When polarization fails — the call-3-bet exploit

What if Villain just **calls your 3-bet** instead of folding?

Boards become a problem because your range has a giant "no medium pairs/no medium cards" hole:

- Suppose you 3-bet TT+/AK as value and 44/A10o/A9s as bluffs.
- Flop comes Q-Q-7. Your value hands miss (bottom of value: TT now an underpair), and your bluffs missed too. Villain knows your range and can attack.
- The polarized 3-bettor can also be exploited if Villain is loose enough to call the bluff hands with worse — A10o gets called by ATo, then you wish you'd 3-bet A-J (which would beat A-10).

**So polarization assumes a good, balanced opponent who folds appropriately.** Against fish, just value-3-bet your good hands and call wide with everything else.

#### Adjustments by stack depth

| Effective stack | Recommended approach |
|---|---|
| ≤ ~20 BB | Just raise top X% of hands. Polarization barely matters; raising is essentially committing already. |
| ~25–40 BB (the "sweet spot") | **Polarize** — value + bluff 3-bets, with calls in between. |
| ~100 BB (deep cash games) | "Just call everything in your playing range" is also a valid strategy. Disguised range, plenty of room to realize equity postflop. Not optimal but not terrible. |

#### Trapping (calling with AA)

You should occasionally **call** (rather than 3-bet) with your monsters so opponents can't safely raise into your calling range.

- Heads-up after one open: trap with AA ~20% of the time.
- Already a multi-way pot (one raise + one call before you act): trap with AA only ~1–2% of the time. The math: 1/200 (chance of being dealt AA) × 0.01 = ~1 in 20,000 — basically you're never doing it. So in this spot opponents rarely face AA from a caller, and you can play tighter against their raises with confidence.

#### Dry vs. wet boards (also relevant for postflop in 3-bet pots)

- **Dry boards** (e.g., K-7-2 rainbow): the winner is mostly decided pre-river. Either you're way ahead or way behind. Bet bigger; play more polarized.
- **Wet/coordinated boards** (e.g., 9-8-7 two-tone): every card matters. Lots of draws, hard to fold. Bet smaller; play more linear.
- It's a spectrum, not a binary.

Implications:

- **Dry boards:** big c-bets work; opponents fold or stack off. Tricky check-raise plays can also work.
- **Wet boards:** smaller c-bets; expect more action; have to fold more often.

#### What the actual hand-by-hand walkthrough teaches

Will plays through ~10 hands of the actual tournament. Key moments:

- **The exact same K-Q hand spot reappears two hands later** — but Will doesn't notice in real-time because he was 15-tabling. The fact that he had bluff-3-bet earlier means his next 3-bet got more action — opponent shoved JJ "not believing" the second 3-bet, illustrating why mixing in bluffs creates value-action for your real hands later.
- **Hand: AQ in EP** — opponent re-raises to a sizing that probably commits him. Will folds. *"It's a fairly tight fold."* AQo is just barely not strong enough to call a 4-bet sizing from this opponent in this position.
- **Hand: 99 in middle, two players already in the pot, one short stack jams 30 BB.** Folded to Will. Even though chip-pressure favors calling, Will folds because vs. the combined ranges he's never actually a favorite. Computes "I'd be a tiny coin flip"; passes.
- **Hand: AJo, very short ahead of you can shove.** Will's lesson: when there are short stacks behind that can fast-commit you, you should be *less* incentivized to open speculative hands like 10-9s — those get crushed by an A-Jo over-shove. (AJ itself is fine to open.)
- **Hand: AJ vs. opponent who just doubled through you.** Calling and shoving are *almost* equivalent here. The reason to shove instead of just call: it removes opponent's option to call cheaply with K-Qs and see a flop. *"Minimize the options you give your opponent."*

## Lecture 5 — Guest Speaker: Jennifer Shahade (no recording / no slides)

> Jennifer Shahade is a 2-time U.S. Women's Chess Champion, professional poker player, and author. The lecture was not recorded for OCW. Her general focus areas in talks/writing: women in mind sports, mental game (tilt, bankroll psychology), the chess–poker overlap.
>
> No primary materials. To find her thinking, see her poker books *Chess Bitch* and *Play Like a Girl* and her PokerStrategy/Poker.org articles, and her TED-style talks on YouTube.

---

## Lecture 6 — Independent Chip Model (ICM) and final-table play

> Will introduces the formula behind ICM (the framework for converting your tournament chip stack into expected dollars) and replays the second half of the same tournament from Lecture 4, this time with ICM commentary on every final-table decision.
>
> **Watch:** [video](https://www.youtube.com/watch?v=zlmokDj0DaU) · **Slides:** [PDF, 628 KB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/5a8392e939175758331a28be9a64645c_MIT15_S50IAP16_L6.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/02adec22ced11914900976a4efa80016_zlmokDj0DaU.pdf)

### Key takeaways

- **Chip EV ≠ Money EV in tournaments.** A chip in a 100-BB stack is worth less per chip than a chip in a 5-BB stack — because the short stack is closer to the next pay jump.
- ICM = formula assuming **chance of finishing 1st is proportional to your % of total chips.** Use it (or a calculator) to convert chip stacks into dollar equity.
- **Big stacks have money EV < chip EV.** **Short stacks have money EV > chip EV** (and small short stacks tend to *win* chip EV from blind-stealers because they get extra fold equity).
- **ICM matters most at the money bubble and the final table** — i.e., where the payout schedule is *steepest*. Early in a tournament, ICM is irrelevant — just maximize chips.
- Heads-up = no ICM. (Three players is the minimum where ICM matters.) Cash games = no ICM, ever.
- ICM creates incentives to **avoid big pots with players who cover you** (especially when there's a shorter stack still alive).
- Sometimes you should **fold pocket aces preflop** in extreme satellite/bubble spots where the payout structure makes survival worth more than chip accumulation.
- Big stacks are "free" to bully short and medium stacks who can't risk busting; this is why chips tend to *flow* to the big stack at the final table.

### Detailed notes

#### Why Chip EV ≠ Money EV

In cash games, $1 in chips = $1 in cash. In tournaments, the payouts are non-linear:

- 80% of the field gets nothing.
- The top 20% get a small minimum cash.
- Payouts then escalate, with a steep jump at the final table.
- 1st place gets a huge fraction of the prize pool.

So your stack converts to money via a *concave* curve — the 1000th chip in your stack is worth less than the 1st chip. **Survival is value.**

> The exception: if you can play in enough tournaments that the LLN converges (i.e., you're a pro), you should still maximize money EV, not "survival." But even maximizing money EV requires you to *understand* ICM because the curve isn't linear.

#### The ICM formula (calculated by hand on a 3-player example)

Setup: 3 players left. Payouts $5/$3/$2. Chip stacks 5K/3K/2K.

If chip EV = money EV:
- Player A's equity = $5
- Player B's equity = $3
- Player C's equity = $2

**This is obviously wrong** — player C is *guaranteed* $2 (they finish at worst 3rd) and has a non-zero chance of winning. So C's equity is > $2.

**The actual ICM calculation (for player C):**

- P(C wins) = 2K / 10K = 20%.
- P(C comes 2nd | A wins) = 2K / (B+C chips) = 2/5 = 40%.
- P(C comes 2nd | B wins) = 2K / (A+C chips) = 2/7 ≈ 28.6%.
- P(C comes 2nd) = P(A wins) × 40% + P(B wins) × 28.6% = 50% × 40% + 30% × 28.6% ≈ **29%**.
- C's equity = $2 (guaranteed) + 0.20 × $3 (if 1st) + 0.29 × $1 (if 2nd) = **$2.89**.

Notice C is closer to a 2nd-place finish than 3rd in equity terms.

For more players, you recurse — condition on each finishing order. **You can't do this in your head**, but online ICM calculators do it instantly.

#### When ICM matters most

Plot the payout vs. finishing position. The slope (money per chip) is highest at:

1. **The money bubble** (right around top 20% — the giant 0 → small cash jump).
2. **The final table** (the escalating payouts as you ladder up).

These are the two spots where ICM dominates your decisions.

> **Conversely, ICM is irrelevant early.** If you have 1000 BB and there are 800 players left, none of the payout-curve nonlinearities affect this hand. Just play to maximize chips.

#### Practical ICM corollaries you can use without a calculator

1. **Don't get all-in with the player who covers you** when there are shorter stacks still alive. You're risking the full payout difference between (your current expected finish) and (busted), with no upside that justifies it.
2. **Big stacks should bully more.** Short stacks can't risk busting → big stacks have huge fold equity. This is why chips flow to the chip leader at the final table.
3. **Short stacks at the bubble should sometimes pass on +chip-EV spots** because busting is so much worse for money EV than slow-laddering.
4. **In satellites** (top N players each win a single equal-value seat to the bigger event), you should sometimes fold pocket aces preflop. The math: if you're already locked into a seat, calling AA preflop is +chip EV but 0 money EV — and you're risking your seat.

#### Final-table walkthrough — ICM in action

Will replays the final table of his Party Poker $55 tournament with ICM commentary:

- **Hand:** Will is 2nd in chips. The chip leader (Panpancrisy) covers him. Will is *very* incentivized to avoid getting it in with Panpancrisy in marginal spots.
- **Hand:** A short stack shoves T-2s for 23 BB. BB calls with A-4o. Short stack actually *holds* and doubles up. Will analyzes: T-2s shove looks crazy, but ICM justifies aggression for the short stack who has no fold equity later. A-4o call is also justified because of the chip-EV math.
- **Hand:** Mid-stack jams 23 BB with A-Q. Will calls with QQ and wins. The opponent's shove was actually *fine* under ICM — A-Q at this stack depth from this position is good enough. Will's only critique: shoving makes the opponent's range too readable (it has to be exactly AKo / AKs / AQs / AQo / 88-TT).
- **Hand:** A short stack's "stop-and-go" — call preflop instead of shoving, then shove the flop blind. The (largely false) justification: maximize the chance the bigger stack folds the river card it sees. Will calls this "interesting in theory but not very good" in practice. Mostly worth knowing about.

> **The "I would pay 10K chips to skip this all-in" insight:** when a short stack is about to bust and you're up against another competitor, you'd often pay enormous amounts in chips to make the short stack lose. Because moving a player from "alive" to "out" jumps everyone's payout by the next ladder rung — and that's worth a *lot* of chips.

#### Tournament play philosophy summary

1. Early: ignore ICM, just accumulate.
2. Middle: stay near average; don't punt; cover stealing as opportunity arises.
3. Bubble: tighten up significantly if you have anything to lose; loosen up massively if you're a big stack.
4. Final table: pay attention to *every* stack, not just yours and your immediate opponent's. ICM influences every decision, not just the all-in ones.

## Lecture 7 — In-depth Combinatorial Hand Analysis (Cash Games) + General Poker Thoughts

> Will walks through one cash-game hand (8♣7♣ on the button vs. cutoff at 100 BB deep) in extreme detail, demonstrating how to deduce opponent's range street-by-street using combinatorics. Then closes with general thoughts about poker as a game and as a life pursuit.
>
> **Watch:** [video](https://www.youtube.com/watch?v=u14ymLSF8y4) · **Slides:** [PDF, 3 MB](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/ca4ca289859d44b9af3b786d4a5360f5_MIT15_S50IAP16_L7.pdf) · **Transcript:** [PDF](https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/284dbaf79f3efe623f251890fab94a7c_u14ymLSF8y4.pdf)

### Key takeaways

- **Continuation-bet sizing depends on board texture:** bigger on dry boards, smaller on wet boards; bigger when out of position; if your bet would commit ≥ 40% of remaining stack, just shove.
- **Get the last bet in with both your nuts AND your bluffs.** With "nuts" (top of range) you want to be called by Villain's shove; with weak draws you're happy to fold to a shove. With *medium* hands, you want to *avoid* being shoved on.
- After the action is over, **replay the hand from Villain's perspective** and rebuild their range street-by-street. Each action narrows the range; you can often pin them down within ~10 combos by the river.
- **Bluff river bet sizing:** bet big when polarized. Polarized = Villain has to fear nuts or air. A small bet lets them call with marginal pairs.
- Poker is unique because: (1) money concretizes good vs. bad decisions; (2) it forces you to operate under uncertainty; (3) it uses real-world skills (probability, modeling, psychology); (4) it teaches you not to be results-oriented.
- **"Results-oriented" is a *negative* term among poker players.** Smart, motivated people often struggle with poker's variance because hard work alone doesn't guarantee good short-term results.
- You don't get to be a winning poker player just from skill — **you also need lucky big scores early** to bankroll your career and stay motivated. This is unsettling but true.

### Detailed notes

#### The hand setup

- $1/$2 cash game, 100 BB effective.
- Cutoff opens to $6. Hero on button has 8♣7♣. Big blind also calls.
- Flop: T-8-6 with one club. Cutoff c-bets $14 into $19 (3-way).

This is a deep cash-game spot — exactly where a hand like 8-7s shines (suited connector, in position, has a pair plus open-ended straight draw plus backdoor flush). In a tournament, the call would be looser than is comfortable; in cash, with deep stacks, it's clearly a call.

#### C-bet sizing principles (review)

- Don't bet so small that Villain has odds to call with anything.
- Don't bet so big that you're risking too much when you're bluffing.
- If your bet commits ≥ 40% of your remaining stack, **just shove** — your hand has enough equity that you're not folding to a 3-bet anyway.
- **Bigger bets on dry boards, smaller bets on wet boards.**
- Bigger bets when out of position (compensates for the disadvantage).
- Raising a bet always invites a re-raise — that's a constant penalty against raising.

#### Get the last bet in with both nuts and bluffs

With deep stacks and lots of betting rounds, *someone* will be the one to put the last bet in (shove first). The question: who do you want to be?

- **You want to be the one who shoves first** when you have the nuts (Villain has to decide call/fold; you want their decision to be the hard one).
- **You want to be the one who shoves first** when you have a weak draw / bluff (if Villain shoves first, you have an easy fold; if you shove first, *they* have a tough call).
- **You want to AVOID being the first shover** with medium-strength hands (top pair, decent kicker; flush draw with overcard). If Villain shoves on you, the call is agonizing.

So with a hand like 8-7c on this T-8-6 flop, **calling is right.** The hand is medium-strong: vulnerable to a check-raise shove if you raise, but with enough showdown value that you don't need to bluff to win.

#### Continuing the hand street by street

- **Turn:** Q♣ — Hero now has gutshot + flush draw + pair of 8s. Big blind folds. Cutoff bets 30 into 47.
- Calling is again right — see-the-river is high-value (a club gives a likely-best flush; another out makes two pair / trips / straight).
- **River:** A♠ — completely missed. Cutoff *checks*. Hero bets $70 into $107. **The whole lecture is about analyzing this $70 river bluff.**

#### Why bluff the river here?

- **Pair of 8s isn't enough** to win at showdown given the action so far. Both ranges are now strong (lots of money in).
- The **A♠** is a scare card — Hero can credibly represent A-x.
- **Pot is big** — making Villain fold a queen wins a substantial pot.
- Position matters: Villain's check is a sign of weakness (he could be trapping K-Jo for a straight, but more often he's giving up).

#### River bluff sizing — why $70 (not $30 and not $107)

- Smaller bet → Villain calls anything (third pair, mid pair, all the bluff catchers). Hero needs Villain to *fold*.
- Bigger bet → not necessarily better; getting closer to all-in might trigger Villain to shove with marginal hands.
- $70 into $107 is ~⅔ pot — gives Villain bad odds to bluff-catch with a non-pair, prices out marginal one-pair hands.
- **General rule:** when your range is polarized (nuts or bluffs), bet *big*. Small bets price Villain's calls with anything.

#### Reverse-engineering Villain's range — the full combinatorial walkthrough

This is the technical clinic at the heart of L7. It's a template an agent can re-use for any cash-game postflop analysis a student brings.

##### The 5-category framework: what is Villain doing with each of his hands?

On any given street, every hand in Villain's range falls into exactly one of five buckets:

| Category | What Villain does | Why |
|---|---|---|
| 1. Monsters | **Check** to trap / check-raise | Hand is so strong he wants opponent to build the pot |
| 2. Strong-but-not-trap | **Bet for value** | Good hand, but not strong enough to slowplay |
| 3. Medium strength | **Check** to check-call | Has showdown value; doesn't want to bloat pot or fold out worse |
| 4. Draws / bluffs | **Bet as a bluff / semi-bluff** | No showdown value but good fold equity or outs |
| 5. Pure air | **Check** to give up | No equity, no showdown value; just fold to any bet |

**The key deduction move:** when Villain takes an action, you can *eliminate* the categories that wouldn't take that action.

- Villain **bets** → eliminate categories 1, 3, 5 (all three check). Villain's range is now narrowed to categories 2 + 4 — **value bets + bluffs**. This is the polarization insight from the opposite direction.
- Villain **checks** → eliminate categories 2 + 4. Villain's range is narrowed to 1, 3, 5 — **monsters + medium + air**.

This categorization is *exactly* the same structure as Will Ma's Fundamental Theorem of Poker from L2, just viewed from the other seat. You bet value or bluff and check medium; so does Villain; so the *inverse* of his action tells you the classification.

##### Applied to the 8-7s hand on T-8-6, Q♣, A♠

Hero holds 8♣7♣ on the button. Final board: T♠ 8♦ 6♥ Q♣ A♠. Villain (in cutoff seat, opened preflop and bet flop + turn) checks the river. Hero is considering a $70 bluff into a $107 pot.

**Step 1 — Preflop range (Villain opens from cutoff):**

Will builds this in PokerStove to ~30% of hands: 22+, all suited aces, A9o+, K9s+, KTo+, Q9s+, QTo+, J9s+, JTo, T8s+, 97s+, 86s+, 75s+, 64s+, 53s+, plus suited Broadway down to KJ / QJ.

**Step 2 — Villain bets the flop T-8-6 (eliminate categories 1, 3, 5):**

From the preflop range, remove hands Villain would *check* on this board:
- **Category 5 (air):** small pocket pairs that gave up (22, 33, 44, 55); weak suited aces with no equity (A5s, A4s, A3s, A2s); pure bricks (53s).
- **Category 3 (medium, check-call):** middle pairs and weak pairs that don't want to build a pot (pocket 7s, 9s; Jx Qx Kx hands that whiffed; J9s/J-T; 9-8, 10-9, 10-7; most Ax-no-draw).
- **Category 1 (monster slowplays):** very few hands slow-play this board texture; most sets / straights bet for value, not trap.

Remaining after flop bet: **top pairs (T-x)**, **overpairs (JJ+)**, **sets (TT, 88, 66)**, **straight draws (9-7, 7-5, 5-4)**, **two-pair combos (T-8s, T-6s, 8-6s)**, some **overcard-with-backdoor combos** (A-J, A-9, K-J with club, etc.).

**Step 3 — Villain bets turn (Q♣) — eliminate more:**

- Weak 10s (A-T, K-T) transition from "continue for value" to "give up" — Villain likely *checks* these on the turn. **Remove A-T, K-T, Q-T (now two-pair, actually this stays a value bet), J-T.**
- Pocket jacks become underpair-ish and more vulnerable; often still bet but some players check.
- Weak straight draws that missed (6-5, 5-4) tend to give up on scare-card turns.
- *(Gain)* Hands that picked up equity bet: A-J, A-Q, K-J with club — these barrel.

Remaining after turn bet: **strong top pairs (Q-T becomes two-pair; A-T now underrepresented)**, **overpairs**, **sets**, **completed straights (9-7)**, **strong-equity semibluffs (A-K, A-J suited with club, K-J with club)**, **two-pair hands**.

**Step 4 — Villain checks the river (A♠) — the critical step:**

The ace is a scare card that hits *Villain's* range (lots of A-x's) but *not Hero's* (Hero's 8-7s doesn't have an ace). Paradoxically, Villain's *check* signals weakness here because:

- If Villain had an **ace**, he'd usually bet for value (category 2). **Remove A-K, A-J, A-Q, A-A, A-T-the-remaining-combos.**
- If Villain had **two-pair or a set** he'd usually bet for value (category 2). **Remove sets, remove two-pair.**
- If Villain had **pure air** he'd continue bluffing on a scare card that helps his range (category 4). **Remove K-J missed, K-7, pure bluffs.**
- If Villain had **a monster** like the 9-7 straight, he'd bet (no reason to trap at this stack depth). **Remove 9-7.**

Remaining check range (categories 1-weak + 3 + 5-that-gave-up-already), based on Will's live narration: **medium top pairs that fear the ace and check-call (KQs, QJ offsuit)**, **underpair-to-the-ace bluff-catchers (KK)**, **two-pair hands afraid of the ace (T-8s, T-6s, 8-6s)**, **broken value combos that turned weak (A-K, A-J, A-9 — Will keeps these in despite the case for value-betting)**, **third-pair gave-ups (7-6s, 6-5s)**, and **broken queens (Q-9s)**. Note that Will *removed* TT on the flop (slow-play) and JJ on the turn (became too marginal after the queen) — they are not in the river check range.

##### Counting combos — the payoff

Now Will does the hand-counting. **Offsuit hands have 3× more combos than suited hands** — this is the key math move. Because Hero holds 8♣ and 7♣, every combo that includes an 8 or a 7 or a club is reduced.

Going through each remaining hand:

| Villain's hand | Combos | How | Reasoning |
|---|---|---|---|
| Q-J (suited + offsuit) | **12** | 3 Q (one on board) × 4 J | Will groups suited + offsuit together because they play identically here. By far the largest single weight — pivot of the whole analysis. |
| A-K suited (if still in) | 3 | 4 suits, minus A♠ on board | One suit eliminated |
| A-J suited | 3 | 4 suits, minus A♠ | |
| A-9 suited | 3 | | |
| K-Q suited | **2** | 4 suits → minus K♣Q♣ (Q♣ on board) → minus K♠Q♠ (Will assumes Villain folds preflop because no spade on flop = no backdoor flush draw) → 2 left (♥, ♦) | Will explicitly walks through this in the lecture as a player-tendency adjustment on top of the board blocker |
| Q-9 suited | 3 | | |
| T-8 suited | **2** | 4 suits, minus ♣ (Hero has 8♣) minus ♠ (board) | |
| T-6 suited | 2 | | |
| 8-6 suited | **1** | 4 suits, minus ♣, minus ♠, minus ♦ (board has 8♦, so 8♦-6♦ impossible) | Heavily blocked |
| 7-6 suited | **2** | 4 suits, minus ♣ | |
| 6-5 suited | 3 | | |
| K-J suited (hearts/clubs if he checks back) | 2 | | |

**Totals after categorizing outcome:**

| Category | Combo count | Contents |
|---|---|---|
| **(a) Beat us + would call our bluff** | **14** | Top-pair-with-an-ace combos (A-K, A-J, A-9 suited), top-pair-queen with the king kicker (K-Q suited), and two-pair from the flop that survived (T-8s, T-6s, 8-6s) |
| **(b) Beat us + would fold** | **23** | **Q-J offsuit alone is 12 combos** — by far the largest weight. Plus pocket K-K (an underpair afraid of the ace), Q-9s (broken queen) |
| **(c) We beat + would fold** | **5** | 7-6s and 6-5s — third-pair sixes that Hero's pair of 8s actually beats |

##### The EV calculation

Risking **$70 to win $107** (the pot before Hero's bet). Hero needs Villain to fold **more than 70 / (70+107) = ~40%** of the time for the bluff to break even *as a pure bluff* (ignoring the times Hero wins at showdown by checking).

- Villain folds (b) + (c) = 23 + 5 = **28 combos out of 42 total = 66.7% fold rate.** ✓ (Well above 40%.)
- But wait — this is 28/42. Hero also has to compare against *just checking*, because if Hero checks, he wins against the 5 combos where Villain has 7-6/6-5 and loses to everything else.

Compare:
- **Check**: win ~5/42 = 11.9% of the pot at showdown → EV ≈ 0.119 × $107 = **$12.7**
- **Bet $70**: win the pot 28/42 of the time (fold), lose $70 the other 14/42 of the time → EV = (28/42) × $107 + (14/42) × (−$70) = **$71.3 − $23.3 = +$48**

**Bluffing is overwhelmingly profitable.** The +$35 delta (vs. checking) is the concrete value of the combinatorial analysis.

##### The key teaching move (L7's most important insight)

> "If you just look at PokerStove, you might actually think bluffing is bad because most of the hands listed — A-K, A-J, A-9, T-8, T-6, 8-6 — beat us. But when you count combos, Queen-Jack offsuit **alone is 12 combos** while the sum of all suited 'hands that beat us and call' is ~14. **Looking at hand types without weighting by combos will give you exactly the wrong answer.**"

**Coaching takeaway:** every deep range analysis must include a combo count. The heuristic shortcut: *offsuit hands count ~3× suited hands. Board cards and Hero's hole cards block specific combos. Never eyeball it — count.*

> **Rule of thumb cheat sheet for combo counting:**
>
> - Pocket pair: **6 combos** (4 choose 2).
> - Pocket pair with one on board: 3 combos. Two on board: 1 combo.
> - Suited hand (both ranks unseen): **4 combos** (one per suit). Subtract 1 for each relevant board/hole blocker.
> - Offsuit hand (both ranks unseen): **12 combos** (4 × 3, minus the 4 suited combos).
> - AK combined (suited + offsuit): **16 combos total.**
> - With one rank appearing once on board: multiply by 3/4 (one suit eliminated).

#### Closing thoughts on poker — the four reasons there's so much money in it (the second half of L7)

Will closes the course (this was effectively the last student lecture; L8 was Bill Chen guest) with a structured framework. He asks: *Why is there so much money in poker but not in chess or hockey?* He identifies **four unique aspects of poker** that allow there to be so much money flowing around. Each is a coaching topic in its own right.

##### 1. Overconfidence (and how to spot it in yourself)

> "If you can't spot the fish at the table, you are the fish." — popular poker saying

People are systematically overconfident in poker — more than in almost any other domain Will can think of. The 95%-confidence-interval calibration test illustrates the general phenomenon: ask normal people to give 95% confidence ranges for trivia (population of Mongolia, length of the Nile…) and only ~70% of intervals contain the true answer instead of 95%. People are dramatically overconfident.

Why is poker even worse than baseline? Three forces compound:

- **The mental-battle nature of the game** — you're constantly modeling your opponent ("is he bluffing?"). It's natural to assume you're the smarter one.
- **Selective memory** — you remember the bad beat where they hit a king on the river, you forget the time you sucked out on aces.
- **No clear benchmarks** — unlike a 100m sprint where a 30-second time obviously rules you out of the Olympics, poker results have so much variance that anyone can rationalize a losing streak as "luck."

Two non-poker analogies Will uses: **driving** (no one ever admits to being a below-average driver) and **teaching** (the same).

**The David Einhorn anecdote** (Will's go-to example of correct calibration): Einhorn, the billionaire founder of Greenlight Capital, played a $1M-buy-in poker tournament against the world's best pros. He was honest with himself: he expected to lose. He framed it as "I'm a billionaire who's happy to spend a million dollars playing this tournament." He ended up winning $4M (came 3rd) and donated all of it to charity. The healthy mentality: just admit you're playing for fun and don't expect to be the world's best at everything.

> **The hard tension** Will surfaces: in poker, **overconfidence is poison** but **underconfidence is also poison** — you need confidence to make risky decisions, to trust your reads, to play through a downswing. Striking the balance is something even pros struggle with daily.

##### 2. Gambling self-control (tilt)

The classic patterns:

- **Playing tired** because you want to "get unstuck" — win back what you lost. Will admits to doing this many times in his career.
- **Letting an unlucky previous hand affect the next decision.** The cards don't remember; the LLN doesn't owe you a refund.
- **Rationalizing gambling itself** — there's stigma; you have to internalize that you've chosen a high-luck game and that's OK.

Even very smart people fall into these. Tilt is a coaching topic, not just a personal weakness.

##### 3. Fast evolution of the game

Texas Hold'em is a relatively new game with a lot of hidden depth. Other games (chess, the 100m sprint) evolve incrementally — the world record in the 100m won't go from 10 seconds to 5 seconds in a year. **Poker did exactly that.** Will's frame: *"the best player in 2000 would be like a terrible player by 2004; the best player in 2004 would be a bad player by 2008."*

Audience analogies: CrossFit (the 2009 Games winner couldn't even compete by 2015) and competitive math contests (much harder to make the US national team now than 30 years ago).

The implication: even if you were the best player in your home game four years ago, you cannot assume you can sit down at a current $1/$2 game and win. **You have to keep studying.** The frontier moves.

##### 4. Decision mentality (not being results-oriented)

This is the framework from Lecture 1 brought back full circle. Among poker players, **"results-oriented" is a negative term** — they laugh at people who put it on resumes. Outside of poker, the same trait is celebrated as a virtue. Smart, motivated people often struggle with poker variance specifically because everywhere else in their lives, hard work + intelligence → good results. In poker, hard work + intelligence → +EV → eventually good results, but the *eventually* can be very long.

> "I think even if you're working very hard, you do need some lucky big scores along the way, especially at the start, even if you're very smart and working in the right way."

Will is candid about his own career: he was lucky early. There's a parallel-universe version of him who made the same decisions, didn't get the early hot streak, and never made it as a pro.

##### "The joy of making good decisions" — Will's closing thesis

> The Bill Gates / Doyle Brunson story: Bill Gates was actually a pretty good poker player for a while. Money obviously meant nothing to him — he could make $500/second running Microsoft. But when asked why he played, Gates said: *"I love making good decisions. I love thinking about this game and making decisions. Even though the money means nothing to me, it's still important to me, as a personal goal, to succeed at this game."* Will argues this mentality — process-focus, not outcome-focus — is *part of why Gates was good.* He didn't care about results, so he focused on decisions.

The closing image (which Will credits to **Jennifer Shahade's "Goldilocks" video** from her L5 guest lecture): *think of your life — and your poker career — as one long session.* Don't optimize for today's result. Make the best decisions you can over the long run, and trust the LLN to do its job.

##### Online resources Will recommends

For continuing study after the course:

- **CardRunners** (cardrunners.com) — paid subscription site where pros record themselves playing while talking through their reasoning. Will is a CardRunners pro himself, so disclosed bias.
- **Two Plus Two forums** (twoplustwo.com) — free, "lots of garbage and banter, but most of the best poker players in the world still post there."
- **Twitch** poker streams — watch pros play in real time, with their cards visible after a 10-minute delay (so you can't action-cheat). More entertaining than educational, but useful.

Will explicitly says **books go out of date too fast in poker** — online is the better primary source. The book list (above and below) is for theory and writing quality, not for the strategic frontier.

#### One last book list (Will's actual favorites, in order)

1. **Small Stakes Hold'em** by Miller, Sklansky, Malmuth — Will's all-time favorite. Limit hold'em is "solved" now but the theory is foundational. *Note:* Ed Miller is an MIT graduate; Will's friend Mike "Timex" McDonald (who got Will into poker) re-read this book ~20 times when he was a young player.
2. **Harrington on Hold'em Vols. 1 & 2** — outdated but well written; how Will himself learned tournaments.
3. **Kill Phil / Kill Everyone** — decent and reasonably current.
4. **Every Hand Revealed** by Gus Hansen — entertaining over educational.
5. **The Mathematics of Poker** by Bill Chen — *not* practical but theoretically gorgeous (Bill Chen was the L8 guest speaker).
6. **Building a Bankroll** by Pawel Nazarewicz — recent, cash-game focused.

---

## Lecture 8 — Guest Speaker: Bill Chen (no recording / no slides)

> Bill Chen is the co-author of *The Mathematics of Poker*, a quantitative finance professional, and a multi-WSOP-bracelet winner. The lecture was not recorded for OCW. His Lecture-7 cameo (referenced in PS2 below) suggests he focused on game-theoretic / Nash-equilibrium aspects of poker.
>
> No primary materials. To dig into his thinking, see his book and his published papers.

## Problem Sets — work these before peeking at solutions

These are the two homeworks Will assigned during the IAP. Each is a tight 4-question set that drills the exact concepts from the lectures. Write your own answers first, then compare.

### Problem Set 1

> Reference video / lecture: L1 (concepts), L2 (math).

**Q1.** In Jennifer Tilly's hand (the famous "I thought you had pocket kings"), she has J♦ J♣ and the board is T♠ J♥ 7♣ K♠ K♣. List all hands that actually beat her (you don't have to list suits, just cards).

**Q2.** In Texas Hold'em, getting dealt two Aces ("pocket Aces") is the best possible starting hand. What is the probability of being dealt this hand?

**Q3.** You are on the Button (you are the dealer) and it's folded to you. You're trying to exploit the SB and BB, who are way too tight. You know their strategy: only call any raise with AA, fold everything else. Effective stack = 20 BB. Roughly speaking, what should your strategy be? By "strategy" I mean a description of what to do with each potential hand you could have (e.g., "raise QQ, KK, AA and fold everything else").

**Q4.** After the flop, assuming you'll see the turn and river, what is the probability of being dealt at least one of 6 cards, *without* any of 9 other cards appearing? Construct a situation in which two players go all-in on the flop, and one player's win probability is approximately this calculation.

> *Question 4 is taken from Eric Beren's poker homework at Jane Street Capital.*

#### Problem Set 1 — solutions

**Q1.** **KK, KJ, KT, K7** (any suits).

Tilly holds J♦ J♣ on a board of T♠ J♥ 7♣ K♠ K♣. Her best 5-card hand is J-J-J-K-K → **jacks full of kings.** For an opponent to beat her they need either:

- **Quads:** only quad kings (KK in hand → K-K-K-K + any 5th card). The board has 2 kings, so opponent needs both remaining kings in the hole.
- **A higher full house:** must be *kings full of something*. The opponent needs trip kings (one king in hand + 2 board kings) plus a pair, which means their second hole card must pair with a board card (J, T, or 7). So **KJ → kings full of jacks**, **KT → kings full of tens**, **K7 → kings full of sevens** — all higher than jacks full of kings.

Other near-misses: TT and 77 in hand make tens full and sevens full of kings respectively — both *lose* to Tilly's jacks full. JJ is impossible (Tilly holds the only two jacks left).

**Q2.** P(first card is an Ace) × P(second card is an Ace | first was) = (4/52) × (3/51) = 12/2652 = **1/221 ≈ 0.45%.**

**Q3.** Intuitively, the best strategy is to **raise (or shove) any-two-cards** to "steal" the blinds. Why: the blinds put up resistance with only AA, which is ~0.45% of hands (extremely rare). So you'll win the blinds nearly 99.55% of the time. **However**, when they *do* call (with AA), you should only continue postflop on flops where your specific holding can beat AA — because at that point you know they have AA. So shove/raise wide preflop; play super-tight postflop only when called.

**Q4.** At this point in the hand, 7 cards have been exposed (2 in each player's hand + 3 flop cards). Of the 45 cards remaining, **6 are "good"** (helps Hero), **9 are "bad"** (helps Villain), and **30 are "neutral"** (helps neither).

We want P(at least one "good" card on turn or river, AND no "bad" card on either).

This happens via two paths:
- **Both turn + river are "good":** 6/45 × 5/44 = 30/1980 = 1/66.
- **One "good" + one "neutral" (in either order):** 2 × (6/45 × 30/44) = 360/1980 = 6/33 = 2/11.

Total: 1/66 + 2/11 × (6/6) = 1/66 + 12/66 = **13/66 ≈ 19.7%.**

**Concrete situation:** Hero holds 9♣ 8♣. Villain holds K♥ K♠. Board: T♥ 7♥ 2♥. Hero has an open-ended straight draw (need a 6 or J — that's 8 outs, but minus 2 hearts that complete Villain's flush = 6 "good" cards). Villain holds two kings already and has a flush draw (the 9 remaining hearts that complete the flush = 9 "bad" cards). Any neutral card is fine for Hero if they hit a "good" card. So Hero's win probability ≈ 13/66.

> **Note on a typo in the published OCW solution:** the official solution writes "2*(6/45*30/44)=3/55" for the one-good-one-neutral term, but the correct value is **2/11** (or equivalently 12/66). The final answer 13/66 is right; just the intermediate is mislabeled.

---

### Problem Set 2

> Reference video / lecture: L1 (exploitative reasoning), L4 (polarization), L7 (Nash equilibrium intuition).

**Setup:** Jen is dealt a random card from a deck with cards 1, 2, …, 10. Bill is dealt a random card from a separate deck with cards 1, 2, …, 10. Both players ante $50 into the pot at the start of the hand.

**Betting rules:** Only Jen has the option to **Bet $100 or Check**.
- If Jen *checks* → showdown immediately. Higher card wins. Ties go to Bill.
- If Jen *bets* → Bill can **Call ($100)** or **Fold**.
  - If Bill calls → showdown for $300 pot.
  - If Bill folds → Jen wins the $100 pot without showdown.

For each version of "Bill" below, find Jen's most-profitable exploitative strategy. Circle which hands Jen should *bet* with, and compute her EV per game.

**Example given:** vs. Bill Cosby (calls every card). Jen value-bets 6+ (it actually doesn't matter whether she bets a 6 — indifferent). Computation:
- Half the time Jen has 6+ → both players wager $150 (she bets, he calls). Win 70% (avg of 50% with a 6 to 90% with a 10) × +$150 + 30% × −$150.
- Half the time Jen has 1–5 → both wager $50 (she checks). Win 20% × +$50 + 80% × −$50.
- Total EV = 0.5 × (0.7 × 150 + 0.3 × −150) + 0.5 × (0.2 × 50 + 0.8 × −50) = **+$15/game.**

**The four Bills:**

1. **Bill Gates** — very tight, calls only with 10+.
2. **Bill Nye** — pretty loose, calls with 4+.
3. **Bill Clinton** — pretty tight, calls with 8+.
4. *(bonus)* **Bill Chen** — calls with the optimal strategy. He calls with a range of hands that minimizes how much Jen can expect to win per game. (May be randomized — e.g. "always call 8+, and call a 7 60% of the time.") Outline his optimal strategy and circle the hands you'd bet against it.

   *(corollary to bonus)* If Jen Shahade (playing optimally vs. Bill's optimal strategy) plays vs. Bill Chen, who's expected to win? Jen (gets to bet) or Bill (wins ties)?

#### Problem Set 2 — solutions

1. **vs. Bill Gates (calls only 10+):** **Bluff 8- or 9-** (but check 1–7 since you can't get value-betting bluffs through, and you can't value-bet a hand worse than a 10 since he never calls anyway). Bet small (8/9 only). EV ≈ **+$31/game.** *(Gates folds so much that any decent-strength bluff prints money, but tiny hands aren't worth it because the pot you win when he folds isn't enough to justify when he does have a 10.)*

2. **vs. Bill Nye (calls with 4+):** **Value-bet 8+.** EV ≈ **+$4/game.** *(He's so loose-calling that pure bluffs lose money, but value-betting your strong hands is profitable.)*

3. **vs. Bill Clinton (calls with 8+):** **Bluff 4- or 5-** (and value-bet — wait, the solution as stated by Will is "bluff 4- or 5-; EV is +$6/game." So the strategy is: bluff with 4 or 5 (he folds, you steal), check 6 and 7 (no value possible against his 8+ calling range), value-bet 8+ (he calls with 8+ which still loses to your 9 and 10 a lot, especially the 10).

4. **vs. Bill Chen (optimal):** Bill's optimal strategy is to **call with the top x% of hands**, where x is anywhere in [0.45, 0.5]. (E.g., x = 0.45 → call 7+, plus call a 6 50% of the time.) Against this:
   - Jen's optimal strategy: **always bluff with a 1, never bluff with a 2, value-bet 9+.**
   - **Bill actually wins** when both play optimally — he profits **$1 per game.** (The bettor's advantage is not enough to overcome the tie-goes-to-Bill rule.)

> The bonus is the most important pedagogically — it's an honest, fully-worked Nash equilibrium for a tiny but realistic poker-like game. Build the iterated best-response table and watch it converge.

---

## Quick-reference principles (coaching cheat sheet)

> Fast-lookup distilled rules for mid-conversation reference. Every entry links to the lecture where it's developed. Use these as **named concepts** when coaching — e.g., "That's a reverse implied odds spot" — then explain. When a student's question maps to one of these rules, say the rule *by name*, then show the reasoning.

### Preflop

- **Never limp.** If no one has raised, raise. (L1, Beginner Mistake #1)
- **Default tournament open size:** 2.25 BB. (L1)
- **Shove-or-fold threshold:** ≤12 BB with antes; ≤10 BB without. (L1, L3)
- **Three inputs in order:** position → effective stack → cards. Re-anchor any student who leads with cards. (L1)
- **Open ranges widen toward the button:** UTG ~6%, cutoff ~30%, button ~55%. Cutoff opens 5× more than UTG. (L1)
- **Suitedness matters more for weaker hands.** 98s vs. 98o is a huge upgrade; AKs vs. AKo is tiny. (L1)
- **SB shove is wider than SB open.** Position irrelevance after all-in compensates for OOP disadvantage. SB shove Nash at 15 BB ≈ 67% of hands. (L3)
- **Position matters more than stack size for shove ranges.** CO at 7 BB (38.8%) is wider than LJ at 10 BB (23.4%). (L3)
- **Small pairs at short stacks: shove for value.** Set mining doesn't pay at 20 BB. (L3)
- **Polarize 3-bets at 25–40 BB.** Value (TT+/AK) + bluffs (A9s, A10o — the tier below your calling range). Medium hands call. (L4)
- **Bluff-3-bet with the *worst* hands in your call range.** Don't waste AJo; bluff-3-bet A10o. (L4)
- **At ≤20 BB: just raise top X%.** Polarization barely matters; raising is committing. (L4)
- **At 100 BB cash: just call everything in your playing range** is a valid strategy. (L4)
- **Trap with AA ~20% when 2nd-in; ~1–2% when multiway.** (L4)

### Postflop

- **Fundamental Theorem of Poker (Will's version):** value-bet best, bluff worst, check medium. Never bet a hand you can't classify as value or bluff. (L2) *(Note: distinct from Sklansky's FTOP.)*
- **C-bet sizing progression:** ~½ pot flop → ⅔ turn → ¾+ river. Fraction *increases* on later streets. (L2)
- **Skip the c-bet on:** super-coordinated scary boards; 5+ way pots with no made hand; monsters that want Villain to draw out. (L2)
- **Bigger bets on dry boards, smaller on wet.** Dry → folds or stack-offs. Wet → give draws bad odds. (L4)
- **Stack-off threshold at 40+ BB: two-pair or better**, and *both* your cards must play. TPTK doesn't clear the bar. (L2)
- **Don't check-raise one-pair hands.** Invites bluff-3-bets; just call. (L2)
- **Never lead (donk-bet)** unless you really know what you're doing. It's fine never to lead. (L2)
- **Reverse implied odds beat raw equity.** 7-2o has 28% (barely enough) — still fold. A-2o has 43% — still fold. 9-8s has 37% — call. Playability > raw equity. (L2)
- **Bluffing Epiphany #1:** what matters is outs vs. their *calling* range, not hand strength. 10-high with 8 outs > 6-5 with 0 outs as a check-raise bluff. (L2)
- **Bluffing Epiphany #2:** bluffs need a credible story. "What hand can I represent?" (L2)
- **Best time to bluff:** your draw missed but a *different* draw completed. (L2)
- **Get the last bet in** with nuts (their hard decision) and with weak bluffs (your easy fold to a reshove). **Avoid being the first shover with medium hands.** (L7)
- **River bet sizing for polarized ranges: big.** ⅔ to full pot. Small bets price Villain's bluff-catchers. (L7)
- **When Villain checks a scare card that helps his range:** he often has a medium hand that fears it. Good bluff spot. (L7)

### Range analysis (combinatorics)

- **Always think in ranges, never a specific hand.** Level 2 > Level 1 is the single highest-leverage upgrade. (L1)
- **Three levels of reasoning:** Level 1 wrong; Level 2 exploitative (career-making); Level 3 optimal (uncrushable). (L1)
- **Count combos, not hand types.** (L7)
- **5-category framework for any street:** (1) trap/check-raise, (2) value-bet, (3) check-call medium, (4) bluff/semi-bluff, (5) check-fold. Villain's action eliminates categories. (L7)
- **Villain bets → eliminate check categories** (1, 3, 5). Range = value + bluff. (L7)
- **Villain checks → eliminate bet categories** (2, 4). Range = monster + medium + air. (L7)
- **Blockers matter:** your hole cards and the board reduce specific combos. (L7)

#### Combo-counting shortcuts

| Hand type | Combos | Adjustment |
|---|---|---|
| Pocket pair (no board match) | **6** | C(4,2) |
| Pocket pair, 1 on board | 3 | |
| Pocket pair, 2 on board | 1 | |
| Suited hand (both ranks unseen) | **4** | One per suit |
| Offsuit hand (both ranks unseen) | **12** | 4 × 3 |
| Any two unpaired ranks (suited + offsuit) | **16** | |
| One rank has 1 card on board | × 3/4 | One suit eliminated |
| You hold one of the two ranks | × 3/4 | Blocker |

> **The offsuit ≈ 3× suited rule** is the most important combo-count insight. QJo = 12 combos, QJs = 3. A single offsuit holding can outweigh several suited holdings combined. When counting Villain's range, always weight by combos — eyeballing gives systematically wrong answers.

### Tournaments / ICM

- **Chip EV ≠ Money EV.** Concave curve — chips lose marginal value as stack grows. (L6)
- **ICM matters most at bubble and final table.** Where payout slope is steepest. Irrelevant early. (L6)
- **Heads-up = no ICM.** Cash games = no ICM ever. (L6)
- **Don't get all-in with players who cover you** when shorter stacks are still alive. (L6)
- **Big stacks bully shorts** at the final table. Chips flow to the chip leader. (L6)
- **Sometimes fold AA preflop in satellites.** Extreme payout structures. (L6)
- **"Stop-and-go" is mostly theoretical.** Rarely better than preflop shove. Know it exists. (L6)

### Mental game

- **Judge decisions, not results.** Credit-card-roulette logic: thank Matt, not Steven. (L1/L7)
- **"Results-oriented" is an insult in poker.** Outside poker it's a virtue. Adjust. (L7)
- **"If you can't spot the fish at the table, you are the fish."** Overconfidence is the #1 leak among smart new players. (L7)
- **Poker is uniquely easy to overestimate yourself in** — mental-battle nature, selective memory, no clear benchmarks. Calibration test: normal 95% CIs contain ~70%. (L7)
- **Tilt:** don't play tired, don't play to "get unstuck." (L7)
- **The game evolves fast.** Best player in 2000 = bad by 2004. Keep studying. (L7)
- **Need luck plus skill.** Accept that variance cooperates with some players and not others, even early. (L7)
- **The joy of making good decisions.** Bill Gates model: love the decisions, not the money. (L7)
- **One long session.** Treat career as one session; don't optimize today. (L7, Shahade's Goldilocks framing)

### Canonical hand examples (re-use as coach)

| Example | Source | What it teaches |
|---|---|---|
| Jennifer Tilly / Pocket Jacks | L1 | Level 1 reasoning fails. Think in ranges. |
| Credit card roulette (Matt & Steven) | L1 | EV vs. results. |
| A-T river vs. tight Villain (Macau) | L1 | Combo counting + pot odds; exploitative vs. optimal diverge. |
| Who's Taller game | L1 | Every hand is fundamentally about dead money. |
| SB 15 BB shove / Nash equilibrium | L3 | Iterated best-response → ~67% shove / 38.5% call. |
| KQo button 3-bet bluff | L4 | Polarization — bluff the worst hands in call range. |
| 8-7s on T-8-6, Q♣, A♠ | L7 | Full combinatorial range deduction with combo count. |
| David Einhorn $1M tournament | L7 | Correct calibration — knowing when you're the underdog. |
| Bill Gates / Doyle Brunson | L7 | "The joy of making good decisions." |

### Anti-patterns — what to redirect

| Student says | Redirect to |
|---|---|
| "I put him on AK" | "His *range* is…" |
| "It worked, so it was right" | "Given what you knew, the decision was…" |
| "I had to call — pot odds" | "What did you expect to do on future streets?" (implied odds) |
| "I bet to see where I'm at" | "Was that bet value or bluff?" |
| "I called because I might hit" | "How many outs? Vs. what *calling* range?" |
| "The board was scary, so I check-folded" | "What did *your* range look like there? What would Villain bet with?" |
| "Bad beat" (as explanation) | Redirect to decision quality; the result isn't the lesson. |
| "I just had a feeling" | "What read is that based on? How many data points?" |
| "I played it like the solver says" | "Are you sure? What's the stack depth / pool the solver was built for?" |

### Source discipline (important limits on this document)

- **This is 2016 source material.** Modern preflop charts (solver-derived) are looser than Will's intentionally-tight recommendations. Modern postflop GTO is more advanced than L2/L4 content. When a student asks about modern solver ranges or specific sim outputs, explicitly note the limit and point at the follow-on docs.
- **Don't claim certainty about what's "optimal"** for complex multi-street spots. Will himself repeatedly says "I don't think anyone knows the optimal strategy yet" for these. Heads-up push-fold Nash is the rare place where he gives exact numbers.
- **When quoting Will Ma directly**, use the passages already in this doc — they're verbatim-faithful. Don't invent new "Will Ma said" quotes.
- **Jennifer Shahade's L5 and Bill Chen's L8 were not recorded.** Don't manufacture content from those lectures. The one verified Shahade reference is the "Goldilocks / one long session" framing that Will cites in L7.

---

## Glossary — every term used in this course

> Organized by category. Terms are defined as Will uses them in the lectures.

### Hand strengths and made-hand types

- **Pocket pair** — two cards of the same rank as your hole cards (e.g., 99, AA). **Pocket aces** = AA, the best starting hand.
- **Set** — three of a kind made by holding a pocket pair and seeing that rank on the board (e.g., 5-5 in hand on a 5-J-T flop).
- **Trips** — three of a kind made with one hole card and two of that rank on the board.
- **Top pair / middle pair / bottom pair** — pairing the highest, middle, or lowest card on the flop with one of your hole cards.
- **Top kicker** — your second hole card is the highest possible (e.g., A-K on a K-7-2 flop = top pair top kicker).
- **Two pair** — *both* of your hole cards make a pair (e.g., A-K on a K-J-A board). Will is strict: pairing one hole card + a board pair does *not* count as "two pair" for stack-off purposes.
- **Overpair** — pocket pair higher than every card on the board.
- **Overcards** — your hole cards are higher than every card on the board (e.g., A-K on a 9-7-2 board has 6 outs to top pair).
- **Nuts** — the best possible hand on a given board.
- **Stone-cold nuts** — emphatic version of "nuts."
- **Boat / full house** — three of a kind plus a pair.
- **Quads** — four of a kind.
- **Straight flush / royal flush** — five-in-a-row of the same suit.

### Drawing terminology

- **Out** — an unseen card that improves your hand to (likely) the winner.
- **Open-ended straight draw (OESD)** — four-in-a-row needing the card on either end (~8 outs).
- **Gutshot / inside straight draw** — four cards to a straight needing exactly one rank in the middle (~4 outs).
- **Double gutter / double gutshot** — a non-obvious 8-out straight draw made from two interlocking gutshots (e.g., J-9 on K-T-7 → 8 or queen makes a straight, even though you're not "four-in-a-row").
- **Flush draw** — four to a flush, needing one more of that suit (~9 outs).
- **Backdoor draw** — needing *two more* cards (turn AND river) to complete a draw. Backdoor flush draws and backdoor straight draws contribute to total equity but aren't counted as full draws.
- **Drawing dead** — having 0 outs to win.
- **Showdown value** — your hand is good enough to win at showdown without needing to bluff or improve.

### Action terms

- **Open / open-raise** — be the first player to put in a raise preflop.
- **Limp** — call the big blind preflop instead of raising. Will: don't do this (Beginner Mistake #1).
- **3-bet** — re-raise (the BB is the "1-bet," the open is the "2-bet," the re-raise is the "3-bet"; same convention preflop and postflop).
- **4-bet, 5-bet** — re-raise the 3-bet, etc.
- **Squeeze** — 3-bet over both an open-raise and a caller, putting both opponents in a tough spot.
- **Continuation bet (c-bet)** — the preflop aggressor bets out on the flop.
- **Float** — call a c-bet with the intention of taking the pot away on a later street.
- **Check-raise** — check first, then raise after someone else bets in the same round.
- **Lead / donk-bet** — the non-preflop-aggressor bets out on the flop (instead of checking to the raiser). Considered tricky.
- **Slowplay / trap** — play a strong hand passively to disguise it.
- **Stop-and-go** — call preflop instead of shoving, then shove the flop unconditionally. Niche ICM play.
- **Shove / jam** — go all-in.
- **Cover** — your stack is bigger than your opponent's; you "cover" them.
- **Walk** — everyone folds to the big blind, who wins the small blind unopposed.

### Position

- **UTG (Under-the-Gun)** — left of big blind, first to act preflop.
- **UTG+1, UTG+2** — middle positions.
- **Lojack (LJ)** — 3 from the button.
- **Hijack (HJ)** — 2 from the button.
- **Cutoff (CO)** — 1 from the button (right of dealer).
- **Button (BU/BTN)** — the dealer; best position because they act last postflop.
- **Small Blind (SB), Big Blind (BB).**
- **In position (IP)** — you act after Villain on the relevant street(s).
- **Out of position (OOP)** — you act before Villain.

### Math and theory

- **Equity** — your share of the pot at showdown, expressed as a probability of winning.
- **Pot odds** — the ratio of (call amount) : (current pot you'd win). E.g., calling $8 into $24 pot = 3:1 odds, need 1/(3+1) = 25% equity.
- **Expected value (EV)** — probability-weighted average outcome. **+EV** = profitable on average; **−EV** = losing on average.
- **Implied odds** — the *additional* money you can win on later streets when your draw hits. Lets you call without immediate pot odds.
- **Reverse implied odds** — the *additional* money you'll lose on later streets with marginal hands. Forces you to fold hands that "have the odds."
- **Polarization / polarized range** — your range = (top hands for value) ∪ (bottom hands for bluffs); no medium hands. You bet big with this kind of range.
- **Linear range / merged range** — your range = top X% of hands, with no gaps. You bet smaller with these.
- **Way ahead / way behind** — situation where Villain either has a much worse hand (folds when you bet) or a much better hand (calls when you bet). Pot control by checking.
- **Adverse selection** — the situation where your bet only gets called by hands that beat you and only folds out hands you already beat.
- **Range** — the set of all hands Villain could plausibly hold given their actions so far. The unit of analysis for Levels 2 and 3 reasoning.
- **Combos / combinations** — number of ways to make a specific hand. AKs has 4 combos (one per suit); AKo has 12 combos (4 × 3 for the off-suit); a pocket pair has C(4,2) = 6 combos.
- **Card-removal / blockers** — having a card in your hand reduces the number of combos of certain Villain hands. Hero with the A♠ blocks Villain's nut flush draws and AA combos.
- **Effective stack size** — the smaller of (your stack, opponent's stack) — the actual maximum at risk.
- **Big blind (BB) as unit** — stack and bet sizes measured in BB are independent of the actual blinds level.
- **Cover** — to have more chips than another player (so you can put them all-in).

### Game-theory and strategy levels

- **Level 1** — "my hand vs. their hand." Wrong; never put Villain on a single specific hand.
- **Level 2 / Exploitative play** — model Villain's range and play the response that maximizes EV against that model.
- **Level 3 / Optimal play / GTO / Nash equilibrium** — choose a randomized strategy such that Villain has no profitable deviation.
- **Best response** — the strategy that maximizes EV against a fixed opponent strategy.
- **Iterated best response** — alternate computing best responses; converges to Nash.
- **Dominated strategy / hand** — a hand always beaten in matchup form (e.g., A-7 dominates A-3 because both have an ace and the first kicker is better).

### Tournament-specific

- **ICM (Independent Chip Model)** — formula converting tournament chip stacks to expected dollar payout. Assumes P(finish 1st) ∝ chip share.
- **Bubble** — the position right before payouts begin (e.g., 11th in an event paying top 10).
- **Final table** — last 9 (or whatever) players in a multi-table tournament, where ICM matters most.
- **Pay jump / ladder** — the discrete dollar increase between consecutive payout positions.
- **Stack depth (in BBs)** — how many big blinds you have. Different play depending on shallow (≤ 12 BB), medium (~25 BB), or deep (100+ BB).
- **Antes** — small forced bets each player puts in every hand; sum to ~1 BB. Late-tournament feature; absent from cash games.
- **Set mining** — calling preflop with a small pair hoping to flop a set.
- **Sit-and-go (SnG)** — small (often 9 or 6 player) one-table tournament with fixed payout structure.
- **Satellite** — a tournament whose prize pool is seats to a bigger tournament (everyone in the top N gets equal value).

### Behavioral / poker culture

- **Tilt** — playing badly because of emotional reactions (anger, frustration) to bad results.
- **Results-oriented** — judging plays by outcomes rather than EV. Negative term in poker; positive term outside it.
- **Bankroll** — total money you have set aside for poker.
- **Hit and run** — win a big pot in a cash game and immediately leave.
- **Multi-tabling** — playing multiple online tables simultaneously.
- **Fish / recreational player** — bad / casual player.
- **Shark** — strong / professional player.
- **Nitpick / nit** — extremely tight player who only plays premium hands.

### Tools mentioned in the course

- **PokerStove** — equity calculator. [Download via PokerBank](http://www.thepokerbank.com/tools/software/pokerstove/).
- **Holdem Manager 2** — hand-history tracking and HUD software (shown in slides).
- **Nash equilibrium calculators** — apps that solve preflop shove/call ranges. (Online ICM calculators serve a related purpose.)


## Resources & links — all in one place

### Course pages

- **Course home:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/>
- **Syllabus:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/pages/syllabus/>
- **Lecture slides index:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/pages/lecture-slides/>
- **Video lectures gallery:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/video_galleries/video-lectures/>
- **Assignments:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/pages/assignments/>
- **Study materials:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/pages/study-materials/>
- **Full course download:** <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/download/>
- **Internet Archive mirror (videos):** <https://archive.org/details/MIT15.S50IAP16>

### Lecture videos (YouTube)

- L1 — <https://www.youtube.com/watch?v=62nDLA_A8gs>
- L2 — <https://www.youtube.com/watch?v=uFsM8pc36QQ>
- L3 — <https://www.youtube.com/watch?v=KTzFk1s2ymE>
- L4 — <https://www.youtube.com/watch?v=_GgdGtQME1I>
- L6 — <https://www.youtube.com/watch?v=zlmokDj0DaU>
- L7 — <https://www.youtube.com/watch?v=u14ymLSF8y4>

### Lecture videos (downloadable MP4s, Internet Archive)

- L1: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L1_300k.mp4>
- L2: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L2_300k.mp4>
- L3: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L3_300k.mp4>
- L4: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L4_300k.mp4>
- L6: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L6_300k.mp4>
- L7: <https://archive.org/download/MIT15.S50IAP16/MIT15_S50IAP16_L7_300k.mp4>

### Lecture slides (PDFs, MIT OCW)

- L1: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/344b1adafb254e9925e712d0e1832129_MIT15_S50IAP16_L1.pdf>
- L2: <https://ocw.mit.edu/ans7870/15/15.S50/IAP16/MIT15_S50IAP16_L2.pdf>
- L3: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/aa986499d8d260e79708c7c48ebc1b0c_MIT15_S50IAP16_L3.pdf>
- L4: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/7cbdefd67186f0bbfb56790b976d7a82_MIT15_S50IAP16_L4.pdf>
- L6: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/5a8392e939175758331a28be9a64645c_MIT15_S50IAP16_L6.pdf>
- L7: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/ca4ca289859d44b9af3b786d4a5360f5_MIT15_S50IAP16_L7.pdf>

### Lecture transcripts (PDFs, MIT OCW)

- L1: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/3a2b8d0b59b02cd5e18b3e042bf55230_62nDLA_A8gs.pdf>
- L2: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/98a7f135b0794feacd5aeffdd4c8b133_uFsM8pc36QQ.pdf>
- L3: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/f102ce580666f88c0574c9a966e95a1b_KTzFk1s2ymE.pdf>
- L4: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/bfbd0df94ed6538b710070855ff2d5b6__GgdGtQME1I.pdf>
- L6: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/02adec22ced11914900976a4efa80016_zlmokDj0DaU.pdf>
- L7: <https://ocw.mit.edu/courses/15-s50-how-to-win-at-texas-holdem-poker-january-iap-2016/284dbaf79f3efe623f251890fab94a7c_u14ymLSF8y4.pdf>

### External references mentioned in the course

- **Texas Hold'em rules** — <https://www.pokernews.com/poker-rules/texas-holdem.htm#2-texas-hold-em-rule>
- **Hand rankings** — <https://www.cardplayer.com/rules-of-poker/hand-rankings>
- **PokerStove (equity calculator)** — <http://www.thepokerbank.com/tools/software/pokerstove/>
- **CardPlayer Hold'em odds calculator** — <http://www.cardplayer.com/poker-tools/odds-calculator/texas-holdem>
- **Jennifer Tilly "I thought you had pocket kings" video** — <http://www.poker.org/videos/jennifer-tilly-i-thought-you-had-pocket-kings-118900/>
- **Earlier version of this course (15.S50, IAP 2015 — different syllabus, also on OCW)** — <https://ocw.mit.edu/courses/15-s50-poker-theory-and-analytics-january-iap-2015/>

### Companion course

- **15.S50 Poker Theory and Analytics (IAP 2015)** — Will Ma's earlier offering. Different lecture order, different focus areas. Worth comparing for additional examples. <https://ocw.mit.edu/courses/15-s50-poker-theory-and-analytics-january-iap-2015/>

---

## Where this fits in your knowledge base

This is **Doc 1** of the larger poker training KB. It covers a full one-semester university intro to no-limit hold'em from a math/decision-theory perspective. Logical companion docs to build next:

1. **Modern preflop charts & ranges** — opening, 3-betting, 4-betting charts by stack depth, tournament vs. cash. The course's recommended ranges are intentionally tight; modern solver-derived ranges are looser.
2. **Postflop solver concepts** — beyond the Fundamental Theorem of Poker: range vs. range equity, equity realization, board texture analysis, blocker effects in modern GTO.
3. **ICM deep-dive** — full final-table strategy, FGS (future game simulation), bubble factor adjustments.
4. **Mental game & tilt management** — Jared Tendler's framework, A-game vs. C-game, bankroll psychology.
5. **Hand history review template** — a structured way to review a tournament/session and convert leaks into drills.
6. **Drill library** — flop equity quizzes, range vs. range battle calculations, ICM spots from real final tables.
7. **Modern training resources** — current comparisons of GTO Wizard, PioSolver, Run It Once, Upswing, etc., with specific course recommendations by skill level.

---

*Document generated from MIT OpenCourseWare 15.S50 (January IAP 2016), instructor Will Ma. Source materials available under [Creative Commons BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). All synthesis, organization, and added commentary in this document is original.*
