Estimating the Impact of Microcredit Using Causal Forests
Overview

This project analyzes the impact of microcredit access on small business profits using data from a randomized controlled trial (RCT).

While traditional analysis shows that loans increase profits on average, this project focuses on a deeper question:

Who benefits from microcredit—and who does not?

To answer this, I use a causal forest to estimate heterogeneous treatment effects at the individual level.

📊 Key Results
Average Effect (ATE)

Access to loans increases profits by approximately $3,100 on average (statistically significant)

This confirms prior findings that microcredit has a positive mean effect

Heterogeneous Effects (CATE)

However, the average effect masks substantial variation:

Top 20% of households: +$8,311 increase in profits

Bottom 20% of households: –$7,179 decrease in profits

This represents a $15K spread in outcomes across households

This suggests that microcredit is not universally beneficial—and may harm some households.

Targeting Improves Outcomes

Average predicted effect across all households: –$76 (roughly neutral out-of-sample)

Average predicted effect among positive responders only: +$4,650

Targeting loans to likely beneficiaries could significantly improve program effectiveness.

🔍 What Drives These Differences?

The most important drivers of treatment effect heterogeneity are:

Age of household head

Household size

Number of adults

Number of children (ages 6–16)

Key patterns:

Household size: Effects peak around ~4 members and decline beyond 5

Head age: Effects peak around ~40 and decline after ~60

Children: Households with ≥4 children show negative effects

🧠 Interpretation

These variables all relate to labor capacity vs. dependency burden:

Households with sufficient working-age members can convert loans into productive income

Households with high dependency burdens may divert capital toward consumption

Microcredit appears most effective for mid-sized, working-age households with balanced dependency ratios

🌳 Policy Segmentation (Decision Tree)

A decision tree trained on treated households reveals simple targeting rules:

Moderate household size (<5 members) performs best

Lower dependency burden (fewer children) improves outcomes

Middle-aged household heads outperform older ones

These rules provide a practical framework for targeting lending programs.

⚠️ Key Takeaway

A uniform lending strategy masks large inefficiencies.

Some households benefit substantially

Others may be harmed

Targeted lending could increase returns while reducing risk to vulnerable populations.

🛠 Methods

Linear regression (ATE estimation)

Causal Forest (heterogeneous treatment effects)

LOESS smoothing (response visualization)

Decision tree (interpretable segmentation)

📁 Data Source

AEA Microcredit Study
