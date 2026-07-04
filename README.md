# HR Analytics Dashboard (Tableau)

An interactive Tableau dashboard that analyzes employee attrition across departments, age groups, gender, education background, and job roles — built to help HR teams spot where and why employees are leaving, and to support faster, data-driven retention decisions.

## Dashboard Preview

![HR Analytics Dashboard](HR%20ANALYTICS%20DASHBOARD_.png)

## Overview

The dashboard brings together KPI summary cards, categorical breakdowns, and demographic cross-tabs into a single view. A global Education filter lets users slice every chart by education level, and the age histogram includes an adjustable Bin Size control for exploring different age groupings on the fly.

## Objective

- Track overall headcount and attrition rate at a glance
- Identify which departments and education backgrounds are most affected by attrition
- Understand how attrition varies across age groups and gender
- Analyze the relationship between job satisfaction and job role
- Give HR stakeholders a single, filterable view to support retention planning

## Dataset

The workbook connects to an HR employee dataset (`HR Data.xlsx`) with employee-level records, including:

- **Demographics:** Age, Gender, Marital Status, Education, Education Field
- **Job details:** Department, Job Role, Job Level, Business Travel, Over Time
- **Attrition:** Attrition (Yes / No), Employee Number
- **Satisfaction & performance:** Job Satisfaction, Environment Satisfaction, Job Involvement, Performance Rating, Work Life Balance
- **Compensation & tenure:** Monthly Income, Daily Rate, Hourly Rate, Total Working Years, Years At Company, Years Since Last Promotion, Years With Curr Manager

## Tools Used

- **Tableau Desktop / Tableau Public** — dashboard design and visualization
- **Microsoft Excel** — source data
- **Tableau Calculated Fields & Parameters** — custom KPI logic and dynamic age binning

## Key Metrics (KPIs)

| Metric | Value |
|---|---|
| Employee Count | 961 |
| Attrition Count | 133 |
| Attrition Rate | 13.84% |
| Active Employees | 828 |
| Average Age | 37 |

## Dashboard Components

1. **KPI Summary Bar** – Employee Count, Attrition Count, Attrition Rate, Active Employees, Average Age
2. **Attrition by Gender** – bar comparing attrition counts for Male vs Female employees
3. **Department wise Attrition** – pie chart of attrition distribution across HR, R&D, and Sales
4. **No of Employees by Age Group** – histogram of employee counts by age, with a live Bin Size control
5. **Job Satisfaction Rating** – heat-mapped matrix of job satisfaction scores (1–4) by job role
6. **Education Field wise Attrition** – bar chart of attrition counts by education field (Life Sciences, Medical, Technical Degree, Other)
7. **Attrition Rate by Gender for Different Age Groups** – donut charts breaking attrition down by gender across five age bands (Under 25, 25–34, 35–44, 45–54, Over 55)

An **Education** filter at the top right lets users slice every view by education level.

## Calculated Fields & Parameters

| Field | Logic |
|---|---|
| Attrition Count | `IF [Attrition] = 'Yes' THEN 1 ELSE 0 END` |
| Active Employees | `SUM([Employee Count]) - SUM([Attrition Count])` |
| Age (bin) | Binned version of `[Age]`, driven by the Bin Size parameter |
| Bin Size (parameter) | Default value **4** — dynamically controls the age histogram's bucket width |

## Key Insights

- Overall attrition rate stands at **13.84%**, with 133 employees having left out of 961.
- Attrition skews heavily male: **90 male vs 43 female** exits (about 68% vs 32% of all attrition).
- The **25–34 age band** is the single biggest attrition hotspot — it alone accounts for 65 of the 133 exits (nearly **49% of all attrition**), with men in that band contributing 33.83% of company-wide attrition on their own.
- Attrition falls off sharply after age 45: the 45–54 and Over 55 bands together make up less than **14%** of total attrition.
- By education background, **Life Sciences (59)** and **Medical (47)** account for roughly 80% of all attrition, far ahead of Technical Degree (20) and Other (7).
- Employees with a Job Satisfaction score of 4 (the highest rating) still make up the largest group in the workforce (295 of 961) — a reminder that stated satisfaction alone doesn't fully explain who leaves, and other factors (age, overtime, income, tenure) are worth exploring further.

## Repository Structure

```
├── HR ANALYTICS DASHBOARD_.png     # Dashboard screenshot
├── Tableau_Project.twb             # Tableau workbook file
└── README.md                       # Project documentation
```

## How to Use

1. Download `Tableau_Project.twb` and open it in Tableau Desktop or Tableau Public.
2. Make sure the source file `HR Data.xlsx` is available, or reconnect the data source to your own HR dataset with matching column names.
3. Use the **Education** filter to explore attrition patterns by education level.
4. Adjust the **Bin Size** control on the age histogram to regroup ages on the fly.
5. Hover over any chart element for detailed tooltips.

## Author

**Meraj Husen**
GitHub: [Merajhusen7](https://github.com/Merajhusen7)
