# Puerto Rico Wages and Employment Analysis

## Overview

This project analyzes employment and average wages in Puerto Rico using data from the U.S. Bureau of Labor Statistics (BLS). It uses R to clean and combine occupational data, estimate wage elasticity by occupation, and review model fit and assumptions.

## Research question

How is employment associated with changes in average wages for different occupations in Puerto Rico?

## Data

The occupational wage and employment data come from the BLS Occupational Employment and Wage Statistics (OEWS), using May estimates.

The analysis also includes a Puerto Rico employment time series for examining changes over time and selected economic events.

**The source files are not included in this repository.** Download the required files from the BLS and place them in the data folder before running the analysis.

BLS OEWS information: https://www.bls.gov/oes/oes_emp.htm

## Methods

The project:

1. Reads and cleans the annual Excel files.
2. Combines the files into a consistent table.
3. Filters the occupational records for Puerto Rico.
4. Fits a log-log linear regression for each occupation:

   `log(employment) = β₀ + β₁ × log(average_wage) + error`

5. Reviews model results and diagnostics, including R-squared, coefficient significance, residual normality, and heteroskedasticity.
6. Creates charts of employment and wage-related results.

The estimated coefficient, `β₁`, describes the percentage association between average wages and employment in the fitted data. It should not be interpreted as proof that a wage change causes an employment change.

## Tools and R packages

- R
- readxl
- tidyverse
- janitor
- broom
- gridExtra
- grid
- ggpubr
- xts
- data.table
- kableExtra
- lmtest

## Project structure

```text
project/
├── data/          # BLS Excel files and employment time-series data
├── scripts/       # R analysis scripts
├── output/        # Tables, charts, and model results
└── README.md
```

## How to run 

1. Install R.
2. Install the required packages:
      install.packages(c(
        "readxl", "tidyverse", "janitor", "broom", "gridExtra",
        "ggpubr", "xts", "data.table", "kableExtra", "lmtest"
            ))
3. Download the required BLS files and place them in data/.
4. Update the file paths in the R script to point to the data folder.
5. Run the script in RStudio or from the R console.


## Limitations
- Results depend on the available BLS estimates and the years included.
- Some occupations may have few observations, which can make their regression estimates less reliable.
- The regression describes an association in the data; it does not establish causation.
- The PDF title says 2001–2022, while the listed occupational files in the code appear to run from 2001–2021. Confirm the actual years included before publishing results.

## Author
Yadel Rosario
