# End-to-End Data Engineering Pipeline: Fintech Data Migration

## Overview
This project implements a comprehensive data migration solution, moving financial data from a traditional SQL Server database to a modern cloud-based Azure architecture. The solution leverages Azure's Lakehouse architecture and implements automated ETL processes using Azure Synapse Analytics.

## Architecture
![Concept map](https://github.com/user-attachments/assets/d9e5ac14-f2b7-47ee-912e-cb86f6c00bdd)


The data migration and transformation process follows the medallion architecture with three distinct layers:

- **Bronze Layer**: Contains raw data extracted from the source systems
- **Silver Layer**: Implements data quality checks and initial transformations
- **Gold Layer**: Stores fully processed, analytics-ready data

Data flows through these layers via an automated Synapse pipeline, ultimately landing in SynapseDWH for analytical purposes.

## Technology Stack

### Core Technologies
- **Programming**: Python
- **Data Processing**: PySpark
- **Query Language**: SQL

### Azure Services
- Azure Data Lake Storage (ADLS)
- Azure SQL Database
- Azure Synapse Analytics
- Azure Logic Apps
- Delta Tables

## Implementation Details

### 1. SQL Server to Bronze Layer Migration
The initial data extraction process was optimized using dynamic pipeline activities:
- Implemented Lookup and ForEach activities for automated table discovery
- Eliminated manual configuration requirements
- Established automated data movement from SQL Server to ADLS

### 2. Bronze to Silver Layer Transformation
- Utilized Notebook 1 for data validation and transformation
- Implemented data cleaning processes
- Prepared data for advanced processing

### 3. Silver to Gold Layer Processing
- Employed Notebook 2 for advanced transformations
- Applied business logic and aggregations
- Created analytics-ready datasets

### 4. Automated Monitoring
- Configured Azure Logic App for pipeline monitoring
- Implemented email notifications for:
  - Successful pipeline execution
  - Pipeline failures
  - Critical errors

## Challenges and Solutions

### Technical Challenges
1. **Initial Pipeline Configuration**
   - Challenge: Manual creation of copy activities for individual tables
   - Solution: Implemented dynamic activity generation using Lookup and ForEach activities

2. **System Integration**
   - Challenge: Connection issues between various Azure services
   - Solution: Implemented robust error handling and retry mechanisms

3. **Lookup Activity Data Retrieval**
- Challenge: Lookup activity only retrieved one table when multiple tables were present
- Solution:
  - Truncated and re-populated the tables
  - Created a new linked service with Synapse
  - Verified proper table metadata synchronization

## Project Outcomes
- Successfully implemented a scalable Lakehouse architecture
- Automated end-to-end data migration processes
- Created a robust foundation for advanced analytics
- Established reliable monitoring and notification systems
