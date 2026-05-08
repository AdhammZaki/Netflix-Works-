# 🎬 Netflix Content Analytics Dashboard

A data analysis project that cleans and explores the Netflix titles dataset using **Python (pandas)** and visualizes insights through an interactive **Power BI dashboard**.

---

## 📌 Project Overview

This project walks through the full data pipeline — from raw, messy CSV data to a polished Power BI dashboard — covering:

- Data cleaning and transformation in a Jupyter Notebook
- Power Query error handling inside Power BI
- An interactive dashboard with KPI cards, trend charts, and slicers

---

## 🗂️ Repository Structure

```
netflix-analytics/
│
├── Netflix-data.ipynb          # Python data cleaning notebook
├── Netflix.pbix                # Power BI dashboard file
├── netflix_titles_cleaned.csv  # Raw input dataset (pre-cleaning)
├── netflix_titles.csv          # Final cleaned dataset (output)
└── README.md
```

---

## 🧹 Data Cleaning Steps (Python)

All cleaning logic lives in `Netflix-data.ipynb`. The steps below were applied to the raw dataset:

| # | Step | Description |
|---|------|-------------|
| 1 | **Handle Missing Values** | Filled nulls in `Director`, `Cast`, `Country`, `Rating`, and `Release_Date` with `'Unknown'` or `'UR'` |
| 2 | **Date Standardization** | Converted `Release_Date` strings to datetime using `pd.to_datetime(..., errors='coerce')` |
| 3 | **Feature Engineering** | Extracted `Year_Added` and `Month_Added` from the clean date column |
| 4 | **Duration Split** | Separated `Duration` (e.g. `"90 min"`) into `Duration_Value` (numeric) and `Duration_Unit` (text) |
| 5 | **Drop Redundant Column** | Removed the original `Release_Date` string column |
| 6 | **Normalize & Export** | Lowercased all column names, standardized spacing, and saved to `netflix_titles.csv` |

---

## ⚡ Requirements

**Python**
```
pandas
numpy
jupyter
```

Install with:
```bash
pip install pandas numpy jupyter
```

**Power BI**
- Power BI Desktop (free) — [Download here](https://powerbi.microsoft.com/desktop)

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/netflix-analytics.git
cd netflix-analytics
```

**2. Run the notebook**
```bash
jupyter notebook Netflix-data.ipynb
```
Execute all cells in order. The cleaned file `netflix_titles.csv` will be saved to your specified path.

**3. Open the dashboard**

Open `Netflix.pbix` in Power BI Desktop. If prompted, update the data source path to point to your local `netflix_titles.csv`.

---

## 📊 Dashboard Features

The Power BI dashboard (`Netflix.pbix`) includes:

- **KPI Cards** — Total Titles, Total Movies, Total TV Shows, Countries Covered
- **Line Chart** — Content added per year (Movies vs TV Shows)
- **Donut Chart** — Movies vs TV Shows split
- **Bar Chart** — Top countries by content volume
- **Bar Chart** — Content distribution by maturity rating
- **Gauge** — Average movie duration
- **Slicers** — Filter by Type, Year, Month, Country, and Rating

---

## 🛠️ Power Query — Error Handling

After loading the CSV into Power BI, errors were handled inside Power Query Editor:

1. **Home → Transform Data** to open Power Query
2. **Home → Remove Rows → Remove Errors** to drop rows with any error values
3. For column-specific errors: right-click column → **Replace Errors** → set a default value
4. **Close & Apply** to reload the cleaned data into the report

---

## 📁 Dataset

The dataset is based on the publicly available **Netflix Movies and TV Shows** dataset from [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows), containing titles, directors, cast, countries, ratings, and duration information.

---


---

## 👤 Author

**Adham**
Business Information Systems — Misr University for Science and Technology

---

*Feel free to fork, star ⭐, or open an issue if you have suggestions!*
