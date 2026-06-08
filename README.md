# SQL Data Warehouse Project

A modern Data Warehouse implementation built using **Microsoft SQL Server** following the **Medallion Architecture (Bronze, Silver, Gold)** approach. This project demonstrates how raw business data from multiple source systems can be transformed into clean, standardized, and business-ready datasets for reporting, analytics, and machine learning.

---

## 📖 Project Overview

Organizations often store data across multiple operational systems such as CRM and ERP platforms. These systems are optimized for transactions rather than analytics, making it difficult to generate reliable business insights.

This project solves that problem by building a centralized Data Warehouse that:

- Integrates data from multiple source systems
- Improves data quality through cleansing and standardization
- Applies business logic and transformations
- Delivers analytics-ready datasets
- Supports reporting, dashboards, and advanced analytics

---

## 🏗️ Architecture

### High-Level Data Flow

```text
CRM CSV Files
        │
        ▼
┌───────────────────┐
│   Bronze Layer    │
│     Raw Data      │
└───────────────────┘
        │
        ▼
┌───────────────────┐
│   Silver Layer    │
│ Cleaned & Standard│
│    ized Data      │
└───────────────────┘
        │
        ▼
┌───────────────────┐
│    Gold Layer     │
│ Business-Ready    │
│      Data         │
└───────────────────┘
        │
        ▼
 Power BI | SQL Queries | ML
```

---

## 📂 Data Sources

### CRM System
Contains customer-related information:

- Customer Details
- Customer Demographics
- Sales Information
- Customer Interactions

### ERP System
Contains operational business information:

- Products
- Orders
- Inventory
- Transactions

### Source Format

| Property | Value |
|-----------|---------|
| File Type | CSV |
| Interface | Folder-Based |
| Load Type | Batch Processing |

---

# 🥉 Bronze Layer

### Purpose

The Bronze Layer stores raw source data exactly as received.

### Characteristics

- Raw data ingestion
- No transformations
- Historical preservation
- Audit-friendly storage

### Load Strategy

- Batch Processing
- Full Load
- Truncate & Insert

### Data Model

Source structure is preserved without modification.

### Example Objects

```sql
bronze.crm_customers
bronze.crm_sales
bronze.erp_products
bronze.erp_orders
```

---

# 🥈 Silver Layer

### Purpose

The Silver Layer improves data quality and creates standardized datasets.

### Transformations

- Data Cleansing
- Data Standardization
- Data Normalization
- Derived Columns
- Data Enrichment
- Duplicate Removal
- Null Handling

### Load Strategy

- Batch Processing
- Full Load
- Truncate & Insert

### Example Objects

```sql
silver.customers
silver.products
silver.orders
silver.sales
```

---

# 🥇 Gold Layer

### Purpose

The Gold Layer provides business-ready data optimized for analytics and reporting.

### Transformations

- Data Integration
- Business Rules
- Aggregations
- KPI Calculations

### Data Models

- Star Schema
- Flat Tables
- Aggregated Tables

### Example Objects

```sql
gold.fact_sales
gold.dim_customer
gold.dim_product
gold.dim_date
```

---

## ⚙️ ETL Workflow

### Step 1: Data Ingestion

Load CRM and ERP CSV files into Bronze tables.

### Step 2: Data Transformation

Clean and standardize Bronze data into Silver tables.

### Step 3: Business Modeling

Apply business rules and create Gold-layer analytical models.

### Step 4: Data Consumption

Consume Gold-layer datasets using:

- Power BI
- SQL Queries
- Machine Learning Models

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|----------|
| SQL Server | Data Warehouse |
| T-SQL | Data Transformation |
| Stored Procedures | ETL Processing |
| CSV Files | Source Data |
| Power BI | Reporting & Visualization |
| GitHub | Version Control |

---

## 📁 Project Structure

```text
sql-data-warehouse/
│
├── datasets/
│   ├── crm/
│   └── erp/
│
├── scripts/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── docs/
│   └── architecture.png
│
├── stored_procedures/
│
├── README.md
│
└── LICENSE
```

---

## 📊 Business Use Cases

- Customer Analytics
- Sales Performance Analysis
- Product Performance Tracking
- Revenue Reporting
- Executive Dashboards
- Data-Driven Decision Making

---

## 🎯 Key Learning Outcomes

Through this project I gained hands-on experience in:

- Data Warehousing
- Medallion Architecture
- SQL Server Development
- ETL Pipeline Design
- Data Modeling
- Data Transformation
- Business Intelligence Concepts
- Power BI Integration

---

## 🚀 Future Enhancements

- Incremental Loading
- Change Data Capture (CDC)
- SQL Server Agent Scheduling
- Data Quality Monitoring
- Azure Data Factory Integration
- Cloud-Based Data Warehouse Deployment

---

## 👨‍💻 Author

**Bhaddirraju Manideep**

- eJPT Certified
- ISC2 Certified in Cybersecurity (CC)
- Microsoft Azure Fundamentals (AZ-900)
- Exploring Data Engineering, Data Analytics, and Cybersecurity

---

## ⭐ If you found this project useful, consider giving it a star.


