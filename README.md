# Messy-Customer-Dataset-Data-Cleaning-Preprocessing-Python

A real-world customer sales dataset containing demographic, transactional, and feedback data. The dataset includes missing values, duplicates, inconsistent formats, and outliers, making it suitable for practicing data cleaning, preprocessing, and data quality improvement using Python.

---
## 📘 Project Overview

This project focuses on cleaning and preprocessing a real-world messy customer sales dataset using Python.
The dataset contained missing values, duplicates, inconsistent formats, incorrect data types, and outliers, which were systematically identified and resolved to prepare it for analysis and modeling.

---
 ## **Dataset Description**

The dataset includes customer demographic and transactional data, such as:

| Column Name            | Description                              |
|------------------------|------------------------------------------|
| Customer_ID            | Unique identifier for each customer      |
| Name                   | Customer full name                       |
| Gender                 | Gender of the customer                  |
| Age                    | Age of the customer                     |
| City                   | City of residence                       |
| Signup_Date            | Customer signup date                   |
| Last_Purchase_Date     | Most recent purchase date               |
| Purchase_Amount        | Transaction amount                     |
| Feedback_Score         | Customer feedback rating (1–10)         |
| Contact_Information    | Email and phone number                  |
| Country                | Country of residence                   |


Initial dataset size: 10,200 rows × 12 columns 

---
## 🧰 Tools & Libraries Used

**Python**

**Pandas** – data manipulation

**NumPy** – numerical operations

**Matplotlib & Seaborn** – data visualization

**SciPy (stats)** – outlier detection

**Regex (re)** – text extraction

**Jupyter Notebook**

---
## 📋 Step-by-Step Data Cleaning Process

### 1. Data Inspection & Understanding

Loaded the dataset using pd.read_csv()

Checked:

Shape of data

Column data types

Summary statistics

Missing value distribution

Identified:

Inconsistent text values

Incorrect data types

Negative and unrealistic values

### 2. **Handling Missing Values**

Applied column-specific strategies:

Dropped rows with missing Customer_ID (primary identifier)

Filled:

Age → median value

Purchase_Amount → median

Feedback_Score → mode

Gender, City, Country → most frequent value

Forward-filled Last_Purchase_Date where required

### 3. **Cleaning Age Column (Text + Numeric Issues)**

Age values contained:

Strings like "51.0 years"

Invalid values like "nan years", "250", "-10"

Used Regular Expressions to extract numeric values

Converted Age to integer

Replaced invalid and missing values using median age (43)

### 4. **Fixing Inconsistent Categorical Data**

Standardized text formatting:

Converted values to lowercase

Removed leading/trailing spaces

Unified categories such as:

Gender: m, M, MALE → male

City: KOLKATA, kolkata → kolkata

Country: ind, InDia → india

### 5. **Handling Duplicate Records**

Identified duplicate rows using df.duplicated()

Removed exact duplicates

Removed duplicate Customer_IDs, keeping the first occurrence

Reduced dataset to 9,000 clean unique customer records

### 6. **Correcting Data Types**

Converted columns to appropriate data types:

Age → Integer

Signup_Date → DateTime

Last_Purchase_Date → DateTime

Ensured numerical columns were correctly typed

### 7. **Outlier Detection & Treatment**

Visualized outliers using boxplots

Used Z-score method to identify extreme outliers

Removed rows where Z-score > 3

Revalidated distributions after cleaning

---
## Final Cleaned Dataset

✅ No missing values

✅ Standardized categorical data

✅ Correct data types

✅ Duplicate-free customer records

✅ Outliers handled

Final dataset ready for analysis, visualization, and modeling

---
📊 **Key Learnings from This Project**

- Importance of data inspection before analysis
- Handling missing data using business-relevant logic
- Using Regex for cleaning mixed text-numeric fields
- Standardizing categorical variables for consistency
- Identifying and handling duplicate records correctly
- Applying statistical methods (Z-score) for outlier removal
- Converting raw data into analysis-ready datasets
