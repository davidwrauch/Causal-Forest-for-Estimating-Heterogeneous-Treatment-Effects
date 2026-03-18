# 💸 Microcredit: Who Actually Benefits?

## TLDR

- Used a **causal forest** to estimate heterogeneous treatment effects from an RCT  
- Average impact: **+$3,100** increase in profits  
- But effects vary dramatically:  
  - Top 20%: **+$8,300**  
  - Bottom 20%: **–$7,200**  
- Targeting only likely beneficiaries increases impact to **+$4,650**  
- Key drivers: household size, age, and dependency burden  

> Microcredit works on average—but not for everyone. Targeting matters.

---

## What this project does

This is a causal ML analysis of a well-known microcredit RCT.

Instead of stopping at the average treatment effect, I use a **causal forest (grf)** to estimate how the effect of receiving a loan varies across households.

The goal is simple:

> Understand **who benefits**, **who doesn’t**, and whether we can do better than a one-size-fits-all policy.

---

## Results

### Average effect (ATE)

A baseline regression shows that access to loans increases profits by about:

**+$3,100 (statistically significant)**

This matches the headline result you’d get from a standard analysis.

---

### Heterogeneous effects (CATE)

The causal forest tells a very different story:

- **Top 20% of households:** +$8,311  
- **Bottom 20% of households:** –$7,179  

That’s a **$15K spread** in outcomes.

Some households benefit a lot. Others appear to be worse off.

---

### Targeting vs. uniform policy

Across all households:

- Average predicted effect: **–$76**

Among households with positive predicted effects:

- Average effect: **+$4,650**

> This suggests that targeting loans—even with a simple model—could substantially improve outcomes.

---

## What drives the differences?

The most important variables are:

- Household size  
- Age of the household head  
- Number of adults  
- Number of children (ages 6–16)  

A few patterns stand out:

- **Households around 4 members perform best**; outcomes drop after ~5  
- **Heads around age 40 perform best**; effects decline after ~60  
- **More children → worse outcomes**, especially beyond 3–4  

---

## Interpretation

These variables all relate to a common theme:

**Ability to turn capital into productive income vs. pressure to consume it**

- Mid-sized, working-age households → better able to invest loans  
- Larger or high-dependency households → more likely to divert funds  

> The results suggest microcredit is most effective for households with **balanced labor capacity and lower dependency burden**

---

## Making this actionable

To make the results more interpretable, I trained a simple decision tree on treated households.

It produces rules like:

- Smaller to mid-sized households perform better  
- Fewer dependents improves outcomes  
- Middle-aged household heads outperform older ones  

This provides a rough—but usable—framework for targeting.

---

## Methods

- Linear regression for ATE  
- **Causal forest (grf)** for heterogeneous treatment effects  
- LOESS smoothing to visualize non-linear relationships  
- Decision tree for interpretable segmentation  

---

## Data

- AEA Microcredit Study: https://www.aeaweb.org/articles?id=10.1257/app.20130535
