# ☁️ Azure Data Factory ETL & Data Lake Integration Project

<p align="center">
  <img src="https://img.shields.io/badge/Microsoft%20Azure-Data%20Factory-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
  <img src="https://img.shields.io/badge/Azure-Data%20Lake%20Storage-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
  <img src="https://img.shields.io/badge/Azure%20SQL%20Database-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white">
  <img src="https://img.shields.io/badge/Apache%20Parquet-50ABF1?style=for-the-badge&logo=apache&logoColor=white">
  <img src="https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white">
  <img src="https://img.shields.io/badge/GitHub-Version%20Control-181717?style=for-the-badge&logo=github&logoColor=white">
</p>

<p align="center">
  <b>Cloud-based ETL pipeline for integrating SQL and JSON data into Azure Data Lake Storage using Azure Data Factory.</b>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-etl-workflow">ETL Workflow</a> •
  <a href="#-project-structure">Structure</a> •
  <a href="#-installation--setup">Setup</a> •
  <a href="#-future-enhancements">Future</a>
</p>

---

# 📌 Table of Contents

- [Overview](#-overview)
- [Project Objectives](#-project-objectives)
- [Problem Statement](#-problem-statement)
- [Solution](#-solution)
- [Architecture](#-architecture)
- [Architecture Components](#-architecture-components)
- [ETL Workflow](#-etl-workflow)
- [Data Sources](#-data-sources)
- [Data Destinations](#-data-destinations)
- [Azure Data Factory Components](#-azure-data-factory-components)
- [Pipeline Overview](#-pipeline-overview)
- [Dataset Configuration](#-dataset-configuration)
- [Linked Services](#-linked-services)
- [Data Transformation](#-data-transformation)
- [Data Flow Examples](#-data-flow-examples)
- [Project Structure](#-project-structure)
- [Technologies Used](#-technologies-used)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#-installation--setup)
- [Configuration](#-configuration)
- [Running the Pipeline](#-running-the-pipeline)
- [Monitoring](#-monitoring)
- [Expected Output](#-expected-output)
- [Data Engineering Concepts Demonstrated](#-data-engineering-concepts-demonstrated)
- [Key Learnings](#-key-learnings)
- [Challenges](#-challenges)
- [Security Considerations](#-security-considerations)
- [Best Practices](#-best-practices)
- [Future Enhancements](#-future-enhancements)
- [Possible Production Architecture](#-possible-production-architecture)
- [Use Cases](#-use-cases)
- [Project Outcomes](#-project-outcomes)
- [Interview Explanation](#-interview-explanation)
- [Conclusion](#-conclusion)
- [Author](#-author)
- [License](#-license)

---

# 📖 Overview

This project demonstrates the development of a **cloud-based ETL and data integration solution using Microsoft Azure Data Factory (ADF)**.

The objective is to build a centralized data ingestion workflow capable of extracting data from different sources, processing and transferring the data through Azure Data Factory pipelines, and storing the resulting data in **Azure Data Lake Storage** in an analytical-friendly format.

The project works with multiple data entities such as:

- Customers
- Products
- Orders
- JSON-based data

The repository contains the exported Azure Data Factory configuration required to reproduce the data integration environment, including:

- Pipelines
- Datasets
- Linked Services
- Factory configuration
- Source definitions
- Destination definitions
- JSON configuration files

The project demonstrates the practical implementation of a modern cloud data engineering workflow.

---

# 🎯 Project Objectives

The major objectives of this project are:

### 1. Learn Azure Data Factory

Understand how Azure Data Factory can be used to design, execute, and monitor data integration pipelines.

### 2. Build ETL Pipelines

Create pipelines capable of extracting data from different sources and loading it into cloud storage.

### 3. Integrate Multiple Data Sources

Connect Azure Data Factory with SQL and JSON-based sources.

### 4. Implement Data Lake Storage

Use Azure Data Lake Storage as a centralized destination for processed data.

### 5. Work With Parquet

Store structured data in Parquet format for efficient analytical processing.

### 6. Understand ADF Components

Gain practical knowledge of:

- Pipelines
- Datasets
- Linked Services
- Copy Data Activities
- Source and Sink configurations
- Activity dependencies

### 7. Practice Cloud Data Engineering

Understand how traditional database data can be moved into a cloud-based data lake architecture.

---

# ❗ Problem Statement

Organizations often have data distributed across multiple systems.

For example:

```text
Customer Data       → SQL Database
Product Data        → SQL Database
Order Data          → SQL Database
External Data       → JSON / HTTP
