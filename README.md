# Virtual Global Apprenticeship with TwoDotSeven
## Overview

TwoDotSeven is a revolutionary credit decisioning platform that is changing the way companies manage their working capital. We combine the power of technology and analytics with financing. Our objective is to leverage our strengths in machine learning and predictive analysis to provide you granular visibility into your working capital and leverage your receivables for getting access to capital.

## Business Objectives

This analysis can help the business minimize credit card default risk, increase revenue from interest and fees, and identify profitable customers for targeted marketing.

## Problem Statement

By analyzing the factors that influence the setting of a card limit, the bank can benefit in several ways. The analysis can provide valuable insights into customer segments and their creditworthiness, allowing the bank to make informed decisions when determining credit limits. This can help minimize the risk of default by setting appropriate credit limits for different customers based on their income, credit rating, and other relevant factors. Additionally, the analysis can identify potential high-value customers who may be eligible for higher credit limits, enabling the bank to tailor marketing strategies to attract and retain profitable customers. Ultimately, this data-driven approach can lead to improved risk management, targeted marketing efforts, and increased profitability for the bank.

## Dataset

It has 2 files in .csv format. The columns of files are as follows:

### Customer Details:

Name- name of the customer
<br>CustomerID- Unique ID of a customer
<br>Age - The age of the individual
<br>Marital Status- Status of the customer( Married/Unmarried/Widow/Separated/Divorced)
<br>Gender - Gender of the individual 
<br>Ethnicity - Ethnicity of the individual
<br>Education - Education level


### Card Details:

CustomerID- Unique ID of a customer 
<br>Income - Income of the individual (Lakhs)
<br>Limit  - Current credit card limit 
<br>Rating - Credit rating of the individual
<br>Cards - Number of cards the individual has
<br>Balance - Current account balance of the individual (Thousands)


# Data Cleaning and Visualization

Both the dataset has distinct columns except CustomerID and number of rows are same.
<br>Joining both the dataset for ease of analysis.
<br>Here Concat funtion keys are not used since, both the datasets have same order and number of CustomerIDs.
![image](https://github.com/nayankm/Capstone/assets/122444022/9c9cef4f-d070-4eec-ae2a-66de185a6f6d)


## There is no missing value in dataset
![image](https://github.com/nayankm/Capstone/assets/122444022/a9004443-0db3-413a-89ec-1b4908f3d282)

## No duplicate values
![image](https://github.com/nayankm/Capstone/assets/122444022/7da2968a-5ebb-4458-b6ea-f6f44a957abd)

## dataset data type
There are 6 categorical data and 6 numerical data
<br>![image](https://github.com/nayankm/Capstone/assets/122444022/e322dd75-c928-41eb-bbe7-ad60209d199d)

## Unique value in dataset
![image](https://github.com/nayankm/Capstone/assets/122444022/07d2cc83-457e-4f0f-ab1b-99dfc6edc51a)
<br>From the above data only "Age, Income, Limit, Rating, Balance" are quantitative continuous variables
<br>whereas "Cards, " is quantitative Discrete variables
<br>From above data CustomerID is removed from mode as there will be no repetative values and all values are unique
<br>From the data above "Marital Status, Gender, Ethnicity" are qualitative Nominal data
<br>where as "Education" is qualitative Ordinal data
<br>Above observation is done using data description given and finding value_count of the variables

## Statistic summary of numerical data
![image](https://github.com/nayankm/Capstone/assets/122444022/3c104203-fc8a-42c9-bb1e-04a1d120de87)
![image](https://github.com/nayankm/Capstone/assets/122444022/2ed0783c-f988-4772-8071-19c68cf2b048)
<br>From the statistics summary, we can infer the below findings :
<br>1. Card holders age is between 25 - 86 years. Most of the card holders are mid-age to senior citizen.
<br>2. Income-wise most card holders are in 20-60Lakhs cap. However, there is group earning higher income which must be target separately for more service and facilities.
<br>3. Card limits mostly lies between 27 - 56Lakhs. There are card holder with 1 Crores Limit need to reviewed with their spending.
<br>4. Most of card holders are not having good ratings ranging between 200 - 400. However, there are card holders with excellent rating to be consider for Limit update.
<br>5. Number of Card holders has mostly 2-4 cards.
<br>6. Most of the card holders have low balance.

## Statistic summary of categorical data
![image](https://github.com/nayankm/Capstone/assets/122444022/efbdb7eb-0dce-4770-aacf-b61b8e4e70eb)
![image](https://github.com/nayankm/Capstone/assets/122444022/6f9c1c57-aa31-4502-89fe-4a4509e7301f)
![image](https://github.com/nayankm/Capstone/assets/122444022/00a1a02f-7f55-44fe-b9fd-ab3d0169ab2a)
<br>From the statistics summary, we can infer the below findings :
<br>1. Similar card holder names are existing where Claude appears 9 times.
<br>2. Dataset data is unique as each card holder has unique Customer ID.
<br>3. Most of the customer are Unmarried, Female and from Caucasian.
<br>4. Most of the customer are highly educated holding Master degree.

## The measures of central tendency for all the variables
![image](https://github.com/nayankm/Capstone/assets/122444022/a1e0c89b-f37c-479c-8b8b-f9d49f2ba484)

## Outliers in dataset
![image](https://github.com/nayankm/Capstone/assets/122444022/9647f3a2-3560-481c-ba50-4ff3549db3d1)
<br>Number of Cards, Age and Balance have no outliers
<br>Income, Limit and Rating have outliers

### Number of outlier in Income
number of outliers: 3036
<br>max outlier value: 160.231
<br>min outlier value: 114.232<br>
Income outliers are almost 9% of total data and should be consider for EDA. There are individual with higher income.

### Number of outlier in Limit
number of outliers: 895
<br>max outlier value: 11200
<br>min outlier value: 10063<br>
<br>Limit outliers are 2.7% of dataset and not too much far from upper limit, should be consider for EDA.

### Number of outlier in Rating
number of outliers: 571
<br>max outlier value: 805
<br>min outlier value: 677<br>
<br>Rating outliers are 1.8% of dataset and are above upper limit. Higher rating is not unusual and should be consider for EDA.<br>

## Hence, the dataset is clean and fine for analysis.

# Exploratory Data Analysis









