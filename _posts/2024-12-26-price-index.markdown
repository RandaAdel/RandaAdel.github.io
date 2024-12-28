---
layout: post
title:  Construct Stock Market Indices
date:   2024-12-26 14:05:55 +0300
image:  /assets/images/blog/price-index.jpg
author: Randa Ahmed
tags:   Price Index
---

**If you, like me, prefer understanding the bigger picture, you may have come across terms such as price index, index funds, shares, and other interconnected financial concepts. In this discussion, I’ll begin with an exploration of the price index and its creation. I will be linking thoese concepts to mathematics and statistics to make them approachable for those without a finance background.**

<br><br><br>

***Company Shares:*** Shares are units of ownership in a company. When you buy shares, you own a small part of that company. Shares of multiple companies often make up the components of a price index. There are two types of shares to focus on: those that are publicly traded on the market and those that are privately held by institutions or insiders. 

***Free Floated Shares:*** Not all shares are avilible to purchase on the market as mentioned before. Free floated shares are only the shares that are available to purchase on the market. 

***Price Index:*** A price index is a tool commonly used to measure the performance of a group of financial assets—specifically stocks in this context—by tracking changes in their prices over time. This means that it is built using a dataset that have only dates and price changes over time. 

***Index Fund:*** An index fund is an investment vehicle that pools money to replicate the performance of a specific price index, such as the S&P 500 or the Russell Index. In simple terms, it allows you to invest in a group of stocks that make up an index you prefer. 

> For this post I will be using more than one company's stock prices over time to construct my price index. I will be using the FAANG companies (Facebook, Amazon, Apple, Netflix, and Google) to help me demonstrate how to weight the price change in each one of them to come up with one aggregated price index that tracks their compined performance if you decide to invest in them. 

***There two main things that I need to calculate to get a sense of the overall daily price change:***

<!-- 1- Price differences per company: 
    * I will be using share price data for 2023, to calculate price differences for FAANG. 
    * Then, I will take the difference between (this day's price - previous day's price). 
    * The result will be a 3 column data set per company that has date, price, and price difference  -->
<!-- 
<p style="text-align: justify;">
  <span style="float: right; margin-left: 10px;">
    <img src="/assets/images/blog/post-2.jpg" alt="Additional image description" style="max-width: 300px; height: auto;">
  </span>
  1- Price differences per company:
  <br>
  &emsp; • I will be using share price data for 2023 to calculate price differences for FAANG.
  <br>
  &emsp; • Then, I will take the difference between the current day’s price and the previous day’s price.
  <br>
  &emsp; • The result will be a 3-column data set for each company that includes the date, price, and price difference.
  <br>
</p>


<p style="text-align: justify;">
  <span style="float: right; margin-left: 10px;">
    <img src="/assets/images/blog/post-2.jpg" alt="Additional image description" style="max-width: 300px; height: auto;">
  </span>
  2- Free floated shares weight:
  <br>
  &emsp; • As I mentioned previously, there are shares that are owned by insiders and institutions. To get a representative weight of the index, I will subtract them from the overall company shares to calculate the free floated shares for each company.
  <br>
  &emsp; • To get the weight for a company, I will divide the company's free floated shares by the sum of the total free floated shares for the 5 companies.
  <br>
</p> -->

<!-- <p style="text-align: right;">
  <img src="/assets/images/blog/post-2.jpg" alt="Additional image description">
</p> -->

<!-- 2- Free floated shares weight: 
    * As I mentioned previously there are shares that are owned by insiders, and institutes. To get a representative weight of the index I will subtract them from 
    the overall company shares to get free floated shares for each company. 
    * To get the weight for a company, I will divide the company's free floated shares by the sum of the total free floated share for the 5 companies.  -->

<!-- <p style="text-align: right;">
  <img src="/assets/images/blog/post-2.jpg" alt="Additional image description">
</p> -->

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

<p class="content-block">
  <img src="/assets/images/blog/price-changge.jpg" alt="price change %">
  1- Price differences per company:
  <br>
  &emsp; • I will be using share price data starting from 1/1/2023 to 31/12/2023 for each FAANG.
  <br>
  &emsp; • Then, I will use the following formula to calculate the price change %
  <br>
  &emsp; (Price of the day/price of previous day) - 1
  <br>
  &emsp; • The result will be a 3-column data set for each company that includes the date, price, and price change %.
</p>

<p class="content-block">
  <img src="/assets/images/blog/post-2.jpg" alt="Additional image description">
  2- Free floated shares weight:
  <br>
  &emsp; • As I mentioned previously, there are shares that are owned by insiders and institutions. To get a representative weight of the index, I will subtract them from the overall company shares to calculate the free floated shares for each company.
  <br>
  &emsp; • To get the weight for a company, I will divide the company's free floated shares by the sum of the total free floated shares for the 5 companies.
</p>


<p style="text-align: justify;">
  3- Construct the FAANG index:
  <br>
  &emsp; • The first day will be my base 1000$ (the starting point I am comparing to throughout the year).  
  <br>
  &emsp; • Then, I will have 5 weights from step 2. For each company, I will multiply its weight by the difference in price column.
  <br>
  &emsp; • Finally, I will use the following formula to calculate the daily overall price index for the 5 companies combined: 
  <br>
  &emsp; (1 + the weighted price differences) * 1000$
  <br>
<br>
</p>

<!-- 
3- Construct the FAANG index:
    * The first day will be my base 1000$ (the starting point I am comparing to throught the year)   
    * Then, I will have 5 weights from step 2. For each company I will multiply its weight by the difference in price column
    * Finally, I will use the following formulla to calculate the daily overall price index for the 5 companies compined
             (1 + the weighted price differences) * 1000$

This price index I just constructed could tell me if I invested 1000$ on the first day of 2023, how much I will be making for each following day till the end of the year ..  -->

<p style="text-align: center;">
  <img src="/assets/images/blog/price-index-full-size.jpg" alt="Additional image description">
</p>