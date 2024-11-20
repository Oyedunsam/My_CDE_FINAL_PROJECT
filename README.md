# My_CDE_FINAL_PROJECT


# CDE Capstone Project
## Project Overview
This project involves building a data platform for a travel agency to process country-related data using the REST API (https://restcountries.com/v3.1/all). The processed data is stored in a cloud-based Data Lake and Database/Data Warehouse for predictive analytics by the Data Science team. The solution incorporates ETL workflows, data modeling, and CI/CD pipelines.

# Features
## Data Extraction

Fetch data from the REST API containing details about countries.
Store raw data in Parquet format in an AWS S3 bucket (Data Lake).
Data Transformation

Extract specific attributes for downstream analytics:
Country Name
Independence
United Nations Membership
Start of the Week
Official Country Name
Common Native Name
Currency Details (Code, Name, Symbol)
Country Code
Capital
Region and Sub-Region
Languages
Area
Population
Continents
Load transformed data into a PostgreSQL Database.
Orchestration

Apache Airflow is used to automate the ETL pipeline:
Extract data from API and store it in the Data Lake.
Transform and load specific attributes into the Database.
Data Modeling

DBT (Data Build Tool) is used for modeling data into Fact and Dimension tables.
CI/CD Integration

CI: Code linting and best practices checks.
CD: Build and push Docker images to a cloud-based Container Registry.
Infrastructure as Code

All cloud resources (e.g., S3, IAM, RDS) are provisioned using Terraform.
Terraform state management is handled in AWS S3.

# Project Architecture
Components:
Data Extraction

REST API: https://restcountries.com/v3.1/all
Object Storage: AWS S3 (Raw Data Lake)
Data Transformation and Loading

Orchestrator: Apache Airflow
Transformation Tool: Python, Pandas
Cloud Database: PostgreSQL on AWS RDS
Data Modeling

Tool: DBT
CI/CD Pipeline

Code Repository: GitHub
CI/CD Tool: GitHub Actions
Containerization: Docker
Infrastructure Provisioning

Tool: Terraform
Setup Instructions
Prerequisites
Python (3.7+)
PostgreSQL database
AWS CLI configured with appropriate permissions
Docker
Terraform
Git


# How to Use
Data Pipeline Execution
Extract and Load Raw Data

Raw data is fetched from the REST API and stored in the S3 bucket in Parquet format.
Extract Specific Attributes and Load into Database

Transformed data is extracted from the Data Lake and loaded into PostgreSQL.
Data Analytics and Modeling

Use DBT to transform data into analytical models for use by the Data Science team.



# Folder Structure

CDE_Final_Project/
├── dags/                          # Airflow DAGs
├── dbt/                           # DBT models and configurations
├── terraform/                     # Terraform scripts for infrastructure
├── scripts/                       # Python scripts for data extraction and transformation
├── requirements.txt               # Python dependencies
├── Dockerfile                     # Docker configuration
├── README.md                      # Project documentation
└── .gitignore                     # Git ignore rules


# Technologies Used

Cloud Provider: AWS (S3, RDS)
Orchestration: Apache Airflow
Data Processing: Python, Pandas
Database: PostgreSQL
Data Modeling: DBT
Infrastructure as Code: Terraform
CI/CD: GitHub Actions
Version Control: Git

# Challenges and Solutions
Handling Large Data Sets
Used Parquet format for efficient storage and processing.
Automating the Workflow
Leveraged Apache Airflow for end-to-end pipeline orchestration.
Cloud Infrastructure Management
Implemented Terraform for consistent and reusable infrastructure provisioning.

# Insights and Learnings

Successfully automated ETL pipelines for raw and analytical data storage.
Improved performance by using efficient file formats and structured data models.
