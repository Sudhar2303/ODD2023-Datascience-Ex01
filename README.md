# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT

```
#importing the libraries
import pandas as pd
import numpy as ny
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/b7979902-26fa-4365-bef3-9dce02109b11)

```
#uploading the csv file
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/53cd6efe-b19c-427c-a5eb-18f3eb2cfc47)

```
#reading the csv file
df = pd.read_csv('Data_set.csv')
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/99a79413-4bb9-4bbb-a845-c721f62126fe)

```
#checking the null values
df.isnull().sum()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/f635e05e-dd56-4022-8298-06c19e3ae675)

```
#displaying the statistical values
df.describe()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/786ffd75-7293-4341-b9c0-ad5de3f4e340)

```
#counting the unique elements
df['show_name'].nunique()
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/52d95905-0d22-4d51-b33a-e0f8ebb72ea2)

```
# droping the rows which has null value because the column is full of unique elements so filling it is not an appropiate way.
#so instead of using fill it,I have used droping method
df = df.dropna(subset=['show_name'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/46a5a4ed-153c-4376-9751-8b0cdfe3a42a)

```
#counting the repeated value of this particular column
df['aired_on'].value_counts()
# there is some values which is repeated , so I have used filling method
df['aired_on'] = df['aired_on'].fillna(df['aired_on'].mode()[0])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/f2b35ad0-fdc0-4676-b77d-3f08607680ab)

```
#counting the repeated value of this particular column
df['original_network'].value_counts()
# there is some values which is repeated , so I have used filling method
df['original_network'] = df['original_network'].fillna(df['original_network'].mode()[0])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/7104b25f-f02e-469d-af2a-5276c1b3a3b5)

```
# rating is based on individual interest of a person rather than filling it i used to drop it
df = df.dropna(subset=['rating'])

```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/eef36078-5c2b-458f-8f86-251d91811a60)

```
# rank is a sensitive data ,so I dropping it
df = df.dropna(subset=['current_overall_rank'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/412d87a9-a54c-49bb-b500-e75d279a9978)

```
# watchers is not much sensitive data , so i filling it by meadian
df['watchers'] = df['watchers'].fillna(df['watchers'].median())
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/13e4a6a8-21d5-475e-ad58-ba51ded55a03)

```
#after data cleaning checking whether there is any null values
df.isnull().sum()
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/deae6802-1050-4f9f-b55d-6dabc3790c5c)

```
#uploading the csv file
from google.colab import files
uploaded = files.upload()
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/00bacdcb-5634-4670-9d39-33337c733af7)

```
#reading the csv file
df = pd.read_csv('Loan_data.csv')
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/faed5f3f-dbd3-449c-9c80-2911c8c4fa9d)

```
#checking the null values
df.isnull().sum()
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/1d172115-f1f1-4ab4-bec4-11ef5e54a2c0)

```
#Gender data can't be filled based on repeated or common values , so I am dropping it
df = df.dropna(subset=['Gender'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/73c8015e-df20-4899-af13-07baeec84828)

```
# dependents is a sentitive data ,so I am dropping it
df = df.dropna(subset=['Dependents'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/4fc8cfa3-8209-4998-953b-a5f9d5501549)

```
#Self_Employed is a sentitive data ,so I am dropping it
df = df.dropna(subset=['Self_Employed'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/e81bb3eb-75d1-4e77-9e6b-c1d9f7b47dfc)

```
#LoanAmount is a sentitive data,so I am  dropping it
df = df.dropna(subset=['LoanAmount'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/fc4e22b2-ee01-40a7-a9b4-fc4124630eef)

```
#Loan_Amount_Term is a sentitive data,so I am  dropping it
df = df.dropna(subset=['Loan_Amount_Term'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/e1ad84bf-5fd5-4078-b5de-92988b58edf4)

```
#Credit_History is a sentitive data,so I am  dropping it
df = df.dropna(subset=['Credit_History'])
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/ac9ff177-ca59-4e4b-9fe3-7ab0271b4042)

```
#after data cleaning checking whether there is any null values
df.isnull().sum()
```

![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex01/assets/133684710/30f8917a-d8d0-4d4a-9e7e-bed58d967ea7)

# RESULT:
Data cleaning for the given file has been done successfully 
