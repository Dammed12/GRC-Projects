# FAIR Analysis — Meridian Advisory Group Phishing Risk

**Model:** Factor Analysis of Information Risk (FAIR)
**Scenario:** Phishing attack compromising client project data
**Decision under review:** Fund a $80,000/year Security Awareness & Simulation Program?
**Analyst:** [Your Name]
**Date:** [Date]

---

## 1. Risk Scenario

> *"A phishing attack could compromise client project data."*

| Element | Value |
|---------|-------|
| Asset at risk | Client project data held by Meridian Advisory Group |
| Threat | Phishing actor targeting staff |
| Loss form | Compromise of confidential client information |

---

## 2. Loss Event Frequency (LEF)

How often a loss is expected to occur per year.

| Factor | Description | Value |
|--------|-------------|-------|
| Threat Event Frequency (TEF) | Phishing attempts per year | 25 |
| Susceptibility | Share of attempts that succeed | 20% (0.20) |
| **Loss Event Frequency (LEF)** | TEF × Susceptibility = 25 × 0.20 | **5 / year** |

---

## 3. Loss Magnitude (per event)

| Factor | Description | Value |
|--------|-------------|-------|
| Primary Loss | Direct response & recovery per incident | $40,000 |
| Secondary Loss | Legal, reputational, client compensation | $60,000 |
| **Total Loss per Event** | Primary + Secondary | **$100,000** |

---

## 4. Annualized Loss Exposure (ALE) — Before Control

```
ALE = Total Loss per Event × LEF
ALE = $100,000 × 5
ALE = $500,000 per year
```

**Baseline risk: $500,000 per year.**

---

## 5. Modeling the Control

The Security Awareness Program reduces **Susceptibility** (how often phishing succeeds),
which lowers LEF — it does **not** reduce the cost of a breach when one happens. This is
the key modeling judgment: training makes loss *rarer*, not *cheaper*.

| Factor | Description | Value |
|--------|-------------|-------|
| Control effect | Reduction in phishing success rate | 60% (0.60) |
| New LEF | 5 × (1 − 0.60) = 5 × 0.40 | 2 / year (1.92) |
| New ALE | $100,000 × 1.92 | ~$200,000 / year |
| Control cost | Annual program cost | $80,000 |
| Total annual cost with control | New ALE + Control cost | $280,000 |

---

## 6. Decision — Return on Security Investment

| Option | Annual Loss | Control Cost | Total Cost | Net Savings |
|--------|-------------|--------------|------------|-------------|
| Without control | $500,000 | $0 | $500,000 | — |
| With control | $200,000 | $80,000 | $280,000 | **$220,000** |

```
Net savings = $500,000 − $280,000 = $220,000 per year
ROSI = $220,000 saved ÷ $80,000 invested = 275%
```

**Recommendation:** Fund the program. It cuts total annual risk cost from $500,000 to
$280,000 — a net saving of **$220,000/year** at a **275% return on security investment**.

---

## 7. Assumptions & Sensitivity

Every figure here is an estimate. What would move the conclusion:

| Assumption | Current | If wrong... |
|------------|---------|-------------|
| Susceptibility | 20% | At 30%, baseline ALE rises to $750K — control looks even better |
| Secondary Loss | $60,000 | Likely understated; reputational cost is hard to bound |
| Control effectiveness | 60% reduction | At 40%, new ALE = $300K, savings shrink to $120K — still positive |
| TEF | 25/year | Sourced from email gateway logs; should be re-checked annually |

Even under less favorable assumptions, the control remains cost-justified — which is the
strongest form of a FAIR conclusion: the decision holds across the plausible range, not
just at the point estimate.

---

*FAIR earns its credibility from defensible inputs and honest assumptions, not from the
illusion of precision. A dollar figure is only as good as the reasoning behind it.*
