---
layout: post
title:  Conformal Prediction (part 1) 
date:   2025-08-29 12:05:55 +0300
image:  /assets/images/blog/cp-p1-2-re.jpg
author: Randa Ahmed 
tags: conformal prediction 
---

**"A model producing predictions is like making promises, It is all about trust, but what if we can quantify the uncertainty? This is how I was first interested in understanding what conformal predictions are all about"**

<br><br><br>

***When would quantifying the uncertainty would be possibly useful?***
  &emsp; 1- Claim predictions when we need to priorities the cases which we want to handle first within a pool of predicted fraudulent claims.
<br>
  &emsp; 2- When we have transactions that are hard to classify within an algorithm and we need a method to flag them so we can ask the user to classify them.
<br>
  &emsp; 3- Demand forecasting when we need a certain confidence in the predictions to be able to justify our production.

***Why can't we use model probabilities as our measure of uncertainty:***
Probabilities are not calibrated. If probabilities are calibrated then among all classification with 95% probability there should be 95% true values. This is normally not the case in our model outputs. 
<br>

***How does conformal predictions solve the problem then?***
By taking the uncertain probabilities and turn it into rigorous scores that has a probabilistic guarantee that it covers the true outcome. It turns prediction points into prediction regions. 
<br>

***There are some main advantages that come with conformal predictions that make them valuable:***
<br>
  &emsp; • They are distribution free: No assumption about the data distribution is made which is normally not the case in other approaches. 
  <br>
  &emsp; • Model agnostic: They can be applied with any type of model and with any data types.
  <br>
  &emsp; • Coverage guarantee: The conformal sets or conformal intervals come with a percentages of statistical guarantee of covering the true outcome. 
<p style="text-align: center;">
  <img src="/assets/images/blog/cp-p1-1-re.jpg" alt="Additional image description">
</p>

To conclude the promise that comes with conformal predictions, at least in the context of classification, is that you will be getting your classes with a certainty level associated to them which will help in quantifying the statistical uncertainty of the predictions we are looking at. 
<p style="text-align: center;">
  <img src="/assets/images/blog/cp-p1-3.jpg" alt="Additional image description">
</p>