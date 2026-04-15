# zivana-oracle

Revenue attestation infrastructure for the Zivana Protocol, built on 
the [Cardano Open Oracle Protocol (COOP)](https://developers.cardano.org/docs/build/integrate/oracles/orcfax/) 
and powered by [Orcfax](https://orcfax.io).

This repository solves the hardest problem in bringing informal 
economy finance on-chain: how do you verify that a market trader in 
Lagos generated real revenue, and publish that verification in a form 
that a smart contract can trust and act on?

The answer is a tiered attestation architecture — starting with 
platform-attested on-chain fact statements and progressing to direct 
marketplace and mobile money API attestations as the protocol matures.

---

## What lives here

| Component | Purpose |
|---|---|
| Attestation schema | Orcfax COOP fact statement schema for SME revenue events |
| Tier 1 publisher | Platform-attested revenue fact statement publisher — auditable, on-chain |
| Tier 2 connectors | Marketplace and mobile money API connectors (Flutterwave, Paystack) |
| Multi-source triangulator | Requires minimum 2 independent sources before Tier 2 publication |
| Oracle node operator | Full node operator setup for running a Zivana attestation node |
| Charli3 integration | Price feed integration for ADA/NGN and multi-currency conversion |

---

## Attestation Tiers

| Tier | Source | Status |
|---|---|---|
| Tier 1 | Platform-attested | Phase 1 — centralised but fully auditable on-chain |
| Tier 2 | Marketplace and mobile money APIs | Phase 2 — semi-decentralised, multi-source |
| Tier 3 | Banks and mobile network operators | Post-mainnet roadmap |

---

## Protocol Context

`zivana-oracle` feeds directly into the Distribution primitive:

Revenue event → Oracle attestation → Distribution validator → 4 output UTxOs

Full protocol documentation: [zivana-docs](https://github.com/zivana-labs/zivana-docs)

---

## Development Status

> Phase 0 — Orcfax integration verification and attestation schema definition

This repository is under active early development. The attestation 
schema is being tested on Cardano testnet against live Orcfax 
infrastructure before any production deployment.

---

## Getting Started

Prerequisites:
- Node.js 18+
- Cardano preprod access via Blockfrost
- Orcfax testnet access

```bash
# Clone the repository
git clone https://github.com/zivana-labs/zivana-oracle.git
cd zivana-oracle

npm install
cp .env.example .env
# Configure BLOCKFROST_API_KEY and ORCFAX_NODE_URL in .env

npm run dev
```

Full setup guide: coming in Phase 0 documentation.

---

## Contributing

Read the [contributing guidelines](https://github.com/zivana-labs/.github/blob/main/CONTRIBUTING.md) 
before opening a pull request. All PRs target the `develop` branch.

## Licence

MIT — see [LICENSE](./LICENSE)

---

*Part of [Zivana Labs](https://github.com/zivana-labs) — 
built for African, open to the world.*
