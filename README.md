# Wildlife Conservation Analytics — AWS Data Engineering

## 📌 Project Overview

An end-to-end AWS data engineering project that builds a serverless data lake and analytics pipeline for wildlife conservation data.

The project demonstrates data ingestion, schema discovery, ETL processing, data quality validation, data cataloging, and SQL-based analytics using AWS services.

## 🏗️ Architecture

```text
animal_dataset.csv
        │
        ▼
   Amazon S3
        │
        ▼
 AWS Glue Crawler
        │
        ▼
 Glue Data Catalog
        │
        ▼
 AWS Glue ETL
        │
        ▼
 Processed / Curated CSV
        │
        ▼
 Amazon Athena
        │
        ▼
    SQL Analytics
```

## ☁️ AWS Services Used

* Amazon S3
* AWS Glue
* AWS Glue Data Catalog
* Amazon Athena

## 🛠️ Technologies

* Python
* PySpark
* SQL
* CSV
* AWS Data Lake
* ETL
* Data Quality

## 📂 Data Pipeline

### 1. Data Ingestion

Uploaded the wildlife CSV dataset to Amazon S3 under the raw data layer.

```text
S3
└── raw/
    └── animal_dataset.csv
```

### 2. Schema Discovery

Configured an AWS Glue Crawler to scan the S3 raw data and automatically create metadata in the Glue Data Catalog.

### 3. Data Transformation

Developed an AWS Glue ETL process using Python/PySpark to:

* Clean the dataset
* Standardize column names
* Handle missing values
* Validate data types
* Remove duplicate records
* Validate endangered-level values
* Generate processed datasets

### 4. Curated Data

Created processed and analytical CSV datasets for downstream querying.

```text
processed/
curated/
```

### 5. SQL Analytics

Used Amazon Athena to analyze:

* Species distribution
* Conservation status
* Habitat distribution
* Geographic regions
* Endangered levels
* Average lifespan
* Average weight
* Average speed
* Nocturnal distribution
* Data quality

## 🔎 Example Athena Query

```sql
SELECT
    Species,
    COUNT(*) AS animal_count
FROM raw
GROUP BY Species
ORDER BY animal_count DESC;
```

## 📊 Data Quality

Implemented checks for:

* Missing values
* Duplicate Animal IDs
* Invalid endangered-level values
* Invalid or inconsistent records
* Schema consistency

## 📁 Repository Structure

```text
wildlife-conservation-aws-data-engineering/
│
├── README.md
├── data/
│   └── README.md
├── glue/
│   └── animal_etl.py
├── sql/
│   ├── species_analysis.sql
│   ├── conservation_analysis.sql
│   ├── habitat_analysis.sql
│   ├── region_analysis.sql
│   └── data_quality.sql
├── docs/
│   ├── architecture.png
│   └── screenshots/
└── .gitignore
```

## 🎯 Key Outcomes

* Built a serverless AWS data lake architecture.
* Automated schema discovery using AWS Glue.
* Developed ETL transformations using Python/PySpark.
* Created a centralized metadata layer using Glue Data Catalog.
* Performed serverless SQL analytics using Amazon Athena.
* Implemented data-quality validation for analytical datasets.

## 🚀 Future Enhancements

Potential future improvements include:

* Converting CSV data to Parquet
* Adding Amazon Redshift
* Implementing AWS Lake Formation
* Adding Step Functions orchestration
* Adding CloudWatch monitoring
* Building a QuickSight dashboard

## 👨‍💻 Author

**Ayush Sharma**

**AWS Cloud | DevOps | Data Engineer**
