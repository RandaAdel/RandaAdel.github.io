---
layout: post
title:  Conformal Prediction (part 1) 
date:   2025-08-29 12:05:55 +0300
image:  /assets/images/blog/cp-p1-2-re.jpg
author: Randa Ahmed 
tags: conformal prediction 
---

**"A model producing predictions is like making promises, it’s all about trust. But in practice, promises in machine learning are fragile, because we rarely know how reliable they really are. That sparked my curiosity: what if we could not only make predictions but also quantify the uncertainty behind them? This led me to explore conformal prediction, a framework that provides rigorous, distribution-free guarantees on prediction reliability. The more I learned, the more I realized how powerful it is to shift the conversation from ‘What is the answer?’ to ‘How confident are we in this answer?’ That perspective makes models not just smarter, but also safer and more transparent which is crucial when deploying AI."**

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

***What is the recipe for conformal prediction then?***
<br>
  &emsp; • **Training:**
    <br>
    &emsp;&emsp; 1. Split the data into training and calibration.
    <br>
    &emsp;&emsp; 2. Train model on training data.
  <br>
  &emsp; • **Calibration:**
  <br>
    &emsp;&emsp; 1. Compute uncertainty score (non conformity score) for calibration data.
    <br>
    &emsp;&emsp; 2. Sort the scores from certain to uncertain.
    <br>
    &emsp;&emsp; 3. Decide on a confidence level α (α=0.1 means 90% coverage).
    <br>
    &emsp;&emsp; 4. Find the quantile q̂ where 1-α (multiplied with a fintie sample correction) of non-conformity score are smaller. 
  <br>
  &emsp; • **Prediction:**
  <br>
    &emsp;&emsp; 1. Compute the non conformity score for the new data.
    <br>
    &emsp;&emsp; 2. Pick all y's that produce score below q̂.
    <br>
    &emsp;&emsp; 3. These y's form your prediction set or interval.
  <br>
<!-- ***What is the recipe for conformal prediction then?***
<br>
  &emsp; • Training: bla bla.
  <br>
  &emsp; • Calibration: bla bla.
  <br>
  &emsp; • Prediction: bla bla.
  <br> -->

***How to interpret prediction regions and coverage?***
If the desired coverage is 90% (α=0.1), we would expect 90% of the prediction regions to cover the true outcome. This doesn't mean that each individual predioction region has a 90% probablity of conraining the true outcome. If you have 10 prediction regions, you would expect 9 out of the 10 to cover the true class. 
<br>