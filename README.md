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

---

## Why hexa-finance?

`hexa-finance` is the 💰 rollup of canon's finance·blockchain·crypto·economics·law verbs — the part of the
substrate concerned with blockchain, cryptography, economics, finance, law and insurance. Each leaf was previously embedded in
the larger `canon` monorepo; this standalone repo extracts 11 leaves
(`domains/compute/blockchain, domains/compute/cryptography, domains/infra/currency-economics, domains/infra/ecommerce-fintech, domains/infra/economics, domains/infra/economics-finance, domains/infra/insurance, domains/infra/jurisprudence, domains/infra/law-justice, domains/infra/marketing, domains/infra/monetary-history`) into a flat, top-level per-verb layout.

---

## Verbs

| Verb | Spec | Concern | Status |
|------|------|---------|--------|
| `blockchain` | [blockchain/blockchain.md](blockchain/blockchain.md) | blockchain substrate | grounded |
| `cryptography` | [cryptography/cryptography.md](cryptography/cryptography.md) | cryptography substrate | grounded |
| `currency-economics` | [currency-economics/currency-economics.md](currency-economics/currency-economics.md) | currency economics substrate | grounded |
| `ecommerce-fintech` | [ecommerce-fintech/ecommerce-fintech.md](ecommerce-fintech/ecommerce-fintech.md) | ecommerce fintech substrate | grounded |
| `economics` | [economics/economics.md](economics/economics.md) | economics substrate | grounded |
| `economics-finance` | [economics-finance/economics-finance.md](economics-finance/economics-finance.md) | economics finance substrate | grounded |
| `insurance` | [insurance/insurance.md](insurance/insurance.md) | insurance substrate | grounded |
| `jurisprudence` | [jurisprudence/jurisprudence.md](jurisprudence/jurisprudence.md) | jurisprudence substrate | grounded |
| `law-justice` | [law-justice/law-justice.md](law-justice/law-justice.md) | law justice substrate | grounded |
| `marketing` | [marketing/marketing.md](marketing/marketing.md) | marketing substrate | grounded |
| `monetary-history` | [monetary-history/monetary-history.md](monetary-history/monetary-history.md) | monetary history substrate | grounded |

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

### Via `hx` (works today)

```bash
hx install hexa-finance --entry cli/hexa-finance.hexa
hexa-finance --version           # → 0.1.0
hexa-finance selftest            # → 11/11 verb specs PASS
```

### CLI subcommands

```bash
hexa-finance list                # 11-verb table
hexa-finance <verb>              # read verb spec (path + first 20 lines)
hexa-finance selftest            # 11/11 spec presence sweep
```

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
