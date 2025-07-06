# 🧬 Survival Data Analysis of HIV Patients

This project presents a statistical survival analysis of HIV patient data using R. The analysis was carried out in an academic context to model and evaluate the effect of clinical and demographic variables on patient survival time.

## 🧠 Context

Survival analysis refers to a collection of statistical techniques designed to analyze the expected duration of time until one or more events happen, such as death or relapse. In this study, we investigate the survival of individuals diagnosed with HIV, focusing on the impact of variables such as age, gender, treatment status, and more.

The dataset includes right-censored data, a common feature in survival analysis, where the event of interest has not occurred for some individuals during the observation period.

## 📐 Methodology

We employed the following statistical techniques:

### 1. **Kaplan-Meier Estimator**
Used to estimate the survival function \( \hat{S}(t) \), which is defined as:

\[
\hat{S}(t) = \prod_{t_i \leq t} \left(1 - \frac{d_i}{n_i} \right)
\]

Where:
- \( t_i \): time of the \( i^{th} \) event
- \( d_i \): number of events (e.g., deaths) at time \( t_i \)
- \( n_i \): number of individuals at risk just prior to \( t_i \)

We compared survival curves across subgroups (e.g., treatment vs. no treatment) using the **log-rank test**.

### 2. **Cox Proportional Hazards Model**

We modeled the hazard function as:

\[
h(t | X) = h_0(t) \cdot \exp(\beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_p X_p)
\]

Where:
- \( h(t | X) \): hazard at time \( t \) given covariates \( X \)
- \( h_0(t) \): baseline hazard
- \( \beta_j \): coefficient for covariate \( X_j \)

This model allows estimation of hazard ratios (HR) and their confidence intervals.

**Model assumptions checked:**
- Proportional hazards (via Schoenfeld residuals)
- Linearity of continuous covariates (via Martingale residuals)
- No high-leverage outliers

## 📁 Project Files

- **HIV_Surv.Rmd**: RMarkdown source with code and commentary
- **HIV_Surv.html**: rendered interactive report
- **hiv.csv**: cleaned dataset of HIV patients

## 📊 Key Findings

- The treatment group showed significantly improved survival compared to the no-treatment group (log-rank p < 0.01).
- Age and CD4 count were found to be significant predictors in the Cox model.
- The proportional hazards assumption held for all included covariates.

## ⚙️ Tools and Packages

- **R** and **RMarkdown**
- Key packages:
  - `survival`
  - `survminer`
  - `ggplot2`
  - `dplyr`

## 📅 Date

March 2024

## ✍️ Author

**Aymane Mimoun**

## 📚 References

- Hosmer, D.W., Lemeshow, S., & May, S. (2008). *Applied Survival Analysis: Regression Modeling of Time-to-Event Data*. Wiley.
- Therneau, T.M. (2020). *A Package for Survival Analysis in R*. [CRAN survival package](https://cran.r-project.org/package=survival)
