# Ex-04 Multivariate_Analysis

# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
## STEP 1
Import the built libraries required to perform EDA and outlier removal.

## STEP 2
Read the given csv file

## STEP 3
Convert the file into a dataframe and get information of the data.

## STEP 4
Return the objects containing counts of unique values using (value_counts()).

## STEP 5
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8
Save the final data set into the file

# PROGRAM
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/9c4857c4-2d6e-4bd0-91f7-f9221790176e)

```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/7c2e3113-87ea-4f44-aca1-8d38731a405a)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/71665b6c-2770-4964-baf3-1032b9014511)

```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/e662aab8-4741-4849-96f0-bebbfd1d5b88)

```
sns.boxplot(df)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/143d035a-b207-4fcf-9390-e7fd018028da)

```
plt.figure(figsize = (14,6))
sns.scatterplot(x = 'Glucose',y='BloodPressure',data = df)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/e9d6a2c7-774c-4885-b653-7cbb75dfa3f8)

```
sns.scatterplot(x = 'Glucose',y='Insulin',data = df)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/e6e48f39-bada-4b3a-a702-01c3e8596f8e)

```
sns.scatterplot(x = 'Glucose',y='DiabetesPedigreeFunction',data = df)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/87538ada-7685-4eff-b588-64cfbc537907)

```
sns.scatterplot(x = 'Glucose',y='Age',data = df)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/a1ddf5ad-2409-4ba5-97f9-3ecb968a36d3)

```
sns.heatmap(df.corr(),annot = True)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/2d2b9ac4-70f5-46df-b942-1502d1ba09a8)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/a5d7de5b-d301-44dc-9487-60740d73ee25)

```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/c760fdbc-bd24-4b0b-bb60-19e797cf8252)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/a37d4a6d-fc05-42a1-82f0-dae8d5284c3e)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/2937a873-3061-4c39-9292-b9c172e6cef1)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric
_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/32ebbf24-9edc-4b41-8ad6-d96cb8988cea)

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/d4dd0440-5149-465f-9b80-8a4efe3c9b5e)

```
sns.scatterplot(x = 'Salary',y='Age',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/cdb11a3e-14bd-4bcf-b6d0-5b7e8b5c1d3c)

```
sns.scatterplot(x = 'Experience_Years',y='Salary',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/bd3d9fe3-da0b-4c1a-a4ab-3d568ab17c14)

```
sns.scatterplot(x = 'Experience_Years',y='Age',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/2ce56206-80ff-407f-83a5-eae3d3b93089)

```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/6c1c74fb-6750-4322-8a41-2b5758a20713)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/0c1aa82f-4ae0-429b-b7a8-1a033ed28e4c)

```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/b7ea5162-9a65-4b86-ba4b-7829cb0972bb)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/ed424f27-6f61-4373-a1cc-3fd5331da6bb)

```
df.dropna()
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/2ed399c2-27df-44ed-b6f1-69bac5f3632f)

```
df.dtypes
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/0cb3ac70-d369-41f5-8baf-bc4d905cc885)

```
numeric_cols = df.select_dtypes(include=[int,float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/4a65488f-1668-490d-b01b-d82f10c1ce66)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
```
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/26fd06bb-99c9-4830-8a41-4e9f7c86a512)

```
sns.heatmap(numeric_cols.corr(),annot = True)
```
![image](https://github.com/Poojariyaa/Multivariate_Analysis/assets/127511817/057fe9ec-a72e-485b-8415-471ea762af94)


# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.





