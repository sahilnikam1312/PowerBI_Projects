# PowerBI_Projects
Dashboard for car_price




## Dataset
- **Filename:** Price_table.csv
- **Rows × Columns:** [replace with numbers]
- **Columns & description:**
  - `Maker` — manufacturer name (text)
  - `Genmodel` — model name (text)
  - `Genmodel_ID` — model identifier (text)
  - `Year` — model year (integer)
  - `Entry_price` — price (integer, currency)

## What I did (Steps)
1. Loaded `Price_table.csv` into Power BI Desktop.
2. Explored column datatypes and inspected for missing/invalid values.
3. Performed cleaning and transformations in Power Query:
   - Trimmed whitespace, standardized `Genmodel_ID` to uppercase,
   - Converted `Year` and `Entry_price` to numeric,
   - Removed duplicates / blank rows,
   - Added `Entry_price_k` = `Entry_price / 1000`.
4. Built visuals (bar chart by Maker, trend line by Year, matrix) and created DAX measures.
5. Published the report to Power BI Service (link below).

## Visuals & Insights (short)
- Insight 1: e.g. “Top Maker by average entry price: [Maker Name]”
- Insight 2: e.g. “Entry prices peaked in Year: [Year]”
- Visuals included: Bar chart (Avg price by Maker), Line chart (Avg price by Year), Matrix (Maker × Year).

## Important files in this repo
- `Price_table.csv` — raw dataset (if allowed)
- `report.pdf` — 1-page summary (PDF)
- `price_analysis.pbix` — Power BI file (if uploaded)
- `README.md` — this file

## DAX measures used
```dax
AvgPrice = AVERAGE('Price_table'[Entry_price])
AvgPrice_k = DIVIDE([AvgPrice], 1000)
MinPrice = MIN('Price_table'[Entry_price])
MaxPrice = MAX('Price_table'[Entry_price])
