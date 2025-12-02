# BRFSS Smoking Behavior Analysis: End-to-End Data Project

## Overview
This project analyzes smoking behavior among U.S. adults using the 2023 BRFSS dataset, combining SQL, Python, and Tableau to understand demographic patterns, socioeconomic disparities, and state-level differences in smoking prevalence. The goal is to demonstrate a full-stack analytical workflow from raw data preparation to interactive visualization.

Across tools, the project includes:

**Python:** detailed data cleaning, creation of export-ready datasets for SQL and Tableau, and visualization

**SQL:** querying, filtering, and summarizing the BRFSS data subset 

**Tableau:** interactive dashboards highlighting state-level smoking z-scores, income × education effects, and demographic risk patterns

The final product is a Tableau dashboard, giving a clear view of where smoking disparities are most pronounced and which population groups are at higher risk. 

## Dataset Description
The analysis uses the 2023 Behavioral Risk Factor Surveillance System (BRFSS) dataset, a nationally representative U.S. health survey with over 400,000 adult respondents. The raw dataset includes demographic, socioeconomic, and health behavior variables. For this project, the focus was on smoking-related variables along with key demographics such as income, education, age, sex, race, and state. After cleaning and standardizing categories, the dataset was used to examine population-level smoking patterns and state-level disparities.

**Source:** BRFSS (Behavioral Risk Factor Surveillance System) - https://www.kaggle.com/datasets/isuruprabath/brfss-2023-csv-dataset?resource=download 

*sample extracted for project use.

**Size:** 410187 rows 

**Key Variables Used:**

- `_smoker3`: Smoking status (Current smoker – every day, Current smoker – some days, Former smoker, Never smoked)
- `_state`: Respondent’s state.
- `sexvar`: Identifier for sex (male/female).
- `_ageg5yr`: Categorical age variable, with ages in 5 year bins
- `_incomg1`: Categorical Income classification
- `_educag`: Categorical Edcucation level completed
- `_racegr3`: Five level race/ethnicity category

## Project Goals
To understand patterns and disparities in smoking behavior across the U.S. and highlight high-risk populations:

- Analyze smoking prevalence across demographic and socioeconomic groups
- Detect states and populations with unusually high or low smoking rates
- Identify the top 5 highest-risk demographic groups
- Build an interactive Tableau dashboard to communicate findings

## Python Workflow Summary

- Loaded and inspected the dataset to understand structure, data types, and missing values
- Selected relevant columns and cleaned the data by standardizing formats, handling missing values, and correcting any inconsistencies
- Engineered new variables needed for deeper analysis
- Exported a cleaned version of the dataset for use in SQL and Tableau
- Conducted exploratory analysis using visualizations showing:
  - Overall smoking status
  - Smoking prevalence across demographic categories
  - Multivariate patterns (e.g. income × education interactions)
- Extracted preliminary insights to guide the SQL queries and Tableau dashboard design

(link)

## SQL Analysis
SQL was used for:
Validate Python visualizations numerically
Filtering valid smoking responses
Standardizing demographic categories
Aggregating smokers vs. total respondents
Creating summary tables (e.g., smokers by sex, age, race, region)
Ranking demographic groups by smoking prevalence
Full SQL code: (link to your GitHub file)

## Tableau dashboard
Components included:
1. U.S. Map: Smoking Prevalence by State
A filled map showing smoking % by state to quickly spot geographic patterns.
2. Z-Score Table (State Outliers)
Highlights states with unusually high or low rates compared to the national average.
3. Socioeconomic Heatmap: Income × Education
Shows a clear gradient: smoking prevalence decreases as income and education increase.
4. Top 5 Highest-Risk Demographics
Uses the pivoted demographic fields and smoking percentages to reveal the groups with the highest prevalence.
5. Interactive Demographic Breakdown
Users can select "Sex", "Race", "Age", "Region", or "Income" to view smoking percentages for that group individually.
6. Smoking Status Breakdown (Total Population)
A simple table summarizing:
Never smoked
Former smoker
Current smoker (every day + some days)
This gives context for all further charts.
Tableau Dashboard (Image + Link)

Key Findings (Insights)
1. Clear socioeconomic gradient
Smoking prevalence decreases steadily with:
Higher income
Higher educational attainment
Income × Education interaction shows the strongest effect of any demographic variable.

2. Demographics with highest smoking prevalence
Across all categories, the groups appearing most frequently in the “Top 5” include:
Lower income brackets
Lower education levels
Certain age groups (e.g., 25–44 depending on the year)
This matches public health research and validates the analysis.

3. Regional differences
Certain states in the Southeast have significantly higher smoking rates.
Z-scores identify meaningful outliers rather than raw differences.

Limitations
Self-reported survey data may include recall or reporting bias.
Missing demographic values (e.g., income) were categorized as “Unknown” but excluded from rankings.
Cross-sectional data limits causal inference.

Conclusion + Next Steps
This end-to-end project demonstrates:
SQL skills for cleaning and aggregating large datasets
Python skills for exploratory and statistical analysis
Tableau skills for interactive data storytelling
The resulting dashboard provides an accessible visual summary of U.S. smoking patterns, offering valuable insights for public health decisions or demographic research.

Links
Tableau Dashboard: (insert link)
GitHub Folder (All Code + Workbook): (insert link)
SQL Script: (insert link)
Python Notebook: (insert link)
