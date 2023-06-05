# Ex-04-Multivariate-Analysis

# AIM

To perform Multivariate EDA on the given data set.
Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1

Import the built libraries required to perform EDA and outlier removal.
# STEP 2

Read the given csv file
# STEP 3

Convert the file into a dataframe and get information of the data.
# STEP 4

Return the objects containing counts of unique values using (value_counts()).
# STEP 5

Plot the counts in the form of Histogram or Bar Graph.
# STEP 6

Use seaborn the bar graph comparison of data can be viewed.
# STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()
# STEP 8

Save the final data set into the file

# PROGRAM

Name : VIJAYARAJ.V
Register Number : 212222230174

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

df=pd.read_csv("SuperStore.csv")

df

df.info()

df.describe()

df.isnull().sum()

df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

df.dtypes

sns.scatterplot(df['Row ID'],df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Row ID"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Row ID",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("ROW ID")

plt.show()

states=df.loc[:,["Segment","Row ID"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")

sns.barplot(x=states.index,y="Row ID",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("ROW ID")

plt.show()

sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])

df.corr()

sns.heatmap(df.corr(),annot=True)

# OUTPUT

# DATA

![image](https://user-images.githubusercontent.com/121303741/230762049-f5645c76-ef5e-452c-a7e3-14900744a127.png)

# DATA INFORMATION

![image](https://user-images.githubusercontent.com/121303741/230762059-4041b0c1-7d6e-4e08-b4df-c1959fdcd879.png)

# DATA DESCRIBE

![image](https://user-images.githubusercontent.com/121303741/230762086-29dfca4e-84c7-4a5c-9f2f-009eddd4893e.png)

# Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/121303741/230762112-8ed7e275-6492-48ba-a496-e5d4ba6e048d.png)

![image](https://user-images.githubusercontent.com/121303741/230762135-fb9483ab-319d-4258-958f-b13be55b38a3.png)

# DATA TYPES

![image](https://user-images.githubusercontent.com/121303741/230762145-4b015bfc-b050-48d9-9240-733e252e142f.png)

# SCATTERPLOT

![image](https://user-images.githubusercontent.com/121303741/230762116-deb0ee77-196e-46cc-b176-106246b2f746.png)

# BARPLOT

![image](https://user-images.githubusercontent.com/121303741/230762156-34920300-7f60-4a86-a54f-95a7b8d73fb4.png)

![image](https://user-images.githubusercontent.com/121303741/230762166-09211e0d-7d03-4bfe-9ea2-a6974e86a673.png)

![image](https://user-images.githubusercontent.com/121303741/230762171-faedb3a7-fdc8-467e-82a3-6828be2a7e70.png)

![image](https://user-images.githubusercontent.com/121303741/230762181-6d9ce210-63ad-4a92-92c0-0ffe1e1460f5.png)

# CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/121303741/230762211-c713f7bb-20d6-4ba6-970e-a4ab6aa891b1.png)

# HEATMAP

![image](https://user-images.githubusercontent.com/121303741/230762236-337e072b-3c8d-48d3-a2b8-24d3b63915f6.png)

# RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.



