# 📺 YouTube Trending ETL Pipeline & Sentiment Analysis

## 📘 Project Overview

This project builds a robust ETL (Extract, Transform, Load) pipeline using Apache Airflow to process trending YouTube video data and perform sentiment analysis. It automates data ingestion, transformation, and storage, and adds business intelligence value by analyzing viewer sentiments through natural language processing techniques.

---

## 🎯 Objectives

- Automate the data pipeline for trending YouTube videos
- Clean, transform, and prepare the data for analysis
- Perform sentiment analysis on video titles and descriptions
- Enable downstream analytics and dashboarding

---

## 🛠️ Tools & Technologies

| Component      | Tool                      |
|----------------|---------------------------|
| Orchestration  | Apache Airflow (DAG)      |
| Programming    | Python 3                  |
| Data Source    | YouTube Data API v3       |
| Storage        | CSV / Local file system   |
| Analysis       | NLP (VADER), Pandas       |

---

## 📦 ETL Pipeline (Airflow DAG)

### DAG Name: `youtube_trending_etl_pipeline`

This pipeline follows a classic ETL architecture:

1. **`extract_trending_videos`**
   - Connects to the YouTube API
   - Fetches metadata of trending videos (title, category, views, etc.)
   - Saves the raw JSON or CSV file

2. **`transform_data`**
   - Cleans and normalizes data
   - Handles missing values and renames columns
   - Prepares textual data for NLP

3. **`load_data`**
   - Stores the transformed data locally or in a target database
   - Prepares it for downstream analysis

✅ All tasks shown as `success` in the DAG run (`2025-01-09, 12:36:10 UTC`)

---

## 🧠 Sentiment Analysis

The notebook `YOUTUBESENTIMENTS.ipynb` performs sentiment analysis using:

- **VADER (Valence Aware Dictionary and sEntiment Reasoner)**
- Sentiment scoring on:
  - Video titles
  - Video descriptions
- Classification into:
  - Positive
  - Neutral
  - Negative

📈 Outputs include visualizations and summary statistics for:
- Sentiment distributions
- Most positive/negative videos
- Trends by category

---


## ✅ How to Run

### 1. Set up Airflow
```bash
airflow db init
airflow users create --username admin --password admin --role Admin --email you@example.com
airflow scheduler
airflow webserver

2. Trigger the DAG
Navigate to Airflow UI

Turn on youtube_trending_etl_pipeline

3. Run Sentiment Notebook
Open YOUTUBESENTIMENTS.ipynb

Run all cells to generate analysis


