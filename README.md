# ☁️ Azure Data Factory ETL Pipeline

<p align="center">
  <img src="https://img.shields.io/badge/Microsoft%20Azure-Data%20Factory-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
  <img src="https://img.shields.io/badge/Azure-Data%20Lake%20Storage-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
  <img src="https://img.shields.io/badge/Azure%20SQL%20Database-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white">
  <img src="https://img.shields.io/badge/Format-Parquet-4B8BBE?style=for-the-badge">
</p>

<p align="center">
  <b>A cloud-based ETL and data integration project built using Azure Data Factory.</b>
</p>

---

## 📌 Overview

This project demonstrates the implementation of an **ETL and data integration workflow using Microsoft Azure Data Factory**.

The project is designed to extract data from different sources, move and transform it through Azure Data Factory pipelines, and store the processed data in **Parquet format in Azure Data Lake Storage**.

The project includes data integration workflows for:

- 👥 Customer data
- 📦 Product data
- 🛒 Order data
- 📄 JSON data
- 🗄️ Azure SQL Database sources
- ☁️ Azure Data Lake Storage destinations
- 🔗 Multiple Azure Data Factory linked services
- ⚙️ Reusable datasets and pipelines

The complete Azure Data Factory configuration is maintained in this repository as JSON files.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Understand Azure Data Factory architecture.
- Build cloud-based ETL pipelines.
- Connect Azure Data Factory with different data sources.
- Extract data from Azure SQL Database.
- Process JSON-based data sources.
- Load data into Azure Data Lake Storage.
- Store analytical data in Parquet format.
- Understand datasets, linked services, and pipelines.
- Implement dependencies between pipeline activities.
- Maintain Azure Data Factory resources using JSON definitions.

---

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │     Data Sources     │
                    └──────────┬───────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
                 ▼                           ▼
        ┌─────────────────┐         ┌─────────────────┐
        │  Azure SQL DB   │         │   JSON Source   │
        │                 │         │   / GitHub      │
        │ Customers       │         └────────┬────────┘
        │ Products        │                  │
        │ Orders          │                  │
        └────────┬────────┘                  │
                 │                           │
                 └─────────────┬─────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │    Azure Data Factory    │
                 │                          │
                 │  Linked Services         │
                 │          ↓               │
                 │  Datasets                │
                 │          ↓               │
                 │  Copy Data Activities    │
                 │          ↓               │
                 │  Pipeline Orchestration  │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │ Azure Data Lake Storage  │
                 │          Gen2            │
                 │                          │
                 │     Parquet Files        │
                 └──────────────────────────┘
