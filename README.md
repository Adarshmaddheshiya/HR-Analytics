# HR Analytics Dashboard -- Power BI

## 📊 Project Overview

This project is an **HR Analytics Dashboard** built in **Microsoft Power
BI** to analyze employee attrition, workforce demographics, salary
levels, job satisfaction, and department-wise employee exits.

The dashboard helps HR teams identify patterns behind employee attrition
and understand which employee groups, salary ranges, job roles, and
departments require attention.

------------------------------------------------------------------------

## 🎯 Project Objectives

-   Analyze overall employee attrition.
-   Track the total employee count and attrition rate.
-   Understand attrition across education fields.
-   Analyze attrition by salary slab.
-   Compare job roles with job satisfaction levels.
-   Identify age groups with higher employee attrition.
-   Analyze the relationship between years at company and attrition.
-   Compare employee exits across departments.
-   Provide interactive filtering using **Gender** and **Department**
    slicers.

------------------------------------------------------------------------

## 🛠️ Tools & Technologies

  Tool              Purpose
  ----------------- ----------------------------------------------
  **Power BI**      Data modeling, DAX, visualization, dashboard
  **Power Query**   Data cleaning and transformation
  **CSV**           Source dataset
  **DAX**           KPI calculations and analytical measures

------------------------------------------------------------------------

## 📁 Dataset

**File:** `HR_Analytics(1).csv`

The source dataset contains:

-   **1,480 employee records**
-   **38 columns**

### Important Fields

  Field                       Description
  --------------------------- ---------------------------------------
  `EmpID`                     Employee identifier
  `Age`                       Employee age
  `AgeGroup`                  Employee age category
  `Attrition`                 Whether the employee left the company
  `Department`                Employee department
  `Gender`                    Employee gender
  `EducationField`            Employee education field
  `JobRole`                   Employee job role
  `JobSatisfaction`           Job satisfaction rating
  `MonthlyIncome`             Monthly employee income
  `SalarySlab`                Salary category
  `OverTime`                  Overtime status
  `YearsAtCompany`            Years spent at the company
  `TotalWorkingYears`         Total professional experience
  `YearsInCurrentRole`        Years in current role
  `YearsSinceLastPromotion`   Years since last promotion
  `YearsWithCurrManager`      Years working with current manager

------------------------------------------------------------------------

## 📌 Dashboard KPIs

The dashboard displays key HR metrics such as:

### 1. Total Employees

Shows the number of employees included in the current dashboard context.

### 2. Attrition Rate

``` dax
Attrition Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS('HR Analytics'),
        'HR Analytics'[Attrition] = "Yes"
    ),
    COUNTROWS('HR Analytics')
)
```

Format the measure as **Percentage**.

### 3. Average Monthly Income

``` dax
Average Monthly Income =
AVERAGE('HR Analytics'[MonthlyIncome])
```

------------------------------------------------------------------------

## 📈 Dashboard Visuals

### 1. Attrition Rate by Education Field

A doughnut chart showing employee attrition across:

-   Human Resources
-   Technical Degree
-   Marketing
-   Life Sciences
-   Other
-   Medical

**Purpose:** Identify education fields associated with employee exits.

### 2. Attrition by Salary Slab

A horizontal bar chart showing attrition across salary categories:

-   Upto 5k
-   5k--10k
-   10k--15k
-   15k+

**Purpose:** Understand whether attrition is concentrated in particular
salary ranges.

### 3. Job Role vs Job Satisfaction

A matrix showing job roles against satisfaction ratings from **1 to 4**,
with totals.

**Purpose:** Compare satisfaction levels across different job roles.

### 4. Attrition by Age Group

A column chart comparing attrition across age groups:

-   18--25
-   26--35
-   36--45
-   46--55
-   55+

**Purpose:** Identify age groups with comparatively higher employee
exits.

### 5. Years at Company vs Attrition Count

A line chart showing attrition count by years employees have spent at
the company.

**Purpose:** Analyze whether employee exits are concentrated during
particular stages of tenure.

### 6. Employees Left by Department

A column chart comparing attrition across:

-   Research & Development
-   Sales
-   Human Resources

**Purpose:** Identify departments with higher numbers of employee exits.

------------------------------------------------------------------------

## 🎛️ Interactive Filters

The dashboard includes slicers for:

### Gender

-   Female
-   Male

### Department

-   Human Resources
-   Research & Development
-   Sales

Users can select one or multiple values to dynamically update the
dashboard visuals.

------------------------------------------------------------------------

## 🔄 Data Preparation

The dataset was prepared for Power BI analysis by:

1.  Importing the CSV file into Power BI.
2.  Reviewing data types and column quality.
3.  Checking missing values.
4.  Validating categorical fields such as Department, Gender, Attrition,
    and SalarySlab.
5.  Using existing analytical fields such as AgeGroup and SalarySlab.
6.  Creating DAX measures for KPI calculations.
7.  Building interactive visuals and slicers.

> **Data-quality note:** The source CSV contains missing values in
> `YearsWithCurrManager`. This field should be handled appropriately
> before using it in calculations that require complete values.

------------------------------------------------------------------------

## 💡 Key Analytical Questions

This dashboard can answer questions such as:

-   What is the overall employee attrition rate?
-   Which department has the highest number of employee exits?
-   Which age group shows the highest attrition count?
-   Which salary slab has the highest number of employees leaving?
-   How does job satisfaction vary by job role?
-   Is attrition concentrated among employees with shorter tenure?
-   Which education fields have higher attrition counts?
-   How do gender and department filters change the HR metrics?

------------------------------------------------------------------------

## 📊 Sample Dataset-Level Findings

Based on the provided CSV before dashboard filtering/model
transformations:

-   **Total records:** 1,480
-   **Employees with Attrition = Yes:** 238
-   **Employees with Attrition = No:** 1,242
-   **Overall attrition rate:** approximately **16.08%**
-   **Average monthly income:** approximately **6,505**
-   The largest number of attrition records is in the **Research &
    Development** department.
-   The **26--35** age group has the highest attrition count in the
    source data.
-   The **Upto 5k** salary slab contains the largest number of attrition
    records.

These values describe the source CSV and can differ from the Power BI
dashboard when filters, transformations, or model-level exclusions are
applied.

------------------------------------------------------------------------

## 📂 Recommended Project Structure

``` text
HR-Analytics/
│
├── README.md
├── HR Analytics.pbix
├── HR_Analytics(1).csv
│
├── Documentation/
│   └── Dashboard_Screenshots/
│
└── Assets/
    └── HR_Dashboard.png
```

------------------------------------------------------------------------

## ▶️ How to Use the Project

1.  Download or clone the project.
2.  Open `HR Analytics.pbix` in **Microsoft Power BI Desktop**.
3.  If Power BI asks for the data source, reconnect it to
    `HR_Analytics(1).csv`.
4.  Open the dashboard page.
5.  Use the **Gender** and **Department** slicers.
6.  Select different values and observe how the KPIs and charts change.
7.  Hover over visuals to inspect detailed values.

------------------------------------------------------------------------

## 🚀 Future Improvements

Possible extensions for this project:

-   Add an **Overtime vs Attrition** analysis.
-   Add **Job Level vs Attrition** analysis.
-   Add **Monthly Income vs Attrition** analysis.
-   Add employee tenure buckets.
-   Add drill-through pages for department and job role.
-   Add tooltip pages for detailed employee insights.
-   Add a dedicated **Executive Summary** page.
-   Add HR recommendations based on statistically supported patterns.
-   Add automated data refresh when the source data changes.

------------------------------------------------------------------------

## 👤 Project Type

**Data Analytics / HR Analytics / Business Intelligence**

### Skills Demonstrated

-   Data Cleaning
-   Data Transformation
-   Data Analysis
-   Power BI
-   Power Query
-   DAX
-   Data Visualization
-   Dashboard Design
-   KPI Development
-   HR Analytics
-   Business Intelligence

------------------------------------------------------------------------

## 📌 Disclaimer

This dashboard is intended for analytical and educational purposes. The
results describe patterns in the provided dataset and should not be
treated as causal conclusions about why individual employees leave an
organization.
