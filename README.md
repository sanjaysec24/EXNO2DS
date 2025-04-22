# EXNO2DS
## DEVELOPED BY: sanjay kumar.B
## REG NO: 212224230242
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/e2d2d875-46d9-42e9-93ad-fe067e648502)
```
df.info()
```
![image](https://github.com/user-attachments/assets/e99e26de-9426-4b2f-85a3-d90b8ffce2c0)
```
df.shape
```
![image](https://github.com/user-attachments/assets/e55c4a25-4f3c-458f-a374-98bd1b4224a4)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/6b250da6-81b4-4ec7-a9b2-7c6bc5930af7)
```
df.shape
```
![image](https://github.com/user-attachments/assets/2c961098-5e20-412d-a2c6-db2e55f7f2f8)

## Categorical Data Analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/8ad8dad4-d234-437d-a629-e4ea8045bc7c)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/0acab847-8d9e-4a90-a8af-bfd22194f5cb)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/ebfdb587-f0b4-46c8-83e6-6d2cef83057a)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/27b9dea5-90b8-4962-b12e-e9183061f6a9)
```
df
```
![image](https://github.com/user-attachments/assets/0070c361-77d0-477b-8db6-e77ccf1996d9)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/dffe47c4-563e-43f4-838f-3cabc351ac3e)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/5152d58d-495d-4e9a-acb7-5b58fab2c2e2)

## Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/b27fb88b-d65e-44be-9ac5-c5968462d313)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/dcdebbe3-babd-4c8a-a163-6bd3ac5154d7)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/35716570-3d4e-423f-ae71-a0420461c579)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/96d064e9-3538-47e1-916a-f0b884a877ed)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/69f655d9-5ae9-49cf-a414-803aa05aca05)

## Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/8024fca6-50b4-4e58-be15-9c38a4ed97ae)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/9ba54b14-2874-4066-889b-1fe9ab0395a5)
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/1d969854-162c-495e-86aa-3b7f98f44540)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/fe85f59f-9cdf-4385-a79b-3e4b3d4aa968)






# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
