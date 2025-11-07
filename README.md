
# Liver Disease survival Analysis: Logistic & Survival Modeling

## Project Overview

This repository contains an analysis of liver disease progression using the **Primary Biliary Cirrhosis (PBC)** dataset from the `survival` R package. The study focuses on understanding the relationships between patient demographics, clinical biomarkers, and outcomes such as hepatomegaly (enlarged liver) and survival status.

Key goals of the analysis include:

* Identifying significant predictors of hepatomegaly using **logistic regression**.
* Modeling patient survival using **Cox proportional hazards (CoxPH) regression**.
* Performing diagnostic checks and interpreting model results for clinical insights.

## Dataset

The dataset includes 276 patients diagnosed with liver disease. Key variables include:

* **Demographics:** `age`, `sex`
* **Clinical measurements:** `albumin`, `bilirubin (bili)`, `alkaline phosphatase (alk.phos)`, `AST`, `cholesterol`, `platelet`, `protime`
* **Clinical indicators:** `ascites`, `hepato`, `spiders`, `edema`
* **Survival outcome:** `time`, `status`

Missing values were handled using `na.omit`, and relevant categorical variables were converted to factors.

## Methodology

1. **Data Preparation:**

   * Removed patient `id` and transformed certain variables into factors.
   * Created a reduced dataset excluding `trt`, `time`, and `status` for logistic regression.

2. **Logistic Regression:**

   * Outcome variable: `hepato` (presence of hepatomegaly)
   * Predictors: `age`, `sex`, `albumin`, `alk.phos`, `ast`, `bili`
   * Key findings: `albumin` and `bilirubin` were significant predictors.

3. **Cox Proportional Hazards Regression:**

   * Outcome variable: `newstatus` (0 = censored/transplant, 1 = dead)
   * Predictors: `age`, `sex`, `albumin`, `alk.phos`, `ast`, `bili`
   * Significant predictors: `age`, `albumin`, `bilirubin`

4. **Model Diagnostics:**

   * Residual analysis and Q-Q plots were used to assess model fit.
   * CoxPH proportional hazards assumption checked using `cox.zph`.

## Key Insights

* Higher bilirubin levels increase the risk of hepatomegaly and mortality.
* Higher albumin levels are protective against hepatomegaly and mortality.
* Age is a significant predictor of mortality risk.
* Logistic and survival models provide complementary perspectives for understanding liver disease progression.

## Tools & Libraries

* **R** programming language
* Libraries: `survival`, `dplyr`, `ggplot2`, `faraway`

## References

* Therneau TM, Grambsch PM. *Modeling Survival Data: Extending the Cox Model*. Springer, 2000.
* `survival` R package documentation: [https://cran.r-project.org/package=survival](https://cran.r-project.org/package=survival)

