# EXNO2DS
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
```import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-09-10 114355](https://github.com/user-attachments/assets/eba0b356-9f60-4e98-827e-4e35778a6f0f)



```
dt.info()
```
<img width="346" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/e51b198d-fae7-47df-879a-144416702737">

```
dt.shape
```

<img width="89" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/520383e6-c15c-4be4-b880-496b5ce80346">

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```

<img width="421" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/d606eb72-0c2d-4327-a21b-86b76038e584">

```
dt.nunique()
```

<img width="227" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/6967ad72-73bf-4422-bc60-9d4bfa0682f1">

```
dt["Survived"].value_counts()
```

<img width="242" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/ea72042a-be5a-4498-a80c-daf4f77c91b5">

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

<img width="317" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/fc430e2b-cdaf-4c17-ad5b-6a8947d17fca">

```
sns.countplot(data=dt,x="Survived")
```

<img width="452" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/19eafe6f-cda7-44ec-afca-a36149a77fb0">

```
dt
```

<img width="758" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/107164a9-e6c3-491c-8791-165a689a4c43">

```
dt.Pclass.unique()
```

<img width="127" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/57fff508-72c5-47d8-a7b6-87d487a97ed6">

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

<img width="806" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/d4a5afd1-90ae-462f-bbdc-85916f3b771c">

```
sns.catplot(x='Gender',col='Survived',kind="count",data=dt,height=5,aspect=.7)
```

<img width="601" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/099819e4-5216-4597-817e-bc22661bd01c">

```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```

<img width="469" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/64109bdb-a76a-4d61-ac10-2e458de78608">

```
dt.boxplot(column="Age",by="Survived")
```

<img width="511" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/cdd5d41e-578a-410e-a331-70166e14edc4">

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

<img width="475" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/fd157125-2aaa-4097-8da4-a9b3ced0847b">

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

<img width="515" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/fa5b09e2-91e8-4c78-922a-b38c69fc24a9">

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```

<img width="453" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/67784567-973a-4be7-88ee-c26500f1c7a5">

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="646" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/960e08d5-f75b-4433-8a8c-eb06952d060e">

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

<img width="818" alt="image" src="https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/e0d30880-2c72-4421-afc7-d60c58161ff8">

```
sns.pairplot(dt)
```

![image](https://github.com/Jeevapriya14/EXNO2DS/assets/121003043/fcf007a6-a691-4ea3-85b6-e6af87632abe)














# RESULT
      Thus, The result has been successfully verified!
