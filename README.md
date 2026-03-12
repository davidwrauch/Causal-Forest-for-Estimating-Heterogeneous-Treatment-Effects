Causal Forest for Estimating Heterogeneous Treatment Effects

TLDR

This project applies a causal forest model to estimate how the effect of a treatment varies across individuals rather than assuming a single average effect. Instead of only asking “does the treatment work?”, the model identifies who it works best for, which is often the more useful question in product, marketing, and policy decisions.

Overview

Many analytics questions are fundamentally causal. For example:

Does a new feature actually increase user engagement?

Does a marketing campaign improve conversion?

Does a pricing change increase revenue?

Traditional machine learning models are designed to predict outcomes, but they do not distinguish between correlation and causation.

This project uses a causal forest, a machine learning method designed to estimate treatment effects directly. The model is an extension of random forests that focuses on identifying how the impact of a treatment varies across different subgroups in the data.

Rather than predicting an outcome like “conversion probability,” the model estimates the conditional treatment effect for each observation.

In practical terms, it answers questions like:

Which users benefit most from a product feature?

Which customers respond best to a promotion?

Where might a policy intervention have the strongest impact?

Why causal forests are useful

In many real-world systems, the effect of an intervention is not uniform across the population.

A marketing discount might increase purchases for price-sensitive customers but have little effect on loyal customers who would buy anyway.

A causal forest helps uncover these differences by learning where treatment effects vary across the feature space. Instead of minimizing prediction error like a standard random forest, it splits the data to maximize differences in estimated treatment effects between groups.

This allows the model to estimate heterogeneous treatment effects, which can be used for targeted decisions.

Dataset and structure

The dataset includes:

covariates describing each observation

a treatment indicator (whether the individual received the intervention)

an outcome variable

The analysis follows a typical causal inference structure:

Define treatment and outcome variables

Use covariates to control for confounding

Train a causal forest model to estimate conditional treatment effects

The model produces an estimated treatment effect for each observation, which can then be analyzed to understand how the intervention behaves across different groups.

Modeling approach

The analysis uses the generalized random forest implementation of causal forests.

Conceptually, the algorithm works as follows:

Many causal trees are built on random subsets of the data

Each tree partitions the data into groups with different estimated treatment effects

The forest aggregates results across trees to estimate individual-level treatment effects

This ensemble approach helps stabilize estimates and detect patterns that would be difficult to identify with traditional regression models.

Causal forests are particularly useful when:

treatment effects vary across individuals

the dataset has many potential confounders

relationships are nonlinear or complex

Interpreting the results

Instead of producing a single coefficient like a linear model, the causal forest estimates how the treatment effect varies across observations.

Typical outputs include:

estimated treatment effect distribution

variable importance for treatment effect heterogeneity

subgroup-level treatment effects

These outputs can be used to guide practical decisions such as targeting interventions only where they produce meaningful impact.

Example applications

Methods like this are increasingly used in real-world systems, including:

marketing uplift modeling

recommendation systems

pricing optimization

healthcare treatment personalization

policy evaluation

The ability to estimate who benefits from an intervention can dramatically improve decision-making compared with relying on average effects alone.

Tools used

R
grf (generalized random forest)
tidyverse
ggplot2
