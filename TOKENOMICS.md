# $COMMONS Tokenomics

> **Status:** Direction set; genesis mechanics under active design. This document records
> the reasoning and the decisions made so far. Sections marked *(under design)* are not
> final — the exact formulas, thresholds, and allocations are being worked out.

---

## Principles

$COMMONS follows the same ethos as the rest of SORA Commons:

- **Earned by the record, never bought or farmed.** Tokens flow to demonstrated, verifiable
  work — not to signups, promises, or presence.
- **No pay-to-rank.** Holding or earning $COMMONS does not buy visibility or influence over
  the record.
- **Honesty over polish.** The distribution mechanism should embody the values, not
  contradict them.

Two mechanisms are already locked (see the main build/design notes):

- **Dual burn:** $COMMONS buys and burns XOR via a buy-back-and-burn (BBB), plus a direct
  $COMMONS burn.
- **Polkaswap** as the DEX infrastructure.

---

## Cold Start & Genesis Distribution (direction — mechanics under design)

### The problem

SORA Commons is a two-sided market: builders need backers, and backers need builders worth
backing. At mainnet launch, each side waits on the other — the classic cold-start deadlock.

### The approach

The initial $COMMONS distribution IS the cold-start incentive. Rather than a sale, an
airdrop to signups, or LP farming, the first $COMMONS is earned by the early record —
awarded retroactively to the builders and backers who produced real, verifiable activity in
the opening mainnet window. The genesis distribution literally is the early record.

### Two-sided by necessity

- **Builders** earn by delivering — completing real proposals with real backing.
- **Backers** earn by backing deliverers — donating to builders who go on to complete their
  work.

This is structural, not optional. A builder-only reward undercuts itself: the builder
eligibility bar ("completed a proposal with real backers") can't be met if backers have no
reason to show up. Both sides must be incentivized, or neither activates.

### Why it fits the ethos

- **Earned by the record.** Rewards gate on delivery — expensive to fake, and visible to the
  challenge window — not on presence or promises.
- **Backing real work is itself a contribution.** A donation is the most concrete value
  signal in the system: real XOR at risk on unproven builders, and it triggers the burn.
  Early backers took a risk before there was social proof; rewarding them gives the people
  who bootstrapped the network a stake in it.
- **The mechanism embodies the values.** No pay-to-rank, no manufactured activity.

### Key design clause: anti-farming

Backer rewards weight toward backing builders who deliver — not flat per-donation — so the
incentive is to fund likely-deliverers, not to spray tiny donations to farm the reward. Both
sides pull in the same direction: backers are rewarded for discernment (funding work that
gets completed).

---

## Open Design Questions (dedicated design session)

1. **Eligibility & weighting.** "Completed a proposal" is the clean line for builders. Open:
   whether and how to weight rewards by real backing received without enabling self-dealing.

2. **Window & pool.** The length of the cold-start window (e.g. launch to month 3) and the
   fixed percentage of total supply allocated to the genesis cohort.

3. **Anti-sybil / anti-collusion.** Real XOR and real $COMMONS at stake raise the
   fake-delivery incentive above testnet levels. The attack: one actor running a builder
   account plus several backer accounts, self-funding a proposal, delivering it, and
   collecting on both sides. The self-support guard blocks donating to your own proposal, but
   not a colluding ring. Candidate mitigations:
   - A minimum number of distinct real backers for reward eligibility.
   - Reward weighting that diminishes for concentrated backing — many small backers count
     for more than one whale.
   - Using the challenge window as a vesting / verification cooling period before rewards
     finalize.

---

## Highest-Leverage Non-Token Lever

Incentives amplify a working thing; they don't create one from zero. The most important
cold-start action is not a token mechanic: seed a handful of genuinely good, real proposals —
builders already doing public-good or dev work in the SORA ecosystem — so the record has real
substance from day one. Backers show up for work worth backing, not for an empty feed. Do
this first; let the incentives amplify it.
