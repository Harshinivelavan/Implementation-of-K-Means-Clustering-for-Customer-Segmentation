# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the Cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HARSHINI.V
RegisterNumber: 212224040109 
*/


import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")

```

## Output:


![Screenshot 2025-05-17 120724](https://github.com/user-attachments/assets/8651fdc7-f097-453a-b858-a8986f1f5493)

![Screenshot 2025-05-17 120732](https://github.com/user-attachments/assets/475e534b-b80c-494e-9f5b-7623177f018a)

![Screenshot 2025-05-17 120738](https://github.com/user-attachments/assets/57b520ff-0493-4aaf-85c7-207984d27ee5)

![Screenshot 2025-05-17 120817](https://github.com/user-attachments/assets/527dd06b-0d60-4266-82da-2dba349d3682)

![Screenshot 2025-05-17 120824](https://github.com/user-attachments/assets/05bceeb3-f3f7-4c11-9fbc-ff82dbd88326)

![Screenshot 2025-05-17 120829](https://github.com/user-attachments/assets/82fef4e8-827f-4b9f-8d83-6cdae6ada6f7)

![Screenshot 2025-05-17 120839](https://github.com/user-attachments/assets/a3c3f2bc-fe8d-4597-9e84-d506283a2111)









## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
