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
```
import pandas as pd
import numpy as np
import seaborn as sns
a=pd.read_csv("/content/titanic_dataset.csv")
a

```
<img width="1418" height="476" alt="image" src="https://github.com/user-attachments/assets/c89771fb-53da-4d07-aa01-e4e9b154a924" />


```
a.info()


```
<img width="435" height="392" alt="image" src="https://github.com/user-attachments/assets/5d30d6c6-eb87-4e0d-9855-57bfe399d2a2" />


```
a.describe()


```
<img width="815" height="334" alt="image" src="https://github.com/user-attachments/assets/f99db55d-afdf-4260-a39a-bdf123365ced" />


```
a.dtypes


```
<img width="278" height="507" alt="image" src="https://github.com/user-attachments/assets/362be858-cb36-4dfc-828a-6af53ae7a6a8" />


```
a.shape


```
<img width="170" height="47" alt="image" src="https://github.com/user-attachments/assets/0b3b0954-2ddc-4066-ba1a-1bb2459e0aec" />


```
a.value_counts()

```
<img width="1393" height="550" alt="image" src="https://github.com/user-attachments/assets/b1d24c93-59cf-4764-952e-a73e4f95f19b" />


```
a['Age'].value_counts()


```
<img width="239" height="755" alt="image" src="https://github.com/user-attachments/assets/9fc4fe89-be07-46ef-844b-292ba8ee0875" />



```
a.set_index("PassengerId",inplace=True)
a

```
<img width="474" height="343" alt="image" src="https://github.com/user-attachments/assets/49c6e447-bbed-4a12-a327-c94af8c3f5fa" />


```
a.nunique()


```
<img width="255" height="403" alt="image" src="https://github.com/user-attachments/assets/36482443-d33e-4ebc-809b-b9a94e12d888" />


```
sns.countplot(data=a,x='Age')


```
<img width="574" height="423" alt="image" src="https://github.com/user-attachments/assets/9dacbf24-31f5-4e90-a406-cb45b64e2f93" />


```
a.rename(columns={'Sex':'Gender'},inplace=True)
a


```
<img width="1128" height="410" alt="image" src="https://github.com/user-attachments/assets/bd99cc57-fad1-4ba0-a80a-c2b3cefc63a4" />


```

sns.catplot(x="Gender",col="Survived",kind="count",data=a)

```

<img width="1096" height="489" alt="image" src="https://github.com/user-attachments/assets/6b029986-65a8-4101-939e-ae603b057065" />

```

a.boxplot(column="Age",by="Survived")

```

<img width="578" height="457" alt="image" src="https://github.com/user-attachments/assets/f94045bf-92e3-4e73-84c0-999afe49fd23" />

```

sns.scatterplot(x=a["Age"],y=a["Fare"])

```

<img width="593" height="433" alt="image" src="https://github.com/user-attachments/assets/641b0688-a275-4437-a57c-32a6814b4d97" />

```

plt=sns.boxplot(x="Pclass",y="Age",hue="Gender",data=a)

```

<img width="585" height="421" alt="image" src="https://github.com/user-attachments/assets/6158f3c7-d1f2-4470-8eb9-7fbf0af4618a" />

```

sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=a)

```

<img width="593" height="276" alt="image" src="https://github.com/user-attachments/assets/289fa90a-5550-480a-b620-c712b1ab724d" />

```

corr=a.corr(numeric_only=True)
sns.heatmap(corr,annot=True)

```

![Uploading image.png…]()













































        

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
