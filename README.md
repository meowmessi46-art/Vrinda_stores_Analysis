# 🚀 Modern SQL Data Warehouse Project (SQL Server)  
### Medallion Architecture | ETL Pipelines | Star Schema Modeling | Data Quality Checks

## 📌 Objective
The objective of this project is to design and implement a **modern SQL Server-based Data Warehouse** using a **layered Medallion Architecture (Bronze, Silver, Gold)** to transform raw operational data into **clean, integrated, and analytics-ready datasets** for reporting and business intelligence.

This project demonstrates real-world **Data Engineering + BI Modeling practices**, including ETL pipeline development, data cleansing, integration of multiple sources, dimensional modeling, and documentation.

---

## 🧩 Problem Statement
Organizations often struggle with:
- Multiple source systems (CRM, ERP) containing inconsistent data formats
- Manual reporting processes that are slow, error-prone, and unscalable
- Poor data quality (duplicates, null values, inconsistent naming conventions)
- Lack of a centralized and trusted dataset for analytics teams

The challenge is to build a scalable data warehouse solution that:
- Integrates CRM and ERP datasets into a single unified model
- Cleans and standardizes raw data
- Produces business-ready dimensional models (Star Schema)
- Supports fast and reliable reporting

---
<img width="1031" height="637" alt="image" src="https://github.com/user-attachments/assets/b48db30c-fe9d-4ef3-a202-fed6cf70fc03" />


## 🏗️ Architecture Overview (Medallion Framework)

This project follows a **3-layer Medallion Architecture**:

### 🥉 Bronze Layer (Raw Data Storage)
- Stores data exactly as received from source files (CRM & ERP CSVs)
- Minimal transformation
- Used for traceability and audit purposes

### 🥈 Silver Layer (Cleaned + Standardized Data)
- Cleans, standardizes, and validates raw data
- Handles duplicates, missing values, invalid formats
- Adds metadata columns for tracking

### 🥇 Gold Layer (Business-Ready Data Model)
- Creates dimensional model using **Star Schema**
- Fact and Dimension tables are published as views
- Optimized for BI reporting and analytics consumption

📌 **Data Flow:**
`Source CSV Files → Bronze → Silver → Gold → BI/Reporting`

---

## 🛠️ Tech Stack
- **SQL Server Express**
- **SQL Server Management Studio (SSMS)**
- **T-SQL**
- **Stored Procedures**
- **Bulk Insert (CSV ingestion)**
- **Git & GitHub (Version Control + Documentation)**

---

## 📂 Data Sources
This project uses two operational source systems:

### CRM System (CSV Files)
- Customer details
- Sales transactions
- Product and customer mapping

### ERP System (CSV Files)
- Orders and fulfillment data
- Product inventory details
- Business operations records

These datasets contain real-world issues such as:
- Missing values
- Duplicate records
- Invalid formats
- Inconsistent text patterns
- Data type mismatches

---

## 🔄 ETL Workflow (Pipeline Design)

### Step 1: Extract (Bronze Load)
- Raw CSV files loaded into Bronze schema tables
- Implemented using **BULK INSERT**
- Full refresh approach (truncate + insert)

### Step 2: Transform (Silver Cleanse)
Key transformations applied:
- Removing unwanted spaces (`TRIM`, `REPLACE`)
- Standardizing text and abbreviations
- Converting invalid date formats
- Handling null values
- Removing duplicates using window functions (`ROW_NUMBER`)
- Validating business rules

### Step 3: Load (Gold Publish)
- Star schema design implemented
- Surrogate keys created for dimensions
- Fact table created with proper joins
- Business-friendly naming conventions applied

---

## 📊 Data Modeling Approach (Gold Layer)

The Gold Layer is designed using **Dimensional Modeling (Star Schema)**:

### Dimension Tables
- DimCustomer
- DimProduct
- DimDate
- DimSalesRegion *(example)*

### Fact Tables
- FactSales
- FactOrders *(example)*

Key modeling practices:
- Surrogate keys for consistent joins
- Fact table built at a defined grain level
- Referential integrity ensured through lookups

---

## 📌 Analysis
The project includes analysis at multiple stages:

### Bronze Layer Analysis
- Schema exploration
- Raw data profiling
- Identifying data quality issues

### Silver Layer Analysis
- Duplicate detection
- Null distribution checks
- Data type validation
- Standardization checks across CRM and ERP datasets

### Gold Layer Analysis
- Business object identification
- Defining fact grain and dimension relationships
- Ensuring star schema supports reporting needs

---

## 🔍 Insights
After building the warehouse, the following insights become possible:

- Unified view of customer transactions across CRM and ERP systems
- Clean and consistent reporting dataset without manual preparation
- Ability to track performance by product, region, and customer segment
- Improved data reliability through automated validation checks
- Standardized data definitions across the organization

---

## 💡 Recommendations
Based on the project outcomes, the following improvements are recommended for real-world implementation:

1. **Implement Incremental Loads**
   - Full refresh works for small datasets but incremental loads reduce compute cost.

2. **Introduce Slowly Changing Dimensions (SCD Type 2)**
   - Useful for tracking historical customer/product changes.

3. **Automate Scheduling**
   - Use tools like SQL Server Agent / Airflow for scheduled ETL execution.

4. **Data Quality Monitoring Framework**
   - Store validation results in audit tables for ongoing monitoring.

5. **Performance Optimization**
   - Add indexing strategies and partitioning for large-scale datasets.

---

## ✅ Conclusions
This project successfully demonstrates how to build a **modern SQL Server Data Warehouse** using best practices:

- Implemented Medallion Architecture (Bronze → Silver → Gold)
- Developed robust ETL pipelines with stored procedures
- Applied data cleansing and standardization techniques
- Designed an analytics-ready Star Schema model
- Delivered business-consumable datasets with proper documentation

This warehouse design enables reliable reporting, faster analytics, and improved business decision-making.

---

## 📦 Deliverables
This repository contains:

- SQL scripts for database and schema creation
- Bronze layer table scripts + bulk load procedures
- Silver layer cleansing and transformation scripts
- Gold layer dimensional model views (fact/dimension)
- Data quality validation queries
- Architecture and star schema diagrams
- Documentation explaining workflow and design decisions

---

## 🧪 Data Quality & Validation Checks
Implemented validation checks include:

- Null checks on key columns
- Duplicate record detection
- Primary key uniqueness checks
- Data type conversion validations
- Referential integrity verification between fact and dimension tables

---

## ▶️ How to Run the Project

### Step 1: Setup Database
Run scripts from:
`sql/01_database_setup/`

### Step 2: Load Bronze Layer
Run:
`sql/02_bronze_layer/`

### Step 3: Transform into Silver Layer
Run:
`sql/03_silver_layer/`

### Step 4: Publish Gold Layer (Star Schema)
Run:
`sql/04_gold_layer/`

### Step 5: Run Validation Checks
Run:
`sql/05_quality_checks/`

---

## 📌 Project Folder Structure
SQL-DataWarehouse-Project/
│
├── README.md
├── docs/
├── diagrams/
├── datasets/
├── sql/
│ ├── 01_database_setup/
│ ├── 02_bronze_layer/
│ ├── 03_silver_layer/
│ ├── 04_gold_layer/
│ ├── 05_quality_checks/
│
└── stored_procedures/

yaml
Copy code

---

## 🔮 Future Enhancements
Planned improvements for scalability:

- Incremental loading using watermark strategy
- SCD Type 2 implementation for historization
- ETL audit logging table for monitoring load runs
- Cloud deployment (Azure Synapse / Snowflake equivalent architecture)
- Power BI Dashboard integration

---

## 👨‍💻 Author
**Abdul Malik**  
Data Analyst | BI Developer | SQL | Power BI | Python  

📌 GitHub: *(Add your link here)*  
📌 LinkedIn: *https://www.linkedin.com/in/abdulmalik2001/*  

---
