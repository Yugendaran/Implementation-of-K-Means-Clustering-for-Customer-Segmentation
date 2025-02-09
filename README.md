# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.
2. Initialize and print the Data.head(),data.info(),data.isnull().sum()
3. Import sklearn.cluster import KMeans
4. calculate the value of  KMeans Clusters.
5. plot the graph from Elbow method and find y_pred values .  
6. plot the graph from Customer Segments Graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: YUGENDARAN.G
RegisterNumber:  212221220063

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

print("data.head():")
data.head()

print("data.info():")
data.info()

print("data.isnull().sum():")
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range (1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
    
print("Elbow Method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans cluster value:")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred = km.predict(data.iloc[:,3:])
y_pred

print("Customer Segments Graph:")
data["cluster"] = y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="yellow",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/6e89e8cd-b661-4029-8c1d-5c6fc8421a72)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/2044fa08-4dec-418d-b6e4-4d754d69dc0b)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/a16f664f-d77e-4019-aac2-9d6f79605c0c)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/f185f86d-188e-4fa2-8fb4-4865845df531)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/a1eb4456-65b9-4507-a5f7-cca30b726fdc)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/9c3b2405-16d9-4c1a-a5e9-dcd8cf6a7e8a)

![image](https://github.com/Yugendaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135616/401de1d5-4102-4836-ace2-4ae4529bde6b)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
