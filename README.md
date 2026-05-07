
# Crypto ETL Pipeline (Python + PostgreSQL)

## Overview
This project is a simple **ETL (Extract, Transform, Load) pipeline** that retrieves real-time cryptocurrency market data from the CoinPaprika API, processes it using Python (Pandas), and loads it into a PostgreSQL database.

The pipeline is designed for learning and demonstrating core data engineering concepts such as API ingestion, data transformation, and relational database storage.

---

## Architecture

**Extract → Transform → Load**

1. **Extract**
   - Data is fetched from the CoinPaprika REST API
   - Cryptocurrencies include: Bitcoin, Ethereum, XRP, Solana

2. **Transform**
   - JSON response is normalized using Pandas
   - Unnecessary fields are removed
   - Columns are renamed for clarity
   - Timestamp (`ingested_at`) is added

3. **Load**
   - Cleaned data is inserted into PostgreSQL
   - Table: `crypto_market_data`

---

## Tech Stack

- Python 3.x
- Pandas
- Requests
- SQLAlchemy
- Psycopg2
- PostgreSQL
- python-dotenv

---

## Project Structure

Crypto_etl.py/
│
├── crypto_etl.py ***Main ETL script***
├── requirements.txt ***Python dependencies***
├── .env ***Environment variables (not pushed to GitHub)***
├── .gitignore ***Ignored files (venv, env, etc.)***
└── README.md ***Project documentation***


---

## Setup Instructions

### 1. Clone repository

```
bash
git clone https://github.com/your-username/crypto-etl.git
cd crypto-etl
```


## 2. Create virtual environment

```
python3 -m venv venv
source venv/bin/activate
```

## 3. Install dependencies

```
pip install -r requirements.txt
```

## 4. Configure environment variables

***Create a .env file***:


```
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=crypto_db
```

## 5. Run ETL pipeline

```
python crypto_etl.py
```

##Database Schema

Table: **crypto_market_data**

| Column            | Description              |
| ----------------- | ------------------------ |
| coin_id           | Unique coin identifier   |
| coin_name         | Name of cryptocurrency   |
| coin_symbol       | Symbol (BTC, ETH, etc.)  |
| price_usd         | Current price in USD     |
| volume_24h_usd    | 24h trading volume       |
| volume_24h_change | Volume change percentage |
| market_cap_usd    | Market capitalization    |
| ingested_at       | Timestamp of ingestion   |

## Features
- Real-time crypto data ingestion
- Automated transformation using Pandas
- PostgreSQL data storage
- Environment variable configuration
- Modular and extensible ETL structure

## Future Improvements
- Add scheduling (cron/Airflow)
- Implement upsert logic (avoid duplicates)
- Dockerize the pipeline
- Add logging and error handling
- Build dashboard for visualization

## Author
**Wangeci Ndovu**
**Data Engineer**

dev.to link https://dev.to/wangeci_ndovu/crypto-etl-pipeline-akf


