# Data Cleaning and modeling

# Project Overview

This project analyzes internal employee training attendance data using Power BI and Power Query. The goal is to improve the reliability of training records, standardize inconsistent session names, identify invalid employee IDs and duplicate attendance entries, and provide visibility into data quality.

The project demonstrates an end-to-end analytics workflow, from raw data ingestion and transformation to data quality reporting and interactive dashboard development.

# Business Problem

Inconsistent session names, invalid employee identifiers, missing values, and duplicate attendance records can reduce the reliability of training reports. These issues make it difficult for HR and training teams to accurately monitor participation and maintain trustworthy records.

This project addresses these challenges by cleaning and validating attendance data and presenting data quality indicators in Power BI.


## 🔹 Steps Followed

### 1. Data Import
- Imported raw dataset (`messy_training_attendance.xlsx`) into Power BI.
- Reviewed columns: Employee_ID, Name, Session, Date, Feedback.

### 2. Data Cleaning (Power Query)
- **Trimming & Standardization**
  - Applied `Text.Trim` to remove leading/trailing spaces.
  - Converted text to lowercase for consistency.

- **Session Normalization**
  - Created a **Mapping Table** with RawValue → CleanValue.
  - Replaced inconsistent entries (e.g., *powerbi, power-bi → Power BI*).
  - Ensured final column had standardized session names.

- **Employee_ID Validation**
  - Extracted numeric part from IDs using `Text.Select`.
  - Converted valid IDs into numbers with `try … otherwise null`.
  - Created a **Flag column** (`Valid` / `Invalid`) for data quality checks.

- **Duplicate Handling**
  - Checked duplicates across Employee_ID + Session + Date.
  - Marked records with duplicate counts for review.

- **Null Handling**
  - Identified missing values in critical fields (Employee_ID, Session, Date).
  - Replaced or removed based on context.

-**Refer to below images:**
<p float="left">
  <img src="screenshots/messy_data.png" width="400"/>
  <img src="screenshots/clean_data.png" width="400"/>
</p>


### 3. Data Quality Reporting
- Added summary metrics:
  - % Valid Employee_IDs
  - % Invalid Employee_IDs
  - % Duplicate Records
  - % Unmapped Session Names



## 📁 Project Structure

```text
Internal_Team_Training_Analytics/
├── data/
│   ├── messy_training_attendance.xlsx
│   └── cleaned_training_attendance.csv
├── screenshots/
│   ├── messy_data.png
│   ├── clean_data.png
│   └── data_cleaning_steps.png
└── README.md
```
## 🔹 Tech Stack
- **Power BI**: Power Query (M language), DAX, Data Modeling
- **Excel**: Raw data input
- **SQL**: Basic validation queries

---

## 🔹 Key Learnings
- Handling messy real-world data with Power Query
- Using mapping tables for scalable text cleaning
- Validating and flagging IDs for data quality

---

