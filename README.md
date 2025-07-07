## ETL Pipeline with Airflow, Postgres, and NASA API

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline using **Apache Airflow**. It pulls daily data from NASA's Astronomy Picture of the Day (APOD) API, transforms it, and loads it into a **PostgreSQL** database — all orchestrated and scheduled with Airflow. The pipeline is fully containerized with Docker and has been deployed to **Astro Cloud**.

---

## Tech Stack

| Tool/Technology     | Purpose                              |
|---------------------|--------------------------------------|
| **Apache Airflow**  | Workflow orchestration               |
| **PostgreSQL**      | Relational database for data storage |
| **Docker**          | Containerization of services         |
| **NASA APOD API**   | External data source                 |
| **Python**          | Transformation logic                 |
| **Astro Cloud**     | Managed Airflow deployment           |

---

## Workflow Overview

### 1. **Extract**
- `HttpOperator` fetches data from NASA APOD API.
- JSON response includes `title`, `explanation`, `url`, `date`.

### 2. **Transform**
- Data is cleaned/processed using Airflow’s TaskFlow API (`@task`).
- Ensures formatting is database-ready.

### 3. **Load**
- Data is inserted into a PostgreSQL table using `PostgresHook`.
- Table creation is handled automatically if not present.

---
---

## Deployed on Astro Cloud

The Airflow pipeline is also deployed to [Astro Cloud](https://www.astronomer.io/), providing scalable, production-ready orchestration.

DAG tested with Astro CLI  
Image pushed and deployed to Astro  
Logs, runs, and scheduling managed via Astro UI  

---


### Airflow DAG in Astro UI
![Airflow DAG](https://github.com/jimmymuthoni/Nasa-ETL-Pipeline-with-Airflow/blob/64b193940856b48dc7681e0e5ab2b06d399aeed3/Airflow1.png)

---

