# Combining Estimates – Statistics for Data Science Project

**Course**: Statistics for Data Science  
**Based on**: *Combining Estimates* by Thomas Struppeck (FCAS, ASA, CERA, 2014)

---

## Project Overview

This project aims to **reproduce and simulate** the key findings from the paper *“Combining Estimates”* by Thomas Struppeck, using the **R programming language**.

The paper addresses how to optimally combine different estimates—possibly with different variances or correlations—to improve the precision of predictions. The context is primarily **insurance and actuarial science**, where combining expert estimates or model outputs is a critical task.

The project is organized into two main parts, each reproducing different sections of the paper.

---

## Repository Structure

### `1Comb_Est_Same_Quantity`

Reproduces **Section 2** of the paper: combining two or more estimates of the **same quantity** (e.g., unpaid claims).

**Key files:**
- `global_variables_1.r`: Variables and assumptions.
- `functions_1.r`: Statistical utility functions.
- `generate_samples_functions_1.r`: Sample generation (normal distributions).
- `plot_functions_1.r`: Custom plotting utilities.
- `comb_two_estimates.r`: Combines θₐ and θᵦ with optimal weights.
- `comb_two_estimates_100%Corr.r`: Case of perfect correlation (ρ = 1).
- `comb_more_estimates.r`: Extension to 3+ estimates via inverse variance weighting.
- `plot/`: Output plots showing comparisons and confidence intervals.

---

### `2Comb_Est_Mult_Components`

Reproduces **Sections 3 and 4**: combining estimates across **multiple components** (e.g., lines of business).

**Key files:**
- `global_variables_2.r`: Setup of means, variances, and percentiles.
- `functions_2.r`: Statistical methods and simulation utilities.
- `generate_samples_functions_2.r`: Generate correlated component-level data.
- `multiple_components.r`: Replicates calculations for total loss estimates.
- `simulation_multiple_comp.r`: Simulates multiple scenarios under various correlation structures.
- `user_application.r`: A **Shiny app** that reproduces the Excel tool in the paper with a dynamic R interface.

---

## Key Concepts Explored

### Combining Estimates (Same Quantity)
- Optimal **weighted average** of two or more independent estimates.
- Impact of **correlation** on estimator variance.
- Simulation of **95% confidence intervals**.
- Trade-off between **accuracy vs. precision**.

### Combining Multiple Estimates
- Generalization to 3+ estimates using **Inverse Variance Weighting (IVW)**.

### Combining Multiple Components
- Total loss estimation across multiple **correlated components**.
- Comparative approaches:
  - Naïve total (ρ = 1),
  - Independent assumption (ρ = 0),
  - Covariance-adjusted estimator using the **variance-covariance matrix**.

---

## Shiny App (Interactive Tool)

A fully interactive **Shiny app** is available in `user_application.r`, replicating the Excel calculator from the original paper:

- Input percentiles, means, and correlations for each component.
- Explore how changes in correlation impact the total estimate and uncertainty.
- View interactive tables and visual feedback.

**Packages used:**
- [`shiny`](https://shiny.posit.co/) – interactive web UI  
- [`DT`](https://rstudio.github.io/DT/) – responsive data tables

---
