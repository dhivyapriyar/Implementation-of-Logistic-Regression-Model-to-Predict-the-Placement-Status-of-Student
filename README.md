## EX-4 Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:

To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:

1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the required packages and print the present data.

2.Print the placement data and salary data.

3.Find the null and duplicate values.

4.Using logistic regression find the predicted values of accuracy , confusion matrices.

5.Display the results.


## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Dhivyapriya.R
RegisterNumber: 212222230032
*/
```
```
import pandas as pd
data=pd.read_csv("/content/Placement_Data.csv")
data.head()
```
```
data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
data1.head()
```
```
data1.isnull()
```
```
data1.duplicated().sum()
```
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
data1
```
```
x=data1.iloc[:,:-1]
x
```
```
y=data1["status"]
y
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
```
```
from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred
```
```
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
accuracy
```
```
from sklearn.metrics import classification_report
classification_report1=classification_report(y_test,y_pred)
print(classification_report1)
```
```
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

## Output:

## Placement data
![Screenshot 2024-03-12 093935](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/f9ff90a4-51d4-4e14-b5ca-feb2d32689e5)

## Salary data
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/41e00850-801b-4638-a53d-18385076a039)

## Checking the null function
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/50d1f15b-9686-440c-8fd1-de688e938a96)

## Data duplicate
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/4cc78ffb-511b-4556-a6d6-be3de77cbf29)

## Print data
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/499105b3-f315-4688-bcdd-ec29b9d69e04)

## Data status
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/436462b2-5adf-4545-917d-166899d0e9c2)

## y prediction array
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/8624b5ea-2e07-4228-985e-b7513662af4c)

## Accuracy value
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/1f276fdd-dde1-4612-91fe-00fc53520a7c)

## Classification report
![image](https://github.com/dhivyapriyar/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/119477552/da22f7df-2d32-4dab-96f4-5cb0460731f4)

## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
