# StreamFlix Content Analytics

SQL and Power BI analysis of a simulated streaming platform: data quality checks, exploratory analysis, 12 business KPIs, a 5-page dashboard and a management report.

**Business question:** Which content and customers drive StreamFlix's engagement and revenue, and where is the platform losing subscribers?

## Key findings

| Metric | Result |
| --- | --- |
| Subscribers | 15,000 (11,199 active) |
| Churn rate | **25.3%** (74.7% active) |
| Monthly recurring revenue (MRR) | $175,868.51 |
| ARPU (active subscribers) | $15.70 |
| Watchlist conversion | **46.2%** (30,048 of 65,000 saved titles watched) |
| Top genre by watch hours | Drama (about 501,900 hours) |
| TV Shows vs Movies | TV Shows account for about 86.5% of watch hours |
| Best content investment efficiency | Animation (0.21 watch hours per $1,000 of licensing spend) |
| Most-used devices | Smart TV 34.1%, Mobile 27.0% |

Average completion is about 65% for both movies and TV shows, and engagement per subscriber is similar across plans (Premium 228.8 hours, Basic with Ads 226.9, Standard 214.2).

## Project phases

| Phase | What I did | File |
| --- | --- | --- |
| 1. Data quality checks | 7 SQL checks on a 6-table MySQL schema: churn-date logic, active/inactive consistency, completion % consistency, valid sentiment values and watchlist references. All passed; 321 recently signed-up subscribers were flagged as informational. | `Phase1_DataCleaningStreamflix_Mayuri_Maneguldhe.ipynb` |
| 2. Exploratory data analysis | SQL aggregations and 10 Matplotlib charts on viewing trends, genre performance, demographics and device usage. | `Phase2_EDAStreamflix_Mayuri_Maneguldhe.ipynb` |
| 3. KPI calculation | 12 KPIs using SQL joins, aggregations and subqueries: engagement, MRR and ARPU, churn, watchlist conversion and content investment efficiency. | `Phase3_KPIStreamflix_Mayuri_Maneguldhe.ipynb` |
| 4. Dashboard and report | 5-page interactive Power BI dashboard and a management report with findings, risks, opportunities and recommendations. | `Phase4_Report_Mayuri_Maneguldhe.docx` |

## Dashboard

[View the dashboard as PDF](Phase4_StreamFlix_Mayuri_Maneguldhe.pdf)
## Data

The dataset is simulated, about 980,000 records across 6 tables: subscribers, titles, watch_history, ratings, reviews and watchlist. The raw data is not included in this repository.

Notes on the data:
- Watch duration for TV Shows looks like per series, not per episode (about 10.8 hours per session), so TV vs Movie hours are not directly comparable per session.
- Titles released in 2026 dominate the catalogue, so hours per title is a fairer comparison than total hours by release year.

## How to run

1. Load the tables into a MySQL database named `streamflix`.
2. Install the packages: `pip install pandas sqlalchemy pymysql matplotlib python-dotenv jupyter`
3. Create a `.env` file in the project folder:
   ```
   DB_PASSWORD=your_password_here
   ```
4. Run the notebooks in order, Phase 1 to Phase 3. Each reads the password from `.env`, so no credentials are stored in the code.

## Tech stack

MySQL · Python (pandas, SQLAlchemy, Matplotlib) · Jupyter Notebook · Power BI

## Author

Mayuri Maneguldhe · [GitHub](https://github.com/mayurimaneguldhe-a11y) · [LinkedIn](https://www.linkedin.com/in/mayuri-maneguldhe-558621309)
