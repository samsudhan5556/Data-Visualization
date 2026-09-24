# Healthcare Dataset Exploration and Cleaning

A Python notebook that loads a healthcare admissions dataset, inspects its structure, checks data quality, converts date columns, standardizes text values and creates a new hospital stay duration feature.

## Contents

- `healthcare.ipynb` - the exploration and cleaning notebook
- `healthcare_dataset.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset contains 55,500 patient admission records with 15 columns and no missing values. Admissions run from May 2019 to May 2024.

| Group | Columns |
|-------|---------|
| Patient | Name, Age, Gender, Blood Type |
| Clinical | Medical Condition, Medication, Test Results |
| Admission | Date of Admission, Discharge Date, Admission Type, Room Number |
| Provider | Doctor, Hospital, Insurance Provider |
| Billing | Billing Amount |

## Notebook Walkthrough

1. **Load and preview** - reads the CSV with pandas and shows the first five rows.
2. **Structure check** - `info()`, `describe()`, `dtypes` and `columns` show the size, data types and summary statistics.
3. **Missing value check** - `isnull().sum()` confirms that no column has missing values.
4. **Date conversion** - converts `Date of Admission` and `Discharge Date` from text to datetime.
5. **Category review** - counts each value in `Admission Type`.
6. **Text standardization** - converts `Admission Type` values to lowercase.
7. **Feature engineering** - adds a `Hospital Stay (Days)` column (discharge date minus admission date).
8. **Billing summary** - summary statistics for `Billing Amount`.

## Key Results

Summary statistics:

| Metric | Value |
|--------|-------|
| Records | 55,500 |
| Mean age | about 51.5 years (range 13 to 89) |
| Mean billing amount | about 25,539 |
| Billing amount range | -2,008 to 52,764 |
| Mean hospital stay | about 15.5 days (range 1 to 30) |
| Room numbers | 101 to 500 |

Admission types are almost evenly split:

| Admission Type | Count |
|----------------|-------|
| Elective | 18,655 |
| Urgent | 18,576 |
| Emergency | 18,269 |

## Requirements

- Python 3
- pandas

Install with:

```
pip install pandas
```

## How to Run

1. Place `healthcare_dataset.csv` in the same folder as the notebook.
2. Open `healthcare.ipynb` in Jupyter Notebook, JupyterLab or Google Colab.
3. Run all cells in order.

## Notes

- The `Billing Amount` column contains negative values (minimum about -2,008). These may be refunds or data errors and should be reviewed before any financial analysis.
- The `Name` column has inconsistent capitalization (for example "DaNnY sMitH"). Only `Admission Type` is standardized in this notebook.
- The dataset contains personal-style fields such as names and doctors. If working with real patient data, follow applicable privacy rules; this dataset appears to be synthetic.
- The notebook does not check for duplicate rows or outliers.

## Possible Extensions

- Standardize name capitalization and remove duplicate records
- Investigate and handle negative billing amounts
- Analyze billing and length of stay by medical condition, hospital or insurance provider
- Compare test results across conditions and medications
- Visualize admissions over time and age distribution
- Build a model to predict billing amount or length of stay
