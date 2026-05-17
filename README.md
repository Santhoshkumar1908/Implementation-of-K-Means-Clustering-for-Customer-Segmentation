# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments
## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SANTHOSHKUMAR J
RegisterNumber:  212225230249

```
~~~
from google.colab import drive
drive.mount('/content/drive')
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("drive/MyDrive/ML/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No_of_Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:, 3:])
y_pred
data["cluster"] = y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")
~~~

## Output:
<img width="932" height="322" alt="Screenshot 2026-05-17 204334" src="https://github.com/user-attachments/assets/d4521acc-cb3b-4bf9-bc36-aee785c68c34" />

<img width="668" height="363" alt="Screenshot 2026-05-17 204342" src="https://github.com/user-attachments/assets/bab3e7fb-c0fa-4f99-bfe3-3ec7490893a3" />

<img width="387" height="386" alt="Screenshot 2026-05-17 204350" src="https://github.com/user-attachments/assets/539329b5-ae24-4ea7-8896-57bbdad17e3a" />

<img width="1059" height="777" alt="Screenshot 2026-05-17 204409" src="https://github.com/user-attachments/assets/b6f673b2-8125-476b-b42a-f0d3a29e6448" />

<img width="974" height="307" alt="Screenshot 2026-05-17 204417" src="https://github.com/user-attachments/assets/035d1bcd-b3d0-4141-884a-c7aff568d4ed" />

<img width="961" height="758" alt="Screenshot 2026-05-17 204430" src="https://github.com/user-attachments/assets/5785b770-8766-4693-b3df-484204185765" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
