# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary libraries.
   
2.Read the csv file.

3.Make necessary preprocessing.

4.Convert all the object data type to categorical data.

5.Now convert the categorial data to numbers representation using cat.codes

6.Define the feature and target variable.

7.Split the data as training and testing data.

8.Train the model using LogisticRegression().

9.Predict and test the accuracy of the model.


## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: SANDEEP S
RegisterNumber: 212223220092 
*/
```
```
  import pandas as pd
  import numpy as np
  import matplotlib.pyplot as plt
  
  data=pd.read_csv("/content/Placement_Data.csv")
  data.info()
  
  data=data.drop('sl_no',axis=1)
  data
  
  data["gender"]=data["gender"].astype('category')
  data["ssc_b"]=data["ssc_b"].astype('category')
  data["hsc_b"]=data["hsc_b"].astype('category')
  data["hsc_s"]=data["hsc_s"].astype('category')
  data["degree_t"]=data["degree_t"].astype('category')
  data["workex"]=data["workex"].astype('category')
  data["specialisation"]=data["specialisation"].astype('category')
  data["status"]=data["status"].astype('category')
  data.dtypes
  
  data["gender"]=data["gender"].cat.codes
  data["ssc_b"]=data["ssc_b"].cat.codes
  data["hsc_b"]=data["hsc_b"].cat.codes
  data["hsc_s"]=data["hsc_s"].cat.codes
  data["degree_t"]=data["degree_t"].cat.codes
  data["workex"]=data["workex"].cat.codes
  data["specialisation"]=data["specialisation"].cat.codes
  data["status"]=data["status"].cat.codes
  data
  
  data=data.drop(['salary'],axis=1)
  data
  
  x=data.iloc[:,:-1].values
  y=data.iloc[:,-1]
  
  from sklearn.model_selection import train_test_split
  x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)
  
  from sklearn.linear_model import LogisticRegression
  model=LogisticRegression(max_iter=1000)
  model.fit(x_train,y_train)
  y_pred=model.predict(x_test)
  y_pred
  
  from sklearn.metrics import accuracy_score
  acc=accuracy_score(y_pred,y_test)
  acc
  
  model.predict([[0,85,0,92,0,2,75,2,1,1,0,0]])
```

## Output:
![image](https://github.com/user-attachments/assets/43c65107-031e-4377-82d0-703f0d615fb2)

![image](https://github.com/user-attachments/assets/e9cfed27-1f0e-44b7-9bf3-307e7c007191)
![image](https://github.com/user-attachments/assets/b42e8e61-6f09-4852-8d31-55893978ccdc)
![image](https://github.com/user-attachments/assets/d69acb8c-65d4-4081-8ddc-888509eb4950)
![image](https://github.com/user-attachments/assets/8b76795a-c66c-4b63-8708-26f61f9eee5a)
![image](https://github.com/user-attachments/assets/33cb03b6-3cc5-46a8-97db-2a9bb12412f8)
![image](https://github.com/user-attachments/assets/b244cc86-9376-447f-aba4-a1fc6df198e8)
![image](https://github.com/user-attachments/assets/2f6dc7f2-ebc3-42ac-9577-c34b9477754a)   ![image](https://github.com/user-attachments/assets/aba26ad8-8b10-4088-8c3d-2e2857542dda)



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
