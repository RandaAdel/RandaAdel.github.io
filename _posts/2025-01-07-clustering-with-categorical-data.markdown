---
layout: post
title:  Bridging the Gap Between K-Means and K-Modes
date:   2025-01-07 08:00:00 +0300
image:  /assets/images/blog/cluster.jpg
author: Randa Ahmed
tags:   Clustering
---

**In today’s data-driven world, making sense of complex data types—both categorical and numerical—is crucial for effective decision-making. Enter the K-Prototypes algorithm: a powerful tool that bridges the gap between traditional clustering methods like K-Means and the challenge of mixed data types. K-Prototypes provides a way to identify meaningful patterns across these mixed attributes, unlocking insights that were previously difficult to access.**

<br><br><br>
***Data:*** The dataset that is related to direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be (or not) subscribed. I will be clustering the different customers to see if there is a potential in understanding the profiles of customers within the bank.

<p style="text-align: center;">
  <img src="/assets/images/blog/data-clustering.jpg" alt="Additional image description">
</p>

***Algorithm:*** For each new data point, K-Prototypes calculates a distance for the numerical features and another distance for the categorical features. The data point is then assigned to the cluster with the least combined distance to its centroid.

The numerical distance is computed as the Euclidean distance between the data point's numerical values and the centroid's numerical values. The categorical distance is calculated as the number of mismatches (differences) between the data point's categorical values and the centroid's categorical mode (most common value).

***Preprocessing:*** In the dataset, the numerical features include age, with a maximum value of 80 years, and balance, with a maximum value of 100,000. Since K-Prototypes relies on distance calculations, it is crucial to normalise or apply a transformation to the numerical features. This ensures that the distance computation is not biased by the differences in the scale or range of the features, allowing the clustering process to be range-agnostic and fair to all attributes.

<p style="text-align: center;">
  <img src="/assets/images/blog/transformations1_resized.jpg" alt="Additional image description">
</p>

<p style="text-align: center;">
  <img src="/assets/images/blog/post-1.jpg" alt="Additional image description">
</p>

<!-- <p style="text-align: center;">
  <img src="/assets/images/blog/transformations2_resized.jpg" alt="rest of transformations">
</p> -->

***Important parameters:*** In this section I will list the important parameters in K-Prototypes and how they affect the fitting process of the algorithm: 
  <br>
  &emsp; • n_clusters: The number of clusters to generate 
  <br>
  &emsp; • init: There are two centroid initialisation methods for K-Prototypes: 'Cao' and 'Huang'. The Huang method selects 12 centroids randomly, providing a stochastic   &approach. In contrast, the Cao method is more deterministic, selecting 12 centroids in a manner that maximises the distances between them.
  <br>
  &emsp; • n_init: Specifies how many times the algorithm will run to select the most optimal centroids. This parameter is particularly important for the 'Huang' method, as it relies on random assignment of centroids, unlike the 'Cao' method. The default value is 10, meaning the initialisation process will be repeated 10 times to enhance the chances of finding the best centroids.
  <br>
  &emsp; • max_iter: Specifies the maximum number of iterations the algorithm will run for each initialization attempt before calculating the final cost.
</p>


<!-- ***Data:*** The dataset that is related to direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be (or not) subscribed. I will be clustering the different customers to see if there is a potential in understanding the profiles of customers within the bank.

***Algorithm:*** Although K-Prototypes can handle both numerical and categorical variables, it depends on distances between the data points. This means that the features with the highest value ranges could be more inflencial on the algorithm and hence the need for the preprocessing steps.

***Preprocessing:*** The numerical features in the dataset range from age with maximum of 80 years, and balance that has 100k maximum value. K-Prototypes depends on distance calculation and hence there is a need for normalisation or applying a transformation that allows the distance calcuation to be range agnostic. 

***Number of clusters:*** I used two measures to decide the number of clusters:  -->

