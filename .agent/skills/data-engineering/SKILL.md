---
name: data-engineering
description: Data pipeline design, ETL/ELT patterns, data warehousing, and processing frameworks. Use when building data pipelines, analytics infrastructure, or batch processing systems.
---

# Data Engineering

> Move data reliably from where it is to where it needs to be.

---

## 1. Pipeline Architecture

### ETL vs ELT

| Approach | Transform Where | Best For |
|----------|----------------|----------|
| **ETL** | Before loading | Legacy DW, data cleansing |
| **ELT** | After loading | Modern cloud DW (BigQuery, Snowflake) |

### Pipeline Patterns

| Pattern | Use Case |
|---------|----------|
| **Batch** | Daily/hourly aggregations |
| **Streaming** | Real-time analytics, alerts |
| **Micro-batch** | Near-real-time (Spark Streaming) |
| **Lambda** | Batch + streaming combined |
| **Kappa** | Streaming-only (simplicity) |

---

## 2. Technology Selection

| Layer | Options |
|-------|---------|
| **Ingestion** | Kafka, Debezium, Fivetran, Airbyte |
| **Processing** | Spark, Flink, dbt, Pandas |
| **Storage** | S3, GCS, Delta Lake, Iceberg |
| **Warehouse** | BigQuery, Snowflake, Redshift, ClickHouse |
| **Orchestration** | Airflow, Dagster, Prefect |
| **Visualization** | Metabase, Looker, Superset |

---

## 3. dbt Patterns

| Concept | Purpose |
|---------|---------|
| **Sources** | Raw data documentation |
| **Staging** | Clean, rename, type-cast |
| **Intermediate** | Business logic transforms |
| **Marts** | Final business-facing tables |
| **Tests** | Data quality assertions |

### dbt Best Practices

| Principle | Application |
|-----------|-------------|
| **DRY models** | Use CTEs and refs |
| **Incremental** | Process only new data |
| **Documentation** | Describe every model and column |
| **Testing** | unique, not_null, relationships |
| **Version control** | Git for all SQL transforms |

---

## 4. Data Quality

| Dimension | Check |
|-----------|-------|
| **Completeness** | No missing required fields |
| **Uniqueness** | No unexpected duplicates |
| **Freshness** | Data is recent enough |
| **Accuracy** | Values within expected ranges |
| **Consistency** | Same data across systems |

### Tool Options

| Tool | Purpose |
|------|---------|
| **Great Expectations** | Python-based validation |
| **dbt tests** | SQL-based assertions |
| **Soda** | Data monitoring |
| **Monte Carlo** | Data observability |

---

## 5. Data Modeling

### Dimensional Modeling

| Concept | Purpose |
|---------|---------|
| **Fact tables** | Measurable events (orders, clicks) |
| **Dimension tables** | Descriptive context (users, products) |
| **Star schema** | Simple, denormalized joins |
| **Snowflake schema** | Normalized dimensions |
| **Slowly Changing Dimensions** | Track changes over time |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Transform in ingestion | Load raw, transform in warehouse |
| No data contracts | Define schemas and SLAs |
| Monolithic pipeline | Modular, testable stages |
| Skip data quality | Test at every stage |
| Manual CSV workflows | Automated, versioned pipelines |

---

> **Remember:** The best data pipeline is the one you can trust. Invest in testing, monitoring, and documentation — data bugs are silent and expensive.
