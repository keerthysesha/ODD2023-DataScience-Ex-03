# Univariate_Analysis

# ODD2023-DataScience-Ex-03

## Aim
To read the given data and perform the univariate analysis with different types of plots.

## Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## Algorithm :
Step1 Read the given data.

Step2 Get the information about the data.

Step3 Remove the null values from the data.

Step4 Mention the datatypes from the data.

Step5 Count the values from the data.

Step6 Do plots like boxplots,countplot,distribution plot,histogram plot.

## Program:
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from google.colab import files
uploaded = files.upload()
df = pd.read_csv('diabetes.csv')
df
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/b86a25e3-875a-4476-b8cf-32bed3549f6e)

df.isnull().sum()

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/f57425f8-09fb-45b6-a01f-d5518de65b2c)


```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/b040f414-b6d3-423f-b2d1-9d4e894c2d65)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/08ceca22-d480-48fb-84ae-157cc84c4da4)


sns.boxplot(df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/d6fd9202-38a1-44ce-998d-8bd696467add)

sns.displot(x ="Glucose", data = df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/e146c91d-a012-48cd-85eb-32fd36964bd3)


sns.displot(x ="BloodPressure", data = df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/c87cb98a-abd1-457b-a016-460c7e92fe95)

sns.displot(x ="BMI", data = df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/1167331c-ae25-4556-86fa-5f2a634c0166)


sns.displot(x ="DiabetesPedigreeFunction", data = df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/c21461aa-3c40-4ab5-b13d-fae8e89ec87e)


sns.displot(x ="Age", data = df)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/ba27e6e9-1f4c-4b66-bd91-0a8085e61f1e)

```
from google.colab import files
uploaded = files.upload()

df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/45cd23b9-499b-4706-a51d-0a9f9f0caf93)


df.isnull().sum()

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/5ef1ca70-1a08-4883-9a68-3b0787113401)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/712b62f3-12bc-4cef-84c2-2e6da98112a0)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/90b08078-886c-4d30-bf90-393ebd469ea2)

sns.boxplot(numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/b35d9ab4-deeb-47e6-8731-ecfacf5dfbd2)


sns.histplot(x = 'Experience_Years',data = numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/8c42099c-52b4-404e-8c90-a1770c8da17c)


sns.histplot(x = 'Age',data = numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/2b3b5d0b-3aef-4d77-9c13-3e30f9b6b69f)


sns.histplot(x = 'Salary',data = numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/dead7ada-fe4b-439f-868f-b734cf4845a0)

```
from google.colab import files
uploaded = files.upload()
df = pd.read_csv('SuperStore.csv')
df
df.isnull().sum()
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/b2199f75-e978-4476-8189-b0720fd812c7)


df.dropna()

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/f7e14f2a-05c9-4b44-9d8b-3c58971dc52e)


df.dtypes

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/f8486673-7e1c-43ad-a7a8-bb9c6c44760d)

```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/c86beda7-7110-4047-9fab-aefa82da0849)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
sns.boxplot(numeric_cols)
```

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/45e91879-6091-42cf-bc32-78f4e4061079)


sns.histplot(x = 'Sales',data = numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/f749f0e8-0d8d-4e63-9978-ddbd4930530c)



sns.countplot(x="Postal Code", data=numeric_cols)

![image](https://github.com/keerthysesha/ODD2023-DataScience-Ex-03/assets/125575936/34ac89ed-cca6-4e7d-ac0e-546776211c92)


## RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.
