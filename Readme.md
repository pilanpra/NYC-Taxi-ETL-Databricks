# 🚕 NYC Taxi Trip Analysis with Databricks

This project uses the NYC Yellow Taxi dataset to build an end-to-end data engineering and analytics pipeline on **Databricks**, demonstrating key skills in data ingestion, Delta Lake management, SQL analysis, and basic predictive modeling using PySpark and MLflow.

---

## 🔍 Project Overview

The goal is to derive insights and build a scalable analytical pipeline using **Apache Spark on Databricks**, working with real-world trip records from NYC taxis. We simulate real-time data workflows and performance optimization using Delta Lake and notebook jobs.

---

## 🧱 Tech Stack

- **Databricks (Community Edition or Enterprise)**
- **Apache Spark (PySpark APIs)**
- **Delta Lake**
- **Databricks SQL**
- **MLflow (optional)**
- **Databricks Notebooks**

---

## 📂 Project Structure

nyc-taxi-databricks/ ├── notebooks/ │ ├── 01_ingest_clean.ipynb # Load raw CSV into Databricks, clean and convert to Delta table │ ├── 02_feature_engineering.ipynb # Engineer features like trip duration and pickup hour │ ├── 03_eda.ipynb # Analyze peak hours, zones, and earnings │ ├── 04_modeling.ipynb # Predict fare amount using regression (optional) │ └── 05_scheduler_jobs.ipynb # Setup and simulate job scheduling logic │ ├── dashboards/ │ └── taxi-insights-dashboard.png # Screenshot of Databricks SQL dashboard │ ├── resources/ │ └── sample-data.csv # 1-month slice of yellow_tripdata │ └── README.md # This file

---

## 📌 Phases & Highlights

### 📥 Phase 1: Ingest & Clean

- Upload CSV to DBFS and read with `spark.read.csv()`
- Parse timestamps, filter invalid records, and write as Delta Table

### 🧠 Phase 2: Feature Engineering

- Create:
  - `trip_duration` (dropoff - pickup)
  - `hour_of_day`, `day_of_week`, `is_weekend`
- Partition Delta table by pickup date

### 📊 Phase 3: EDA

- Answer business questions like:
  - What are the peak taxi hours in NYC?
  - What zones generate the most revenue?
- Visualized using **Databricks SQL dashboards**

### 🤖 Phase 4: (Optional) Fare Prediction Model

- Train a linear regression model using:
  - Distance, duration, passenger count
- Use **MLflow** to track model versioning and metrics

### 🛠️ Phase 5: Optimization & Scheduling

- Apply **caching**, **Z-Ordering**, and **job scheduling** for performance
- Set up notebook tasks for daily insights generation

---

## 📈 Sample Questions Answered

- 🔸 What are the busiest pickup hours in Manhattan?
- 🔸 Which zones yield highest average fares per mile?
- 🔸 How does trip distance affect fare amount?

---

## 📎 Dataset Reference

[NYC Yellow Taxi Trip Records](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)  
Format: CSV | Size: Varies by month (100K–5M rows)

---

## ✅ Skills Demonstrated

| Category            | Tools/Techniques Used                    |
| ------------------- | ---------------------------------------- |
| Data Engineering    | PySpark, Delta Lake, DBFS                |
| Analytics           | SQL, Databricks Dashboards, Aggregations |
| Data Science (opt.) | Regression, Feature Engineering, MLflow  |
| Optimization        | Z-ordering, Partitioning, Caching        |
| Scheduling          | Notebook Jobs in Databricks              |

---

## 📸 Preview

![dashboard](dashboards/taxi-insights-dashboard.png)

---

## 🚀 How to Reproduce

1. Upload raw taxi CSV to Databricks FileStore
2. Open and run notebooks in order (`01_ingest_clean.ipynb` → `05_scheduler_jobs.ipynb`)
3. Attach cluster to each notebook before execution
4. Explore results using Databricks SQL interface

---

## 🤝 Credits

Project by [Your Name]  
Built to showcase Databricks proficiency for data engineering & analytics roles.
