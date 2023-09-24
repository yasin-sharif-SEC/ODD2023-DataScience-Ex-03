# ODD2023-DataScience-Ex-03

# AIM
To read the given data and detect outliers and remove them. 

# EXPLANATION
An Outlier is an observation in a given dataset that lies far from the rest of the observations. That means an outlier is vastly larger or smaller than the remaining values in the set.
Outliers badly affect mean and standard deviation of the dataset. These may statistically give erroneous results.
Most machine learning algorithms do not work well in the presence of outlier. So it is desirable to detect and remove outliers.
Outliers are highly useful in anomaly detection like fraud detection where the fraud transactions are very different from normal transactions.

# ALGORITHM
### Step 1
Read the given Data
### Step 2
Perform box plot to find the presence of outlier
### Step 3
Use IQR method and Z Score method to remove the outlier
### Step 4
Perform box plot on the new dataset to ensure the absence of outlier

# CODE
```python
import pandas as pd
import numpy as np
import seaborn as sb
from scipy import stats

df1=pd.read_csv('diabetes.csv')
sb.boxplot(data=df1)

# data cleaning
z=np.abs(stats.zscore(df1['Glucose']))
df1c=df1[z<3]
z=np.abs(stats.zscore(df1c['BloodPressure']))
df1c=df1c[z<2]
z=np.abs(stats.zscore(df1c['SkinThickness']))
df1c=df1c[z<3]
z=np.abs(stats.zscore(df1c['Insulin']))
df1c=df1c[z<2]
z=np.abs(stats.zscore(df1c['DiabetesPedigreeFunction']))
df1c=df1c[z<2]
z=np.abs(stats.zscore(df1c['Age']))
df1c=df1c[z<3]
z=np.abs(stats.zscore(df1c['BMI']))
df1c=df1c[z<2]
print(df1c.info())
sb.boxplot(data=df1c)
sb.histplot(x='Glucose',data=df1c)
sb.histplot(x='BloodPressure',data=df1c)
sb.histplot(x='SkinThickness',data=df1c)
sb.histplot(x='Insulin',data=df1c)
sb.histplot(x='BMI',data=df1c)
sb.histplot(x='DiabetesPedigreeFunction',data=df1c)
sb.histplot(x='Age',data=df1c)


df2=pd.read_csv('employeesal.csv')
print(df2.info())
sb.boxplot(data=df2)
sb.histplot(x='Experience_Years',data=df2)
sb.histplot(x='Age',data=df2)
sb.histplot(x='Salary',data=df2)


df3=pd.read_csv('SuperStore.csv')
print(df3.info())
sb.boxplot(data=df3['Sales'])

# data cleaning
z=np.abs(stats.zscore(df3['Sales']))
df3c=df3[z<0.8]
print(df3c.info())
sb.boxplot(data=df3c['Sales'])
sb.histplot(x='Sales',data=df3c)
sb.histplot(x='Ship Mode',data=df3c)
sb.histplot(x='Segment',data=df3c)
sb.histplot(x='Region',data=df3c)
sb.histplot(x='Region',data=df3c)
```

# OUTPUT
### bhp.csv describe


### bhv.csv after removing outlier using IQR


### bhv.csv after removing outlier using Z SCORE


### height_weigth.csv boxplot


### height_weigth.csv after removing outlier using IQR


### height_weigth.csv after removing outlier using Z SCORE


### heights.csv box plot


### heights.csv after removing outlier using IQR


### heights.csv after removing outlier using Z SCORE


# RESULT
Thus, the given data is read and the outliers are removed from it.
