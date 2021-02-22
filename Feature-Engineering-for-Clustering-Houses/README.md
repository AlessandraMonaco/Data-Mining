# FEATURE ENGINEERING FOR CLUSTERING HOUSES

## Introduction
The goal of this notebook is to understand the impact of the **Feature engineering** process on the effectiveness of K-Means++ clustering.
We will first cluster data as they are, and then we will try to apply some Feature engineering techniques in order to build more reasonable clusters. 

The entire process is described in details in the report file.

## Dataset
The dataset that we used is the famous California House Pricing, available on Kaggle (see the references).

## Challenges
Clustering is not always a trivial task; it may be challenging, in particular:
- the number of clusters of your data is not knows: you have to find the optimal number of clusters using some heuristics, such as the *Elbow method* with distortion, inertia or silhouette score;
- it is not certain that your clusters will be meaningful, they will just mathematically optimize some metric: a deep data understanding (such as **Exploratory Data Analysis**) and **cluster analysis** (also visual) are often needed;
- in high dimensional spaces everything seems similar and it's much harder to group data into different clusters (*"curse of dimensionality"*): **dimensionality reduction** techniques are often helpful.

## References
Dataset : https://www.kaggle.com/camnugent/california-housing-prices
Elbow Method tutorial : https://www.geeksforgeeks.org/elbow-method-for-optimal-value-of-k-in-kmeans/
The book from which we got inspired : http://artoffeatureengineering.com/book.html
