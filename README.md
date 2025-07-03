# Elevate_Lab_project
HR Analytics Dashboard for Attrition 

# 📊 HR Analytics Dashboard – Power BI Project

## 🧩 Project Overview

This Power BI project provides an end-to-end solution to analyze and visualize HR data for a company's workforce. It helps track employee attrition trends, satisfaction levels, age and gender distribution, and department-level insights, empowering data-driven HR decisions.



## 🎯 Objective

* To identify patterns and causes of employee attrition.
* To analyze employee demographics (age, gender, department).
* To monitor job satisfaction across various roles.
* To assist HR teams with actionable insights for workforce planning.



## 🛠️ Tools & Technologies Used

| Tool           | Purpose                                            |
| -------------- | -------------------------------------------------- |
| Power BI       | Dashboard building and data visualization          |
| DAX (Measures) | KPI calculations, custom logic                     |
| Power Query    | Data cleaning, transformation, conditional columns |
| Excel/CSV      | Data source format (assumed from context)          |


## 🚀 Implementation Steps (Start to End)

### 1. **Data Import**

* Imported raw HR dataset from Excel/CSV using **Get Data**.
* Used fields like `EmployeeID`, `Age`, `Department`, `Attrition`, `Job Role`, `Gender`, `Education`, and `Satisfaction`.


### 2. **Data Cleaning & Transformation**

* Renamed columns for clarity.
* Removed nulls or irrelevant rows.
* Created a **conditional column**: `Age Band` with categories:

  * `Under 25`, `25–34`, `35–44`, `45–54`, `Over 55`



### 3. **Calculated Columns & Conditional Logic**

* Used **Power Query Editor** to define new columns like:

  * `Age Band`
  * Possibly others like `Education Field Category` or `Attrition Flag`

### 4. **DAX Measures Created**

Defined custom measures using DAX for KPI cards:

```DAX
Total Employees = COUNT(EmployeeID)
Attrition Count = CALCULATE(COUNT(EmployeeID), HR[Attrition] = "Yes")
Attrition Rate = DIVIDE([Attrition Count], [Total Employees]) * 100
Active Employees = [Total Employees] - [Attrition Count]
Average Age = AVERAGE(HR[Age])
```

Also used DAX in matrix and donut charts (e.g., counts by conditions, percentage distributions).



### 5. **Visualizations Added**

Used a clean, dark-themed dashboard layout with the following visualizations:

* 🔹 **KPI Cards**: Total Employees, Attrition, Attrition Rate, Active Employees, Average Age
* 🔹 **Pie Chart**: Department-wise attrition
* 🔹 **Bar/Column Charts**:

  * Employees by age band and gender
  * Education field-wise attrition
* 🔹 **Matrix Table**: Job satisfaction ratings by job role
* 🔹 **Donut Charts**: Attrition by gender and age group


### 6. **Filters and Interactivity**

* Added slicers and filters like Age, Gender, Department (optional)
* Enabled **cross-filtering** for dynamic interaction between visuals
* Configured tooltips for detailed hover insights

## 💡 Key Insights from Dashboard

* The **HR department** has the highest attrition percentage.
* **Young employees (Under 25, 25–34)** have the highest attrition rates.
* **Life Sciences** shows highest attrition in education field.
* Some job roles like **Research Scientists** have high attrition despite high satisfaction.

## 🔒 Data Privacy Note

Ensure anonymization of employee data before publishing or sharing. Always comply with data privacy regulations.


## 📌 Outcome

This dashboard helps HR teams track workforce trends in real-time, identify high-risk groups, and make informed retention and recruitment decisions.


