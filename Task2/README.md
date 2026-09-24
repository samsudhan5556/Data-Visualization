# Superstore Exploratory Data Analysis

A Python notebook that performs exploratory data analysis (EDA) on the Sample Superstore retail dataset. It cleans the data, engineers a delivery-time feature, and uses bar plots, box plots, a scatter plot and a correlation heatmap to study sales, profit and the effect of discounts.

## Contents

- `Superstore_2_.ipynb` - the analysis notebook (written for Google Colab)
- `samplesuperstore.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset has 10,194 rows and 21 columns, each row being one order line item from a fictional US retail store.

| Group | Columns |
|-------|---------|
| Order details | Row ID, Order ID, Order Date, Ship Date, Ship Mode |
| Customer | Customer ID, Customer Name, Segment |
| Location | Country/Region, City, State/Province, Postal Code, Region |
| Product | Product ID, Category, Sub-Category, Product Name |
| Metrics | Sales, Quantity, Discount, Profit |

There are three product categories: Furniture, Office Supplies and Technology. The dataset has no missing values.

## Notebook Walkthrough

1. **Setup** - imports pandas, numpy, matplotlib and seaborn.
2. **Load and inspect** - reads the CSV, then uses `head()`, `info()` and `describe()` to understand structure and summary statistics.
3. **Data preparation**
   - Converts `Order Date` and `Ship Date` to datetime.
   - Creates a new `Delivery Days` column (ship date minus order date).
   - Checks for missing values and lists the unique categories.
4. **Sales overview**
   - Total sales by category, shown as a bar chart.
   - Histogram of the sales distribution.
5. **Part 1: Bar plots** - average profit and average sales by category, to answer which category generates the most profit.
6. **Part 2: Box plots** - overall profit distribution and profit variation across categories, showing medians, spread and outliers.
7. **Part 3: Discount vs profit** - lists the discount levels used and plots a scatter of discount against profit, to see at what discount level profit starts to fall.
8. **Part 4: Correlation heatmap** - computes the correlation matrix of the numeric columns and displays it as an annotated heatmap.

## Key Results

Total sales by category:

| Category | Total Sales |
|----------|-------------|
| Technology | 839,893 |
| Furniture | 754,748 |
| Office Supplies | 731,893 |

Summary statistics:

| Metric | Value |
|--------|-------|
| Mean sales per line item | about 228.23 |
| Median sales per line item | about 53.91 |
| Mean profit per line item | about 28.67 |
| Mean discount | about 15.5% |
| Quantity per line item | 1 to 14 |

Correlations with profit:

| Variable | Correlation |
|----------|-------------|
| Sales | 0.48 (moderate positive) |
| Discount | -0.22 (weak negative) |
| Quantity | 0.07 (very weak) |
| Delivery Days | -0.00 (none) |

Other observations:

- Sales and profit are highly skewed. The mean is far above the median, and there are extreme values (profit ranges from about -6,600 to 8,400), so outliers strongly affect the averages.
- Higher discounts tend to be associated with lower profit, and the scatter plot shows losses concentrated at high discount levels.
- Delivery time has essentially no relationship with sales or profit.

## Requirements

- Python 3
- pandas
- numpy
- matplotlib
- seaborn

Install locally with:

```
pip install pandas numpy matplotlib seaborn
```

## How to Run

### In Google Colab

1. Open `Superstore_2_.ipynb` in Google Colab.
2. Upload `samplesuperstore.csv` to the session storage so that it is available at `/content/samplesuperstore.csv`.
3. Run all cells in order.

### Locally (Jupyter)

1. Place the CSV file in the same folder as the notebook.
2. Change the file path in the second cell:
   ```python
   df = pd.read_csv("samplesuperstore.csv")
   ```
3. Run all cells in order.

## Notes

- The notebook expects the CSV at `/content/samplesuperstore.csv`; a different location or name will cause a `FileNotFoundError`.
- Seaborn bar plots show the mean of the y variable by default, so the "Profit by Category" and "Sales Distribution by Category" charts show averages, while the first bar chart shows totals.
- The correlation matrix includes `Row ID`, which is only an identifier and carries no analytical meaning.

## Possible Extensions

- Profit analysis by region, segment and sub-category
- Grouping discounts into bands and calculating average profit per band
- Monthly and yearly sales trends using the order date
- Identifying loss-making products and customers
- Building a regression model to predict profit

- ## Output:
- <img width="1137" height="580" alt="image" src="https://github.com/user-attachments/assets/01de2315-e475-48e8-8df2-a7c145993075" />
<img width="1005" height="690" alt="image" src="https://github.com/user-attachments/assets/3ebd2b0c-6208-4ab8-9200-799e9cb77e35" />
<img width="805" height="585" alt="image" src="https://github.com/user-attachments/assets/4bf78822-d39a-405f-9861-a82fda2edc03" />
<img width="742" height="572" alt="image" src="https://github.com/user-attachments/assets/f11f2749-2c6d-4f34-9d90-520b78b6f2a5" />
<img width="776" height="515" alt="image" src="https://github.com/user-attachments/assets/35b316fd-714b-4dc0-ae34-c8c6bc1e880a" />
<img width="785" height="551" alt="image" src="https://github.com/user-attachments/assets/6b56dde2-2417-453d-8987-68552eafcd80" />
<img width="760" height="541" alt="image" src="https://github.com/user-attachments/assets/c2370797-b318-44cd-aaf2-f5c9ea5dc93a" />
<img width="752" height="637" alt="image" src="https://github.com/user-attachments/assets/ec210be3-8674-4324-a1dc-fbdabbbce786" />








