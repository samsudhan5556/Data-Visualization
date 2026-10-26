House Data Analysis
Project Overview
This project explores and prepares a real estate housing dataset using Python. It examines the dataset structure, checks for missing and duplicate values, creates additional features, visualizes numerical distributions, identifies potential outliers, and exports the processed dataset.
Dataset
The notebook loads kc_house_data.csv.

The dataset is expected to contain housing information such as sale price, living area, lot area, construction year, renovation year, and sale date.

Place the dataset in the location expected by the notebook or update the file path before running it.
Technologies Used
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook or Google Colab
Project Workflow
1. Import the required Python libraries.
2. Load the housing dataset into a Pandas DataFrame.
3. Inspect the first and last rows, data types, summary statistics, column names, and dataset dimensions.
4. Check for missing values and duplicate rows.
5. Convert the sale date to a datetime value.
6. Create additional features:
   - Sale Year: year extracted from the sale date.
   - Property Age: sale year minus construction year.
   - Is Renovated: indicates whether the property has a renovation year greater than zero.
   - Years Since Renovation: sale year minus renovation year for renovated properties; otherwise zero.
7. Calculate price per living square foot and price per lot square foot.
8. Plot boxplots for price, living area, lot area, and the two price-per-square-foot features.
9. Use the interquartile range method to identify potential outliers in those numerical columns.
10. Export the processed dataset to a CSV file.
Output
The notebook saves the processed data as:

cleaned_real_estate.csv

The output includes the original dataset columns and the additional engineered features.
How to Run
1. Open housedata.ipynb in Jupyter Notebook or Google Colab.
2. Upload or place kc_house_data.csv in the expected location.
3. If running locally, change the input path from /content/kc_house_data.csv to the correct local file path.
4. Run the notebook cells in order.
5. Find the generated cleaned_real_estate.csv file in the notebook's working directory.
Notes
- The notebook checks and reports missing values and duplicate rows but does not remove them.
- The notebook reports potential outliers using the IQR method but does not remove or modify them.
- Years Since Renovation is set to zero for properties where yr_renovated is zero or absent.
- Ensure sqft_living and sqft_lot do not contain zero values before interpreting the price-per-square-foot calculations

- ##OUTPUT
- <img width="1687" height="712" alt="image" src="https://github.com/user-attachments/assets/b1ed2973-c211-4e61-aaf7-6414eabf2683" />
