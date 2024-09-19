# AWS Data Analytic Platform for The City of Vancouver

## Implementation and Analysis of 3-1-1 Inquiry Volumes Using AWS

### Introduction
The City of Vancouver has migrated its data processing to Amazon Web Services (AWS) to optimize the speed and quality of data analysis for better decision-making. The 3-1-1 inquiry system is a crucial public service that allows citizens to report issues, ask questions, and request services from various city departments. This project establishes a Data Analytics Platform (DAP) on AWS for sourcing, storing, processing, and analyzing 3-1-1 inquiry volumes to improve resource allocation and service delivery.

---

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
  <img width="432" alt="image" src="https://github.com/user-attachments/assets/e2dfdd0c-ac5b-47c0-81ea-2000c14c9bbd">
  <img width="432" alt="image" src="https://github.com/user-attachments/assets/a9ee02d7-cf61-4ea8-8ad9-ab3e2f17c169">



### 4. Data Preparation
AWS DataBrew was used to clean and transform the data, applying standardization and filtering irrelevant data points.


### 5. Data Injection
The cleaned data was ingested into the S3 Raw bucket for storage and further processing.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/7f9326ab-bd7d-4c6d-9de2-3c9e6f2e4108">


### 6. Data Pipeline Design
AWS Glue was employed to create a data pipeline for ETL (Extract, Transform, Load) processes, ensuring the data flows efficiently to the desired destinations.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/4b643870-4462-4c8a-8c25-4611c8de4503">



### 7. Data Cleaning
Data cleaning involved removing null values and resolving formatting issues using AWS DataBrew.

### 8. Data Structuring
The data was restructured by the department and monthly trends were to fit the analytical questions posed at the beginning of the project.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/4b47ad2d-805a-4c2c-8f97-87d22a0c7a1e">



### 9. Data Pipeline Implementation
AWS Glue Jobs were set up to ensure the correct transformation and loading of data into the designated S3 buckets.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/8b48a649-895c-440f-b911-f13c108d4c97">

<img width="432" alt="image" src="https://github.com/user-attachments/assets/5153e479-bc47-4c36-81ef-4e0c878d3478">


### 10. Data Analysis
AWS Athena was utilized for SQL queries to analyze the data. For example, the following query was executed to retrieve relevant information:
```sql
SELECT FROM "group2_part1_govfinance_3_1_1_inquiry_volume_database_hemanth"."group2_part1_govfinance_3_1_1_inquiry_volume_table_hemanth";
```
<img width="432" alt="image" src="https://github.com/user-attachments/assets/e52ef05e-2666-4464-b57b-995e12d85309">


### 11.Data Visualization
The comparison of inquiry volumes between 2023 and 2024 was visualized to analyze departmental resource allocation and performance. This was critical for stakeholders to monitor and report on department performance.
<img width="434" alt="image" src="https://github.com/user-attachments/assets/6a66eaf7-1c77-4816-825b-5124acb8b90d">


### 12.Data Publishing
An AWS EC2 instance was deployed to publish the analysis results, enabling remote access for stakeholders.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/914bd676-2774-471f-badc-9dff4a379c39">



