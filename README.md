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
~~~
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
df=pd.read_csv("titanic_dataset.csv")
df
~~~

<img width="1270" height="428" alt="image" src="https://github.com/user-attachments/assets/7136f713-8f37-4c26-b3e6-be022afb602d" />

~~~
df.head()
~~~

<img width="1296" height="292" alt="image" src="https://github.com/user-attachments/assets/124dfa22-8567-4531-a918-a60a625c15cd" />


~~~
df.tail()
~~~

<img width="1143" height="272" alt="image" src="https://github.com/user-attachments/assets/c7ba2313-d4a6-4c64-b662-d4d5b392c045" />


~~~
df.info()
df.describe()
~~~

<img width="931" height="699" alt="image" src="https://github.com/user-attachments/assets/892125e4-f1ca-42fd-8a15-f83db45971b8" />

~~~
df.dtypes
~~~

<img width="440" height="442" alt="image" src="https://github.com/user-attachments/assets/aa147179-ff89-4d70-8d6e-4f243de852f9" />

~~~
df.value_counts()
~~~

<img width="1323" height="469" alt="image" src="https://github.com/user-attachments/assets/73224e28-682b-46ba-a799-f84831afebf5" />

~~~
df["Age"].value_counts()
~~~

<img width="341" height="152" alt="image" src="https://github.com/user-attachments/assets/66ac9bfb-e0cc-489b-b300-6e179a69a5a1" />


~~~
df.shape
~~~

<img width="200" height="85" alt="image" src="https://github.com/user-attachments/assets/2d8a157b-eeb6-491f-b66b-3bd38aa677a9" />


~~~
df.nunique()
~~~

<img width="779" height="330" alt="image" src="https://github.com/user-attachments/assets/9079a1e8-e99c-4da8-8467-b152be95e5e7" />

~~~
sns.countplot(data=df,x="Survived")sns.countplot(data=df,x="Survived")
~~~

<img width="317" height="421" alt="image" src="https://github.com/user-attachments/assets/dfeaa017-54b0-4cb7-8de8-0946b5f7c304" />
~~~
df.Pclass.unique()
~~~

<img width="751" height="500" alt="image" src="https://github.com/user-attachments/assets/bd7cf3b0-31db-4c23-888d-9e589509358b" />

~~~
df.rename(columns={"Sex":"Gender"},inplace=True)
df
~~~

<img width="1233" height="535" alt="image" src="https://github.com/user-attachments/assets/fd166859-347d-468e-8b4e-6b58574d5966" />


~~~
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
~~~

<img width="918" height="582" alt="image" src="https://github.com/user-attachments/assets/964b82cb-2ac5-48c8-ac0d-1606b6249feb" />


~~~
df.boxplot(column="Age",by="Survived")
~~~

<img width="938" height="555" alt="image" src="https://github.com/user-attachments/assets/922c97fa-b0c8-4b6b-8b6f-1ec62d9b896e" />

~~~
sns.scatterplot(x=df["Age"],y=df["Fare"])
~~~

<img width="912" height="533" alt="image" src="https://github.com/user-attachments/assets/13697aa0-4956-4615-bf4e-e991e06995a5" />


~~~
fig,ax1=plt.subplots(figsize=(8,6))
plt=sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)
~~~

<img width="1049" height="634" alt="image" src="https://github.com/user-attachments/assets/739d4f60-a508-4c9f-9c9b-f4ad40cd9523" />

~~~
sns.catplot(col="Survived",x="Gender",hue="Pclass",kind="count",data=df)
~~~
<img width="1369" height="609" alt="image" src="https://github.com/user-attachments/assets/192bdc51-2325-4c3f-bbc5-aac2fed5cfba" />


~~~
sns.heatmap(df.select_dtypes(include=np.number).corr(),annot=True)
~~~

<img width="706" height="531" alt="image" src="https://github.com/user-attachments/assets/e80065e7-f313-4329-a8aa-58f74b0faad5" />




# RESULT
Thus the given exploratory data analysis has been verified successfully

      
