# AAPL Stock Price Visualization and Returns Analysis

A Python notebook that loads weekly Apple Inc. (AAPL) stock data from an Excel file, prepares it, and visualizes price movements, trading volume and the distribution of returns.

## Contents

- `AAPL_2_.ipynb` - the analysis notebook (written for Google Colab)
- `AAPL.xlsx` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset holds 184 weekly records for AAPL, from 29 September 2014 to 29 March 2018, with 7 columns and no missing values.

| Column | Description |
|--------|-------------|
| Date | Start date of the weekly period |
| Open | Price at the start of the period |
| High | Highest price in the period |
| Low | Lowest price in the period |
| Close | Price at the end of the period |
| Adj Close | Close price adjusted for splits and dividends |
| Volume | Number of shares traded in the period |

## Notebook Walkthrough

1. **Setup and loading** - imports pandas, matplotlib and seaborn, then reads `AAPL.xlsx` with `pd.read_excel()`.
2. **Inspection** - `head()`, `columns` and `dtypes` show the first rows, column names and data types.
3. **Preparation**
   - Converts `Date` to datetime.
   - Sorts the data chronologically by date.
   - Confirms structure and non-null counts with `info()` and checks the latest rows with `tail()`.
4. **OHLC price chart** - a line chart of Open, High, Low and Close over time.
5. **Volume chart** - a line chart of trading volume over time.
6. **Return calculation** - adds a `Daily_Return` column using `pct_change()` on the Close price. The first row is empty because it has no previous value.
7. **Return distribution** - a histogram with a density curve (KDE) of the returns, with missing values dropped.

## Key Results

| Item | Value |
|------|-------|
| Records | 184 |
| Date range | 2014-09-29 to 2018-03-29 |
| First close | 99.62 |
| Last close | 167.78 |
| Highest close in the last five rows | 179.98 (week of 2018-03-05) |

Sample returns from the first weeks: 1.1%, -3.0%, 7.7%, 2.6%.

## Requirements

- Python 3
- pandas
- matplotlib
- seaborn
- openpyxl (needed by pandas to read `.xlsx` files)

Install with:

```
pip install pandas matplotlib seaborn openpyxl
```

## How to Run

### In Google Colab

1. Open `AAPL_2_.ipynb` in Google Colab.
2. Upload `AAPL.xlsx` to `/content/sample_data/` using the Files panel.
3. Run all cells in order.

### Locally (Jupyter)

1. Place `AAPL.xlsx` in the same folder as the notebook.
2. Change the path in the first cell:
   ```python
   df = pd.read_excel("AAPL.xlsx")
   ```
3. Run all cells in order.

## Notes

- The data is weekly, so the `Daily_Return` column actually holds week-over-week returns. Renaming it to `Weekly_Return` (and updating the chart title) would describe it more accurately.
- The last record (29 March 2018) covers a shorter period, so its volume is much lower than the others.
- The notebook expects the file at `/content/sample_data/AAPL.xlsx`; a different location will cause a `FileNotFoundError`.

## Possible Extensions

- Add moving averages (for example 4-week and 12-week) to the price chart
- Calculate volatility and cumulative returns
- Compare Close and Adj Close to show the effect of dividends
- Plot volume alongside price to study their relationship
- Build a simple forecasting model for future closing prices
