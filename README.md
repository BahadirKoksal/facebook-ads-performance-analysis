# 📘 Facebook Ads Performance Analysis — Google Sheets

## 🎯 Objective

This project analyzes annual Facebook Ads performance data for a Netflix marketing analytics scenario. The goal is to evaluate ad spend efficiency, calculate key performance metrics, identify the best-performing month, and compare Facebook Ads performance against Google Ads to inform future budget allocation decisions.

**Key Research Questions:**
- How much did we spend on Facebook Ads this year, and what did we get in return?
- What are our key performance metrics (CTR, CPC, CPM, ROAS, Conversion Rate)?
- Which month had the highest spend, conversions, and revenue?
- How does Facebook Ads performance compare to Google Ads across key metrics?

---

## 📁 Dataset

**Source:** Facebook Ads CSV data imported into Google Sheets via `IMPORTRANGE()`  
**File:** `Yıl Sonu Reklam Performansı Analizi`  
**Period:** January – December 2023  
**Live Spreadsheet:** [View on Google Sheets](https://docs.google.com/spreadsheets/d/1sJc2MrZ_zfRWvI5YhrLvpkknNtit-SCO8YDt7pPShG4/edit)

### Raw Data Columns

| Column | Type | Description |
|---|---|---|
| `date` | DATE | Daily date |
| `impressions` | INTEGER | Number of times the ad was shown |
| `clicks` | INTEGER | Number of clicks on the ad |
| `spend` | CURRENCY | Amount spent on ads that day |
| `conversions` | INTEGER | Number of completed purchases/goals |
| `revenue` | CURRENCY | Revenue generated from conversions |

---

## 🗂️ Spreadsheet Structure

| Sheet | Description |
|---|---|
| `Facebook Ads Data` | Raw daily ad data imported via `IMPORTRANGE()` from source file |
| `facebook_metrikler` | Daily performance metrics calculated from raw data |
| `Pivot_table_monthly_analysis_facebook` | Pivot table aggregating data by month |
| `Monthly_Analysis_Facebook` | SUMIF-based monthly breakdown |
| `Özet_Facebook` | Summary dashboard with annual and monthly KPIs |

---

## 🔍 Analysis Steps

**1. Data Import**
Raw Facebook Ads CSV data was imported using `IMPORTRANGE()` function — pulling live data from the source spreadsheet into the analysis file. This keeps the data connection dynamic and up to date.

**2. Daily Metric Calculations (`facebook_metrikler` sheet)**
Six key advertising metrics were calculated for each day:

| Metric | Formula | Description |
|---|---|---|
| CTR | `=clicks / impressions` | % of impressions that resulted in a click |
| Conversion Rate | `=conversions / clicks` | % of clicks that resulted in a conversion |
| CPM | `=spend / impressions * 1000` | Cost per 1,000 impressions |
| CPC | `=spend / clicks` | Cost per click |
| Avg. Conversion Value | `=revenue / conversions` | Average revenue per conversion |
| ROAS | `=revenue / spend` | Revenue generated per £1 spent |

**3. Monthly Aggregation — Two Methods**

*Method 1: Pivot Table (`Pivot_table_monthly_analysis_facebook`)*
Used Google Sheets native Pivot Table to group by month number extracted via `MONTH()`. Custom calculated fields added for Avg. Conversion Amount (`=revenue/conversions`) and ROAS (`=revenue/spend`).

*Method 2: SUMIF (`Monthly_Analysis_Facebook`)*
Used `MONTH()` to extract month numbers, then `SUMIF()` to manually aggregate each metric by month for full layout control.

**4. Summary Dashboard (`Özet_Facebook`)**
Annual KPIs calculated using `SUM()` and `AVERAGE()`. Monthly winner questions answered using `MAX()` and `INDEX/MATCH`.

---

## 📊 Key Results

### Annual Performance

| Metric | Value |
|---|---|
| Total Spend | £513,800.43 |
| Total Clicks | 526,188 |
| Total Impressions | 25,104,458 |
| Average CPC | £0.99 |
| Average CPM | £19.66 |
| Total Conversions | 9,895 |
| Avg. Cost per Conversion | £51.93 |
| Total Revenue | £1,529,802.81 |
| Annual ROAS | 2.98 |

### Monthly Winners

| Question | Answer |
|---|---|
| Highest spend month | December |
| Most conversions month | December |
| Highest revenue month | July |
| July CPC | £0.89 |
| July CPM | £19.69 |
| July avg. conversion value | £152.71 |

---

## 📊 Facebook Ads vs Google Ads — Platform Comparison

Both campaigns ran during the same period (January–December 2023) and were analyzed using the same methodology. Here's how they compare:

| Metric | Facebook Ads | Google Ads | Winner |
|---|---|---|---|
| Total Spend | £513,800.43 | £625,835.16 | ✅ Facebook (lower spend) |
| Total Clicks | 526,188 | 418,914 | ✅ Facebook (+25% more clicks) |
| Total Impressions | 25,104,458 | 20,927,740 | ✅ Facebook (+20% more reach) |
| Average CPC | £0.99 | £1.50 | ✅ Facebook (34% cheaper) |
| Average CPM | £19.66 | £29.79 | ✅ Facebook (34% cheaper) |
| Total Conversions | 9,895 | 7,763 | ✅ Facebook (+27% more conversions) |
| Avg. Cost per Conversion | £51.93 | £80.62 | ✅ Facebook (36% cheaper) |
| Total Revenue | £1,529,802.81 | £1,211,548.17 | ✅ Facebook (+26% more revenue) |
| Annual ROAS | 2.98 | 1.94 | ✅ Facebook (54% higher return) |
| Best month (revenue) | July | December | Different seasonality |

### 💡 Key Insight
Facebook Ads significantly outperformed Google Ads across every major metric in 2023. With 34% lower CPC, 36% lower cost per conversion, and a ROAS of 2.98 vs 1.94, Facebook delivered more reach, more conversions, and more revenue at a lower cost. Based on this data, reallocating a larger share of the ad budget toward Facebook Ads in 2024 would likely improve overall marketing ROI.

---

## 🛠️ Google Sheets Functions Used

| Function | Purpose |
|---|---|
| `IMPORTRANGE()` | Pull live data from source spreadsheet dynamically |
| `MONTH()` | Extract month number from date for grouping |
| `SUMIF()` | Sum metrics conditionally by month number |
| `SUM()` | Calculate annual totals |
| `AVERAGE()` | Calculate annual averages for CPC, CPM etc. |
| `MAX()` | Find the best-performing month value |
| `INDEX/MATCH` | Look up which month corresponds to the max value |
| Pivot Table | Drag-and-drop monthly aggregation with custom calculated fields |

---

## 🔗 Related Project

This analysis is part of a two-platform ad performance study:
- 👉 [Google Ads Performance Analysis](https://github.com/BahadirKoksal/google-ads-performance-analysis)

---

## 🔧 Tools & Environment

- **Google Sheets** — All analysis, formulas, and pivot tables
- **Facebook Ads CSV Export** — Raw data source

---

