# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Tirupathi Jayadeep
RegisterNumber: 212223240169
*/


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
# Head()
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/5fd7ff3c-bb7e-4c7b-9fda-121a140881d6)

# Info()
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/aec32a4c-3c19-44b7-a402-1006900bc8a5)

# isnull.sum()
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/9a344f66-5cf0-49c8-8451-e1eac5a22ece)

# Elbow Method
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/cb9b8296-89c9-48b6-8c2c-af1504ef8eef)

# Fitting the no. of clusters
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/8bd21732-def0-4944-9dd7-046be44f5e9d)

# Prediction of Y
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/fd66a326-e4f3-4469-8f83-a1f786211753)

# Customer Segments
![image](https://github.com/23004426/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144979327/9db0da84-6bc1-441a-8ffc-9e120b9e398f)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
