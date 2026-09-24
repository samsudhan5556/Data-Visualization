# Healthcare Dataset Visualisation

A Python notebook that loads a healthcare admissions dataset and visualizes monthly admission patterns and the relationship between patient age and billing amount.

## Contents

- `healthcare_visualisation.ipynb` - the visualisation notebook
- `healthcare_dataset.csv` - the dataset (not included; must be supplied by the user)

## Dataset

The dataset contains 55,500 patient admission records with 15 columns and no missing values.

| Group | Columns |
|-------|---------|
| Patient | Name, Age, Gender, Blood Type |
| Clinical | Medical Condition, Medication, Test Results |
| Admission | Date of Admission, Discharge Date, Admission Type, Room Number |
| Provider | Doctor, Hospital, Insurance Provider |
| Billing | Billing Amount |

## Notebook Walkthrough

1. **Setup and loading** - imports pandas, matplotlib and seaborn, then reads `healthcare_dataset.csv`.
2. **Inspection** - `info()`, `head()`, `tail()`, `columns` and `dtypes` show the structure and data types.
3. **Monthly admissions**
   - Converts `Date of Admission` to datetime.
   - Extracts the month name into a new `Admission Month` column.
   - Counts admissions per month and sorts the counts in ascending order.
4. **Monthly admissions chart** - a line chart of the monthly counts with a dashed grid and rotated axis labels.
5. **Correlation analysis** - computes the correlation between `Age` and `Billing Amount`.
6. **Correlation heatmap** - displays the correlation matrix as an annotated seaborn heatmap using the coolwarm colour scale from -1 to 1.

## Key Results

Admissions by month (all years combined):

| Month | Admissions |
|-------|-----------|
| August | 4,832 |
| July | 4,812 |
| June | 4,699 |
| January | 4,692 |
| October | 4,678 |
| March | 4,672 |
| December | 4,649 |
| May | 4,599 |
| November | 4,548 |
| September | 4,546 |
| April | 4,518 |
| February | 4,255 |

Other findings:

- August and July have the most admissions, while February has the fewest (it also has fewer days).
- Monthly counts are fairly even overall, ranging from about 4,255 to 4,832.
- The correlation between age and billing amount is about -0.004, meaning there is essentially no linear relationship between the two.

## Requirements

- Python 3
- pandas
- matplotlib
- seaborn

Install with:

```
pip install pandas matplotlib seaborn
```

## How to Run

1. Place `healthcare_dataset.csv` in the same folder as the notebook.
2. Open `healthcare_visualisation.ipynb` in Jupyter Notebook, JupyterLab or Google Colab.
3. Run all cells in order.

## Notes

- The monthly admissions series is sorted by count, not by calendar order, so the line chart connects months in ascending order of admissions. It therefore does not show a true seasonal trend over the year. Reindexing the months in calendar order (January to December) before plotting, or using a bar chart, would give a more meaningful view.
- The counts combine all years (2019 to 2024), and partial years may affect the totals for some months.
- The correlation heatmap covers only two variables, so it is a 2x2 matrix.
- The name column has inconsistent capitalization and the billing amount contains some negative values; neither is cleaned in this notebook.

## Possible Extensions

- Plot admissions in calendar order, or as a year-by-month trend
- Compare billing amount by medical condition, insurance provider and admission type
- Visualize age distribution and test results by condition
- Extend the heatmap to more numeric fields, such as hospital stay length
- Analyze admissions by hospital or doctor
