# Tokyo Olympic Azure Data Engineering Project

## Project Overview

This project demonstrates a complete data engineering pipeline using various Azure tools. The goal is to ingest, store, transform, and analyze data related to the Tokyo Olympics. The final output is visualized using Power BI.

## Project Architecture

![image](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/assets/131516799/89cb43dc-eeb0-45a1-9ef7-f08953a9e1eb)


## Data Set

The data set consists of five tables containing information about athletes, coaches, entries by gender, medals, and teams. The data is available in CSV format and can be accessed through the following links:

- [Athletes.csv](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/Athletes.csv)
- [Coaches.csv](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/Coaches.csv)
- [EntriesGender.csv](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/EntriesGender.csv)
- [Medals.csv](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/Medals.csv)
- [Teams.csv](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/Teams.csv)

## Tools Used

The project leverages the following Azure services:

- **Azure Data Factory**: Used for data ingestion and orchestration.
- **Azure Data Lake Storage Gen2**: Used for storing raw and transformed data.
- **Azure Databricks**: Used for data transformation and processing.
- **Azure Synapse Analytics**: Used for data analysis and querying.
- **Power BI**: Used for data visualization and creating dashboards.

## Project Workflow

1. **Data Ingestion**:
   - Data is ingested from the data source using Azure Data Factory.
   - The ingested data is stored in Azure Data Lake Storage Gen2 as raw data.

2. **Data Transformation**:
   - Raw data is transformed using Azure Databricks.
   - The transformed data is then stored back in Azure Data Lake Storage Gen2.

3. **Data Analysis**:
   - Transformed data is analyzed using Azure Synapse Analytics.
   - Basic charts and analyses are performed in Azure Synapse Analytics.

4. **Data Visualization**:
   - The analyzed data is visualized using Power BI to create interactive dashboards.

## Notebook

The Azure Databricks notebook used for basic data transformation is included in this repository:

- [Tokyo-Olympics-Data.ipynb](Tokyo-Olympics-Data.ipynb)

## Example Query

An example SQL query used in Azure Synapse Analytics for analyzing the data:

```sql
WITH a AS 
(
    SELECT 
        a.Name AS AthleteName,
        COUNT(a.Name) AS Total_Number_of_Athletes,
        c.Event AS Event
    FROM 
        athletes a
    JOIN 
        coaches c ON a.NOC = c.NOC
    GROUP BY 
        a.Name, c.Event
)
SELECT 
    a.AthleteName AS coach
FROM 
    a;
```

## Sample Chart in Azure Synapse Analytics
- [SQL script 1.png](https://github.com/MithunDataPro/Tokyo-Olympic-Azure-Data-Engineering-Project/blob/main/SQL%20script%201.png)

# Conclusion
This project showcases a comprehensive data engineering pipeline using Azure services. From data ingestion to transformation and visualization, each step demonstrates the power and flexibility of Azure for handling complex data workflows.


