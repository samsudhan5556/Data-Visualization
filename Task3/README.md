# AAPL Stock Data Exploration

A Python notebook that performs initial exploration and cleaning of weekly Apple Inc. (AAPL) stock price data. It inspects the structure of the data, summarizes prices and volume, removes duplicates, fixes the date type and checks for missing values.

## Contents

- `AAPL.ipynb` - the exploration and cleaning notebook
- `AAPL.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset holds 184 weekly records for AAPL, from 29 September 2014 to 29 March 2018, with 7 columns.

| Column | Description |
|--------|-------------|
| Date | Start date of the weekly period |
| Open | Price at the start of the period |
| High | Highest price in the period |
| Low | Lowest price in the period |
| Close | Price at the end of the period |
| Adj Close | Close price adjusted for splits and dividends |
| Volume | Number of shares traded in the period |

The last row (29 March 2018) covers a shorter period than the others, which is why its volume is much lower.

## Notebook Walkthrough

1. **Imports** - pandas, matplotlib and numpy.
2. **Structure check** - `df.info()` shows 184 rows, 7 columns, data types and non-null counts.
3. **Preview** - `df.head(11)` and `df.tail()` show the first eleven and last five records.
4. **Summary statistics** - `df.describe()` gives count, mean, min, max, quartiles and standard deviation for each numeric column.
5. **Cleaning**
   - Removes duplicate rows with `drop_duplicates()`.
   - Converts `Date` to datetime with `pd.to_datetime()`.
   - Checks each column for missing values with `isnull().sum()`.

## Key Results

| Metric | Open | High | Low | Close | Adj Close |
|--------|------|------|-----|-------|-----------|
| Mean | 127.04 | 129.92 | 124.34 | 127.35 | 123.84 |
| Minimum | 92.39 | 93.77 | 89.47 | 90.52 | 87.80 |
| Maximum | 180.29 | 183.50 | 177.62 | 179.98 | 179.98 |
| Standard deviation | 24.31 | 24.58 | 24.18 | 24.36 | 25.66 |

Volume statistics:

| Metric | Value |
|--------|-------|
| Mean weekly volume | about 191 million shares |
| Minimum | about 38.4 million shares |
| Maximum | about 500.4 million shares |

Other observations:

- There are no missing values in any column.
- The closing price rose from about 99.62 in the first week to 167.78 in the last week.
- Adj Close is lower than Close in earlier years because of dividend adjustments, and the two match in the most recent rows.

## Requirements

- Python 3
- pandas
- numpy
- matplotlib

Install with:

```
pip install pandas numpy matplotlib
```

## How to Run

1. Open `AAPL.ipynb` in Jupyter Notebook, JupyterLab or Google Colab.
2. Add a cell after the imports to load the data, for example:
   ```python
   df = pd.read_csv("AAPL.csv")
   ```
3. Run all cells in order.

## Notes

- The notebook does not contain a cell that loads the data into `df`. The saved outputs show it was loaded earlier, so add a `read_csv` line (as shown above) before running `df.info()`, otherwise a `NameError` will occur.
- The `Date` column is converted to datetime after the summary statistics are produced. Moving that step earlier would keep the dates typed consistently from the start.
- Matplotlib and numpy are imported but not yet used, as no plots or calculations have been added.

## Possible Extensions

- Plot closing price over time
- Calculate weekly returns and volatility
- Add moving averages (for example 4-week and 12-week)
- Plot trading volume against price movement
- Build a simple forecasting model for future closing prices
