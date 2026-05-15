# Design Team Billability Analysis
### Operational Data Governance | Workforce Analytics | Data Quality Audit

---

## Overview

An end-to-end data governance and analytics pipeline applied to anonymised
time-tracking data from a broadcast and digital entertainment design team.
This project covers data quality auditing, operational risk identification,
and classification modelling — with a deliberate ethical framework around
individual-level data use.

---

## Project Summary

| Item | Detail |
|---|---|
| **Dataset** | 503 rows of anonymised time-tracking data |
| **Source** | South African broadcast and digital entertainment design team |
| **Scope** | February 2026 operational period |
| **Objective** | Audit data quality, identify billing inefficiencies, classify billable vs non-billable tasks |

---

## Data Governance Approach

### Data Quality Audit
Before any analysis, a structured quality assessment was conducted across all fields:

| Column | Issue | Governance Action |
|---|---|---|
| Client | 7 missing values | Flagged as data entry gap |
| Project Code | 7 missing values | Flagged for process review |
| Logged Fee | 510 missing values (entire column) | Identified as critical governance failure |
| Billable Hours | 6 missing values | Flagged for remediation |
| Non-Billable Hours | 6 missing values | Flagged for remediation |

**Key Finding:** The complete absence of fee data across all 503 rows represents
a material operational risk — billing decisions were being made without a
governed data trail.

### Ethical Boundaries
A deliberate governance decision was made to exclude individual-level analysis
from this project. Analysing performance by person without proper HR governance
frameworks risks unfair assessment and policy violations. All analysis is scoped
to clients, projects, and task categories only.

---

## Pipeline Overview

### 1. Data Cleaning (SQL)
- Identified and documented all NULL values across all fields
- Standardised categorical fields for consistency
- Applied structured transformation queries with documented rationale

### 2. Exploratory Data Analysis (Python)
- Distribution of billable vs non-billable hours by project and client
- Time trend analysis across the operational period
- Identification of task categories with highest non-billable concentration

### 3. Feature Engineering
- Created `billable_ratio` feature (billable hours divided by total hours)
- Extracted temporal features including day of week
- Created binary `is_billable` target variable for classification

### 4. Classification Model

| Item | Detail |
|---|---|
| **Algorithm** | Random Forest Classifier |
| **Target** | Billable vs non-billable task classification |
| **Evaluation** | Confusion matrix, classification report |

### 5. Model Limitations
With 503 rows, 2 clients, and 2 projects, the dataset lacks sufficient
complexity for a robust production classifier. High accuracy reflects class
imbalance rather than genuine predictive power. A larger, more varied dataset
would be required before deploying in a production governance context.

---

## Key Findings

- A critical data governance gap was identified — the fee column, intended as
  the primary billing reference, was entirely unpopulated across all records
- Non-billable time was concentrated in specific task types, suggesting process
  design rather than individual behaviour as the root cause
- Data entry inconsistencies across client and project code fields indicate a
  need for structured data governance policies and input validation

---

## Relevance to AI and Data Governance

| What I Did | Governance Skill Demonstrated |
|---|---|
| Audited data quality across all fields before analysis | Data quality assessment and documentation |
| Identified a critical missing data field across 503 records | Operational risk identification |
| Applied ethical boundaries around individual-level data | Responsible data use and privacy governance |
| Documented all transformation decisions with rationale | Data lineage and auditability |
| Disclosed model limitations prior to any production recommendation | Responsible AI disclosure |
| Recommended structured data governance policies based on findings | Governance advisory and remediation |

---

## Tools

`Python` `Pandas` `Scikit-learn` `Seaborn` `Matplotlib`
`SQL` `DB Browser for SQLite` `Jupyter Notebook`

---

## Data Note

Data access for this project was formally requested from and granted by the
relevant stakeholders prior to analysis. All records were anonymised before
use in line with responsible data handling practices. The dataset covers
February 2026 and reflects the working patterns of a design team operating
across broadcast and digital entertainment productions in South Africa.
All person names, client names, and project names have been anonymised.

---

## About

**Brandon Muchenje** | AI Governance and Risk Specialist
brandonmuchenje01@gmail.com
