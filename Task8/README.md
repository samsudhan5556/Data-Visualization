# Student Performance Analysis

An exploratory data analysis (EDA) notebook that examines how demographic and background factors relate to students' exam scores in **math**, **reading**, and **writing**.

## Overview

The notebook (`Student.ipynb`) loads a preprocessed version of the *Students Performance* dataset and produces a series of visualizations to answer questions such as:

- Does parental education level affect average scores?
- Does the type of lunch (standard vs. free/reduced) relate to performance?
- Do students who completed a test preparation course score higher?
- How strongly are the three subject scores correlated with each other?

## Dataset

The notebook expects a CSV file named `StudentsPerformance_preprocessed.csv`. After loading, columns are renamed to:

| Column        | Description                                      |
|---------------|--------------------------------------------------|
| `gender`      | Student's gender                                 |
| `race`        | Race/ethnicity group                             |
| `parent_edu`  | Parental level of education                      |
| `lunch`       | Lunch type (standard or free/reduced)            |
| `test_prep`   | Test preparation course status                   |
| `math`        | Math score                                       |
| `reading`     | Reading score                                    |
| `writing`     | Writing score                                    |

> **Note:** The dataset is not included in this repository. The public *Students Performance in Exams* dataset (available on Kaggle) is the likely source. Make sure your CSV has the eight columns above, in this order.

## Analysis Steps

1. **Setup & loading**: import libraries, read the CSV, and rename columns.
2. **Group averages**: bar charts of mean math/reading/writing scores grouped by `parent_edu` and by `lunch`.
3. **Test preparation**: boxplots comparing score distributions per subject, split by `test_prep`.
4. **Pairwise relationships**: a seaborn pairplot with regression lines across the three scores.
5. **Correlation heatmap**: annotated correlation matrix of the three scores.

## Requirements

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook / JupyterLab (or Google Colab)

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

## Usage

1. Place `StudentsPerformance_preprocessed.csv` in your working directory.
2. Update the file path in the second cell. The notebook currently uses a Colab path:
   ```python
   df = pd.read_csv("/content/StudentsPerformance_preprocessed.csv")
   ```
   Change it to, for example:
   ```python
   df = pd.read_csv("StudentsPerformance_preprocessed.csv")
   ```
3. Launch Jupyter and run all cells:
   ```bash
   jupyter notebook Student.ipynb
   ```

If using Google Colab, upload the CSV to the session's `/content/` folder and run the notebook as is.

## Outputs

- Bar charts: average scores by parental education and by lunch type
- Boxplots: score distributions by test preparation status
- Pairplot: scatter and regression plots between subjects
- Heatmap: correlation coefficients between math, reading, and writing scores

## Project Structure

```
.
├── Student.ipynb
├── StudentsPerformance_preprocessed.csv   # required (not included)
└── README.md
```

## Output
<img width="1266" height="490" alt="image" src="https://github.com/user-attachments/assets/0989dc39-850a-4271-a7f4-3a105b204124" />
<img width="1233" height="637" alt="image" src="https://github.com/user-attachments/assets/8a086262-081c-4eaf-8a69-585cfae9b12c" />
<img width="732" height="572" alt="image" src="https://github.com/user-attachments/assets/fb38b9db-8a34-4658-9e3d-6d3cc0f6e2d0" />
<img width="935" height="577" alt="image" src="https://github.com/user-attachments/assets/ab0796ed-7c08-4d5c-818a-dedd7ccae056" />
<img width="987" height="377" alt="image" src="https://github.com/user-attachments/assets/9245106b-799c-43f0-8f0e-d052309ec129" />
<img width="662" height="557" alt="image" src="https://github.com/user-attachments/assets/edffe4e2-73fe-4ec5-876c-29d574f4f911" />





