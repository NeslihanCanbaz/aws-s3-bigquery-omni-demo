# AWS S3 + BigQuery Omni Integration Demo

This project demonstrates how to connect Amazon S3 to Google BigQuery Omni and run federated SQL queries directly on data stored in AWS S3.

---

# Project Overview

In this demo project:

* Created an Amazon S3 bucket
* Uploaded CSV datasets to S3
* Configured AWS IAM roles and trust policies
* Connected Amazon S3 to BigQuery Omni
* Created external tables in BigQuery
* Queried S3 data directly using SQL

This project demonstrates a simple cross-cloud analytics workflow using AWS and Google Cloud Platform.

---

# Technologies Used

* Amazon S3
* AWS IAM
* Google BigQuery Omni
* SQL
* Google Cloud Platform (GCP)

---

# Architecture

AWS S3 stores the datasets, while BigQuery Omni accesses and queries the data without moving it into Google Cloud Storage.
```mermaid
flowchart LR
    A[Amazon S3 Bucket<br/>CSV Files] --> B[AWS IAM Role<br/>S3 Access Policy]
    B --> C[BigQuery Omni Connection<br/>aws-eu-central-1]
    C --> D[BigQuery External Tables<br/>category_analysis<br/>state_analysis]
    D --> E[SQL Queries in BigQuery]
```

---

# Sample Queries

## Category Analysis

```sql
SELECT *
FROM `aws-s3-bigquery-analysis.aws_dataset.category_analysis`
LIMIT 10;
```

## State Analysis

```sql
SELECT *
FROM `aws-s3-bigquery-analysis.aws_dataset.state_analysis`
LIMIT 10;
```

---

# Key Learnings

* Cross-cloud analytics architecture
* Federated querying with BigQuery Omni
* AWS IAM role configuration
* Secure S3 access from GCP
* External table creation in BigQuery

---

# Screenshots

## BigQuery Omni Connection
<img width="833" height="521" alt="Screenshot 2026-05-07 at 15 02 31" src="https://github.com/user-attachments/assets/1f30633a-961a-45c8-9c89-7a11b3d858c2" />


## External Table Schema

<img width="631" height="343" alt="Screenshot 2026-05-07 at 15 03 16" src="https://github.com/user-attachments/assets/9d68893d-11b1-46bf-ac6a-ce30eea1ee55" />

<img width="575" height="432" alt="Screenshot 2026-05-07 at 15 22 46" src="https://github.com/user-attachments/assets/ae500551-72bd-43e9-9ac8-1e07e23e068d" />

<img width="575" height="432" alt="Screenshot 2026-05-07 at 15 22 46" src="https://github.com/user-attachments/assets/27e6c381-ff9d-43e2-a98b-af299728e41a" />


## Query Results

<img width="865" height="741" alt="Screenshot 2026-05-07 at 15 02 48" src="https://github.com/user-attachments/assets/13f1fab4-4e8d-49c2-976a-d68bc5f9be69" />
<img width="1027" height="821" alt="Screenshot 2026-05-07 at 15 02 19" src="https://github.com/user-attachments/assets/4ad7f849-9947-4407-9fb1-66bbfe2d3f8c" />


---

# Author

Built as a hands-on cloud and data engineering practice project.
