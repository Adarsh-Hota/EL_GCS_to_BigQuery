## Overview

An EL data pipeline that leverages Apache Airflow to extract a file from the web and upload it to BigQuery.

![Project Overview](/docs/images/project_overview.png)

- The DAG first downloads the source file from the web and uploads it to Google Cloud Storage (GCS).
- Next, BigQuery creates an external table that points to the file in GCS for analysis.

## Setup

### GCP Compute Engine VM

**Instance configuration**
- Machine type: `e2-standard-4`
- Boot disk image: `ubuntu-2004-focal-v20230918`
- Boot disk size: `30 GB`
- Boot disk type: `Balanced persistent disk`

**Environment configuration**
- Apache Airflow: `2.7.2`
- Docker version: `24.0.6`
- Docker Compose version: `3`

## Data Source

NYC Taxi & Limousine Commission trip record data:  
https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

## Airflow DAG Run Screenshots

### DAG Details
![DAG Run Details](/docs/images/dag_run_details.png)

### DAG Graph
![DAG Run Graph](/docs/images/dag_run_graph.png)

### GCS Upload Result
![GCS Bucket Details](/docs/images/gcs_bucket_details.png)

### BigQuery External Table Schema
![BigQuery External Table Schema](/docs/images/bq_et_schema.png)

### BigQuery External Table Details
![BigQuery External Table Details](/docs/images/bq_et_details.png)
