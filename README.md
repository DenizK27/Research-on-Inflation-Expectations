# Research on Inflation Expectations

> **⚠️ Work in Progress** — This repository is under active development. Results, methods, and code are subject to change.

## Overview

This project replicates and extends the methodology of **Malmendier & Nagel (2016)** on heterogeneous inflation expectations across age cohorts. Using micro-level survey data from the **Michigan Survey of Consumers (MSC)**, the analysis examines how personal inflation experiences shape individual expectations over time.

The data spans from the **early 1950s to the present**, covering both the Survey of Consumer Attitudes and Behavior (SCAB) and the Survey of Consumer Finances (SCF).

## Repository Structure

| File | Description |
|------|-------------|
| `InflationExpectation.Rmd` | Data extraction, cleaning, and standardization of raw Michigan Survey data |
| `Inflation Expectations_Imputation and Analysis.Rmd` | Methodological harmonization and distributional imputation of missing values |
| `Imputation.Rmd` | Preliminary distributional imputation experiments (exploratory) |
| `cleaned_survey_data.rds` | Cleaned and standardized survey dataset (R object) |
| `full_survey_data.rds` | Full raw survey dataset before cleaning (R object) |

## Methodology

The pipeline follows three main steps:

1. **Data Extraction & Standardization** (`InflationExpectation.Rmd`): Raw survey files in various formats (`.txt`, `.dta`) are parsed, harmonized across decades, and merged into a single panel dataset. Key variables extracted are categorical inflation expectations, numerical inflation expectations, and respondent age.

2. **Methodological Harmonization** (`Inflation Expectations_Imputation and Analysis.Rmd`): Pre-1978 response categories are recoded for longitudinal consistency. Outlier truncation following Curtin (1996) is applied as a robustness check. Missing numerical expectations are imputed using a distributional sampling approach within survey period and direction cells. A bias correction for the pre-1982 "same rate" misinterpretation is implemented.

3. **Distributional Imputation** (`Imputation.Rmd`): Exploratory regression-based imputation of numerical expectations using categorical response shares as predictors, grouped by age cohort and time period.

## Requirements

All scripts are written in **R** and use R Markdown (`.Rmd`). The following packages are required:

```r
install.packages(c("dplyr", "ggplot2", "tidyverse", "tidyr", "zoo",
                   "knitr", "kableExtra"))
                   ```

                   ## Data Source

                   - **Michigan Survey of Consumers** — University of Michigan, Survey Research Center
                   - Covers survey waves from 1953 onwards
                   - Comparison baseline: Nagel (2020) dataset coverage

                   ## References

                   - Malmendier, U., & Nagel, S. (2016). *Learning from Inflation Experiences*. Quarterly Journal of Economics.
                   - Curtin, R. (1996). *Procedure to Estimate Price Expectations*. University of Michigan.

                   ## Author

                   **Deniz Korkmaz**
