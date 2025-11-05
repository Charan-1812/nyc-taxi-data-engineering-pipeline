# 🚖 NYC Taxi Data Engineering Project

## 👤 Author
**Sai Charan Sheru**

---

## 📘 Project Overview
This project demonstrates a **complete Data Engineering pipeline** using **Azure Databricks**, implementing the **medallion architecture** — Bronze (ingest) → Silver (transform) → Gold (aggregate).  
The dataset used is the **NYC Taxi Trips sample**, which is ingested from **Azure Data Lake Storage Gen2 (ADLS)** and visualized in **Power BI** for business analytics.

---

## 🧱 Architecture Diagram
```
Azure Data Lake Gen2 (Raw Data)
           │
           ▼
   Databricks Bronze Layer
       (Data Ingestion)
           │
           ▼
   Databricks Silver Layer
    (Data Cleaning & Transform)
           │
           ▼
   Databricks Gold Layer
     (Aggregation & Business Data)
           │
           ▼
        Power BI
   (Dashboard Visualization)
```

---

## ⚙️ Tools & Technologies Used
| Category | Tool / Service |
|-----------|----------------|
| Cloud | Microsoft Azure |
| Compute | Azure Databricks (Spark Cluster) |
| Storage | Azure Data Lake Storage Gen2 (ADLS) |
| Language | PySpark / Python |
| Data Format | Delta Lake Tables |
| Orchestration | Databricks Jobs & Workflows |
| Visualization | Power BI Desktop / Service |

---

## 🧩 Step-by-Step Process

### Step 1 – Raw Data Ingestion (Bronze Layer)
- Created a Databricks Notebook named `nyc_taxi_bronze_ingest`.
- Connected to Azure Data Lake Storage Gen2 using the abfss:// path.
- Read the CSV file `nyc_taxi_sample.csv` into a Spark DataFrame.
- Saved the raw data as a Delta table in the Bronze layer.

### Step 2 – Data Transformation (Silver Layer)
- Created `nyc_taxi_silver_transform` notebook.
- Read the Bronze data and performed data cleaning and type correction.
- Removed nulls, duplicate rows, and converted timestamps.
- Saved the cleaned data as Silver Delta table.

### Step 3 – Aggregation (Gold Layer)
- Created `nyc_taxi_gold_aggregate` notebook.
- Aggregated data by trip_date using Spark functions.
- Computed: Total Trips, Total Passengers, Average Trip Distance.
- Saved the aggregated results as Gold table and registered it to Hive Metastore.

### Step 4 – Job Orchestration
- Created Databricks Jobs for each notebook (Bronze, Silver, Gold).
- Configured job dependencies (Bronze → Silver → Gold).
- Scheduled pipeline for automated execution.

### Step 5 – Power BI Integration
- Created a Databricks SQL Warehouse connection.
- Used Power BI → Get Data → Azure Databricks.
- Connected with Server Hostname and HTTP Path.
- Imported `nyc_taxi_gold` table for visualization.

---

## 📊 Power BI Dashboard
**Dashboard Title:** NYC Taxi Analytics Dashboard  

### Visuals
- 🚕 Total Trips  
- 👥 Total Passengers  
- 📏 Average Trip Distance  
- 📈 Total Trips by Date (Bar Chart)  
- 📉 Average Trip Distance by Date (Line Chart)  
- 📅 Slicer for Date Filter  

---

## ✅ Project Outcome
- Implemented the Medallion Architecture (Bronze–Silver–Gold).
- Automated data processing pipeline in Azure Databricks.
- Built live Power BI dashboard from Databricks SQL Warehouse.

---

## 🧾 Repository Structure
```
📂 nyc-taxi-data-engineering/
│
├── notebooks/
│   ├── nyc_taxi_bronze_ingest.py
│   ├── nyc_taxi_silver_transform.py
│   ├── nyc_taxi_gold_aggregate.py
│
├── README.md
├── LICENSE
└── PowerBI_Dashboard/
    └── NYC_Taxi_Analytics.pbix
```

---

## 🧠 Key Learnings
- Practical implementation of Medallion Architecture.
- Managing Delta Lake Tables in Databricks.
- Creating end-to-end ETL with Spark & Delta.
- Integrating Databricks with Power BI.

---

## 🪪 License
This project is licensed under the MIT License.

---

## 🌟 Author
**Sai Charan Sheru**  
_Data Engineer | Azure & AWS | Spark | Databricks | Power BI_  
📧 saicharansheru4@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/saicharansheru)
