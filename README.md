
# 📘 Snowflake Data Engineering Blueprint

A project-based learning repo powered by real-world datasets from [data.world](https://data.world) — designed to teach **Snowflake ingestion**, **transformation**, and **monitoring** using scalable ELT pipelines and developer-friendly workflows.

---

## 📦 Featured Datasets

| Dataset                | Format       | What You’ll Build                                                   |
|------------------------|--------------|----------------------------------------------------------------------|
| Retail Product Sales   | CSV          | `COPY INTO → Stream + Task → Revenue dashboard`                     |
| Global Power Plants    | JSON & CSV   | `Snowpipe + Error validation + enrichment`                          |
| COVID-19 Daily Reports | CSV          | `Real-time ingestion → Rolling averages pipeline`                   |

🧪 *All ingestion methods use:* `COPY INTO`, `Snowpipe`, Python REST triggers, and `SnowSQL`.

---

## 🗂️ Repo Structure

```
snowflake-data-blueprint/
├── data/          # Datasets from data.world
├── sql/           # Ingestion scripts (COPY INTO, Pipes, Streams)
├── python/        # Snowpipe trigger scripts
├── diagrams/      # Architecture flowcharts and ingestion maps
├── exercises/     # Chapter quizzes, challenge tasks
└── README.md      # You’re here!
```

---

## 🚀 Getting Started

### 1. Clone the Repo
```bash
git clone https://github.com/mohammedali899/snowflake-data-blueprint.git
cd snowflake-data-blueprint
```

### 2. Create Table in Snowflake
```sql
CREATE TABLE retail_orders (
  product_id INT,
  category STRING,
  price FLOAT,
  units_sold INT,
  order_date DATE
);
```

### 3. Load Data Using `COPY INTO`
```sql
COPY INTO retail_orders
FROM @retail_stage
FILE_FORMAT = (TYPE = 'CSV' SKIP_HEADER = 1)
ON_ERROR = 'CONTINUE';
```

### 4. Validate & Trigger Transformations
Use a `Stream` + `Task` or dbt model to transform loaded data downstream.

---

## 🎯 Learning Outcomes

✅ Ingest files using **Snowflake Stages**, File Formats, and `COPY INTO`  
✅ Automate data pipelines with **Snowpipe** + Python REST triggers  
✅ Monitor ingestion using `QUERY_HISTORY` and `PIPE_USAGE_HISTORY`  
✅ Transform data using **Streams** and **Tasks**  
✅ Explore advanced features: **Native Apps**, **Cortex AI**, **Unistore**

---

## 🧪 Sample Dataset Preview

| product_id | category         | price   | units_sold | order_date  |
|------------|------------------|---------|------------|-------------|
| 101        | Electronics       | 199.99  | 5          | 2023-07-01  |
| 102        | Home & Kitchen    | 29.99   | 12         | 2023-07-02  |
| 103        | Books             | 15.99   | 8          | 2023-07-03  |
| 104        | Clothing          | 49.99   | 3          | 2023-07-04  |
| 105        | Sports            | 89.99   | 7          | 2023-07-05  |

---

## 🔁 Visual Architecture

```
COPY INTO → Snowpipe → Stream → Task → Dashboard
```

This pipeline covers the full Snowflake ELT flow — from raw file drops to live BI dashboards.

---

## 🙌 Contributions & License

Feel free to fork, clone, or contribute.  
MIT License © Mohammed Zaid — Built for the community.

---
