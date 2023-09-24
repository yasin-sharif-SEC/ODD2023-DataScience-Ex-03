# AIM
To read the given data and perform univariate analysis on them. 

# EXPLANATION
This is simplest form of data analysis, where the data being analyzed consists of just one variable. 
Since it’s a single variable, it doesn’t deal with causes or relationships. 
The main purpose of univariate analysis is to describe the data and find patterns that exist within it.<br/>
Univariate Analysis: Data consists of only one variable (only x value).
- Line Plots / Bar Charts
- Histograms
- Box Plots
- Count Plots
- Descriptive Statistics techniques
- Violin Plot

# ALGORITHM
### Step 1
Read the given data.
### Step 2
Remove null values if present.
### Step 3
Using box plot, determine if outliers are present and remove them.
### Step 4
Apply univariate analysis on each column in the data.

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
sb.boxplot(data=df1c)
sb.histplot(x='Glucose',data=df1c)
sb.histplot(x='BloodPressure',data=df1c)
sb.histplot(x='SkinThickness',data=df1c)
sb.histplot(x='Insulin',data=df1c)
sb.histplot(x='BMI',data=df1c)
sb.histplot(x='DiabetesPedigreeFunction',data=df1c)
sb.histplot(x='Age',data=df1c)


df2=pd.read_csv('employeesal.csv')
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
sb.histplot(x='Category',data=df3c)
```

# OUTPUT
### diabetes.csv before data cleaning
![image](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/87f40d26-238c-463c-a4e9-99c580fd61b3)

### diabetes.csv after cleaning outlier
![image](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/f72c38f2-84e4-4267-80d8-cadc8e7a3c80)

### diabetes.csv univariate analysis
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/dcbf44fd-324d-44dc-b9ef-04d1f1ed32af)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/a05aa9b0-1774-4cab-bec7-02dd3b3df6d7)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/c5dd32ad-cc48-459a-84a7-ddf6a5d2bb37)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/6a0e16c6-adb2-428e-936a-2aee6a98d6d9)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/f1484972-3d0b-4215-9cbb-2427e2595469)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/2f2c8e79-5273-4e3e-bd13-fb45d723692c)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/bcec62ea-5768-4f71-a780-740adfda1602)

### employeesal.csv information
![image](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/daacbb5e-7897-4cdb-b289-1295c16dcc3d)

### employeesal.csv univfariate analysis
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/910834db-025f-4dec-a371-9e72690aa28b)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/27d1b7bd-1e21-4503-a936-d0d316065f90)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/63819caa-37ac-4af6-b2a1-5ca74a16eca1)

### SuperStore.csv before cleaning
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/5a77af19-d6fc-4fc5-9fef-a9cfee9fca12)

### SuperStore.csv after cleaning outlier
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/7c1874e6-1ca3-4d9c-a41b-b42490dcd955)

### SuperStore.csv univariate analysis
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/39727343-757d-4583-b632-6347e32de916)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/0a10373f-3829-4d04-a957-259c962cdfd4)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/fbfdc66b-a684-4b14-b462-4b255f8efc9d)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/c91c9fb5-7a9e-4afd-94b7-512aa881f9e8)
![download](https://github.com/yasin-sharif-SEC/ODD2023-DataScience-Ex-03/assets/142985837/63d82dec-024f-406e-837a-7f565b87a4d6)

# RESULT
Thus, the given data is read and univariate analysis is carried on them.
