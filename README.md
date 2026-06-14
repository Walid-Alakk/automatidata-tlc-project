# Automatidata — NYC TLC Fare Prediction Project

**Course 1 End-of-Course Project | Google Advanced Data Analytics Certificate**

---

## Project Overview

This project is part of a fictional workplace scenario in which I work as a data analyst at **Automatidata**, a data consulting firm. The client is the **New York City Taxi & Limousine Commission (TLC)**, which has contracted Automatidata to build a regression model that predicts taxi fares before a ride begins.

This repository covers **Course 1: Foundations of Data Science** — the initial data inspection and preparation phase before full exploratory data analysis (EDA) begins.

---

## Business Goal

Build a regression model that estimates taxi fares based on trip distance, time of day, and other relevant variables — enabling NYC TLC to display predicted fares to passengers before their ride starts.

---

## Dataset

**2017 Yellow Taxi Trip Data** — provided by NYC TLC

| Property | Value |
|---|---|
| Rows | 22,699 |
| Columns | 18 |
| Missing values | 0 |
| Source | NYC Taxi & Limousine Commission |

Key columns: `trip_distance`, `fare_amount` (target), `tpep_pickup_datetime`, `tpep_dropoff_datetime`, `RatecodeID`, `PULocationID`, `DOLocationID`, `payment_type`, `total_amount`

> Note: This dataset was created for pedagogical purposes and may not fully reflect real NYC taxi rider behavior.

---

## Repository Structure

```
Automatidata/
├── 2017_Yellow_Taxi_Trip_Data..csv        # Raw dataset
├── Course1_Automatidata_Project.ipynb     # Main analysis notebook
├── Course1_PACE_Strategy_Document_Completed.docx  # PACE framework responses
├── Course1_Executive_Summary.pptx         # One-page executive summary
└── README.md
```

---

## What's in the Notebook

The Jupyter notebook (`Course1_Automatidata_Project.ipynb`) covers:

1. **Import & Load** — pandas, numpy, CSV into dataframe
2. **Inspect** — `df.head()`, `df.info()`, `df.describe()`
3. **Data type summary** — column dtypes, null counts, relevant vs. irrelevant columns
4. **Variable investigation** — sort by `trip_distance` and `total_amount`, identify anomalies
5. **Payment & tip analysis** — counts by payment type, average tips (credit card vs. cash)
6. **Vendor analysis** — trip counts and mean total amount per vendor
7. **Engineered features** — `trip_duration_minutes`, `pickup_hour`, `pickup_day_of_week`, `cost_per_mile`

---

## Key Findings

- **No missing data** — all 18 columns are complete across 22,699 records
- **Anomalies found**: negative `fare_amount` and `total_amount` values; zero `trip_distance` records; negative trip durations (dropoff before pickup)
- **Primary predictors** for the fare model: `trip_distance` and time-derived features from `tpep_pickup_datetime`
- **Tip data is incomplete**: cash tips (~32% of trips) are not recorded — tip analysis applies to credit card payments only
- **Outliers**: `total_amount` reaches $1,200.29; requires investigation before modeling

---

## PACE Framework

This project follows the **PACE** problem-solving framework:

| Stage | Status |
|---|---|
| **Plan** — Understand the situation and organize information | ✅ Complete |
| **Analyze** — Inspect data, build dataframe, identify variables | ✅ Complete |
| **Construct** — N/A for Course 1 | — |
| **Execute** — Summarize findings, recommend next steps | ✅ Complete |

---

## Recommended Next Steps

1. Conduct full EDA: distributions, correlations, outlier analysis
2. Clean anomalous records before modeling
3. Engineer time-based features (`pickup_hour`, `pickup_day_of_week`)
4. Build regression model with `trip_distance` as primary predictor of `fare_amount`
5. Apply A/B testing to validate variable relationships

---

## Tools & Technologies

- Python 3 | pandas | numpy
- Jupyter Notebook
- Microsoft PowerPoint (executive summary)

---

## Author

**Walid** | Data Analyst at Automatidata (fictional scenario)  
Google Advanced Data Analytics Certificate — Course 1
