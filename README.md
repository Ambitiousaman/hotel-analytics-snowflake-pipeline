# 🏨 Hotel Booking Analytics Platform  
### End-to-End Data Engineering Project | Snowflake | Medallion Architecture

---

## 🚀 Project Overview

This project showcases a production-style **end-to-end Data Engineering pipeline** built on Snowflake.

The objective was to design and implement a scalable data warehouse that transforms raw hotel booking data into clean, validated, and business-ready datasets using the **Medallion Architecture (Bronze → Silver → Gold)**.

The final output is an interactive analytics dashboard delivering actionable insights for revenue monitoring, booking trends, and city-level performance analysis.

---

## 🏗 Architecture Diagram

```text
                ┌──────────────────┐
                │   Raw CSV Files   │
                └─────────┬────────┘
                          │
                          ▼
                ┌──────────────────┐
                │  External Stage   │
                │ (Snowflake Stage) │
                └─────────┬────────┘
                          │
                          ▼
                ┌──────────────────┐
                │   BRONZE Layer    │
                │ Raw Ingestion     │
                │ (No Transform)    │
                └─────────┬────────┘
                          │
                          ▼
                ┌──────────────────┐
                │   SILVER Layer    │
                │ Data Cleaning &   │
                │ Standardization   │
                └─────────┬────────┘
                          │
                          ▼
                ┌──────────────────┐
                │    GOLD Layer     │
                │ Aggregated Tables │
                │ Business Metrics  │
                └─────────┬────────┘
                          │
                          ▼
                ┌──────────────────┐
                │  Analytics        │
                │  Dashboard        │
                │  (Snowsight)      │
                └──────────────────┘
```

---

## 🧱 Data Architecture (Medallion Pattern)

### 🥉 Bronze Layer – Raw Data Ingestion
- Loaded CSV data using Snowflake Stage
- Used `COPY INTO` with error handling (`ON_ERROR = CONTINUE`)
- Stored raw, unmodified data for traceability

### 🥈 Silver Layer – Data Cleaning & Validation
Applied production-grade data quality checks:

- Email validation
- Invalid date filtering
- Negative revenue correction using `ABS()`
- Safe type casting with `TRY_TO_DATE()` and `TRY_TO_NUMBER()`
- Booking status normalization
- Null handling & standardization

Only validated records are promoted to Silver.

### 🥇 Gold Layer – Business Aggregations
Created optimized analytics tables:
- Daily booking & revenue trends
- Revenue by city
- Cleaned booking master table

Designed for dashboard consumption.

---

## 📊 Dashboard KPIs

The Snowflake dashboard provides:

- 💰 Total Revenue
- 📊 Total Bookings
- 📈 Average Booking Value
- 📅 Monthly Revenue Trend
- 🏙 Top Revenue-Generating Cities
- 📦 Booking Status Distribution
- 🛏 Booking Type Analysis

---

## 🛠 Tech Stack

- ❄ Snowflake (Cloud Data Warehouse)
- 🧠 SQL (Advanced Transformations & Aggregations)
- 📂 CSV File Ingestion
- 🏗 Medallion Architecture
- 📊 Snowsight Dashboard

---

## 🔍 Key Engineering Highlights

✔ Implemented layered data architecture  
✔ Applied data validation using TRY functions  
✔ Designed clean ELT workflow  
✔ Built aggregation tables optimized for analytics  
✔ Ensured data quality before dashboard exposure  
✔ Applied business-driven transformation logic  

---

## 📈 Business Impact

This pipeline enables:

- Reliable monthly revenue tracking  
- Accurate KPI monitoring  
- City-level revenue insights  
- Clean and trusted reporting layer  

---

## 🎯 Why This Project Stands Out

Unlike basic SQL projects, this implementation demonstrates:

- Real-world data engineering workflow
- Data quality enforcement before analytics
- Scalable warehouse design
- Separation of ingestion, transformation, and analytics layers
- Dashboard-ready modeling

---



---
