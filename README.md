# nyc-taxi-lakehouse-databricks

# NYC Taxi Lakehouse Analytics Pipeline

## Overview

This project implements an end-to-end Lakehouse architecture using Databricks, PySpark, Delta Lake, and Unity Catalog. The pipeline processes NYC Yellow Taxi trip data using the Medallion Architecture (Bronze, Silver, Gold) and automates data processing through Databricks Workflows.

---

## Architecture

```text
NYC Taxi Parquet Files
            │
            ▼
      Bronze Layer
 (Raw Data Ingestion)
            │
            ▼
      Silver Layer
(Data Cleaning & Transformation)
            │
            ▼
       Gold Layer
 (Business Aggregations)
            │
            ▼
    Analytics & Reporting
```

---

## Tech Stack

- Databricks
- PySpark
- Delta Lake
- Unity Catalog
- Databricks Workflows
- SQL
- AWS S3
- GitHub

---

## Dataset

NYC Yellow Taxi Trip Records Dataset

Files Processed:

- yellow_tripdata_2026-01.parquet
- yellow_tripdata_2026-02.parquet
- yellow_tripdata_2026-03.parquet
- yellow_tripdata_2026-04.parquet

---

## Bronze Layer

### Objectives

- Ingest raw parquet files from Unity Catalog Volume
- Add metadata columns
- Generate unique trip identifiers
- Support incremental processing

### Transformations

- Added source_file column
- Added ingestion_timestamp column
- Generated trip_id using SHA-256 hash
- Stored data in Delta format

---

## Silver Layer

### Objectives

- Clean and transform Bronze data
- Create analytical columns
- Improve data quality

### Transformations

- Trip Duration Calculation
- Pickup Year, Month, Day Extraction
- Pickup Hour Analysis
- Day of Week Analysis
- Fare Per Mile Calculation
- Data Quality Filtering
- Duplicate Removal

Derived Columns:

- trip_duration_minutes
- pickup_year
- pickup_month
- pickup_day
- pickup_hour
- pickup_day_of_week
- fare_per_mile

---

## Gold Layer

Business-focused aggregate tables:

### Daily Revenue Analysis

- Total Revenue
- Total Trips
- Average Fare

### Peak Hour Analysis

- Trips by Hour
- Peak Demand Hours

### Payment Type Analysis

- Payment Distribution
- Revenue by Payment Type

### Top Pickup Locations

- Most Popular Pickup Zones
- Trip Volume Analysis

---

## Workflow Automation

Databricks Workflows orchestrate:

```text
Bronze Ingestion
        ↓
Silver Transformation
        ↓
Gold Aggregation
```

Features:

- Automated execution
- Dependency management
- End-to-end orchestration

---

## Project Highlights

- Implemented Medallion Architecture (Bronze, Silver, Gold)
- Built scalable data processing pipeline using PySpark
- Developed Delta Lake tables for optimized analytics
- Automated pipeline execution using Databricks Workflows
- Implemented incremental data processing
- Created business-ready Gold layer aggregations

---

## Repository Structure

```text
nyc-taxi-lakehouse-databricks/
│
├── notebooks/
│   ├── bronze_ingestion.py
│   ├── silver_transformation.py
│   └── gold_aggregations.py
│
├── architecture/
│   └── architecture.png
│
├── screenshots/
│   ├── workflow.png
│   ├── bronze_table.png
│   ├── silver_table.png
│   └── gold_table.png
│
└── README.md
```

---

## Future Enhancements

- Real-time streaming ingestion
- Data quality monitoring
- Dashboard integration
- CI/CD deployment pipeline
- Data observability framework

---

## Author

Salvi Tyagi



