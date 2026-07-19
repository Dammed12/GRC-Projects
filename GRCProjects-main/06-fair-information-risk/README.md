# Project 06: Quantifying Risk with FAIR (Factor Analysis of Information Risk)

## Overview

Most risk registers speak in colors: "this is a red risk, that one's amber." That
language is fast to produce and almost impossible to defend. A board member asks "how
much is this actually costing us?" and the heat map has no answer. This project requires
you to treat risk as a **number you can defend**, not a color you can point at.

FAIR is the discipline of decomposing a risk into its factors — how often the loss
happens, and how much it costs when it does — and turning that into an annualized dollar
figure a business leader can act on. The output isn't "we should probably do security
awareness training." It's "this control saves $220,000 a year at a 275% return."

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    RISK LANGUAGE: QUALITATIVE VS FAIR                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│   QUALITATIVE (WEAK)                    FAIR / QUANTITATIVE (STRONG)        │
│   ──────────────────                    ───────────────────────────         │
│   "High risk"                           $500,000 annualized loss exposure    │
│   "Likely to happen"                    Loss Event Frequency = 5/year        │
│   "Significant impact"                  $100,000 loss per event              │
│   "We should fix this"                  ROSI = 275%, saves $220K/year        │
│   Color on a heat map                   Defensible dollar figure             │
│                                                                             │
│   Result: Feels rigorous, isn't         Result: A CFO can act on it          │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

> **Note:** This project is the quantitative engine behind Project 05 (Risk Acceptance
> Documentation). A FAIR analysis produces the loss numbers; a risk acceptance document
> uses them to justify a business decision. Completing both shows you can run the math
> *and* communicate it to leadership.

---

## The Scenario

**Company:** Meridian Advisory Group
**Industry:** Governance, Risk & Compliance consulting
**Sensitive Asset:** Client project data held on behalf of multiple corporate clients
**Trigger:** Repeated phishing attempts targeting staff
**The Decision:** Is a new Security Awareness & Simulation Program ($80,000/year)
financially justified?

Meridian Advisory Group's leadership doesn't want a gut call. They want to know whether spending
$80K to reduce phishing success is worth it — in dollars, not adjectives. The risk
management unit applies the FAIR model (per FAIR Institute guidance) to answer it.

### The Risk Scenario Being Analyzed

> *"A phishing attack could compromise client project data."*

This single sentence sets the scope: the **asset** (client project data), the **threat**
(phishing), and the **loss form** (compromise of confidential client information).

---

## The FAIR Model in This Analysis

FAIR breaks risk into two branches — how often loss occurs, and how bad it is — then
multiplies them into Annualized Loss Exposure (ALE).

```
                    ┌─────────────────────────┐
                    │   ANNUALIZED LOSS        │
                    │   EXPOSURE (ALE)         │
                    │   = Loss/Event × LEF     │
                    └───────────┬─────────────┘
                                │
                ┌───────────────┴───────────────┐
                │                               │
                ▼                               ▼
    ┌───────────────────────┐       ┌───────────────────────┐
    │  LOSS EVENT FREQUENCY │       │   LOSS MAGNITUDE       │
    │  (LEF)                │       │   (per event)          │
    │  = TEF × Susceptibility│      │   = Primary + Secondary│
    └───────────┬───────────┘       └───────────┬───────────┘
                │                               │
        ┌───────┴───────┐               ┌───────┴───────┐
        ▼               ▼               ▼               ▼
  ┌──────────┐   ┌──────────────┐ ┌──────────┐   ┌──────────────┐
  │   TEF    │   │Susceptibility│ │ Primary  │   │  Secondary   │
  │ 25/year  │   │    20%       │ │ $40,000  │   │   $60,000    │
  └──────────┘   └──────────────┘ └──────────┘   └──────────────┘
```

---

## The Calculation (As Built in the Spreadsheet)

### Step-by-step FAIR walkthrough

| # | FAIR Factor | Input / Formula | Value |
|---|-------------|-----------------|-------|
| 1 | Define the risk scenario | Phishing compromises client project data | — |
| 2 | Identify assets & threats | Asset: client data · Threat: phishing actor | — |
| 3 | Threat Event Frequency (TEF) | 25 phishing attempts per year | 25 |
| 4 | Susceptibility (P of success) | 20% of attempts succeed | 0.20 |
| 5 | Loss Event Frequency (LEF) | TEF × Susceptibility = 25 × 0.20 | **5 / year** |
| 6 | Primary Loss (direct) | Response & recovery per incident | $40,000 |
| 7 | Secondary Loss (indirect) | Legal, reputation, client compensation | $60,000 |
| 8 | Total Loss per Event | Primary + Secondary | $100,000 |
| 9 | **Annualized Loss Exposure (ALE)** | Loss/Event × LEF = $100,000 × 5 | **$500,000 / year** |

### Control cost-benefit (the actual decision)

| # | Factor | Formula | Value |
|---|--------|---------|-------|
| 10 | Control effect | Program reduces phishing success by 60% | 0.60 |
| 11 | New LEF after control | LEF × (1 − 0.60) = 5 × 0.40 | 2 / year (1.92) |
| 12 | New ALE after control | $100,000 × 1.92 | ~$200,000 / year |
| 13 | Control cost | Security Awareness Program | $80,000 / year |
| 14 | Total annual cost with control | New ALE + Control cost | $280,000 |
| 15 | **Net savings** | Original ALE − Total cost = $500,000 − $280,000 | **$220,000 / year** |

### Bottom line

| Option | Annual Loss | Control Cost | Total Cost | Net Savings |
|--------|-------------|--------------|------------|-------------|
| Without control | $500,000 | $0 | $500,000 | — |
| With control | $200,000 | $80,000 | $280,000 | **$220,000** |

**Result:** The Security Awareness Program reduces total annual risk cost from $500,000
to $280,000 — a net saving of **$220,000 per year** and a Return on Security Investment
(ROSI) of **275%** ($220,000 saved ÷ $80,000 invested).

> ⚠️ **Consistency note for the spreadsheet:** the summary cell currently reads "$208,000
> saved." Every underlying calculation produces **$220,000** ($500,000 − $280,000). The
> $208,000 figure appears to be a leftover from an earlier input; update the summary line
> so it matches the math. (275% ROSI is correct against the $220,000 figure.) Catching and
> fixing this kind of drift is part of what makes the analysis defensible.

---

## What You Need to Do

### Phase 1: Frame the Risk Scenario
Write the one-sentence scenario that fixes asset, threat, and loss form. A FAIR analysis
is only as good as its scope statement — a vague scenario produces meaningless numbers.

### Phase 2: Source Your Frequency Inputs
Justify TEF and Susceptibility. Where does "25 attempts/year" come from — email gateway
logs? Where does "20% success" come from — past incident data, industry benchmark, or
estimate? **Document the provenance of every number**, because the first thing a skeptical
CFO asks is "says who?"

### Phase 3: Build the Loss Magnitude
Separate Primary Loss (direct response/recovery you'll definitely incur) from Secondary
Loss (legal, reputational, client compensation — conditional and often larger). Be honest
that Secondary Loss is the harder, softer number.

### Phase 4: Calculate ALE
LEF × Loss per Event. This is the headline figure: the annualized dollar risk before any
new control.

### Phase 5: Model the Control
Apply the control's effect to the factor it actually changes. The awareness program
reduces *Susceptibility*, which reduces LEF, which reduces ALE. It does **not** reduce
loss magnitude — training doesn't make a breach cheaper, it makes it rarer. Getting this
mapping right is the core judgment of the phase.

### Phase 6: Decide with ROSI
Compare the cost of the control against the risk it removes. Net savings and ROSI turn
the analysis into a recommendation leadership can approve.

### Phase 7: State the Assumptions & Limitations
Every FAIR analysis rests on estimates. Document what would change the answer: if success
rate is really 30% not 20%, if Secondary Loss is underestimated, if the control only
delivers 40% reduction instead of 60%. This is where you show you understand the model's
limits, not just its mechanics.

---

## Success Criteria

Your project demonstrates strong quantitative risk judgment if:

| Criteria | Evidence |
|----------|----------|
| **Scenario is scoped tightly** | One clear asset, threat, and loss form |
| **Inputs are sourced, not invented** | Provenance stated for TEF, Susceptibility, losses |
| **Primary vs Secondary loss separated** | Direct and indirect costs treated differently |
| **Control mapped to the right factor** | Awareness reduces frequency, not magnitude |
| **Decision expressed in dollars** | ALE, net savings, and ROSI — not "high/medium/low" |
| **Assumptions & sensitivity documented** | You state what would change the conclusion |

### Red Flags (Weak Project)

- Numbers with no stated source ("25/year" appearing from nowhere)
- Control applied to the wrong factor (claiming training reduces loss size)
- Single-point estimates presented as certainty, no sensitivity analysis
- Summary figures that don't match the underlying math
- ALE calculated but never connected to a decision

---

## Deliverables Checklist

```
□ Completed FAIR spreadsheet (FAIR_spreadsheet.xlsx)
□ Risk scenario statement (asset / threat / loss form)
□ Input provenance notes (where each number came from)
□ ALE calculation (before control)
□ Control cost-benefit analysis (ALE after control, ROSI)
□ Assumptions & sensitivity notes
□ 5-minute video walkthrough explaining the numbers to a non-technical leader
```

---

## Resources

- [FAIR Institute](https://www.fairinstitute.org/)
- [Open FAIR Body of Knowledge (The Open Group)](https://www.opengroup.org/)


---

## Reflection Questions

After completing this project, answer:

1. Which input are you least confident in, and how much does the conclusion move if it's wrong?
2. Why does the awareness program reduce Susceptibility rather than Loss Magnitude?
3. How would you explain "$220,000 saved" to a CFO who doesn't trust security estimates?
4. If leadership rejected the $80K spend, what FAIR figure would you use to challenge that?
5. Where does FAIR's precision risk creating false confidence?

---

*Remember: A dollar figure isn't more truthful than a heat map just because it has a decimal
point. FAIR earns its credibility from defensible inputs and honest assumptions — not from
the illusion of precision.*
