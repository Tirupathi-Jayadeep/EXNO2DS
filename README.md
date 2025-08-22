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


import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df


<img width="1332" height="447" alt="image" src="https://github.com/user-attachments/assets/b8566b57-1d97-49a1-af01-50213ce9a618" />


df.shape


<img width="242" height="37" alt="image" src="https://github.com/user-attachments/assets/1a8a4533-01a0-4c87-9b7b-95df75cea527" />


df.set_index("PassengerId", inplace=True)
df


<img width="1313" height="477" alt="image" src="https://github.com/user-attachments/assets/343f1404-2b4e-4269-a35f-c83ec1d96a9b" />


df.nunique()

df['Sex'].value_counts()

df.Pclass.unique()

df.Survived.unique()


<img width="992" height="617" alt="image" src="https://github.com/user-attachments/assets/8b4a21c9-5ff1-452c-849f-fae7117a8ca5" />


df.rename(columns={"Sex" : "Gender"},inplace=True)
df


<img width="1311" height="472" alt="image" src="https://github.com/user-attachments/assets/4aad5abd-5e6f-41ec-9d91-cc64b68d48ad" />


import seaborn as sns
sns.countplot(data=df)


<img width="932" height="558" alt="image" src="https://github.com/user-attachments/assets/13ffb85c-c8c4-407e-a12c-ac18e57c84cd" />


sns.countplot(x="Survived",hue="Gender",data=df)


<img width="897" height="577" alt="image" src="https://github.com/user-attachments/assets/b4336268-68d0-412a-9dcd-5b310e9a3b50" />


sns.catplot(x="Survived",hue="Gender",data=df,kind="count")


<img width="683" height="521" alt="image" src="https://github.com/user-attachments/assets/29eb5326-75fd-47d0-a821-3a06a6244687" />


sns.catplot(x="Survived", hue="Gender", data=df,kind="box")


![WhatsApp Image 2025-08-22 at 15 57 50_01d410e6](https://github.com/user-attachments/assets/e9f19bfc-fb08-49b1-bc0e-6c7cf9c4266e)


sns.boxplot(data=df)


<img width="738" height="446" alt="image" src="https://github.com/user-attachments/assets/7cadcb1e-30ec-48a6-8d77-43561c393811" />


df.boxplot(column="Survived",by="Gender")


<img width="728" height="490" alt="image" src="https://github.com/user-attachments/assets/af055de8-87c5-4a8f-94a0-df228c832af1" />


sns.scatterplot(data=df)


<img width="709" height="459" alt="image" src="https://github.com/user-attachments/assets/46cafe12-df94-4c80-9832-80b6275a55aa" />


sns.scatterplot(x=df['Age'],y=df['Fare'])


<img width="683" height="460" alt="image" src="https://github.com/user-attachments/assets/ff914d63-5d2f-402e-b1d1-0729d61b60e9" />


sns.jointplot(x='Age',y='Fare',data=df,kind='kde')


<img width="695" height="576" alt="image" src="https://github.com/user-attachments/assets/c053a478-85ba-4a9f-82d5-ff19b5ee9615" />


sns.jointplot(x='Age',y='Fare',data=df,kind='hist')


<img width="695" height="582" alt="image" src="https://github.com/user-attachments/assets/be7b5a17-1e95-4c8b-930d-4793661f4b9f" />


sns.pairplot(data=df)


<img width="670" height="638" alt="image" src="https://github.com/user-attachments/assets/741ef848-487f-4c01-b6b6-8e2905608e3e" />


corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)


<img width="634" height="452" alt="image" src="https://github.com/user-attachments/assets/bf1dfcad-2904-43c3-b4b9-24d7d63c24c3" />


# RESULT
Thus,the Exploratory Data Analysis on the given data set was performed successfully.
