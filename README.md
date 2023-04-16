# Ex-04-Multivariate-Analysis

# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
STEP 1
Import the built libraries required to perform EDA and outlier removal.

STEP 2
Read the given csv file

STEP 3
Convert the file into a dataframe and get information of the data.

STEP 4
Return the objects containing counts of unique values using (value_counts()).

STEP 5
Plot the counts in the form of Histogram or Bar Graph.

STEP 6
Use seaborn the bar graph comparison of data can be viewed.

STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8
Save the final data set into the file

# PROGRAM

Name : KAMALI E
Register Number : 212222110015

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

# output 

# data

![Screenshot 2023-04-16 102118](https://user-images.githubusercontent.com/120567837/232269377-e13c6efa-ad2c-44e2-b8e0-f85e8b91cb97.png)

# data information

![Screenshot 2023-04-16 102221](https://user-images.githubusercontent.com/120567837/232269669-09baae3b-c6e7-468f-8543-db7ac4a9ca77.png)

# data describe

![Screenshot 2023-04-16 102303](https://user-images.githubusercontent.com/120567837/232269727-f732a7ab-18b9-4229-b321-bbe001e6ec8d.png)

# Checking the null values and Cleaning it

![Screenshot 2023-04-16 102341](https://user-images.githubusercontent.com/120567837/232269747-007fa34c-a86b-490d-be61-6f17cd297976.png)

![Screenshot 2023-04-16 102420](https://user-images.githubusercontent.com/120567837/232269766-58b69ec9-c7fb-4767-a524-3462970c9c61.png)

# data types

![Screenshot 2023-04-16 102446](https://user-images.githubusercontent.com/120567837/232269805-c80ed4fe-4b8a-4607-a819-e8422a251219.png)

# SCATTERPLOT

![Screenshot 2023-04-16 102528](https://user-images.githubusercontent.com/120567837/232270140-51c55d87-282a-4505-8bf3-00000af98388.png)

# Barplot

![Screenshot 2023-04-16 102647](https://user-images.githubusercontent.com/120567837/232271157-7f14d38f-0188-4095-8567-891f6bf3560f.png)

![Screenshot 2023-04-16 102707](https://user-images.githubusercontent.com/120567837/232271382-e8a9d8cf-77d2-4d0b-9441-809d553df615.png)

![Screenshot 2023-04-16 102737](https://user-images.githubusercontent.com/120567837/232271447-a6d4e008-ec10-4e87-86ec-eb2d2e28abb1.png)

![Screenshot 2023-04-16 102758](https://user-images.githubusercontent.com/120567837/232271507-82afb5bf-884d-4aac-a24b-170d8f75fcc5.png)

# CORRELATION COEFFICIENT INTERPRETATION

![Screenshot 2023-04-16 103258](https://user-images.githubusercontent.com/120567837/232272019-0731d80a-4e33-47de-b9db-860df8dad48d.png)

# HEATMAP

![Screenshot 2023-04-16 103444](https://user-images.githubusercontent.com/120567837/232272032-0b72df69-b64a-4e80-8906-1bfe970b7b4f.png)

# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.







