# EX-05 FEATURE GENERATION
### Aim:
To read the given data and perform Feature Generation process and save the data to a file.
### Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
### Algorithm:
- Step1: Read the given Data.
- Step2: Clean the Data Set using Data Cleaning Process.
- Step3: Apply Feature Generation techniques to all the feature of the data set.
- Step4: Save the data to the file.
### Program:
```
Developed By: Shabreena Vincent
Register No: 212222230141
```
- Encoding.csv:
  ```Python
  import pandas as pd
  df=pd.read_csv('Encoding Data.csv')
  df.head()
  df['ord_2'].unique()
  from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
  climate = ['Cold','Warm','Hot']
  en= OrdinalEncoder(categories = [climate])
  df['ord_2']=en.fit_transform(df[["ord_2"]])
  df
  le = LabelEncoder()
  df['Nom_0'] = le.fit_transform(df[["nom_0"]])
  df  
  from category_encoders import BinaryEncoder
  be = BinaryEncoder()
  data = be.fit_transform(df['bin_1'])
  df = pd.concat([df,data],axis=1)
  df
  be = BinaryEncoder()
  data = be.fit_transform(df['bin_2'])
  df = pd.concat([df,data],axis=1)
  df
  ```
  - Output:
    - Initial data:<br>
      <img height=15% width=35% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/b46c2673-6e5f-4ecb-92b9-7a380b37908a">
    - Unique data:<br>
      <img height=5% width=40% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/27ab6d79-680e-466f-8d6b-a03f4508397c">
    - Original Encoder:<br>
      <img height=15% width=60% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/37731dd9-1302-4dde-84ac-434dd52a4945">
    - Label Encoder:<br>
      <img height=15% width=60% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/e9fd27ca-93ba-47a7-9b69-8ac0c1bc06fe">
    - Binary Encoder:<br>
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/adffa9d7-4a6a-4de2-827e-2f41bd7560ee"><img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/3a6f8f34-7028-4d2f-9d84-cce7b2853d2a">


- Data.csv:
  ```Python
  import pandas as pd
  df1 = pd.read_csv("data.csv")
  df.head()
  df['Ord_1'].unique()
  from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
  climate = ['Cold','Warm','Hot','Very Hot']
  en= OrdinalEncoder(categories = [climate])
  df['Ord_1']=en.fit_transform(df[["Ord_1"]])
  df.head()
  df['Ord_2'].unique()
  cl = ['High School','Diploma','Bachelors','Masters','PhD']
  en= OrdinalEncoder(categories = [cl])
  df['Ord_2']=en.fit_transform(df[["Ord_2"]])
  df.head()
  le = LabelEncoder()
  df['City'] = le.fit_transform(df[["City"]])
  df.head()
  from category_encoders import BinaryEncoder
  be= BinaryEncoder()
  data= be.fit_transform(df['bin_1'])
  df= pd.concat([df,data],axis=1)
  df.head()
  from category_encoders import BinaryEncoder
  be = BinaryEncoder()
  data1 = be.fit_transform(df['bin_2'])
  df= pd.concat([df1,data1],axis=1)
  df  
  ```
  - Output:
    - Initial data:<br>
      <img height=15% width=55% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/9015df9d-e8a6-4267-acc6-80179e575384">
    - Unique data:<br>
      <img height=5% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/7355573d-0c9a-4699-aa3b-21da0ea34136">
    - Original Encoder:<br>
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/55a3e602-a104-439e-8f7a-d5131b41af49"><img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/8d34dec8-2bf1-4be4-a017-53a3f66567d9">
    - Label Encoder:<br>
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/aef111d5-ed57-48d0-bf06-ecb4bba9dc25">
    - Binary Encoder:<br>
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/67b4b397-d891-48b3-9b02-7bd67d6e192f">
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/9211db6c-364d-4310-8c47-38a151d95d7f">

- BMI.csv:
  ```Python
  import pandas as pd
  df2 = pd.read_csv("/content/bmi.csv")
  df2.head()
  be = BinaryEncoder()
  data2 = be.fit_transform(df2['Gender'])
  df2  = pd.concat([df2,data2],axis=1)
  df2
  df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
  df2
  ```
  - Output:
    - Initial data:<br>
      <img height=20% width=45% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/532fcf97-f3bc-424e-9bac-e7157fc98ba8">

    - Binary Encoder:<br>
      <img heeight=20% width=70% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/d09bc5ef-7b73-4ed9-b21a-57535b9ceaf2">

    - Dummies:<br>
      <img heeight=20% width=100% src="https://github.com/ROHITJAIND/EX-05-FEATURE-ENCODING-SCALING/assets/118707073/071fdcea-6db7-48d7-bf64-3dcca16864f5">

### Result:
The Feature Generation process was performed and saved the data to a file.
