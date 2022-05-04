# A-B-Testing-in-Python
A Python-based project that analyses the data of an e-commerce website to test if they should implement the new page, or keep the old page.

## Introduction

A/B tests are very commonly performed by data analysts and data scientists. 
In this project, we will be working to understand the results of an A/B test run by an e-commerce website. Our goal in this project is to help the company understand if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.

## Table of Contents
The contents of our project notebook.
### Importing essential libraries
Importing required libraries like numpy, pandas, seaborn, random etc.
### Reading the Dataset
This dataset is provided by Udacity under the Udacity-Data-Analysis-Nanodegree program. It is named ab_test.csv. It contains 294478 rows and 5 columns namely,
 
**user_id** : User Id of the person who accessed the web page.

**timestamp** : Time at which the user accessed the web page.

**group** : The group of users (‘control’ and ‘treatment’).

**landing_page** : The landing page the user gets (‘new_page’ and ‘old_page’)

**converted** : Whether the users want to convert or not.

### Data Preprocessing

Cleaning the data to further analyse and get insights.

### A/B Test
Background Information to help you better understand the results :

In this case, we will take the difference of conversion rates of the pages as the metric of our A/B Testing.

We will calculate p-value, if p-value is really small, less likely to observe the statistic in the null , more likely from the alternative. p-value is large you will end up staying with the null hypothesis as your choice.

**Type 1 error threshold is alpha**

If **p <= alpha** , reject the null , choose H1
If **p > alpha** , fail to reject the null, choose H0
If you want to assume that the old page is better unless the new page proves to be definitely better at a Type I error rate of 5%, the null and alternative hypotheses be

**H0 : p(new)-p(old) <= 0 old has better conversion**

**H1 : p(new)-p(old) > 0 new has better conversion**

where **p(new)** and **p(old)** are the **conversion rates**.

Assume under the null hypothesis, and both have "true" success rates equal to the converted success rate regardless of page - that is and are equal. Furthermore, assume they are equal to the converted rate in ab_data.csv regardless of the page.

Use a sample size for each page equal to the ones in ab_data.csv.

Perform the sampling distribution for the difference in converted between the two pages over 10,000 iterations of calculating an estimate from the null.

#### Steps
1. Compute the observed difference between the metric, p_new for treatment group and p_old for control group.
2. Simulate the sampling distribution for the difference of the conversion rate.
3. Use this sampling distribution to simulate the distribution under null hypothesis, by creating a random normal distribution centered at 0 with the same size and spread.
4. Compute the p-value by finding the difference of the conversion rates from the null distribution that are greater than our observed difference.
5. Use this p-value to determine the statistical significance of our observed difference.
6. 
### Conclusion
Drawing conclusion of the test we run.
