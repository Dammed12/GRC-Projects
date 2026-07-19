# FAIR Risk Quantification Case Study
## Should Meridian Advisory Group Fund a Security Awareness Program?

**Prepared by:** [Your Name], Risk Analyst
**For:** Meridian Advisory Group Leadership Team
**Date:** [Date]
**Model used:** Factor Analysis of Information Risk (FAIR), per FAIR Institute guidance
**Classification:** Internal — Risk Management

---

## Executive Summary

Meridian Advisory Group experienced a spike in phishing attempts against staff over the past two
quarters. Leadership asked a direct question: *is it worth spending $80,000 a year on a
Security Awareness & Simulation Program, or is that money better spent elsewhere?*

Rather than answer with a color on a heat map, the risk management unit quantified the
phishing risk in dollars using the FAIR model. The finding: the phishing scenario carries
an **annualized loss exposure of $500,000**. The proposed program is expected to cut that
exposure by roughly 60%, bringing total annual risk cost (residual loss + program cost)
down to **$280,000** — a **net saving of $220,000 per year** and a **275% return on the
security investment**.

**Recommendation: fund the program.** The decision remains cost-justified even under
conservative assumptions, which is the strongest form of a quantitative conclusion.

---

## 1. Background — The Business Problem

Meridian Advisory Group is a Governance, Risk & Compliance consulting firm. Its core asset is the
**sensitive client project data** it holds on behalf of multiple corporate clients —
exactly the kind of data a breach would make both costly and reputationally damaging.

Over the last six months, staff reported a rising volume of phishing emails, several
sophisticated enough that employees clicked before recognizing the threat. The security
team flagged the trend. In response, a vendor proposed a **Security Awareness & Simulation
Program** — ongoing training plus simulated phishing campaigns — at **$80,000 per year**.

Leadership didn't want a gut call on whether to buy it. The CFO's question was blunt:
*"Show me the money. What is this risk actually costing us, and what does $80,000 buy us
back?"* That question is what makes this a FAIR problem — FAIR exists to translate risk
into the financial language leadership actually makes decisions in.

---

## 2. Defining the Risk Scenario

A FAIR analysis is only as good as the scenario it's scoped to. A vague scenario produces
meaningless numbers. This engagement analyzed one specific loss event:

> **"A phishing attack could compromise client project data."**

| Scoping element | Definition |
|-----------------|------------|
| **Asset** | Client project data (confidential, held under client contracts) |
| **Threat** | External phishing actor targeting Meridian Advisory Group staff |
| **Threat vector** | Malicious email leading to credential theft or malware |
| **Loss form** | Confidentiality breach of client data |

Everything downstream — every number — is measured against *this* scenario. A different
scenario (e.g. ransomware, insider misuse) would need its own separate analysis.

---

## 3. The Analysis

FAIR decomposes risk into two branches: **how often** a loss happens (Loss Event
Frequency) and **how much** it costs when it does (Loss Magnitude). Multiplied together,
they give Annualized Loss Exposure (ALE).

### 3.1 Loss Event Frequency (LEF)

| Factor | Input | Source / Basis |
|--------|-------|----------------|
| Threat Event Frequency (TEF) | 25 phishing attempts / year | Email security gateway logs, trailing 12 months |
| Susceptibility (P of success) | 20% | Historical click-through + credential-entry rate from prior incidents |
| **Loss Event Frequency** | **25 × 0.20 = 5 / year** | Calculated |

> **Analyst note on inputs:** TEF is well-grounded — it comes straight from gateway logs.
> Susceptibility (20%) is the softer number, estimated from a small sample of past
> incidents. It is the input most worth challenging, so it is stress-tested in Section 6.

### 3.2 Loss Magnitude (per event)

FAIR separates **Primary Loss** (direct costs you will certainly incur) from **Secondary
Loss** (downstream, conditional costs — often larger and harder to bound).

| Loss type | Components | Estimate |
|-----------|-----------|----------|
| Primary Loss | Incident response, forensics, recovery, staff time | $40,000 |
| Secondary Loss | Legal fees, client notification & compensation, reputational damage | $60,000 |
| **Total Loss per Event** | Primary + Secondary | **$100,000** |

### 3.3 Annualized Loss Exposure (ALE)

```
ALE = Total Loss per Event × Loss Event Frequency
ALE = $100,000 × 5
ALE = $500,000 per year
```

**The phishing scenario, unmitigated, costs Meridian Advisory Group an expected $500,000 per year.**

---

## 4. Evaluating the Proposed Control

The Security Awareness Program works by making staff less likely to fall for phishing. In
FAIR terms, it reduces **Susceptibility** — which flows through to a lower LEF, and
therefore a lower ALE.

**Critical modeling point:** the program reduces how *often* a breach happens, not how
*much* each breach costs. Loss Magnitude stays at $100,000 per event. Getting this mapping
right is the difference between a credible analysis and hand-waving — a common error is to
claim training somehow makes breaches cheaper.

| Factor | Value | Basis |
|--------|-------|-------|
| Expected reduction in phishing success | 60% | Vendor benchmark, adjusted down for realism |
| New Susceptibility | 20% × (1 − 0.60) = 8% | Calculated |
| New Loss Event Frequency | 5 × 0.40 = 1.92 ≈ 2 / year | Calculated |
| New ALE (residual risk) | $100,000 × 1.92 = ~$200,000 | Calculated |
| Program cost | $80,000 / year | Vendor quote |
| **Total annual cost with control** | $200,000 + $80,000 = **$280,000** | Residual loss + control |

---

## 5. The Decision

| Option | Annual Loss | Control Cost | Total Annual Cost | Net Savings |
|--------|-------------|--------------|-------------------|-------------|
| **Do nothing** | $500,000 | $0 | $500,000 | — |
| **Fund the program** | $200,000 | $80,000 | $280,000 | **$220,000** |

```
Net annual savings = $500,000 − $280,000 = $220,000
Return on Security Investment (ROSI) = $220,000 ÷ $80,000 = 275%
```

Spending $80,000 removes $300,000 of expected annual loss. Even after paying for the
program, Meridian Advisory Group is $220,000 per year better off. **The program is strongly justified.**

---

## 6. Assumptions & Sensitivity Analysis

A single-point answer can hide fragility. The real test is whether the recommendation
survives when the soft inputs move. It does.

| Assumption | Base case | Stress test | Effect on decision |
|------------|-----------|-------------|--------------------|
| Susceptibility | 20% | If actually 30% | Baseline ALE rises to $750K — control looks *better* |
| Control effectiveness | 60% reduction | If only 40% | Residual ALE = $300K; savings shrink to $120K — still positive |
| Secondary Loss | $60,000 | Likely understated | Any increase strengthens the case for the control |
| TEF | 25/year | From logs, re-check annually | Stable; low uncertainty |

**Conclusion of sensitivity analysis:** across the full plausible range of inputs, funding
the program remains cost-justified. The decision does not hinge on optimistic assumptions —
it holds even at the pessimistic end. That robustness is what gives the recommendation its
credibility.

---

## 7. Recommendation & Next Steps

**Recommendation:** Approve the $80,000/year Security Awareness & Simulation Program.

**Rationale:**
1. It reduces annualized loss exposure from $500,000 to ~$200,000.
2. Net of its own cost, it saves $220,000 per year (275% ROSI).
3. The conclusion is robust to conservative assumptions.

**Next steps:**
- Baseline current phishing susceptibility before rollout, to measure real reduction.
- Re-run this FAIR analysis after 12 months using actual post-program click-through data.
- Feed this analysis into a formal risk acceptance / treatment decision (see Project 05).

---

## 8. Limitations

This analysis is a decision-support tool, not a guarantee. Its figures are informed
estimates, and FAIR's dollar precision can create false confidence if the inputs behind it
aren't scrutinized. The numbers should be revisited as real data accumulates, and the
scenario re-scoped if the threat landscape shifts (e.g. a move from credential phishing to
ransomware). The strength of this analysis is not that it is exactly right — it is that it
makes the reasoning explicit and testable.

---

*Prepared using the FAIR model (Factor Analysis of Information Risk). This document
demonstrates quantitative risk analysis for decision support and is illustrative, based on
a fictional case study.*
