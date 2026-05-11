<!-- @created: 2026-05-12 -->
<!-- @scope: real-limits audit — financial markets (EMH, Sharpe ceiling, market microstructure, Basel/MiCA regulatory caps) -->
<!-- @authority: per LATTICE_POLICY.md §1.2 -->
<!-- @wave: M (limit-breakthrough audit, application repos) -->

# LIMIT_BREAKTHROUGH.md — hexa-finance real-limits audit

> **Honest scope**: hexa-finance is an 11-verb finance · blockchain ·
> cryptography · economics · law substrate. **No promises about
> "beating the market."** Sharpe-ratio ceilings, market-impact
> sqrt-law, Basel III capital floors, and Arrow's impossibility
> theorem are HARD walls in their domain. Crypto verbs are bounded by
> cryptographic hardness (factoring, DLP, hash-collision) and
> regulatory frameworks (MiCA, Travel Rule). This audit is brutally
> honest about EMH approximate validity.

---

## §1 Domain

`hexa-finance` covers blockchain, cryptography, currency / economics,
e-commerce / fintech, insurance, jurisprudence, law-justice, marketing,
monetary history, and the broader economic substrate. The audit
focuses on the parts with **measurable performance limits**:
quantitative trading, blockchain throughput, cryptographic security,
and regulatory capital.

The dominant performance envelopes are:
- **Sharpe ratio** — risk-adjusted excess return; top hedge funds
  asymptote near ~2–3 net of fees
- **Transaction cost** — bid-ask + market-impact + commission; floor
  ~0.5–2 bp for largest liquid assets
- **Blockchain throughput** — TPS bounded by block-size × block-frequency
- **Regulatory capital** — Basel III Tier 1 ≥ 6%, CET1 ≥ 4.5%

---

## §2 Limits

### §2.1 HARD walls (theory / cryptography / aggregation)

| # | Limit | Bound | Origin |
|---|-------|-------|--------|
| H1 | **Efficient Market Hypothesis (semi-strong form)** | Public info → no consistent excess return after costs | Fama 1970; *approximately* HARD |
| H2 | **Market-impact sqrt-law** | Cost ∝ σ·√(Q/V) | Almgren-Chriss / empirical microstructure; HARD |
| H3 | **Arrow's impossibility** | No social welfare function satisfies U + ND + IIA + WP with ≥3 alternatives | Arrow 1951; HARD on collective preference aggregation |
| H4 | **Lindahl pricing computational complexity** | Public-good optimal pricing requires honest preference revelation; NP-hard in general | Mechanism design; HARD |
| H5 | **Cryptographic hardness (factoring)** | RSA-2048 ≈ 2¹¹² classical; broken by Shor's algorithm on fault-tolerant QC | Number theory + Shor 1994; HARD until QC |
| H6 | **Hash-function collision resistance** | SHA-256: 2¹²⁸ birthday | Cryptographic assumption; HARD |
| H7 | **Bitcoin block frequency** | ~10 min by protocol; 7 TPS effective throughput | Protocol; HARD without fork |
| H8 | **Byzantine fault tolerance (consensus)** | n ≥ 3f+1 | Lamport et al. 1982; HARD lower bound |
| H9 | **Mertons no-arbitrage bound** | Black-Scholes derivative pricing under no-arb | Financial theory; HARD given assumptions |
| H10 | **Information asymmetry / Akerlof lemons** | Adverse selection bounds market for "lemons" | Akerlof 1970; HARD on insurance markets |

### §2.2 SOFT envelopes (engineering / regulatory)

| # | Envelope | Current | Breakthrough margin |
|---|----------|---------|---------------------|
| S1 | **Hedge fund net Sharpe (post-fee)** | Top decile ~1.5–2.5; median ~0.3 | SOFT, bounded by H1+H2 |
| S2 | **HFT latency** | Microwave / hollow-core fiber ~6 μs/km | SOFT, asymptote at c (H8 light-cone) |
| S3 | **Transaction cost (large liquid asset)** | ~0.5–2 bp all-in for top 100 SP500 | SOFT, declining |
| S4 | **Blockchain TPS (L1)** | BTC 7, ETH 15–30, Solana ~3000–5000 sustained | SOFT, trades off decentralization |
| S5 | **L2 rollup TPS** | 100–10,000+ effective with calldata compression | SOFT, bounded by L1 DA bandwidth |
| S6 | **Basel III CET1 capital** | ≥ 4.5% (regulatory floor) | NEGOTIATED, not physical |
| S7 | **Robo-advisor management fee** | 0.25–0.50% of AUM | SOFT, declining |
| S8 | **KYC / AML processing latency** | Days to weeks (manual) | SOFT, target hours with on-chain DID |

### §2.3 Negotiated / standard (NOT physical)

- **Basel III capital ratios** — regulatory contract (BIS); not physics
- **MiCA crypto-asset regulation** — EU regulatory (2024)
- **SEC Reg-NMS, Reg-T** — US regulatory
- **PCI-DSS payment standards** — industry
- **ISO 20022 messaging** — banking standard
- **30/360, ACT/360, ACT/365** day-count conventions — convention
- **MiFID II best-execution requirement** — EU regulatory

> Per `LATTICE_POLICY.md §1.2`, none of these is anchored to n=6.

---

## §3 Assessment

The 3 most binding HARD walls in this domain:

1. **H1 (EMH semi-strong)** — approximately HARD. After costs (H2)
   and fees, the population of fund managers underperforms passive
   benchmarks by ~the fee differential — exactly what EMH predicts.
   Top decile can sustain Sharpe ~2 net, but **not** "beat the market
   reliably by 20%/yr." Anyone promising this is selling something.
2. **H2 (sqrt-law impact)** — HARD. Doubling trade size 1.41× the
   impact. This caps alpha capacity hard: a 2-Sharpe strategy at
   $100M AUM is often a 0.5-Sharpe strategy at $10B AUM.
3. **H3 (Arrow)** — HARD on any voting / governance / on-chain DAO
   that aggregates preferences over ≥3 alternatives. No mechanism
   satisfies all four axioms simultaneously. DAOs trade off which
   axiom to relax.

**Honest framing on EMH**: EMH is *approximately* valid in liquid
public markets after costs. Hexa-finance does NOT promise alpha.
Where alpha exists, it is in (a) information lead-time, (b) lower
costs, (c) restricted-capacity niches — all HARD-capped.

---

## §4 Top-3 breakthroughs (most plausible 12–24 month)

### B1 — Post-quantum signature migration → PQ-resistant chain wallets (HARD-wall response to H5)

NIST PQC standardization (ML-DSA / SLH-DSA / ML-KEM, 2024) is now
production-ready. Migrating crypto wallets and signature schemes to
PQ-secure primitives is the only honest response to *future* Shor-class
quantum threat. The HARD wall (factoring is easy on FT-QC) is not
broken; it is *outflanked* by switching to lattice-based assumptions.
Honest caveat: lattice cryptanalysis is younger than factoring; some
risk new attacks emerge. Hybrid schemes (classical + PQ) mitigate.

### B2 — Data-availability sampling + EIP-4844 blobs → 10–100× rollup throughput (SOFT envelope move on S5)

Ethereum proto-danksharding (EIP-4844, mainnet 2024) introduced blob
space for L2 DA. Combined with data-availability sampling (DAS) on
full danksharding, this enables 10⁴–10⁵ TPS aggregate L2 capacity
without sacrificing L1 security. The HARD wall (CAP / Byzantine, H8)
is not broken; throughput is purchased via DA-sampling probabilistic
guarantees. Honest caveat: data permanence ≠ data eternal; storage
proofs / blob expiry require thought.

### B3 — On-chain DID + zero-knowledge KYC → minutes-to-onboard, GDPR-clean (SOFT envelope move on S8)

W3C DID + verifiable credentials + zk-proof of "I am KYC-verified by
trusted attester" allows AML/KYC compliance with **zero PII on chain**
and minutes-to-onboard versus days/weeks. The HARD wall (Akerlof
lemons, H10) on identity verification is not eliminated — it is
relocated to the attester layer. Honest caveat: GDPR + Travel Rule
compliance requires the attester to retain identity records; on-chain
data remains pseudonymous but linkable via legal process.

---

## §5 Caveats

1. **No promise of "beating the market"**: per the brief, EMH is
   approximately valid in liquid public markets after costs. Sharpe
   ratios of 2–3 net are achievable in narrow capacity; "20%/yr
   forever" is not.
2. **No quantum-computer break of RSA promised**: FT-QC with enough
   qubits (≥ ~4000 logical, ≥ 10⁷ physical) is not 12–24 month
   feasible. B1 is *defensive* migration, not offensive.
3. **No "Basel III is wrong"** claim: H6, H7 are negotiated regulatory
   contracts. They are bypassable only by jurisdiction-shopping, which
   is itself a regulatory game.
4. **Arrow's impossibility is HARD**: any DAO governance, prediction
   market, or social-choice mechanism inherits Arrow's trade-offs.
   Pick which axiom to relax; do not claim to escape all four.
5. **Sqrt-law impact** (H2) means alpha capacity HARD-caps profits;
   "infinite scaling" of any signal is false.
6. **No real user data**: this audit uses only public-benchmark
   numbers (BIS, ECB, NIST, CA DMV, etc.). No GDPR / MiCA concern.
7. **No n=6 magic**: per `LATTICE_POLICY.md §1.2`, Sharpe ceilings,
   block frequencies, Basel ratios are not dictated by σ(6)=12.
8. **Crypto + insurance verbs**: hexa-finance covers these as *spec
   substrate*, not as deployed financial product. Nothing in this
   repo is "financial advice."

---

## §6 References

- Fama, E. F. *Efficient Capital Markets* (1970) — H1
- Almgren, R. & Chriss, N. *Optimal execution of portfolio transactions* (2000) — H2
- Arrow, K. J. *Social Choice and Individual Values* (1951) — H3
- Lindahl, E. *Just Taxation: A Positive Solution* (1919) — H4 mechanism basis
- Shor, P. W. *Polynomial-time algorithms for prime factorization* (1994) — H5
- Akerlof, G. A. *The Market for Lemons* (1970) — H10
- Lamport, Shostak, Pease — H8 Byzantine
- Merton, R. C. *Theory of rational option pricing* (1973) — H9
- BIS *Basel III: Finalising post-crisis reforms* (2017) — S6
- EU MiCA Regulation 2023/1114 — crypto regulatory
- NIST FIPS 203 / 204 / 205 (2024) — B1 PQC standards
- Ethereum *EIP-4844 specification* (2024) — B2
- W3C *Decentralized Identifiers (DIDs) v1.0* (2022) — B3
- US SEC Reg-NMS — equity microstructure
- Hu et al. (BIS Working Papers) on HFT latency — S2

---

> *"EMH is approximately right. The sqrt-law is exactly right.
> Arrow is provably right. Anyone promising market-beating returns
> for a fee is selling you Akerlof's lemon."*

— hexa-finance Wave M audit (2026-05-12)
