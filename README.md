
# Employee Attrition Data Cleaning & Preparation Pipeline

**Python | Pandas | NumPy | Data Cleaning | Exploratory Data Analysis**

## Project Overview

This project focuses on assessing, cleaning, and preparing employee workforce data for accurate analysis and reporting. The objective is to identify and resolve data quality issues, including missing values, duplicate records, inconsistent categorical values, formatting problems, incorrect data types, and potential outliers.

Using Python, Pandas, and NumPy, a structured data preparation pipeline was developed to transform raw employee records into a clean, standardized, and analysis-ready dataset.

The prepared dataset provides a reliable foundation for employee attrition analysis, HR reporting, workforce analytics, and future predictive modeling.

## Business Requirements

Organizations rely on accurate workforce data to understand employee turnover, improve retention strategies, and support workforce planning.

The project addresses the following business requirements:

- Assess the quality and structure of the employee dataset.
- Identify missing values and duplicate records.
- Detect inconsistent categorical values and formatting issues.
- Correct data types and standardize data fields.
- Identify and handle potential outliers.
- Produce a clean and validated dataset for further analysis.
- Establish a reliable foundation for workforce analytics and employee attrition reporting.

## Dataset Overview

The dataset contains approximately **10,200 employee records** and **16 variables** representing different workforce attributes.

Key variables include:

| Variable | Description |
|---|---|
| EmployeeNumber | Unique employee identifier. |
| Age | Employee age. |
| Tenure | Years of employment. |
| Turnover | Employee turnover status (Yes/No). |
| HourlyRate | Employee hourly pay rate. |
| HoursWeekly | Weekly working hours. |
| CompensationType | Employee compensation category. |
| AnnualSalary | Annual employee salary. |
| DrivingCommuterDistance | Distance between home and workplace. |
| JobRoleArea | Employee job role or department area. |
| Gender | Employee gender category. |
| MaritalStatus | Employee marital status. |
| NumCompaniesPreviouslyWorked | Number of previous employers. |
| AnnualProfessionalDevHrs | Annual professional development hours. |
| PaycheckMethod | Employee payment method. |
| TextMessageOptIn | Employee text message preference. |

## Data Quality Assessment

The initial dataset was examined using Python-based exploratory data analysis techniques to identify quality issues before transformation.

The assessment included:

- **Dataset Structure:** Reviewed rows, columns, data types, and non-null counts using `df.shape` and `df.info()`.
- **Missing Values:** Identified incomplete records using `df.isnull().sum()`.
- **Duplicate Records:** Detected repeated entries using `df.duplicated().sum()`.
- **Unique Values:** Examined categorical variations using `df.nunique()` and `value_counts()`.
- **Statistical Summary:** Reviewed numerical distributions using `df.describe()`.
- **Formatting Issues:** Inspected currency symbols and inconsistent text representations.
- **Outlier Detection:** Evaluated numerical variables, particularly AnnualSalary, using statistical measures and the IQR method.

## Identified Data Quality Issues

The assessment identified several data quality challenges:

1. **Missing Values:** Incomplete values in professional development hours, previous companies worked, paycheck method, and text message preferences.
2. **Duplicate Records:** Repeated employee records requiring removal.
3. **Inconsistent Categories:** Variations in PaycheckMethod and JobRoleArea values.
4. **Formatting Issues:** Currency symbols in the HourlyRate column affecting numerical operations.
5. **Data Type Issues:** Columns requiring conversion into appropriate numerical formats.
6. **Potential Outliers:** Extreme AnnualSalary values requiring further evaluation.

## Data Cleaning & Transformation

A structured Python pipeline was implemented to resolve the identified issues.

### 1. Data Type Correction

- Removed unnecessary whitespace from column names.
- Removed currency symbols from HourlyRate.
- Converted HourlyRate into a numerical data type.
- Standardized AnnualSalary and other numerical columns using appropriate numeric conversions.

### 2. Missing Value Treatment

- Replaced invalid `N/A` entries with `NaN`.
- Used median imputation for numerical variables.
- Used mode imputation for categorical variables.
- Applied a defined default value for missing TextMessageOptIn entries.

### 3. Duplicate Removal

Removed duplicate records using:

`df.drop_duplicates()`

This ensured repeated observations were excluded from the prepared dataset.

### 4. Categorical Standardization

Standardized inconsistent category representations in:

- PaycheckMethod
- JobRoleArea
- Gender

Examples included converting variations such as `Direct_Deposit` and `DirectDeposit` into `Direct Deposit`.

### 5. Outlier Treatment

Applied the **Interquartile Range (IQR)** method to identify and filter extreme AnnualSalary values.

The lower and upper boundaries were calculated using:

- Q1: First Quartile
- Q3: Third Quartile
- IQR: Q3 − Q1
- Lower Bound: Q1 − 1.5 × IQR
- Upper Bound: Q3 + 1.5 × IQR

Records outside the calculated salary boundaries were excluded from the prepared dataset.

### 6. Feature Standardization

Converted binary categorical variables into numerical representations:

| Original Value | Encoded Value |
|---|---:|
| Yes | 1 |
| No | 0 |

Applied to:

- Turnover
- TextMessageOptIn

This transformation supports further statistical analysis and machine learning workflows.

## Final Data Validation

After completing the cleaning process, the dataset was validated again to check its quality and consistency.

Validation techniques included:

- `df.isnull().sum()` — Verify remaining missing values.
- `df.duplicated().sum()` — Check duplicate records.
- `df.info()` — Review final data structure.
- `df.dtypes` — Verify column data types.
- `df.describe()` — Review numerical distributions.
- `df.head()` — Inspect prepared records.
- `df.shape` — Compare dataset dimensions before and after cleaning.

The final cleaned dataset was exported as a CSV file for future analysis and reporting.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Jupyter Notebook
- CSV

## Technical Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data Profiling and Quality Assessment
- Missing Value Treatment
- Duplicate Detection and Removal
- Categorical Data Standardization
- Data Type Conversion
- Outlier Detection and Treatment
- Feature Encoding
- Data Validation
- Data Preparation and Transformation

## Business Value

The data preparation pipeline improves the reliability and consistency of employee workforce records.

The cleaned dataset supports organizations in:

- Conducting more reliable employee attrition analysis.
- Developing HR dashboards and workforce KPI reports.
- Supporting employee retention initiatives.
- Improving workforce planning and reporting.
- Preparing data for future statistical analysis and predictive modeling.

## Project Deliverables

- Original employee turnover dataset.
- Cleaned and standardized employee dataset.
- Python-based data cleaning and preparation pipeline.
- Documented data quality assessment and cleaning methodology.
- Employee turnover considerations and data dictionary.

## Repository Structure

```text
Employee-Attrition-Data-Cleaning-Pipeline/
│
├── README.md
├── Business Requirement.docx
├── Employee Attrition Pipeline Report.docx
├── Employee Turnover Considerations and Dictionary.docx
│
├── 01_Dataset/
│   ├── Employee Turnover Dataset.csv
│   └── employee_turnover_cleaned.csv
│
└── 02_Python_Implementation/
    └── Employee Attrition Pipeline.ipynb
```

## Project Files

| File | Description |
|---|---|
| [Business Requirement](Business%20Requirement.docx) | Business scenario and project requirements. |
| [Employee Attrition Pipeline Report](Employee%20Attrition%20Pipeline%20Report.docx) | Detailed data quality assessment, cleaning methodology, and validation results. |
| [Employee Turnover Considerations and Dictionary](Employee%20Turnover%20Considerations%20and%20Dictionary.docx) | Business scenario and descriptions of all dataset variables. |
| [Original Dataset](01_Dataset/Employee%20Turnover%20Dataset.csv) | Raw employee turnover dataset. |
| [Cleaned Dataset](01_Dataset/employee_turnover_cleaned.csv) | Cleaned and analysis-ready employee dataset. |

## About the Author

**Muhammad Jan**  
Data Analytics & Business Intelligence Specialist

Interested in transforming raw data into meaningful insights through data analytics, database management, automation, and business intelligence solutions.

- **GitHub:** [Muhammad Jan](https://github.com/Muhammad-Jan)
- **LinkedIn:** [Muhammad Jan](YOUR-LINKEDIN-PROFILE-URL)

---

**Domain:** Human Resources & Workforce Analytics  
**Project Focus:** Data Cleaning & Preparation  
**Technology:** Python, Pandas & NumPy
