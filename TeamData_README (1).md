# Design Team Workflow and Billability Analysis

A full data science pipeline applied to anonymised time-tracking data from a design team in the South African TV and entertainment industry. The project covers data cleaning, exploratory data analysis, feature engineering and machine learning classification.

---

## Project Overview

This project analyses how a creative design team allocates billable versus non-billable time across clients, projects and days of the week. A Random Forest classification model is then built to predict whether a given task entry will be billable based on team and project context.

The dataset is drawn from real internal time-tracking data, anonymised to protect client and team confidentiality.

---

## Key Findings

| Metric | Finding |
|---|---|
| Total entries analysed | 503 clean rows after data wrangling |
| Billable hours share | 92.1% of all logged hours are billable |
| Non-billable hours share | 7.9% spent on administrative and internal work |
| Busiest day | Monday carries the highest billable hours |
| Weekend work | Recurring weekend work confirmed across the team |
| Typical task size | Most entries are under 2 hours |
| Model accuracy | High accuracy limited by class imbalance in small dataset |

---

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data cleaning, wrangling and analysis |
| Matplotlib and Seaborn | Data visualisation with colorblind-safe palette |
| Scikit-learn | Feature engineering, Random Forest classification, model evaluation |
| SQL | Exploratory data analysis |
| Jupyter Notebooks | Analysis environment |

---

## Project Structure

```
design-team-billability-analysis/
│
├── team_data_pipeline.ipynb    # Full analysis notebook
├── team_data.csv               # Anonymised time-tracking dataset
└── README.md
```

---

## Pipeline Overview

**Step 1 - Data Loading and Exploration**
Initial inspection of 510 rows across 11 columns including person, role, department, client, project, date and logged hours. Summary statistics revealed anomalies requiring cleaning.

**Step 2 - Data Cleaning**
Removed 5 junk rows that were report summary rows accidentally included in the export. Dropped 2 rows with null values representing 0.4% of data. Converted date column from object to datetime. Converted logged fee column from text to numeric and found it entirely null, confirming inconsistent data capture. Column was dropped. Final clean dataset: 503 rows, 10 columns.

**Step 3 - Exploratory Data Analysis**
Visualised billable versus non-billable hours per designer, overall team split, hours logged over time, hours by day of week and distribution of task sizes. Key insight: 92.1% billability rate indicates a highly productive and client-focused team. Recurring weekend work reflects broadcast deadline culture in the TV and entertainment industry.

**Step 4 - Feature Engineering**
Created three new features for the classification model: Is_Billable as the binary target variable, Total_Hours as the combined hours per entry, and Day_of_Week_Num as a numeric encoding of day. Categorical columns encoded using LabelEncoder.

**Step 5 - Model Building and Evaluation**
Random Forest classifier trained and evaluated. Leaky features identified and removed before final model run. Class imbalance noted: 89% of entries are billable. Model limitations acknowledged honestly with recommendations for improvement on a larger dataset.

---

## Key Observations

**Billability Rate**
92.1% of all logged hours are billable, which is a strong efficiency metric for a creative team operating in the fast-paced TV and entertainment sector.

**Weekend Work Pattern**
Weekend work is a recurring pattern across the team rather than an isolated incident. This reflects the broadcast deadline-driven nature of the industry where content delivery timelines do not follow a Monday to Friday schedule.

**Task Size Distribution**
Most task entries are under 2 hours, consistent with a creative workflow involving frequent short turnaround deliverables. A small number of larger entries represent more complex or extended productions.

**Model Limitation**
With 503 rows, 2 clients and 2 projects, the dataset lacks sufficient complexity for a robust classifier. The high accuracy reflects class imbalance rather than genuine predictive power. A larger, more varied dataset would be required in a production environment.

---

## Data Note

All person names, client names and project names have been anonymised. The dataset covers February 2026 and reflects the working patterns of a design team operating across broadcast and digital entertainment productions in South Africa.

---

## About the Analyst

**Brandon Muchenje**
Data Analyst based in Johannesburg, South Africa

- GitHub: [github.com/brandonmuch](https://github.com/brandonmuch)
- Email: brandonmuchenje01@gmail.com

**Certifications:**
- IBM Data Science Professional Certificate, 10 courses, ACE Accredited
- Microsoft Power BI Data Analyst Professional Certificate, In Progress
- Data Science and Machine Learning, 360 Careers, Udemy

**Education:**
- Postgraduate Diploma in Risk Management, UNISA, Expected March 2027
- Bachelor of Commerce in Law, Cum Laude, Monash University South Africa
