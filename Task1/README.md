# Superstore Sales Analysis

A Python notebook that performs basic exploratory data analysis (EDA) on the Sample Superstore retail dataset. It loads the data, checks its quality, computes summary statistics, produces two visualizations, and splits the data into training and testing sets.

## Contents

- `superstore_py.ipynb` - the analysis notebook (written for Google Colab)
- `samplesuperstore - samplesuperstore.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset contains 10,194 order line items from a fictional US retail store, starting in January 2023. Columns include:

| Group | Columns |
|-------|---------|
| Order details | Row ID, Order ID, Order Date, Ship Date, Ship Mode |
| Customer | Customer ID, Customer Name, Segment |
| Location | Country/Region, City, State, Postal Code, Region |
| Product | Product ID, Category, Sub-Category, Product Name |
| Metrics | Sales, Quantity, Discount, Profit |

## What the Notebook Does

1. **Imports libraries** - pandas, numpy, matplotlib, seaborn, scikit-learn and scipy.
2. **Uploads and loads the data** - uses the Colab file upload dialog, then reads the CSV into a DataFrame.
3. **Inspects the data** - shows the first five rows, column types and non-null counts, and the number of missing values per column.
4. **Computes summary statistics** - average sales using NumPy and mean sales using SciPy's trimmed mean function.
5. **Aggregates sales by category** - total sales for each product category.
6. **Visualizes the data**
   - Bar chart of total sales by category
   - Scatter plot of sales versus profit
7. **Splits the data** - 80% training and 20% testing using `train_test_split` with `random_state=42`.

## Results

| Metric | Value |
|--------|-------|
| Mean Sales | about 228.23 |
| Training rows | 8,155 |
| Testing rows | 2,039 |

## Requirements

- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- scipy
- google-colab (only needed when running in Google Colab)

Install the dependencies locally with:

```
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

## How to Run

### In Google Colab

1. Open `superstore_py.ipynb` in Google Colab.
2. Run the first cell.
3. When the upload dialog appears, select `samplesuperstore - samplesuperstore.csv`.
4. The remaining output and charts will be generated automatically.

### Locally (Jupyter)

1. Place the CSV file in the same folder as the notebook.
2. Remove the `from google.colab import files` import and the `files.upload()` call.
3. Change the `path` variable to the local file name:
   ```python
   path = "samplesuperstore - samplesuperstore.csv"
   ```
4. Run all cells.

## Notes

- The notebook only splits the data; no predictive model is trained yet. The split is a starting point for future modeling, such as predicting profit from sales, discount and quantity.
- The `path` variable must match the uploaded file name exactly, otherwise a `FileNotFoundError` will occur.

## Possible Extensions

- Analyze profit by region, segment and sub-category
- Study the effect of discounts on profit
- Analyze sales trends over time using order dates
- Train a regression model to predict profit
