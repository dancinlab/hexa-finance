# 💰 hexa-finance — n=6 blockchain, cryptography, economics, finance, law and insurance substrate (11-verb library)

> 11-verb finance·blockchain·crypto·economics·law substrate organized as a closed-form spec catalog.
> Each verb derives every parameter from σ(6)=12, τ(6)=4, φ(6)=2 number theory.
> Sister-rollup of [hexa-mind](https://github.com/dancinlab/hexa-mind),
> extracted from `canon@ded52144` on 2026-05-10.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20114988.svg)](https://doi.org/10.5281/zenodo.20114988)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-informational.svg)](hexa.toml)
[![Verbs: 11](https://img.shields.io/badge/verbs-11-blue.svg)](#verbs)
[![n=6 lattice](https://img.shields.io/badge/n=6-σ·φ_=_n·τ_=_24-blue.svg)](#n6-master-identity)
[![verify 4/4](https://img.shields.io/badge/verify-4%2F4_PASS-brightgreen.svg)](#verify)
[![closure CLOSED](https://img.shields.io/badge/closure-CLOSED_11%2F11-brightgreen.svg)](hexa.toml)
[![not financial advice](https://img.shields.io/badge/NOT-financial_advice-red.svg)](LIMIT_BREAKTHROUGH.md)
[![not legal advice](https://img.shields.io/badge/NOT-legal_advice-red.svg)](LIMIT_BREAKTHROUGH.md)

---

## Why hexa-finance?

`hexa-finance` is the 💰 rollup of canon's finance·blockchain·crypto·economics·law verbs — the part of the
substrate concerned with blockchain, cryptography, economics, finance, law and insurance. Each leaf was previously embedded in
the larger `canon` monorepo; this standalone repo extracts 11 leaves
(`domains/compute/blockchain, domains/compute/cryptography, domains/infra/currency-economics, domains/infra/ecommerce-fintech, domains/infra/economics, domains/infra/economics-finance, domains/infra/insurance, domains/infra/jurisprudence, domains/infra/law-justice, domains/infra/marketing, domains/infra/monetary-history`) into a flat, top-level per-verb layout.

---

## n=6 master identity

```
σ(6) · φ(6) = n · τ(6) = J₂ = 24
   12   ·   2  =  6  ·   4  = 24
```

| Symbol | Value | Projection                                |
|--------|-------|-------------------------------------------|
| n      | 6     | substrate dimension                       |
| σ(6)   | 12    | full divisor sum                          |
| τ(6)   | 4     | divisor count                             |
| φ(6)   | 2     | totient                                   |
| J₂     | 24    | second Jordan totient                     |

---

## Install

```bash
# 1. Install hexa-lang (gives you `hexa` + `hx` package manager)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/dancinlab/hexa-lang/main/install.sh)"

# 2. Install hexa-finance
hx install hexa-finance
```

## Run

```bash
hexa-finance <verb>     # render any of 11 verbs (see `hexa-finance list`)
hexa-finance list       # verb table
hexa-finance selftest   # 11-verb spec presence sweep
```

---

## Verify

`hexa-finance` ships a 4-script SPEC_FIRST closure suite under `verify/`:

| # | Script | Anchor |
|---|--------|--------|
| 1 | `verify/spec_presence.hexa`       | 11/11 verb spec docs present + disclaimer rail (NOT financial advice / NOT legal advice / crypto speculative-high-risk caveat) |
| 2 | `verify/lattice_arithmetic.hexa`  | n=6 self-consistency (aux only per `LATTICE_POLICY.md §1.3`; **never** applied to external entities — CME, Nasdaq, Binance, SEC, CFTC, BoK, Bitcoin, Ethereum use their **own** specs, raw#10 C3) |
| 3 | `verify/real_limits_anchor.hexa`  | `LIMIT_BREAKTHROUGH.md` anchors: EMH · sqrt-law · Arrow · Akerlof · Shor · Bitcoin 21M cap · ~10 min block · Ethereum gas/block · Basel III · MiCA · SEC Rule 10b-5 · FATF Travel Rule · ZLB · statutory usury · MiFID II |
| 4 | `verify/closure_consistency.hexa` | Scoreboard cross-check: CLI · `hexa.toml` · README badge · AGENTS.md |

Run the aggregate sweep:

```bash
hexa run verify/run_all.hexa     # exit 0 ⇒ all 4 scripts PASS
```

### Honesty rails (load-bearing, finance/legal)

- **NOT financial advice.** No alpha promise. EMH semi-strong (Fama 1970) is approximately HARD after costs; the sqrt-law (Almgren-Chriss) caps capacity.
- **NOT legal advice.** Consult a licensed attorney / counsel in your jurisdiction. Statutes (SEC Rule 10b-5, FATF, MiCA, MiFID II, Basel III, usury caps) bind by jurisdiction, not by `σ(6)=12`.
- **Crypto verbs preserve:** speculative, high-risk, **unregulated in many jurisdictions**. Cryptographic hardness (factoring, DLP, SHA-256 collision) and protocol limits (Bitcoin 21M cap, ~10 min blocks, BFT n ≥ 3f+1) are HARD walls.
- **No lattice-fit on externals.** Per `LATTICE_POLICY.md §1.3 rule 4`, exchanges (CME, Nasdaq, Binance), regulators (SEC, CFTC, FSA, BoK), and blockchains (Bitcoin, Ethereum) use *their own* specs — no `n=6` mapping.

---

## Cross-link

- 🧠 [dancinlab/hexa-mind](https://github.com/dancinlab/hexa-mind) — 7-verb mental substrate.
- 💎 [dancinlab/hexa-lang](https://github.com/dancinlab/hexa-lang) — the perfect-number programming language.

Upstream concept SSOT: `canon/{domains/compute/blockchain,domains/compute/cryptography,domains/infra/currency-economics,domains/infra/ecommerce-fintech,domains/infra/economics,domains/infra/economics-finance,domains/infra/insurance,domains/infra/jurisprudence,domains/infra/law-justice,domains/infra/marketing,domains/infra/monetary-history}/`.

---

## Status

**SPEC_CATALOG_ONLY at v0.1.0** — markdown spec library + .hexa CLI router. No verb
ships a working .hexa runtime module yet; this repo is the closed-form spec
catalog only.

---

## License

MIT. See [LICENSE](LICENSE).
