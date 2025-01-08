---
layout: post
title:  Bridging the Gap Between K-Means and K-Modes
date:   2025-01-07 08:00:00 +0300
image:  /assets/images/blog/cluster.jpg
author: Randa Ahmed
tags:   Clustering
---

**In today’s data-driven world, making sense of complex data types—both categorical and numerical—is crucial for effective decision-making. Enter the K-Prototypes algorithm: a powerful tool that bridges the gap between traditional clustering methods like K-Means and the challenge of mixed data types. K-Prototypes provides a way to identify meaningful patterns across these mixed attributes, unlocking insights that were previously difficult to access.**

<br>
***Data:*** The dataset that is related to direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be (or not) subscribed. I will be clustering the different customers to see if there is a potential in understanding the profiles of customers within the bank.

<p style="text-align: center;">
  <img src="/assets/images/blog/data-clustering.jpg" alt="Additional image description">
</p>

> decide on what to highlight later 

<style>
  .content-block {
    text-align: justify;
    overflow: hidden; /* Ensures the floated image does not break the layout */
    margin-bottom: 20px; /* Adds consistent spacing between blocks */
  }
  
  .content-block img {
    float: right;
    margin-left: 10px;
    max-width: 500px; /* Increase the maximum width of the image */
    height: auto; /* Maintain aspect ratio */
  }
</style>

<!-- ***Data:*** 
<p class="content-block">
  <img src="/assets/images/blog/data-clustering.jpg" alt="bank dataset">
  The dataset that is related to direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be (or not) subscribed. I will be clustering the different customers to see if there is a potential in understanding the profiles of customers within the bank.
  <br>
</p> -->


***Algorithm:*** Although K-Prototypes can handle both numerical and categorical variables, it depends on distances between the data points. This means that the features with the highest value ranges could be more inflencial on the algorithm and hence the need for the preprocessing steps.


<!-- ***Data:*** The dataset that is related to direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be (or not) subscribed. I will be clustering the different customers to see if there is a potential in understanding the profiles of customers within the bank.

***Algorithm:*** Although K-Prototypes can handle both numerical and categorical variables, it depends on distances between the data points. This means that the features with the highest value ranges could be more inflencial on the algorithm and hence the need for the preprocessing steps.

***Preprocessing:*** The numerical features in the dataset range from age with maximum of 80 years, and balance that has 100k maximum value. K-Prototypes depends on distance calculation and hence there is a need for normalisation or applying a transformation that allows the distance calcuation to be range agnostic. 

***Number of clusters:*** I used two measures to decide the number of clusters:  -->


<p style="text-align: center;">
  <img src="/assets/images/blog/cluster.jpg" alt="Additional image description">
</p>

rest of the article 