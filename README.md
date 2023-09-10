Adventure Works Data Ingestion and Transformation Documentation
Table of Contents
Introduction

Overview
Purpose
Setup

Database Import
Azure Key Vault Setup
Azure Data Factory Setup
Parquet Format Data Lake Storage
Data Ingestion

Integration Runtime Configuration
Pipeline Configuration
Lookup and ForEach Functions
Data Transformation

Azure Databricks Setup
Transformation using PySpark
Medallion Architecture

Bronze Layer (Raw Data)
Silver Layer (Validated Data)
Gold Layer (Enriched Data)
1. Introduction
Overview
This documentation outlines the process of importing data from the Adventure Works database into an Azure Data Lake, followed by data ingestion and transformation using Azure Data Factory and Azure Databricks. The Medallion architecture, consisting of Bronze, Silver, and Gold layers, is employed to ensure data quality and reliability throughout the process.

Purpose
The purpose of this project is to create a robust data pipeline that extracts data from an on-premise Adventure Works database, validates and transforms it, and stores it in an Azure Data Lake in a structured Parquet format for efficient analytics.

2. Setup
Database Import
Imported the Adventure Works database to be used as the data source.
Azure Key Vault Setup
Created a username and password in Azure Key Vault with read-only access to the Adventure Works database.
Azure Data Factory Setup
Configured Azure Data Factory to facilitate the data ingestion process. This includes installing the self-host integration runtime to connect to on-premise data sources.
Parquet Format Data Lake Storage
Saved the data in Parquet format within the Azure Data Lake, ensuring optimized storage for analytics.
3. Data Ingestion
Integration Runtime Configuration
Configured the self-host integration runtime in Azure Data Factory to establish connectivity between on-premise data and the Azure Data Factory environment.
Pipeline Configuration
Created an ingestion pipeline in Azure Data Factory that extracts data from the Adventure Works database and loads it into the Data Lake storage.
Lookup and ForEach Functions
Utilized Azure Data Factory's lookup and forEach functions within the ingestion pipeline to ingest data from multiple tables simultaneously.
4. Data Transformation
Azure Databricks Setup
Mounted the necessary resources to Azure Databricks, providing access to the ingested data.
Transformation using PySpark
Conducted data transformations using PySpark within Azure Databricks, applying business logic, data cleaning, and enrichment to prepare the data for analytical use.
5. Medallion Architecture
Bronze Layer (Raw Data)
In accordance with the Medallion architecture, the initial data is stored in the Bronze layer. This layer represents the raw data as ingested from the source database.
Silver Layer (Validated Data)
Data is then transitioned to the Silver layer where validation and quality checks are performed to ensure data integrity and consistency. This layer contains validated data.
Gold Layer (Enriched Data)
The final layer, Gold, houses the enriched data that has undergone transformations and enhancements. This layer is optimized for efficient analytics, and the data within it is considered enriched and reliable.
By following this multi-layered approach to data processing and storage, the project ensures atomicity, consistency, isolation, and durability as data progresses through various stages of validation and transformation. This architecture ultimately results in a single source of truth for enterprise data products.