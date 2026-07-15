# SORA Commons

**A public record where real work becomes visible.**

SORA Commons is a web application where builders share what they're making, prove it step by step, and earn direct support — with every contribution tied to real, verifiable progress.

It is built on **[SORA Nexus](https://sora.org)** and the **[Iroha 3](https://github.com/hyperledger-iroha)** ledger, developed by [Soramitsu](https://soramitsu.co.jp). SORA Commons is an independent application built on this ecosystem; it targets Iroha 3 as its settlement layer.

Motto: **Productive work burns true.**

---

## What it is

Most funding platforms ask you to trust a promise. SORA Commons asks you to show the work.

A builder posts a proposal broken into **chapters** (milestones). As each chapter is delivered, they present real evidence — a link, a receipt, a document, a photo. Backers who believe in the work donate directly. There are no gatekeepers deciding who gets funded, and no fee skimmed off the top: **99% of every donation goes to the builder, and 1% is burned.**

The record of what was promised, what was delivered, and what was disputed stays public and permanent. That record *is* the product.

---

## Philosophy

- **Honesty over polish.** No fake data, no vanity defaults. A new account shows real zeros, not inflated numbers.
- **The burn rides on real value, never a toll.** The 1% burn isn't a fee the platform collects — it's destroyed. Nothing is extracted.
- **Isonomia — no pay-to-rank.** Visibility can't be bought. Boosts are free but scarce, so a boost actually means something.
- **The record is the product.** Flags, disputes, and responses live on the record permanently.
- **No verdicts.** The challenge window makes disputes *visible* — it does not adjudicate.
- **Stakes match safeguards.** The project launches low-stakes and adds trust machinery only as real value at stake grows.

---

## How it works

1. **Post** — a builder publishes a proposal: the story, the chapters, and the evidence they commit to presenting for each.
2. **Deliver** — as work progresses, the builder marks each chapter delivered and presents the actual evidence. This is a *claim* on the public record.
3. **Challenge window** — after a delivery, backers have a window to raise flags. Flags, and the builder's responses, stay on the record permanently.
4. **Support** — backers donate XOR directly. 99% reaches the builder; 1% burns.

---

## Architecture

- **Chain (Iroha 3)** — money and identity. Donations, burns, and wallet-proven identity settle on-chain.
- **Database (Supabase / Postgres)** — the social record. Proposals, chapters, comments, flags, documents, and donation records live here as a fast, queryable mirror.
- **If they ever disagree on money, the chain wins.**

**Stack:** Vue 3 (`<script setup>`) + Pinia + hosted Supabase. Money is handled with exact precision (integer/BigInt base units, stored as text, never floats).

**Chain target:** SORA v3 / SORA Nexus (Iroha 3). Taira testnet and Minamoto mainnet.

---

## Status

Early-stage, under active development.

- **Live:** the full social experience — posting, chapters, delivery + evidence, the challenge window, comments, follows, boosts, saves, search, profiles, a burn/donation treasury record, and realtime updates.
- **Preview:** donations currently update in-app totals so the experience can be seen and refined. **No real XOR moves yet.**
- **Waiting on the ecosystem:** real wallet authentication and on-chain XOR land when **SoraSwap** (the v3 wallet) ships. Until then a mock wallet stands in.

Escrow, a Treasury Desk, and formal review are **Phase 2** — they matter once there's real value at stake.

---

## Local setup

**Prerequisites:** Node.js and npm, plus a Supabase project.

```bash
git clone https://github.com/ManOfTomorrow-xor/sora-commons-web.git
cd sora-commons-web
npm install
cp .env.example .env   # then fill in your Supabase values
```

Your `.env` needs:
Run it:

```bash
npx vite --config vite.config.ts   # dev server → http://localhost:5174
npx vite build --config vite.config.ts   # production build → dist/web
```

---

## Roadmap

**Phase 1 (current)** — the public record and direct donations on testnet.

**Phase 2** — real XOR on-chain (Iroha 3 ISIs, exact 1% split, on-chain burn), real wallet auth via SoraSwap, and — as stakes grow — escrow, a Treasury Desk, and formal review.

---

## License

Licensed under the [Apache License 2.0](LICENSE).

---

*Built on SORA Nexus. Productive work burns true.*
