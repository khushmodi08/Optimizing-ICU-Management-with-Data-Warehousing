# Optimizing ICU Management with Data Warehousing

🏥 **ICU Data Warehouse – Optimizing Critical Care with MIMIC-III**

This project delivers a fully functional healthcare data warehouse leveraging the MIMIC-III Clinical Database to enhance ICU resource management, mortality prediction, and medication tracking. Built using Snowflake, SQL, and Power BI, the solution adopts an ELT architecture with structured modeling layers and automated BI insights.

---

## Project Objectives

- Improve ICU resource allocation through centralized data warehousing.
- Analyze patient outcomes (mortality, Length of Stay) and medication administration trends.
- Support hospital planning with data-driven insights on ICU transfers and occupancy.

---

## Architecture Overview

**Platform:** Snowflake

**Data Layers:**

- **RAW** – Direct CSV ingestion  
- **STAGE** – Cleansing, type casting, and enrichment  
- **MODELED** – Star schema with fact and dimension tables  

---

## Data Sources (MIMIC-III CSVs)

- `ADMISSIONS.csv` – Admission, discharge, diagnosis, and mortality  
- `ICUSTAYS.csv` – ICU stay timing and units  
- `PATIENTS.csv` – Demographics and expiration  
- `PRESCRIPTIONS.csv` – Drug records and routes  
- `TRANSFERS.csv` – Patient movement across care units  
- `D_ICD_PROCEDURES.csv` – Procedure metadata  

---

## ETL Process

**Tools Used:** Snowflake SQL, COPY INTO, Views

**Steps:**

- **Extract:** Upload CSVs to Snowflake stages.  
- **Load:** Populate raw tables using COPY INTO.  
- **Transform:**  
  - Clean missing values and nulls (e.g., set default dates)  
  - Derive key attributes (e.g., age, ICU readmission flag)  
  - Build star schema using views and tables  

---

## Star Schema Design

### Fact Tables

- `fact_icu_stay` – Length of Stay, admission type, mortality  
- `fact_medication_admin` – Drug usage and readmissions  
- `fact_transfer` – Unit movement durations  

### Dimension Tables

- `dim_patient` – Gender, DOB, status  
- `dim_admission` – Admission details  
- `dim_procedure` – ICD-9 metadata  
- `dim_service` – Service transitions  
- `dim_caregiver` – Care provider roles  

---

## BI Dashboards (Power BI)

- ICU Mortality & Length of Stay  
  Analyze mortality by age group, unit type, admission type  
  Identify patterns in prolonged ICU stays  

---

*Built with :snowflake: Snowflake, :snake: SQL, and :bar_chart: Power BI*  
