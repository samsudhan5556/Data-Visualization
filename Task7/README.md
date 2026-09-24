# Student Performance Data Exploration and Cleaning

A Python notebook that loads the Students Performance dataset, inspects its structure, checks data quality and standardizes the text formatting of the categorical columns.

## Contents

- `student.ipynb` - the exploration and cleaning notebook
- `StudentsPerformance.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset contains 1,000 student records with 8 columns and no missing values.

| Column | Description |
|--------|-------------|
| gender | Student gender (female or male) |
| race/ethnicity | Anonymized group label (group A to group E) |
| parental level of education | Highest education level of the student's parents |
| lunch | Lunch type (standard or free/reduced) |
| test preparation course | Whether the student completed a test preparation course |
| math score | Math exam score (0 to 100) |
| reading score | Reading exam score (0 to 100) |
| writing score | Writing exam score (0 to 100) |

## Notebook Walkthrough

1. **Imports** - pandas and numpy.
2. **Load data** - reads `StudentsPerformance.csv` into a DataFrame.
3. **Inspection** - `head()`, `tail()`, `info()`, `columns` and `dtypes` show the layout, size and data types.
4. **Missing value check** - `isnull().sum()` confirms that no column has missing values.
5. **Summary statistics** - `describe()` for the three score columns.
6. **Categorical cleaning** - defines the five categorical columns, then strips extra whitespace and converts each value to title case.

## Key Results

| Metric | Math | Reading | Writing |
|--------|------|---------|---------|
| Mean | 66.09 | 69.17 | 68.05 |
| Standard deviation | 15.16 | 14.60 | 15.20 |
| Minimum | 0 | 17 | 10 |
| Median | 66 | 70 | 69 |
| Maximum | 100 | 100 | 100 |

Other observations:

- All 1,000 rows are complete, with no missing values.
- Students score highest on average in reading and lowest in math.
- The lowest math score is 0, which is far below the 25th percentile of 57, so it may be an outlier worth checking.

## Requirements

- Python 3
- pandas
- numpy

Install with:

```
pip install pandas numpy
```

## How to Run

1. Place `StudentsPerformance.csv` in the same folder as the notebook.
2. Open `student.ipynb` in Jupyter Notebook, JupyterLab or Google Colab.
3. Run all cells in order.

## Notes

- Title-casing produces incorrect capitalization in some values, for example "Bachelor'S Degree", "Master'S Degree" and "Associate'S Degree". Using a custom replacement, or converting to lowercase instead, would avoid this.
- The categorical columns are stored in a Python set, so their order is not guaranteed and can change between runs. A list would keep the order fixed.
- The cleaning changes the original values in place, so the loaded data no longer matches the source file exactly.
- The notebook does not check for duplicate rows or outliers, and it does not produce any plots.

## Possible Extensions

- Add an average score column across the three subjects
- Compare scores by gender, lunch type and test preparation course
- Analyze the effect of parental education on performance
- Visualize score distributions with histograms and box plots
- Build a correlation heatmap between the three scores
- Train a model to predict scores from the categorical features
