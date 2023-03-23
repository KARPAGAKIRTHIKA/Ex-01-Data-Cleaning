# Ex-01_DS_Data_Cleansing
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE
import pandas as pd
df=pd.read_csv("/content/Loan_data.csv")
print(df)
df.head(10)
df.info()
df['Loan_ID']=df['Loan_ID'].fillna(df['Dependents'].mode()[0])
df['Dependents']=df['Dependents'].fillna(df['Dependents'].mode()[0])
df['Education']=df['Education'].fillna(df['Dependents'].mode()[0])
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df['Gender']=df['Gender'].fillna(df['Gender'].mode()[0])
df.head()

df['ApplicantIncome']=df['ApplicantIncome'].fillna(df['ApplicantIncome'].mean())
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].mean())
df['LoanAmount']=df['LoanAmount'].fillna(df['LoanAmount'].mean())
df.head()

df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].median())
df.head()

df.info()
df.isnull().sum()

# OUPUT

## DATA

![image](https://user-images.githubusercontent.com/103020162/227207328-75a1a32b-0561-409a-9f1e-c24c9e2b8f50.png)

# NON NULL BEFORE 

df.info

![image](https://user-images.githubusercontent.com/103020162/227207797-9b5b17ff-4af0-4e3a-8e34-5371e573b3c0.png)


## MODE

![image](https://user-images.githubusercontent.com/103020162/227206920-67c7c7a5-1b18-439d-80d4-6a691a14c57c.png)


## MEAN

![image](https://user-images.githubusercontent.com/103020162/227208146-1196658b-980f-4852-b103-06b8b4e4b2fb.png)


## MEDIAN

![image](https://user-images.githubusercontent.com/103020162/227208580-7b0179dd-40c2-4b73-aefe-2b2cf7ab409d.png)

## NON NULL AFTER

df.info()

![image](https://user-images.githubusercontent.com/103020162/227209142-cca601d9-958e-4c24-8773-9d1dda92e3f7.png)


df.isnull().sum()

![image](https://user-images.githubusercontent.com/103020162/227209395-9993b4e5-d19e-48af-aa34-6eba5cf37e9b.png)


## RESULT:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.
