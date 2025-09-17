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
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```


<img width="1433" height="483" alt="image" src="https://github.com/user-attachments/assets/560cd41a-40cd-4c70-a5d5-aca7e924b40e" />

```
df.info()
```


<img width="433" height="417" alt="image" src="https://github.com/user-attachments/assets/e4e737d0-8956-48ce-8aac-41e90f199e4e" />

```
df.dtypes
```


<img width="244" height="550" alt="image" src="https://github.com/user-attachments/assets/e512180b-ba40-4e73-954d-4db3c80f4d16" />

```
df.describe()
```


<img width="861" height="351" alt="image" src="https://github.com/user-attachments/assets/eda8385b-66c6-4eb2-9338-b8f15898b1d0" />

```
df.shape
```


<img width="101" height="35" alt="image" src="https://github.com/user-attachments/assets/d7836745-bed9-45e0-8188-9244a43ab3fb" />

```
df.value_counts()
```


<img width="1494" height="509" alt="image" src="https://github.com/user-attachments/assets/d31f0166-3218-4368-aaaf-01601a30fe68" />


```
df['Age'].value_counts()
```


<img width="179" height="518" alt="image" src="https://github.com/user-attachments/assets/0c1c3ec6-df23-435c-a4d4-22d76bf67c99" />


```
df.set_index("PassengerId",inplace=True)
df
```

<img width="1381" height="519" alt="image" src="https://github.com/user-attachments/assets/10b4cf0f-582f-48d0-8ca1-57182c15fb43" />



```
df.nunique()
```

<img width="180" height="506" alt="image" src="https://github.com/user-attachments/assets/de63cf9f-c5ca-4c41-985a-7074e6fe62c0" />



```
sns.countplot(data=df,x="Survived")
```

<img width="737" height="583" alt="image" src="https://github.com/user-attachments/assets/8dc9550f-ad01-4c4c-b74c-d36da48a7116" />




```
df.Pclass.unique()
```


<img width="167" height="30" alt="image" src="https://github.com/user-attachments/assets/5b7b1b42-11a0-4b93-8a5a-1965b2a99d10" />



```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1382" height="525" alt="image" src="https://github.com/user-attachments/assets/496b1199-5fa5-4183-9d28-af7fab90194e" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)
```


<img width="895" height="645" alt="image" src="https://github.com/user-attachments/assets/2f10b54b-e454-4220-be0b-4d1b953fa7cf" />


```
df.boxplot(column='Age',by="Survived")
```

<img width="720" height="612" alt="image" src="https://github.com/user-attachments/assets/ac0876b1-e83e-4abe-92fc-449ea9a73ef8" />


```
sns.scatterplot( x=df["Age"],y=df["Fare"])
```

<img width="733" height="575" alt="image" src="https://github.com/user-attachments/assets/a4d49699-0c76-488c-975a-1033a9b60a34" />


```
#fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
```

<img width="743" height="556" alt="image" src="https://github.com/user-attachments/assets/79bef174-50ca-47ac-bb78-ac48da51cc16" />


```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1327" height="649" alt="image" src="https://github.com/user-attachments/assets/3593ca3f-686f-47df-b9d4-2dc4610e52b9" />


```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
<img width="709" height="560" alt="image" src="https://github.com/user-attachments/assets/52b9ce16-f956-4046-bc88-2ba8f655f79f" />


# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
