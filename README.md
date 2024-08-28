# Modern Data Engineering with Medallion Architecture using DBT, Databricks, Spark and Azure Cloud 
In this project, a retail company wants to build a comprehensive Customer 360° view to enhance its marketing and sales strategies. By leveraging data from various customer touchpoints—such as in-store purchases, online shopping behavior, social media interactions, and customer service inquiries—the company aims to gain a deeper understanding of customer preferences, behaviors, and buying patterns. This insight will be used to deliver personalized marketing campaigns, optimize product recommendations, and improve customer retention.


## System Architecture
![System Architecture.jpeg](System%20Architecture.jpeg)

## Objective
To implement a scalable, efficient data engineering pipeline using the Medallion Architecture that ingests, processes, transforms, and analyzes large volumes of customer data. The architecture will enable the company to create a unified, reliable, and accessible Customer 360° dataset to drive business decisions.

## Components
- Azure Data Lake Storage (ADLS): Serves as the central repository for all raw data collected from various sources, such as point-of-sale systems, web analytics, social media, and customer relationship management (CRM) systems.
- Azure Data Factory (ADF): Orchestrates the data ingestion pipelines that move raw data from multiple sources into the Bronze Layer of the data lake.
- Azure Databricks:
Bronze Layer (Raw Data): Ingests raw, unstructured data into the data lake.
Silver Layer (Cleaned Data): Cleans and transforms the data using Apache Spark, preparing it for analytical and machine learning purposes.
Gold Layer (Curated Data): Aggregates and integrates data into a final curated format that is ready for business use, such as customer segmentation or personalization models.
- DBT (Data Build Tool): Used for managing and transforming data in the Silver and Gold layers. Provides version control, testing, and documentation of data transformations to ensure data quality and reliability.
- Azure Synapse Analytics or Power BI: Utilizes the curated data from the Gold Layer for building dashboards and reports to visualize customer insights, trends, and behaviors.

## Implementation Steps:
- Data Ingestion: Use Azure Data Factory (ADF) to connect to various data sources (e.g., CRM, e-commerce platforms, social media APIs) and ingest data into the Bronze Layer in Azure Data Lake Storage (ADLS).
- Data Processing and Transformation: Use Azure Databricks to process raw data in the Bronze Layer, transforming it into cleaned and structured data in the Silver Layer. Apply data quality checks, deduplication, and normalization. Further transform data in the Gold Layer to create curated datasets ready for consumption by analytics tools and business intelligence applications.
- Data Modeling and Testing with DBT: Use DBT to define data models, transformations, and tests for the Silver and Gold layers. Generate documentation to maintain transparency and governance of data workflows.
Run commands like dbt run, dbt test, and dbt snapshot to execute transformations, run data tests, and capture changes in slowly changing dimensions.
- Analytics and Reporting: Use Azure Synapse Analytics to create interactive dashboards and reports for stakeholders, enabling them to explore customer data and insights.

## Commands
Try running the following commands:
- dbt run # for running models
- dbt test # for tests
- dbt snapshot # for snapshotting and slowly changing dimensions
- dbt docs generate # for documentation
- dbt docs serve # for documentation preview

## Customization and Future Enhancements:
- Integrate additional data sources (e.g., IoT, third-party data providers) to enhance customer profiles.
- Implement machine learning models on the curated data to predict customer churn, lifetime value, or next-best action.
- Extend the solution to support real-time data ingestion and analytics for time-sensitive use cases.
