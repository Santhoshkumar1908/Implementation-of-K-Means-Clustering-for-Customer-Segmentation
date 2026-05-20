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
Developed by: DAWOOD M
RegisterNumber:  212225040055



import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("Mall_Customer.csv")

X = data.iloc[:, [3, 4]].values

kmeans = KMeans(n_clusters=5, random_state=0)

y_kmeans = kmeans.fit_predict(X)

plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50)

plt.scatter(kmeans.cluster_centers_[:, 0],
            kmeans.cluster_centers_[:, 1],
            s=200,
            marker='X')

plt.xlabel("Annual Income")
plt.ylabel("Spending Score")
plt.title("Customer Segmentation using K-Means")

plt.show()
~~~

## Output:


<img width="961" height="758" alt="Screenshot 2026-05-17 204430" src="https://github.com/user-attachments/assets/5785b770-8766-4693-b3df-484204185765" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
