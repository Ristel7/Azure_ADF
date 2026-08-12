# ☁️ Azure Data Factory ETL & Data Lake Integration Project

<p align="center">
  <img src="https://img.shields.io/badge/Azure-Data%20Factory-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure Data Factory">
  <img src="https://img.shields.io/badge/Azure-Data%20Lake-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure Data Lake">
  <img src="https://img.shields.io/badge/Azure%20SQL-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white" alt="Azure SQL">
  <img src="https://img.shields.io/badge/Parquet-50ABF1?style=for-the-badge&logo=apache&logoColor=white" alt="Parquet">
  <img src="https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white" alt="JSON">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</p>

<p align="center">
  <h3 align="center">A Cloud-Based ETL and Data Integration Pipeline using Microsoft Azure</h3>
</p>

<p align="center">
  <b>Azure Data Factory • Azure SQL Database • Azure Data Lake Storage • Parquet • JSON • ETL</b>
</p>

---

## 📌 Table of Contents

- [ About the Project](#-about-the-project)
- [ Project Objectives](#-project-objectives)
- [ Problem Statement](#-problem-statement)
- [ Proposed Solution](#-proposed-solution)
- [ System Architecture](#️-system-architecture)
- [ Complete Data Flow](#-complete-data-flow)
- [ Azure Services Used](#️-azure-services-used)
- [ Azure Data Factory Components](#-azure-data-factory-components)
- [ Linked Services](#-linked-services)
- [ Datasets](#-datasets)
- [ Pipelines](#-pipelines)
- [ Data Sources](#-data-sources)
- [ Data Destinations](#️-data-destinations)
- [ ETL Process](#-etl-process)
- [ Data Transformation](#-data-transformation)
- [ Project Structure](#-project-structure)
- [ Technologies Used](#️-technologies-used)
- [ Prerequisites](#️-prerequisites)
- [ Setup and Installation](#-setup-and-installation)
- [ Azure Configuration](#️-azure-configuration)
- [ Running the Pipeline](#️-running-the-pipeline)
- [ Pipeline Monitoring](#-pipeline-monitoring)
- [ Data Validation](#-data-validation)
- [ Expected Output](#-expected-output)
- [ Concepts Demonstrated](#-concepts-demonstrated)
- [ Learning Outcomes](#-learning-outcomes)
- [ Challenges](#️-challenges)
- [ Security](#-security)
- [ Best Practices](#-best-practices)
- [ Real-World Applications](#-real-world-applications)
- [ Analytics Possibilities](#-analytics-possibilities)
- [ Production Architecture](#-production-architecture)
- [ Medallion Architecture](#-medallion-architecture)
- [ Future Enhancements](#-future-enhancements)
- [ Project Roadmap](#-project-roadmap)
- [ Resume Description](#-resume-description)
- [ Interview Explanation](#-interview-explanation)
- [ Key Skills](#-key-skills)
- [ License](#-license)
- [ Author](#-author)
- [ Support](#-support)

---

# 📖 About the Project

The **Azure Data Factory ETL & Data Lake Integration Project** is a cloud-based data engineering project designed to demonstrate how data from multiple sources can be integrated, orchestrated, and stored using Microsoft Azure.

The project uses **Azure Data Factory (ADF)** as the central data integration and orchestration service.

Data is collected from different sources such as:

- Azure SQL Database
- SQL Server
- JSON-based sources
- External data sources

The extracted data is processed through Azure Data Factory pipelines and transferred to **Azure Data Lake Storage**.

The destination data is configured to be stored in **Parquet format**, making it suitable for downstream analytics and reporting workloads.

The project demonstrates the fundamental architecture of a modern cloud-based ETL pipeline.

---

# 🎯 Project Objectives

The primary objectives of this project are:

### 1. Cloud Data Integration

To understand how cloud services can be connected to build a centralized data integration system.

### 2. Azure Data Factory

To gain practical experience with Azure Data Factory and understand how pipelines, datasets, linked services, and activities work together.

### 3. ETL Pipeline Development

To design an ETL workflow capable of extracting data from different sources and loading it into a centralized data lake.

### 4. Multiple Data Sources

To integrate structured and semi-structured data sources.

### 5. Azure Data Lake

To understand how Azure Data Lake Storage can be used as a centralized storage layer for analytical data.

### 6. Parquet Storage

To use Parquet as a columnar storage format for analytical workloads.

### 7. Pipeline Orchestration

To understand activity dependencies and execution order inside Azure Data Factory.

### 8. Cloud Data Engineering

To develop practical knowledge of cloud-based data engineering concepts.

---

# ❗ Problem Statement

Modern applications generate data from many different sources.

For example:

```text
Customer Information
        ↓
Azure SQL Database

Product Information
        ↓
Azure SQL Database

Order Information
        ↓
SQL Database

External Information
        ↓
JSON / HTTP
```

When data is distributed across multiple systems, performing analysis becomes difficult.

Some common challenges include:

- Data existing in different systems
- Different data formats
- Different schemas
- Different storage mechanisms
- Difficulty in centralized reporting
- Manual data movement
- Lack of automated pipelines

A centralized data integration solution is therefore required.

---

# 💡 Proposed Solution

This project solves the above problem using **Azure Data Factory**.

Azure Data Factory acts as the central orchestration layer.

```text
                    DATA SOURCES
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   Azure SQL         SQL Server       JSON / HTTP
        │                │                │
        └────────────────┼────────────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │ Azure Data Factory  │
              │                     │
              │ Linked Services     │
              │ Datasets            │
              │ Pipelines           │
              │ Copy Activities     │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │ Azure Data Lake     │
              │ Storage Gen2        │
              └──────────┬──────────┘
                         │
                         ▼
                    Parquet Files
                         │
                         ▼
               Analytics / Power BI
```

This architecture provides a centralized and scalable approach to data integration.

---

# 🏗️ System Architecture

The project can be divided into four major layers.

## 1. Source Layer

Contains the original data.

```text
Azure SQL
SQL Server
JSON
External Sources
```

---

## 2. Integration Layer

Azure Data Factory handles:

```text
Connectivity
Data Extraction
Data Movement
Data Translation
Pipeline Orchestration
```

---

## 3. Storage Layer

Azure Data Lake Storage acts as the centralized storage layer.

```text
Azure Data Lake Storage Gen2
```

---

## 4. Analytics Layer

The processed data can later be consumed by:

```text
Power BI
Python
Databricks
Synapse Analytics
Machine Learning
```

---

# 🔄 Complete Data Flow

```text
┌──────────────────────┐
│    SOURCE SYSTEMS    │
└──────────┬───────────┘
           │
           │ Extract
           ▼
┌──────────────────────┐
│ Azure Data Factory   │
│                      │
│  Linked Services     │
│         ↓            │
│      Datasets        │
│         ↓            │
│  Copy Data Activity  │
│         ↓            │
│    Pipelines         │
└──────────┬───────────┘
           │
           │ Load
           ▼
┌──────────────────────┐
│ Azure Data Lake      │
│ Storage Gen2         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      Parquet         │
│       Files          │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Analytics / BI Layer │
│                      │
│ Power BI / Python    │
└──────────────────────┘
```

---

# ☁️ Azure Services Used

| Azure Service | Purpose |
|---|---|
| Azure Data Factory | ETL and pipeline orchestration |
| Azure Data Lake Storage Gen2 | Cloud data lake storage |
| Azure SQL Database | Structured source data |
| Azure Blob Storage | Cloud object storage |
| Azure Resource Group | Resource management |
| Azure Monitor / ADF Monitor | Pipeline monitoring |

---

# 🧩 Azure Data Factory Components

Azure Data Factory is built around several important components.

---

## 🔗 Linked Services

A Linked Service defines the connection information required to connect Azure Data Factory to an external service.

Examples used in this project include connections for:

- Azure SQL Database
- Azure Data Lake Storage
- Azure Blob Storage
- SQL Server
- JSON / external sources

Conceptually:

```text
Azure Data Factory
        │
        ├── Linked Service
        │       ↓
        │   Azure SQL
        │
        └── Linked Service
                ↓
            Data Lake
```

Linked Services act as the connection layer between ADF and external resources.

---

# 📁 Datasets

A dataset represents the structure and location of the data that a pipeline consumes or produces.

The project contains datasets for:

- Customers
- Products
- Orders
- JSON
- Delimited text
- Azure SQL tables
- Parquet files
- Azure Data Lake destinations

Examples include:

```text
CustomerfromSQL.json
OrdersfromSQL.json
ProductsfromSQL.json
JsonfromGIT.json
DelimitedText1.json
```

Parquet-related datasets are also included for the Data Lake destination.

---

# ⚡ Pipelines

Pipelines define the actual workflow executed by Azure Data Factory.

The project contains pipeline definitions such as:

```text
Customers Data Factory.json
Data to DataLake.json
pipeline2.json
```

The main pipeline is focused on moving data from source systems into Azure Data Lake Storage.

---

# 📊 Data Sources

The project demonstrates data ingestion from multiple source types.

## 👥 Customer Data

Customer information is extracted from a SQL-based source.

```text
SQL Database
      ↓
Customer Dataset
      ↓
ADF Copy Activity
```

---

## 📦 Product Data

Product information is extracted from a SQL-based source.

```text
SQL Database
      ↓
Product Dataset
      ↓
ADF Copy Activity
```

---

## 🛒 Order Data

Order information is extracted from SQL.

```text
SQL Database
      ↓
Orders Dataset
      ↓
ADF Copy Activity
```

---

## 📄 JSON Data

The project also includes JSON-based data ingestion.

```text
JSON Source
      ↓
JSON Dataset
      ↓
ADF Pipeline
```

This demonstrates working with semi-structured data.

---

# 🗄️ Data Destinations

The primary destination is **Azure Data Lake Storage**.

The project contains destination configurations for storing data in Parquet format.

Conceptual structure:

```text
Azure Data Lake
│
├── Customers/
│   └── Customers.parquet
│
├── Products/
│   └── Products.parquet
│
├── Orders/
│   └── Orders.parquet
│
└── JSON/
    └── Data.parquet
```

The actual file names and folder structure depend on the configured datasets and linked services.

---

# 🔁 ETL Process

The complete workflow follows the ETL pattern.

## E — Extract

Data is extracted from different sources.

```text
Azure SQL
SQL Server
JSON
```

---

## T — Transform

ADF performs the required data translation during data movement.

This may include:

- Schema mapping
- Type conversion
- Source-to-sink translation
- Data format conversion

---

## L — Load

The processed data is loaded into Azure Data Lake Storage.

```text
Source
  ↓
ADF
  ↓
Data Lake
  ↓
Parquet
```

---

# 📦 Data Transformation

The project uses source-to-sink data translation.

Conceptually:

```text
Source Schema
      │
      ▼
ADF Mapping / Translator
      │
      ▼
Data Type Conversion
      │
      ▼
Destination Schema
```

For example:

```text
SQL INT
   ↓
ADF Data Type Translation
   ↓
Parquet Integer
```

This allows data from different systems to be represented appropriately in the destination.

---

# 🔗 Linked Service Architecture

The relationship between linked services and datasets can be understood as:

```text
             Azure Data Factory
                    │
       ┌────────────┴────────────┐
       │                         │
Linked Services              Datasets
       │                         │
       ▼                         ▼
Connections                  Data Structure
       │                         │
       └────────────┬────────────┘
                    │
                    ▼
                Pipelines
```

---

# ⚡ Main Pipeline Workflow

The main objective of the project is to move multiple datasets into the Data Lake.

Conceptually:

```text
Customers ───────────────┐
                         │
Products ────────────────┤
                         │
Orders ──────────────────┤
                         ├──► Azure Data Factory
                         │
JSON ────────────────────┘
                                  │
                                  ▼
                          Azure Data Lake
                                  │
                                  ▼
                              Parquet
```

---

# 🔁 Pipeline Dependencies

ADF allows activities to depend on previous activities.

Example:

```text
START
  │
  ▼
Customers
  │
  │ Success
  ▼
Products
  │
  │ Success
  ▼
Orders
  │
  │ Success
  ▼
JSON
  │
  ▼
END
```

Possible dependency conditions include:

```text
On Success
On Failure
On Completion
On Skip
```

This allows complex workflows to be created.

---

# 📋 Project Structure

```text
Azure_ADF/
│
├── 📁 dataset/
│   │
│   ├── AzureSqlTable1.json
│   ├── CustomerfromSQL.json
│   ├── DelimitedText1.json
│   ├── JsonfromGIT.json
│   ├── OrdersfromSQL.json
│   ├── ProductsfromSQL.json
│   │
│   ├── Parquet1.json
│   ├── Parquet2.json
│   ├── Parquet3.json
│   ├── Parquet4.json
│   ├── Parquet5.json
│   ├── Parquet6.json
│   ├── Parquet7.json
│   │
│   └── ProductstoDataLake.json
│
├── 📁 factory/
│   └── Priyanshufactory.json
│
├── 📁 linkedService/
│   │
│   ├── AzureBlobStorage1.json
│   ├── AzureDataLakeStorage1.json
│   ├── AzureDataLakeStorage2.json
│   ├── AzureDataLakeStorage3.json
│   ├── AzureDataLakeStorage4.json
│   ├── AzureDataLakeStorage5.json
│   │
│   ├── AzureSqlDatabase1.json
│   ├── AzureSqlDatabase2.json
│   ├── AzureSqlDatabase3.json
│   │
│   ├── Customers.json
│   ├── CustomerstoDataLake.json
│   ├── JSONfromGITHUB.json
│   ├── JSON to DataLake.json
│   ├── OrdersfromSQL.json
│   ├── OrderstoDataLake.json
│   ├── ProductsfromSQL.json
│   ├── Products to Data Lake.json
│   ├── SqlServer1.json
│   └── priyanshuconnection.json
│
├── 📁 pipeline/
│   │
│   ├── Customers Data Factory.json
│   ├── Data to DataLake.json
│   └── pipeline2.json
│
├── 📄 Customers.json
├── 📄 index.html
├── 📄 publish_config.json
└── 📄 README.md
```

---

# 🛠️ Technologies Used

### Cloud

- Microsoft Azure
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure SQL Database
- Azure Blob Storage

### Data Engineering

- ETL
- Data Integration
- Data Pipeline
- Data Lake
- Data Movement
- Data Transformation

### Data Formats

- JSON
- Parquet
- Delimited Text
- SQL Tables

### Version Control

- Git
- GitHub

---

# ⚙️ Prerequisites

Before running this project, the following resources are recommended:

### Azure

- Active Azure subscription
- Azure Resource Group
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure SQL Database

### Software

- Git
- Web browser
- Azure Portal

### Knowledge

Basic understanding of:

- SQL
- Databases
- ETL
- Cloud Computing
- JSON
- Data Engineering

---

# 🚀 Setup and Installation

## Step 1 — Clone Repository

```bash
git clone https://github.com/Ristel7/Azure_ADF.git
```

Navigate into the repository:

```bash
cd Azure_ADF
```

---

# ☁️ Azure Configuration

## Step 2 — Create Resource Group

Create an Azure Resource Group.

Example:

```text
Resource Group
      │
      ├── Data Factory
      ├── Data Lake
      └── SQL Database
```

---

# Step 3 — Create Azure Data Factory

Create an Azure Data Factory instance.

Example:

```text
Factory Name:
PriyanshuFactory
```

The factory configuration is represented in:

```text
factory/Priyanshufactory.json
```

---

# Step 4 — Configure Azure SQL

Create the required database and tables.

Example:

```sql
CREATE DATABASE SalesDB;
```

Example customer table:

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    CustomerName VARCHAR(100),
    Email VARCHAR(150)
);
```

Example product table:

```sql
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,
    ProductName VARCHAR(100),
    Price DECIMAL(10,2)
);
```

Example orders table:

```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    ProductID INT,
    OrderDate DATE,
    Quantity INT
);
```

The schema should be adjusted according to the actual source data used by your implementation.

---

# Step 5 — Create Data Lake

Create an Azure Data Lake Storage Gen2 account.

Recommended conceptual structure:

```text
DataLake
│
├── raw/
│
├── processed/
│
└── curated/
```

The current project can be connected to the appropriate destination datasets defined in the repository.

---

# Step 6 — Configure Linked Services

Configure the linked services inside Azure Data Factory.

Examples:

```text
Azure SQL
Azure Data Lake Storage
Azure Blob Storage
SQL Server
JSON Source
```

Each Linked Service should point to the corresponding resource in your Azure environment.

---

# Step 7 — Configure Datasets

Configure the datasets contained inside:

```text
dataset/
```

Make sure the following are correct:

- Source connection
- Table name
- File path
- Container
- Folder
- File format
- Sink connection

---

# Step 8 — Configure Pipelines

Import or recreate the pipeline definitions inside:

```text
pipeline/
```

The major pipeline is:

```text
Data to DataLake
```

---

# ▶️ Running the Pipeline

After all resources have been configured:

### 1.

Open Azure Data Factory Studio.

### 2.

Open the required pipeline.

### 3.

Validate the pipeline.

### 4.

Click **Debug**.

### 5.

Check each activity.

### 6.

Verify the output in Azure Data Lake Storage.

---

# 📈 Pipeline Monitoring

Azure Data Factory provides a monitoring interface.

You can inspect:

```text
Pipeline Run
     │
     ├── Start Time
     ├── End Time
     ├── Duration
     ├── Status
     ├── Activities
     ├── Data Read
     ├── Data Written
     └── Error Details
```

A successful pipeline should show:

```text
🟢 Succeeded
```

A failed pipeline should show:

```text
🔴 Failed
```

---

# 🔍 Data Validation

Data validation is an important part of an ETL pipeline.

## Source Validation

Check the source count:

```sql
SELECT COUNT(*)
FROM Customers;
```

---

## Destination Validation

Compare:

```text
Source Record Count
        ↓
ADF Pipeline
        ↓
Destination Record Count
```

For a simple full-load pipeline:

```text
Source Count = Destination Count
```

should generally be expected unless filtering or transformation intentionally changes the number of records.

---

# 📤 Expected Output

After successful execution, the Data Lake should contain the configured output data.

Conceptual output:

```text
Azure Data Lake
│
├── Customers
│   └── customers.parquet
│
├── Products
│   └── products.parquet
│
├── Orders
│   └── orders.parquet
│
└── JSON
    └── data.parquet
```

These files can later be consumed by:

- Power BI
- Python
- Azure Databricks
- Synapse Analytics
- Machine Learning workflows

---

# 🧠 Concepts Demonstrated

This project demonstrates the following data engineering concepts:

## Azure Data Factory

- Factory
- Pipelines
- Datasets
- Linked Services
- Activities
- Copy Data Activity
- Dependencies
- Pipeline Monitoring

## ETL

- Extraction
- Data Movement
- Transformation
- Loading

## Cloud

- Azure SQL
- Azure Data Lake
- Azure Blob Storage
- Cloud-based storage

## Data Formats

- SQL
- JSON
- Parquet
- Delimited Text

## Data Architecture

- Source Layer
- Integration Layer
- Storage Layer
- Analytics Layer

---

# 📚 Learning Outcomes

By completing this project, the following skills were developed:

### Azure Data Factory

Understanding how to create and configure data pipelines.

### Data Integration

Understanding how multiple sources can be connected to a centralized platform.

### Data Lake

Understanding how raw and processed data can be stored in cloud storage.

### ETL

Understanding the complete lifecycle of extracting, transforming, and loading data.

### Pipeline Orchestration

Understanding how different activities can be executed in a controlled sequence.

### Parquet

Understanding the use of columnar storage formats for analytics.

### Cloud Data Engineering

Understanding how traditional data engineering workflows can be implemented using cloud services.

---

# ⚠️ Challenges

Some of the important challenges involved in building this type of project include:

## Connection Management

Different services require different connection configurations.

```text
ADF
 ↓
SQL
 ↓
Authentication
 ↓
Database
```

---

## Dataset Configuration

Incorrect dataset configuration can result in:

- Missing files
- Invalid tables
- Connection failures
- Schema mismatch

---

## Schema Mapping

Source and destination schemas may contain different data types.

For example:

```text
SQL INT
   ↓
ADF Translator
   ↓
Parquet INT
```

---

## Activity Dependencies

Incorrect dependencies can cause pipeline activities to execute in the wrong order.

---

## Permissions

Azure resources need appropriate permissions for:

- Reading data
- Writing data
- Accessing storage

---

# 🔐 Security

Security is critical when working with cloud data.

Never commit sensitive information to GitHub.

Do not expose:

```text
❌ Passwords
❌ API Keys
❌ Access Tokens
❌ Storage Account Keys
❌ SAS Tokens
❌ Database Passwords
❌ Client Secrets
```

For production environments, use:

```text
Azure Key Vault
        ↓
Managed Identity
        ↓
Azure Data Factory
```

and apply appropriate Azure RBAC permissions.

---

# ✅ Best Practices

## 1. Use Parameterized Pipelines

Avoid hardcoding:

```text
Database Names
Storage Paths
Table Names
File Names
```

Use parameters instead.

---

## 2. Use Incremental Loading

Instead of copying everything:

```text
Full Load
```

use:

```text
Last Modified Date
       ↓
New / Updated Records
       ↓
Data Lake
```

---

## 3. Separate Environments

Use:

```text
Development
     ↓
Testing
     ↓
Production
```

---

## 4. Use Secure Authentication

Prefer:

```text
Managed Identity
Azure Key Vault
RBAC
```

---

## 5. Monitor Pipelines

Monitor:

- Pipeline failures
- Activity failures
- Execution time
- Data volume
- Integration runtime

---

# 💼 Real-World Applications

This architecture can be used in multiple industries.

## 🛒 Retail

```text
Customers
Products
Orders
     ↓
ADF
     ↓
Data Lake
     ↓
Power BI
```

---

## 🏦 Banking

```text
Customers
Transactions
Accounts
     ↓
ADF
     ↓
Data Lake
     ↓
Analytics
```

---

## 🏥 Healthcare

```text
Patients
Appointments
Medical Records
     ↓
ADF
     ↓
Data Lake
     ↓
Analytics
```

---

## 🌾 Agriculture

```text
Farm Data
Crop Data
Weather Data
Production Data
     ↓
ADF
     ↓
Data Lake
     ↓
Power BI
```

---

# 📊 Analytics Possibilities

Once data is available in the Data Lake, many analytical tasks can be performed.

## Customer Analytics

- Customer count
- Customer segmentation
- Customer activity
- Customer lifetime value

## Product Analytics

- Best-selling products
- Product performance
- Product category analysis
- Product demand

## Order Analytics

- Total orders
- Revenue
- Average order value
- Monthly sales
- Order frequency

---

# 🏢 Production Architecture

A more advanced production version can be designed as:

```text
                       DATA SOURCES
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
          ▼                 ▼                 ▼
      Azure SQL           APIs              JSON
          │                 │                 │
          └─────────────────┼─────────────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Azure Data Factory│
                  │                   │
                  │ Ingestion         │
                  │ Transformation    │
                  │ Orchestration     │
                  │ Scheduling        │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Azure Data Lake   │
                  │ Storage Gen2      │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Data Processing   │
                  │ / Transformation  │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │      Power BI     │
                  │     Dashboard     │
                  └───────────────────┘
```

---

# 🥉 Medallion Architecture

A future version of this project can use the Medallion Architecture.

```text
                 RAW DATA
                    │
                    ▼
          ┌──────────────────┐
          │  🥉 BRONZE       │
          │                  │
          │  Raw Data        │
          └────────┬─────────┘
                   │
                   ▼
          ┌──────────────────┐
          │  🥈 SILVER       │
          │                  │
          │  Cleaned Data    │
          └────────┬─────────┘
                   │
                   ▼
          ┌──────────────────┐
          │  🥇 GOLD         │
          │                  │
          │ Business Data    │
          └────────┬─────────┘
                   │
                   ▼
               POWER BI
```

---

# 🔮 Future Enhancements

The project can be expanded with the following features.

## 1. Incremental Data Loading

Implement incremental loading based on:

```text
CreatedDate
ModifiedDate
Timestamp
Watermark
```

---

## 2. Scheduled Triggers

Automate pipeline execution.

Examples:

```text
Hourly
Daily
Weekly
Monthly
```

---

## 3. Mapping Data Flows

Introduce advanced transformations:

```text
Join
Filter
Aggregate
Lookup
Derived Column
Conditional Split
Sort
```

---

## 4. Azure Key Vault

Secure database credentials and secrets using Azure Key Vault.

---

## 5. Power BI Integration

Build dashboards on top of the processed data.

---

## 6. CI/CD

Implement automated deployment using:

```text
GitHub
   ↓
GitHub Actions
   ↓
Validation
   ↓
Deployment
   ↓
Azure Data Factory
```

---

## 7. Pipeline Alerts

Add email or Teams notifications when pipeline execution fails.

---

## 8. Metadata-Driven Pipelines

Create dynamic pipelines capable of processing multiple tables using metadata.

```text
Metadata
    ↓
Dynamic Pipeline
    ↓
Multiple Tables
    ↓
Data Lake
```

---

## 9. Data Quality Checks

Introduce validation rules for:

- Null values
- Duplicate records
- Invalid data types
- Missing records
- Incorrect values

---

## 10. Data Catalog

A future version can integrate data cataloging and governance capabilities.

---

# 📈 Project Roadmap

```text
[x] Azure Data Factory Setup
[x] Azure SQL Integration
[x] JSON Data Integration
[x] Linked Services
[x] Dataset Configuration
[x] Pipeline Configuration
[x] Copy Data Activities
[x] Azure Data Lake Integration
[x] Parquet Destination
[x] GitHub Version Control

[ ] Incremental Data Loading
[ ] Scheduled Triggers
[ ] Mapping Data Flows
[ ] Data Quality Checks
[ ] Azure Key Vault
[ ] Power BI Integration
[ ] CI/CD
[ ] Pipeline Alerts
[ ] Metadata-Driven Pipelines
[ ] Medallion Architecture
```

---

# 💼 Resume Description

### Azure Data Factory ETL & Data Lake Pipeline

**Technologies:** Azure Data Factory, Azure Data Lake Storage Gen2, Azure SQL, SQL Server, JSON, Parquet, GitHub

> Designed and implemented a cloud-based ETL pipeline using Azure Data Factory to integrate structured SQL and semi-structured JSON data sources. Configured linked services, reusable datasets, Copy Data activities, pipeline dependencies, and Azure Data Lake Storage destinations, with processed data stored in Parquet format for downstream analytics.

---

# 📌 Key Skills

This project demonstrates practical knowledge of:

### ☁️ Cloud

- Microsoft Azure
- Azure Data Factory
- Azure Data Lake Storage
- Azure SQL

### 🔄 Data Engineering

- ETL
- ELT
- Data Integration
- Data Pipelines
- Data Lake
- Data Movement
- Data Transformation

### 🗃️ Databases

- SQL
- Azure SQL Database
- SQL Server
- Relational Data

### 📄 Data Formats

- JSON
- Parquet
- Delimited Text

### 🔧 Tools

- Git
- GitHub
- Azure Portal
- Azure Data Factory Studio

---

# 📊 Project Summary

| Category | Details |
|---|---|
| Project Type | Data Engineering |
| Cloud Platform | Microsoft Azure |
| ETL Tool | Azure Data Factory |
| Primary Storage | Azure Data Lake Storage Gen2 |
| Source Database | Azure SQL / SQL Server |
| Data Sources | SQL + JSON |
| Destination Format | Parquet |
| Version Control | Git / GitHub |
| Main Workflow | Data → Data Lake |
| Architecture | Cloud ETL |
| Project Status | Completed Learning Project |

---

# 📄 License

This project is licensed under the **MIT License**.

```text
MIT License

Copyright (c) 2026 Ristel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal in the Software
without restriction, including without limitation the rights to use, copy,
modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

# 👨‍💻 Author

## Priyanshu Kumar

**Computer Science Engineering Student**

### Areas of Interest

```text
Data Analytics
Data Engineering
Cloud Computing
Machine Learning
Python
SQL
Power BI
Azure
ETL
```

---

# 🔗 Project Repository

<p align="center">

<a href="https://github.com/Ristel7/Azure_ADF">
<img src="https://img.shields.io/badge/GitHub-View%20Repository-181717?style=for-the-badge&logo=github&logoColor=white">
</a>

</p>

---

# ⭐ Support

If you found this project useful, interesting, or helpful for learning Azure Data Engineering, consider giving the repository a ⭐.

<p align="center">

☁️ <b>Azure</b> • 🔄 <b>ETL</b> • 🗄️ <b>Data Lake</b> • 📊 <b>Data Engineering</b>

<br><br>

<b>Built with curiosity, experimentation, and a lot of data.</b>

</p>

---

# 🚀 Final Note

This project represents a practical implementation of a cloud-based data integration workflow using Microsoft Azure.

It demonstrates how data can move from multiple source systems through an orchestration layer and finally into centralized cloud storage.

The architecture can be extended into a complete modern data platform by adding incremental loading, data quality, security, orchestration, CI/CD, Power BI, and a Medallion Architecture.

The project is intended as a learning and portfolio implementation and provides a foundation for exploring more advanced Azure Data Engineering concepts.
