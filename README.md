# Bank NPA Analytics | Python, SQL & Power BI

## Overview

Bank NPA Analytics is a data analytics project that examines the asset quality of Indian banks using Reserve Bank of India (RBI) data from 2004 to 2025.

The project focuses on understanding historical Gross Non-Performing Asset (NPA) trends, comparing Public Sector Banks (PSUs) with Private Sector Banks, identifying banks with consistently high NPA ratios, and highlighting potential areas of banking risk.

The analysis combines Python-based data cleaning, SQL-based analysis, statistical hypothesis testing, and interactive Power BI dashboards to convert raw banking data into meaningful insights.

## Objectives

- Analyze long-term trends in Gross NPA ratios across Indian banks.
- Compare asset quality between Public Sector and Private Sector Banks.
- Identify banks with high NPA ratios and persistent asset-quality concerns.
- Measure the concentration of Gross NPAs among the largest banks.
- Apply statistical testing to evaluate differences between PSU and Private Sector Banks.
- Develop a risk-monitoring framework using NPA ratios and loan-book size.
- Present findings through interactive Power BI dashboards.

## Tools & Technologies

- **Python:** Data cleaning, validation, and exploratory data analysis.
- **Pandas & NumPy:** Data manipulation and numerical operations.
- **SciPy:** Statistical hypothesis testing.
- **MySQL:** Analytical queries, aggregations, rankings, and trend analysis.
- **Power BI:** Interactive dashboards and data visualization.
- **Jupyter Notebook:** Python-based analysis and documentation.

## Dataset

The project uses RBI bank-level NPA data covering approximately two decades, from 2004 to 2025.

The raw dataset contained approximately 2,020 rows and 6 columns. After cleaning and filtering for the main PSU-versus-Private comparison, the analytical dataset contained 1,004 bank-year observations.

Key fields include:

- Financial Year
- Bank Name
- Bank Group
- Gross NPA
- Gross Advances
- Gross NPA Ratio

The main comparison focuses on Public Sector Banks and Private Sector Banks. Other bank groups are excluded from this specific comparison.

## Data Cleaning & Validation

The raw Excel data was not directly suitable for analysis, so Python and Pandas were used to prepare it.

Key steps included:

- Handling multiple header rows and blank year entries.
- Forward-filling financial-year values where appropriate.
- Separating individual bank records from group subtotals and system-wide totals.
- Standardizing bank names and handling missing values.
- Preserving historical changes in bank classification, including IDBI Bank.
- Validating bank-level figures against reported group totals.

The cleaned dataset was checked for consistency before performing further analysis.

## SQL Analysis

MySQL was used to answer analytical questions about banking-sector asset quality.

Key analyses included:

- Calculating system-wide Gross NPA ratios using weighted aggregation.
- Comparing annual NPA ratios across PSU and Private Sector Banks.
- Ranking banks by Gross NPA ratio.
- Calculating year-over-year changes using `LAG()`.
- Measuring the share of total Gross NPA contributed by the top three banks.
- Categorizing banks into NPA risk quartiles using `NTILE(4)`.
- Tracking banks that repeatedly appeared among the worst-performing banks.
- Comparing loan-book size with NPA ratios.
- Measuring year-over-year NPA volatility across bank groups.
- Analyzing historical bank counts and consolidation trends.
- Calculating long-term growth rates using CAGR.

SQL concepts used include CTEs, aggregate functions, conditional aggregation, subqueries, `CASE WHEN`, `RANK()`, `LAG()`, `NTILE()`, and `COUNT(DISTINCT)`.

## Statistical Analysis

Statistical testing was used to investigate whether the difference in NPA ratios between PSU and Private Sector Banks was statistically significant.

### Shapiro-Wilk Test

Used to check whether the NPA ratio distributions followed a normal distribution. The normality checks indicated non-normal distributions, supporting the choice of a non-parametric comparison.

### Mann-Whitney U Test

Used to compare the NPA ratio distributions of PSU and Private Sector Banks.

The significance level was set at 0.05.

**Latest result for FY2024-25:**

- PSU median NPA ratio: approximately 3.01%
- Private Sector median NPA ratio: approximately 2.60%
- p-value: 0.1393
- Statistical conclusion: The difference was not statistically significant at the 5% level.

This result means that the analysis did not find sufficient statistical evidence of a difference between the two groups for the latest year. It does not prove that their distributions are identical.

## Key Findings

- The system-wide Gross NPA ratio peaked at approximately **11.18% in 2018** and declined to approximately **2.22% in 2025**.
- The weighted PSU-Private NPA ratio gap peaked at approximately **9.96 percentage points in FY2017-18** and narrowed to approximately **0.83 percentage points in FY2024-25**.
- The Mann-Whitney U test for 2025 produced a p-value of **0.1393**, indicating no statistically significant difference at the 5% level.
- The three banks with the largest absolute Gross NPA amounts accounted for approximately **37.55% of total Gross NPA** in the latest year.
- IDBI Bank repeatedly appeared among the banks with the highest NPA ratios in the historical analysis, highlighting a persistent asset-quality concern.
- PSU banks showed higher year-over-year NPA-ratio volatility than Private Sector Banks in the analysis.
- Comparing NPA ratios with loan-book size helped identify banks that may warrant closer monitoring.

*Figures are based on the project's cleaned dataset and analytical definitions.*

## Power BI Dashboards

The project includes four interactive dashboard pages.

### 1. Executive Overview

Provides a high-level view of system-wide NPA trends, current NPA ratios, the PSU-Private gap, and changes in the number of PSU banks over time.

### 2. Bank & Group Comparison

Compares individual banks and bank groups using NPA rankings, loan-book size, historical bank counts, and PSU-Private gap trends.

### 3. Statistical Deep Dive

Presents the Mann-Whitney U test results, p-value trends, bank-group NPA distributions, and banks that repeatedly appeared among the worst-performing banks.

### 4. Risk Analysis

Uses a Probability × Impact matrix to highlight banks for potential supervisory attention. NPA ratio serves as a proxy for asset-quality stress, while Gross Advances represent loan-book exposure and potential impact.

The matrix is a risk-prioritization framework, not a direct prediction of default probability or actual financial loss.

## Business Use Case

The analysis can support bank risk monitoring by helping analysts and decision-makers:

- Track changes in banking-sector asset quality.
- Compare the performance of PSU and Private Sector Banks.
- Identify banks with persistently high NPA ratios.
- Understand how much of the sector's Gross NPA is concentrated in a few banks.
- Prioritize further investigation using both asset-quality indicators and loan-book exposure.

For example, the narrowing PSU-Private NPA gap suggests that the historical difference between the two groups has reduced substantially. However, individual banks can still require attention based on their NPA ratios, exposure, and historical performance.

## Project Workflow

1. Collect and inspect RBI banking data.
2. Clean and validate the dataset using Python and Pandas.
3. Perform exploratory data analysis.
4. Load the prepared data into MySQL.
5. Write SQL queries to analyze trends, rankings, concentration, and risk.
6. Perform statistical tests using Python.
7. Build interactive Power BI dashboards.
8. Interpret the findings in a banking risk-monitoring context.

## Conclusion

This project demonstrates an end-to-end data analytics workflow, from cleaning and validating raw banking data to analyzing trends with SQL, applying statistical tests, and communicating findings through Power BI.

It combines data analysis and visualization to understand historical NPA patterns, compare bank groups, and identify potential areas for closer risk monitoring.

## Author

**Sandhya Sisodiya**

GitHub: [Sandhya251](https://github.com/Sandhya251)

<img width="1327" height="745" alt="image" src="https://github.com/user-attachments/assets/1f39b7bf-bae7-4a05-ae96-2918fe219f23" />
<img width="1325" height="745" alt="image" src="https://github.com/user-attachments/assets/628d9686-3660-44ad-819a-c446685461bd" />
<img width="1327" height="750" alt="image" src="https://github.com/user-attachments/assets/52e479f2-730b-42d2-93b3-ccd31b01a127" />
<img width="1322" height="742" alt="image" src="https://github.com/user-attachments/assets/2b7a3a3b-398c-4b10-9138-c1f08e6111b2" />
