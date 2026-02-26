# 📊 Google Ads Performance Dashboard

## 📌 Project Overview

This project demonstrates a complete data analytics workflow — from **raw, messy Google Ads data** to a **clean, interactive performance dashboard** — for a Data Analytics Course campaign running across Hyderabad.

The dataset contained **2,600 rows** of uncleaned advertising data with multiple data quality issues. After cleaning and transforming the data using Python, a full performance dashboard was built in Excel and connected to **Google Looker Studio** for interactive reporting.

## 🧹 Data Cleaning — Problems Found & Fixed

The raw dataset had **6 major data quality issues:**

| # | Problem | Example | Fix Applied |
|---|---------|---------|-------------|
| 1 | **Inconsistent campaign names** | `Data Anlytics Corse`, `DataAnalyticsCourse` | Unified to `Data Analytics Course` |
| 2 | **Mixed date formats** | `2024-11-16`, `20-11-2024`, `2024/11/16` | Parsed all formats → `YYYY-MM-DD` |
| 3 | **Mixed device casing** | `desktop`, `DESKTOP`, `Desktop` | Standardized to `Desktop / Mobile / Tablet` |
| 4 | **Inconsistent location names** | `hyderabad`, `HYDERABAD`, `Hyderbad` | Unified to `Hyderabad` |
| 5 | **Currency stored as text** | `$231.88`, `$1,892` | Stripped `$` and `,` → converted to float |
| 6 | **Missing values** | 112 nulls in Clicks, 97 in Cost | Filled with column median |

---
## 📐 Calculated Fields Added

After cleaning, three new performance metrics were engineered:

```python
df['CTR']                  = df['Clicks'] / df['Impressions'] * 100
df['Cost_per_Conversion']  = df['Cost'] / df['Conversions']
df['ROAS']                 = df['Sale_Amount'] / df['Cost']
```

---

## 📈 Key Insights from the Data

| Metric | Value |
|--------|-------|
| 📢 Total Impressions | 11,760,272 |
| 🖱️ Total Clicks | 361,293 |
| 💰 Total Ad Spend | $559,282 |
| 🎯 Total Conversions | 16,985 |
| 💵 Total Revenue | $3,897,368 |
| 📊 Overall ROAS | 6.97x |
| 📉 Avg CTR | 3.07% |

**Top findings:**
- 📅 **November 2024** was by far the highest-performing month — accounting for nearly 90% of total conversions
- 📱 **Mobile** drove the highest volume of clicks across all devices
- 💡 **ROAS of 6.97x** means every $1 spent returned ~$7 in revenue — a strong result for a course campaign

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python** | Data cleaning and transformation |
| **pandas** | Data manipulation and aggregation |
| **openpyxl** | Excel dashboard generation |
| **Google Sheets** | Cloud data storage for Looker Studio |
| **Google Looker Studio** | Interactive dashboard and reporting |

The Excel file contains 4 sheets:

| Sheet | Description |
|-------|-------------|
| 📊 Dashboard | Scorecards + Bar chart (Spend vs Conversions) + Line chart (CTR by Device) |
| ✅ Cleaned Data | Full 2,600 rows after cleaning with all calculated fields |
| 📅 Monthly Summary | Month-by-month breakdown: Impressions, Clicks, CTR, Spend, Conversions, Revenue, ROAS |
| 🔗 Looker Studio Guide | Step-by-step instructions to connect to Looker Studio |

---
## 👤 Author

**Saad Khan**

*Dataset source: Kaggle — Google Ads Performance Dataset*



---

