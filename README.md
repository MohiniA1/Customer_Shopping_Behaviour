Customer Shopping Data Cleaning – Python Code Description

This Python script is used to load, explore, and clean the customer shopping behavior dataset before using it for analysis and dashboard creation.

1. Import Required Libraries
import pandas as pd
import numpy as np

Description:
Pandas is used for data manipulation and analysis, while NumPy is used for numerical operations.

2. Load the Dataset
df = pd.read_csv("customer_shopping_behavior.csv")

Description:
The dataset is loaded from a CSV file into a Pandas DataFrame for further processing.

3. Check Dataset Structure
df.info()

Description:
Displays information about the dataset such as the number of rows, columns, data types, and missing values.

4. View Statistical Summary
df.describe()

Description:
Provides statistical details like mean, minimum, maximum, and quartiles for numerical columns.

5. Check Missing Values
df.isnull().sum()

Description:
Identifies the number of missing values in each column.

6. Handle Missing Values
df["Review Rating"] = df.groupby("Category")["Review Rating"].transform(lambda x: x.fillna(x.median()))

Description:
Missing values in the Review Rating column are filled using the median rating of each product category.

7. Standardize Column Names
df.columns = df.columns.str.lower()
df.columns = df.columns.str.replace(" ", "_")

Description:
Column names are converted to lowercase and spaces are replaced with underscores to maintain consistency and make them easier to use in analysis.

8. Export Cleaned Dataset
df.to_csv("customer_shopping_behavior_cleaned.csv", index=False)

Description:
The cleaned dataset is saved as a new CSV file, which can be used for data analysis and dashboard creation (e.g., Power BI).
