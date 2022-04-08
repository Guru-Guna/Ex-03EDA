# Ex-03EDA

## AIM
To perform EDA on the given data set. 

# Explanation
The primary aim with exploratory analysis is to examine the data for distribution, outliers and 
anomalies to direct specific testing of your hypothesis.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file


# CODE
## DATA ANALYSIS STEPS
import numpy as np

import pandas as pd

import seaborn as sns

df=pd.read_csv("titanic_dataset.csv")

df.info()
![img](Screenshot%202022-04-08%20203550.png)
df.head()
![img](op2.png)
df.isnull().sum()
![img](op3.png)
df.drop("Cabin",axis=1,inplace=True)
df.isnull().sum()
![img](op4.png)
df['Age']=df['Age'].fillna(df['Age'].median())
df['Embarked']=df['Embarked'].fillna(df['Embarked'].mode()[0])
df.isnull().sum()
![img](op5.png)
df.boxplot()
![img](op6.png)
df["Embarked"].value_counts()
![img](op7.png)
df["Pclass"].value_counts()
![img](op8.png)
df["Survived"].value_counts()
![img](op9.png)
pd.crosstab(df["Pclass"],df["Survived"])
![img](op10.png)
pd.crosstab(df["Pclass"],df["Sex"])
![img](op11.png)
pd.crosstab(df["Sex"],df["Survived"])
![img](op12.png)
df.corr()
![img](op13.png)
sns.countplot(x='Survived',data=df)
![img](op14.png)
sns.countplot(x='Pclass',data=df)
![img](op15.png)
df.info()
![img](op16.png)
sns.displot(df["Age"])
![img](op17.png)
sns.displot(df["Fare"])
![img](op18.png)
sns.countplot(x='Pclass',hue="Survived",data=df)
![img](op19.png)
sns.countplot(x='Age',hue='Survived',data=df)
![img](op20.png)
sns.displot(df[df['Survived']==0]["Age"])
![img](op21.png)
sns.heatmap(df.corr(),annot=True)
![img](op22.png)
# OUPUT
Finally, the given data's were analyzed successfully.