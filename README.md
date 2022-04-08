# Ex-04-EDA

## AIM
To perform EDA on the given data set. 

# Explanation
The primary aim with exploratory analysis is to examine the data for distribution, outliers and 
anomalies to direct specific testing of your hypothesis.

# ALGORITHM
### STEP 1
Import the required packages(pandas,numpy,seaborn).
### STEP 2
Read the given .csv file.
### STEP 3
Convert the file into a dataframe and get information of the data.
### STEP 4
Remove the non numerical data columns using drop() method.
### STEP 5
Replace the null values using (.fillna).
### STEP 6
Returns object containing counts of unique values using (value_counts()).
### STEP 7
Plot the counts in the form of Histogram or Bar Graph.
### STEP 8
Find the pairwise correlation of all columns in the dataframe(.corr()).
### STEP 9
Save the final data set into the file.
# CODE :
~~~

#Program developed by : K.Balaji
#Register number : 212221230011


import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("supermarket.csv")
df.info()
df.head()
df.tail()
df.isnull().sum()
df["City"].value_counts()
df["Gender"].value_counts()
df["Payment"].value_counts()
sns.countplot(x="Invoice ID",data=df)
sns.countplot(x="Total",data=df)
sns.countplot(x='gross income',data=df)
sns.countplot(x='Payment',data=df)
sns.displot(df["cogs"])
sns.countplot(x="Gender",hue="Quantity",data=df)
sns.displot(df[df["Product line"]==0]["Total"])
pd.crosstab(df["Payment"],df["Quantity"])
pd.crosstab(df["Gender"],df["Quantity"])
df.corr()
sns.heatmap(df.corr(),annot=True)

~~~

# OUTPUT :
## READ THE DATA :
![OUTPUT](./1.png)
![OUTPUT](./2.png)
![OUTPUT](./3.png)
# CHECKING THE MISSING VALUES IN THE DATASET :
![OUTPUT](./4.png)
# VALUE COUNTS :
![OUTPUT](./5.png)
# PLOTTING GRAPHS FOR VARIOUS DATASETS :
![OUTPUT](./6.png)
![OUTPUT](./7.png)
![OUTPUT](./8.png)
![OUTPUT](./9.png)
![OUTPUT](./10.png)
![OUTPUT](./11.png)
![OUTPUT](./12.png)
![OUTPUT](./13.png)
![OUTPUT](./14.png)
# CORRELATION :
![OUTPUT](./15.png)
# HEAT MAP :
![OUTPUT](./16.png)
# RESULT :
Thus the Exploratory Data Analysis (EDA) on the given data set is successfully completed.




