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
