# **Airflow ELT Pipeline for Global Health Data**

## **Project Overview**
This project implements an **ELT (Extract, Load, Transform) data pipeline** using **Apache Airflow** on **Google Cloud Platform (GCP)**. It processes **1 million records** of global health statistics, loads them into **BigQuery**, transforms the data, and generates **Looker Studio dashboards** for analysis.

## **Key Features**
- **ELT Pipeline:** Extracts data from a CSV file, loads it into **BigQuery**, and applies transformations.
- **Apache Airflow Orchestration:** Configured on a **Google Compute Engine VM** for cost efficiency.
- **BigQuery Staging and Transformation Layers:** Ensures **data integrity, optimized querying, and reduced costs**.
- **Looker Studio Dashboards:** Generates interactive reports for country-specific health insights.
- **Automated Email Reports:** Scheduled Looker Studio reports are emailed to stakeholders.

## **Architecture**
1. **Extract:** Read **1M records** from a CSV file in **Google Cloud Storage (GCS)**.
2. **Load:** Transfer raw data into a **BigQuery staging dataset**.
3. **Transform:**
   - Create separate tables for each country in a **transformation dataset**.
   - Create **views** for optimized reporting.
4. **Reporting:** Use **Looker Studio** for dashboards and **automate report emails**.

## **Technology Stack**
- **Apache Airflow** (orchestration)
- **Google Cloud Platform (GCP)**
  - **Compute Engine** (Airflow VM)
  - **Cloud Storage (GCS)** (data source)
  - **BigQuery** (data warehouse)
  - **Looker Studio** (BI visualization)
- **Python** (Airflow DAGs & scripting)

## **Setup Instructions**
1. **Deploy Airflow on Google Compute Engine:**
   - Install dependencies (`Python 3`, `pip`, `virtualenv`).
   - Install and configure **Apache Airflow**.
   - Allow necessary firewall rules for **port 8080**.
   - Start **Airflow scheduler & webserver**.

2. **Configure Cloud Storage and BigQuery:**
   - Upload the CSV dataset to **Google Cloud Storage**.
   - Create **staging, transform, and reporting datasets** in **BigQuery**.

3. **Deploy the Airflow DAGs:**
   - Place DAG scripts in the **Airflow DAGs directory**.
   - Restart Airflow to detect the DAGs.

4. **Trigger the Pipeline:**
   - Monitor the DAG execution in **Airflow UI**.
   - Verify the **staging, transformation, and reporting layers** in BigQuery.

5. **Build Looker Studio Reports:**
   - Connect **Looker Studio** to the **BigQuery views**.
   - Create country-specific dashboards.
   - Schedule automated report emails.

## **DAG Workflow**
1. **Check if the source CSV file exists in GCS.**
2. **Load data into BigQuery staging dataset.**
3. **Transform and split data into country-specific tables.**
4. **Create optimized views for reporting.**
5. **Trigger Looker Studio dashboards and schedule reports.**


## **File Structure**

![image](https://github.com/user-attachments/assets/8e8b8373-9d2a-417b-9fd9-5f42171c06f8)


### Looker Studio Report

![image](https://github.com/user-attachments/assets/d06f0d3e-a1d0-404a-9eb7-c61c85df8257)


