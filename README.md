## Part 1: DAP Design and Implementation

## Introduction

This project outlines the design and implementation of a Data Analytics Pipeline (DAP) to process, analyze, and visualize the 3-1-1 inquiry volume data from the City of Vancouver. This pipeline aims to address key analytical questions related to inquiry trends and departmental performance, utilizing AWS cloud services for data storage, preparation, and analysis.

The pipeline covers multiple stages, starting from data discovery and storage design, to cleaning, structuring, and analysis of the data using AWS services like S3, DataBrew, Glue, and Athena. The final outputs include structured data ready for analysis and visualizations that provide insights into the inquiry patterns over time.

### Key Objectives
1. Formulating analytical questions to guide the inquiry.
2. Leveraging cloud-based infrastructure for scalable data storage and processing.
3. Automating data cleaning and transformation workflows.
4. Performing data analysis to uncover insights about inquiry volumes.
5. Delivering visualizations and reports for stakeholder use.

This project demonstrates the integration of cloud-based tools and data analytics best practices to ensure efficient processing and insightful analysis.


## Part 1: DAP Design and Implementation

### 1. Data Analytical Question Formulation
Key questions driving the analysis include:
- To which departments do citizens most frequently report inquiries?
- What are the monthly trends in inquiry volumes?
- How does the distribution of inquiry volumes vary by year?

### 2. Data Discovery
Data was sourced from the City of Vancouver's 3-1-1 inquiry volume dataset available at [OpenData Vancouver](https://opendata.vancouver.ca/explore/dataset/3-1-1-inquiry-volume/information/?disjunctive.department&disjunctive.type&disjunctive.channel).

### 3. Storage Design
AWS S3 was used for data storage with three distinct buckets:
- **Raw Bucket**: Stores unprocessed data.
- **Landing Bucket**: Contains data post-initial processing and staging.
- **Curated Bucket**: Holds processed data ready for analysis.

### 4. Data Preparation
AWS DataBrew was used to clean and transform the data, applying standardization and filtering irrelevant data points.


### 5. Data Injection
The cleaned data was ingested into the S3 Raw bucket for storage and further processing.
![DataBrew Data Preparation](datapreparation.png)

### 6. Data Pipeline Design
AWS Glue was employed to create a data pipeline for ETL (Extract, Transform, Load) processes, ensuring the data flows efficiently to the desired destinations.
![DataBrew Data Preparation](datapipeline.png)


### 7. Data Cleaning
Data cleaning involved removing null values and resolving formatting issues using AWS DataBrew.

### 8. Data Structuring
The data was restructured by the department and monthly trends to fit the analytical questions posed at the beginning of the project.
![DataBrew Data Preparation](DataStructuring.png)


### 9. Data Pipeline Implementation
AWS Glue Jobs were set up to ensure the correct transformation and loading of data into the designated S3 buckets.

![DataBrew Data Preparation](DataPipelineImplementation1.png)
![DataBrew Data Preparation](DataPipelineImplementation.png)

### 10. Data Analysis
AWS Athena was utilized for SQL queries to analyze the data. For example, the following query was executed to retrieve relevant information:
```sql
SELECT FROM "group2_part1_govfinance_3_1_1_inquiry_volume_database_hemanth"."group2_part1_govfinance_3_1_1_inquiry_volume_table_hemanth";
```
![DataBrew Data Preparation](Dataanalysis.png)

### 11.Data Visualization
The comparison of inquiry volumes between 2023 and 2024 was visualized to analyze departmental resource allocation and performance. This was critical for stakeholders to monitor and report on department performance.
![DataBrew Data Preparation](DataVisualization.png)

### 12.Data Publishing
An AWS EC2 instance was deployed to publish the analysis results, enabling remote access for stakeholders.
![DataBrew Data Preparation](DataPublishing.jpg)

