# 📘 Snowflake Data Blueprint

Designed to teach Snowflake ingestion using modern tools, scalable workflows, and real-world datasets.

---

## 📦 Featured Datasets

| Dataset                  | Format       | Workflow Overview                                       |
|--------------------------|--------------|----------------------------------------------------------|
| Retail Product Sales     | CSV          | `COPY INTO` → `Stream + Task` → Revenue dashboard       |
| Global Power Plants      | JSON & CSV   | Snowpipe → Error validation → Metadata enrichment       |
| COVID-19 Daily Reports   | CSV          | Real-time ingestion → Rolling averages pipeline         |

---

## 🎯 Learning Objectives

- Learn how to use **Stages**, **File Formats**, and `COPY INTO` for structured ingestion.
- Automate ingestion pipelines with **Snowpipe**, **Streams**, and **Tasks**.
- Trigger ingestion with **Python REST API**.
- Monitor ingestion using `COPY_HISTORY` and `SNOWPIPE_USAGE_HISTORY`.
- Practice **error handling**, **validation**, and **data quality control**.
- Explore forward-looking features like **Snowflake Native Apps**, **Cortex AI**, and **Unistore**.

---

## 🗂️ Project Structure

```bash
snowflake-data-blueprint/
├── data/          # Raw datasets from data.world
├── sql/           # SQL scripts: COPY INTO, pipes, streams, tasks
├── python/        # Python scripts to trigger Snowpipe via REST API
├── diagrams/      # Visual architecture and pipeline flows
├── exercises/     # Chapter-wise challenges and quizzes
└── README.md      # You’re here!
```

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/mohammedali899/snowflake-data-blueprint.git
cd snowflake-data-blueprint
```

### 2. Create a Target Table

```sql
CREATE TABLE retail_orders (
  product_id INT,
  category STRING,
  price FLOAT,
  units_sold INT,
  order_date DATE
);
```

### 3. Load Data using COPY INTO

```sql
COPY INTO retail_orders
FROM @retail_stage
FILE_FORMAT = (TYPE = 'CSV' SKIP_HEADER = 1)
ON_ERROR = 'CONTINUE';
```

---

## 🧪 Challenge Yourself

Try these bonus tasks:

- ✅ Use `VALIDATION_MODE = 'RETURN_ERRORS'` before loading.
- ✅ Create a **stream** on the raw table and a **task** to populate a clean table.
- ✅ Set up a **pipe** and trigger ingestion using a Python script from `python/`.

---

## 📊 Monitoring Tips

Use these queries to track ingestion performance:

```sql
-- Snowpipe Monitoring
SELECT * FROM SNOWPIPE_USAGE_HISTORY WHERE PIPE_NAME = 'PIPE_ORDERS';

-- COPY INTO Monitoring
SELECT * FROM COPY_HISTORY WHERE TABLE_NAME = 'RETAIL_ORDERS';
```

---

## 🧠 Interview Readiness

💡 Be prepared to explain:

- How `COPY INTO` differs from `Snowpipe`
- Why `STORAGE_INTEGRATION` is important for secure ingestion
- How `Streams` and `Tasks` automate transformation workflows

---

## 🧠 About the Author

Built by **Mohammed Ali**, data engineer and educator.  
📘 Part of the [Snowflake Data Engineering Blueprint](https://yourcoursepage.com) learning series.

---

## 📜 License

This project is open-source and free for learning use.  
You may **fork**, **clone**, and **contribute**.

---

## 🤝 Contributions

Pull requests welcome. Feel free to open issues for suggestions or bugs.
