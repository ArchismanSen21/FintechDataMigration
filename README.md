# End-to-End Data Engineering pipeline On Fintech Data Migration
## Introduction
This project demonstrates the migration of data from a relational SQL Server database to a cloud-based Azure architecture. The process involves moving financial data from a traditional SQL database to Azure Data Lake Storage (ADLS) using a structured and scalable approach.


The data migration and transformation process is organized using the Bronze, Silver, and Gold layer architecture:

1. Bronze Layer: Raw data extracted from the source.
2. Silver Layer: Data quality checks and transformations applied.
3. Gold Layer: Fully processed data, ready for analytics and reporting. A Synapse pipeline was created to automate the extraction, loading, and transformation (ELT) processes, ensuring seamless data flow through these layers. After transformations, the final data from the Gold Layer is stored in SynapseDWH for further use.
