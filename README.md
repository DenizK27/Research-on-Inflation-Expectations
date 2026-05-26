# Research on Inflation Expectations

> **Work in Progress** — code and results are still being updated.
>
> This project looks at heterogeneous inflation expectations across age groups using
> micro-level survey data from the Michigan Survey of Consumers (MSC). The main idea
> follows Malmendier & Nagel (2016): people's inflation expectations are shaped by
> the inflation they've personally experienced over their lifetime.
>
> The data goes back to the early 1950s and covers both the Survey of Consumer
> Attitudes and Behavior (SCAB) and the Survey of Consumer Finances (SCF).
>
> ## Files
>
> | File | Description |
> |------|-------------|
> | `InflationExpectation.Rmd` | Data extraction and cleaning for all Michigan Survey waves |
> | `Inflation Expectations_Imputation and Analysis.Rmd` | Harmonization and imputation pipeline |
> | `Imputation.Rmd` | Exploratory imputation work (preliminary) |
> | `cleaned_survey_data.rds` | Cleaned dataset used in the analysis |
> | `full_survey_data.rds` | Raw merged dataset before cleaning |
>
> ## How it works
>
> The pipeline has three main steps:
>
> 1. **Extraction** (`InflationExpectation.Rmd`): Raw survey files (`.txt`, `.dta`) from different
> 2.    decades get parsed and merged into a single panel. The key variables are categorical
> 3.   inflation expectations, numerical expectations, and respondent age.
>
> 4.   2. **Harmonization & Imputation** (`Inflation Expectations_Imputation and Analysis.Rmd`):
>      3.    Pre-1978 response categories get recoded for consistency. Missing numerical values are
>      4.   imputed following Curtin (1996) — sampling from observed responses within the same
>      5.      period and direction. There's also a bias correction for the pre-1982 "same rate"
>      6.     measurement issue.
>   
>      7. 3. **Exploratory imputation** (`Imputation.Rmd`): Regression-based approach to impute
>         4.    cohort-level expectations from directional response shares. Still being worked on.
>        
>         5.## Requirements
>
> ```r
> install.packages(c("dplyr", "ggplot2", "tidyverse", "tidyr", "zoo", "knitr", "kableExtra"))
> ```
>
> ## References
>
> - Malmendier, U. & Nagel, S. (2016). Learning from Inflation Experiences. *QJE*.
> - - Curtin, R. (1996). Procedure to Estimate Price Expectations. University of Michigan.
>  
>   - ---
>   Deniz Korkmaz
