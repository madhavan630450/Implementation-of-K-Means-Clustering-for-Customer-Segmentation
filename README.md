# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MARIMUTHU MATHAVAN
RegisterNumber: 212224230153
```
``` python

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![image](https://github.com/user-attachments/assets/cf4e6c8b-7e32-417b-a447-12c402e18fb8)


![image](https://github.com/user-attachments/assets/473acbac-7652-42cf-b060-7aa05f4db8d4)


![image](https://github.com/user-attachments/assets/c2fe4840-e51b-4ede-8334-52ae2d8f3fb3)


![image](https://github.com/user-attachments/assets/9ec48e5c-5959-4585-9315-69a31dd0b2ce)


![image](https://github.com/user-attachments/assets/08543b09-8ffb-4dae-ba85-4d3a8e89d6f7)


![image](https://github.com/user-attachments/assets/ff0e5d2c-1444-4c1d-8df2-77bff73a4c57)

![image](https://github.com/user-attachments/assets/95260503-0abf-4b35-b58d-577b33eb11b0)

![image](https://github.com/user-attachments/assets/5a771fff-5948-4d14-9f7a-e25eba12bcce)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
