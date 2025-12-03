# BRFSS Smoking Behavior Analysis: End-to-End Data Project

## Overview
This project analyzes smoking behavior among U.S. adults using the 2023 BRFSS dataset. It utilizes SQL, Python, and Tableau to understand demographic patterns, socioeconomic disparities, and state-level differences in smoking prevalence. The goal is to demonstrate an analytical workflow from raw data preparation to interactive visualization.

This project integrates:

**Python:** for data cleaning, creation of export-ready datasets for SQL and Tableau, and visualization

**SQL:** for querying, filtering, summarizing the BRFSS data subset, validating Python findings 

**Tableau:** for interactive dashboards highlighting state-level smoking z-scores, income × education effects, and demographic risk patterns

The final product is a Tableau dashboard, giving a clear view of where smoking disparities are most pronounced and which population groups are at higher risk. 

## Dataset Description
The analysis uses the 2023 Behavioral Risk Factor Surveillance System (BRFSS) dataset, a nationally representative U.S. health survey with over 400,000 survey responses. The raw dataset includes demographic, socioeconomic, and health behavior variables. For this project, the focus was on smoking-related variables and key demographics such as income, education, age, sex, race, and state. After cleaning and standardizing categories, the dataset was used to examine how smoking patterns varied by different variables.

**Source:** BRFSS (Behavioral Risk Factor Surveillance System) - https://www.kaggle.com/datasets/isuruprabath/brfss-2023-csv-dataset?resource=download 

*Sample extracted for project use*

**Size:** 410187 rows (sample)

**Key Variables Used:**

- `_smoker3`: Smoking status (Current smoker – every day, Current smoker – some days, Former smoker, Never smoked)
- `_state`: Respondent’s state
- `sexvar`: Identifier for sex (male/female)
- `_ageg5yr`: Categorical age variable, with ages in 5 year bins
- `_incomg1`: Categorical Income classification
- `_educag`: Categorical Edcucation level completed
- `_racegr3`: Five level race/ethnicity category

## Project Objectives
To understand patterns and disparities in smoking behavior across the U.S. and highlight high-risk populations:

- Analyze smoking prevalence across demographic and socioeconomic groups
- Detect states and populations with unusually high or low smoking rates
- Identify the top 5 highest-risk demographic groups
- Build an interactive Tableau dashboard to communicate findings

## Python Workflow Summary

- Loaded and inspected the dataset to understand structure, data types, and missing values
- Selected relevant columns and cleaned the data by standardizing formats, handling missing values, and correcting any inconsistencies
- Engineered new "Region" variable for aggregate geographical analysis
- Exported a cleaned version of the dataset for use in SQL and Tableau
- Conducted exploratory analysis using visualizations showing:
  - Overall smoking status
  - Smoking prevalence across demographic categories
  - Multivariate patterns (e.g. income × education interactions)
- Extracted preliminary insights to guide the SQL queries and Tableau dashboard design

**Full Python notebook:** https://github.com/joannaarreola/Python/blob/main/BRFSS%20Smoking%20Analysis/BRFSS%20Smoking%20Behavior%20Analysis%20-%20Python.ipynb

## SQL Workflow Summary
- Created a relational database and a table using the cleaned dataset exported from Python
- Loaded the data and verified integrity to ensure accurate downstream analysis
- Performed exploratory data checks, including:
  - Counting unknown or missing values per demographic category
  - Examining value distributions for each demographic variable
- Conducted analytical queries to validate Python findings numerically:
  - Calculated the percentage of each smoking status across demographic categories
  - Examined combined education × income patterns
- Ranked demographic groups to identify the top 5 highest-risk populations for current smoking
- Quantified income and education gradients in relation to combined current smoking rates

**Full SQL queries:** https://github.com/joannaarreola/SQL/tree/main/BRFSS%20Smoking%20Behavior%20Analyis%20Project

## Tableau Dashboard
Components included:

**Smoking Status Breakdown (Total Population)**
- A simple table summarizing smoking status for all survey respondents

This gives context for all further charts

**U.S. Map: Smoking Prevalence by State**
 - A filled map showing smoking % by state to quickly spot geographic patterns
   
**Z-Score Table**
- Highlights states with unusually high or low smoking rates relative to the national average
  
**Socioeconomic Heatmap: Income × Education**
- Shows a clear gradient: smoking prevalence decreases as income and education increase
  
**Top 5 High Risk Demographics**
- A table of the top 5 demographics that reflect high risk for current smoking
  
**Interactive Demographic Breakdown**
- Users can select "Age", "Education", "Income", "Race", "Region", and/or "Sex" to view smoking percentages for that group individually or in comparison to another group.

**Tableau Dashboard:** https://public.tableau.com/app/profile/joanna.arreola8667/viz/BRFSSSmokingBehaviorAnalysis/Dashboard1#1
<img width="1099" height="1499" alt="Dashboard 1 (3)" src="https://github.com/user-attachments/assets/61013b79-9f66-457e-8884-bad94e21c4b3" />


## Key Findings 
**Overall Smoking Status**
- A majority of respondents (61.4%) have never smoked
- Former smokers represent the second largest category of the sample (27.6%)
- Among current smokers (11%), everyday smoking (7.7%) is more common than someday smoking (3.3%)

**Geographic Patterns**
- The Virgin Islands, Utah, District of Columbia, and Puerto Rico have the lowest rates of current smoking
- West Virginia, Guam, and Tennessee show the highest rates of current smoking
- The South and Midwest show slightly higher smoking rates than other U.S. regions

**Education Gradient**
- Smoking rates are highest among individuals who did not graduate high school and lowest among college/technical school graduates
- The proportion of “never smoked” rises steadily with education level.
- SQL analysis shows the largest drop in smoking occurs between:
  - Attended College/Technical School → Graduated College/Technical School

**Income Gradient**
- Higher income levels are associated with:
  - more “never smoked” respondents
  - fewer current smokers
- The steepest decrease in smoking occurs between:
  - <$15,000 → $15,000–<$25,000
- Middle income groups show a steady, gradual decline

**Education × Income Interaction**
- Among those with very low income, education has a weaker effect on smoking rates 
- For individuals with middle to high incomes, education has a much stronger effect: smoking drops substantially as both income and education rise
- The highest smoking rates overall appear among adults with low income + low education, while the lowest rates appear among those with high income + higher education

**Age Trends**
- Current smoking follows a bell-shaped pattern, peaking around ages 40–60
- The share of “never smoked” declines up to the 40s and levels off afterward

**Race/Ethnicity Patterns**
- Hispanic respondents have the lowest rates of current smoking
- Multiracial Non-Hispanic respondents have the highest rates of current smoking
- “Never smoked” percentages are highest among Hispanic and Black Non-Hispanic adults

**Gender Patterns**
- Females have higher rates of never smoking
- Males have slightly higher rates of current smokers

**Highest-Risk Demographic Groups (SQL Ranking)**
- Top 5 groups with the highest current smoking prevalence:
  1. Income: <$15,000
  2. Education: Did Not Graduate High School
  3. Income: $15,000–<$25,000
  4. Race: Multiracial, Non-Hispanic
  5. Income: $25,000–<$35,000
- These groups represent the most vulnerable populations for smoking risk based on this dataset.

## Limitations
- Self-reported survey data may include recall or reporting bias
- The cross-sectional nature of the data limits our ability to draw causal conclusions. Results reflect correlations, not causation
- Missing demographic values were categorized as “Unknown” but excluded from rankings and visualizations

## Conclusion + Next Steps

This smoking analysis highlights clear disparities in smoking prevalence across socioeconomic and geographic groups. While causation cannot be established due to the cross-sectional nature of the data, these associations offer valuable insights for public health decisions or demographic research and suggest that public health interventions could be targeted to the most at-risk populations. Future research with longitudinal data could clarify causal pathways and help refine these interventions.

## Links
**Cleaned Dataset:** https://github.com/joannaarreola/Python/blob/main/BRFSS%20Smoking%20Analysis/cleaned_brfss2023.csv.zip

**Raw Dataset:** https://www.kaggle.com/datasets/isuruprabath/brfss-2023-csv-dataset?resource=download

**Python Notebook:** https://github.com/joannaarreola/Python/blob/main/BRFSS%20Smoking%20Analysis/BRFSS%20Smoking%20Behavior%20Analysis%20-%20Python.ipynb

**SQL Queries:** https://github.com/joannaarreola/SQL/tree/main/BRFSS%20Smoking%20Behavior%20Analyis%20Project

**Tableau Dashboard:** https://public.tableau.com/app/profile/joanna.arreola8667/viz/BRFSSSmokingBehaviorAnalysis/Dashboard1#1

**GitHub Project Folder:** https://github.com/joannaarreola/Python/tree/main/BRFSS%20Smoking%20Analysis


