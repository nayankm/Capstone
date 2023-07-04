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
## EDA Univariate Analysis
<br>In the below fig, histogram and box plot is used to show the pattern of the variables, as some variables have skewness and outliers.
<br>All the variables "Age, Income, Limit, Rating, Cards and Balance" are positively skewed distribution.<br>
![image](https://github.com/nayankm/Capstone/assets/122444022/e578d492-dee4-4cdb-9ca2-3133437c0681)
![image](https://github.com/nayankm/Capstone/assets/122444022/92e9025d-949c-4aa5-9465-35c57e5dc1d5)
![image](https://github.com/nayankm/Capstone/assets/122444022/36c25f48-fd13-4a21-bdfb-17026534b896)
![image](https://github.com/nayankm/Capstone/assets/122444022/3163a5ef-5750-4652-bd5a-4320fe297c9c)
![image](https://github.com/nayankm/Capstone/assets/122444022/0b0f794a-2380-416e-8223-fabb1132db4f)
![image](https://github.com/nayankm/Capstone/assets/122444022/10e92a44-8951-4dd6-a17c-964a4b5b8076)
![image](https://github.com/nayankm/Capstone/assets/122444022/801dafc7-7d5c-4ae6-b5a7-577e1c9b7600)
<br>Above data shows that Income data is higly positive skewed. That does not seems to be swaying analysis and may rather help in analysing high income card holders.

## Performing correlation analysis to identify factors that are correlated with card limit.
![image](https://github.com/nayankm/Capstone/assets/122444022/7ef5ab52-4d6f-437c-8140-8130e1d96ecf)
<br>Credit rating and income are both positively correlated with card limit, meaning that customers with higher rating and incomes tend to have higher card limits.

## Relationship of Marital Status with Numerical data
<img width="868" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/2d96e2bd-1e8d-4c6e-bdbb-c288412408eb">
<img width="868" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/50831da0-09a0-4aeb-bae4-c98004024f5c">
<img width="868" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/a5529baf-e9ec-4f0f-afba-0a2070b4defc">
<img width="363" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/5fc97281-386b-4b7b-8621-bf84a1058bff">
We can infer following findings:
<br>Only married and unmarried are evident in the dataset. Seperated, Divorced and Widow are negligible in dataset.
<br>Mostly unmarried are max in all cardholder ages and Widow are aged among all.
<br>Widow are highest earner and Divorced are least earner. After Widow, Married card holder have higher limit.
<br>Rating-wise Widow stands top the list.
<br>Maximum number of cards are held by unmarried.
<br>Most of card holders are using to the maximum limit of the card. Unmarried are slightly higher than married in spending over cards and also hold maximum balance.

## Relationship of Gender with Numerical data
<img width="872" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/1522f84d-43d5-4d59-b12a-7b7c65035f57">
<img width="868" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/01a95d8d-c4ea-4689-b368-6c2c20e82563">
<img width="869" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/ecad592f-ef27-4224-b7b6-e6f10b8aefe4">
<img width="424" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/d6fce1e3-b956-46f2-a21f-9c6880fcaea3">
We can infer following findings:
<br>Female card holders are slightly higher compare to Male in all the parameters.
<br>Maximum female card holders are at lower as well as higher income braket.
<br>Male card holders have better limit.
<br>Female card holders have better rating.
<br>Both stands at same for maximum number of cards are held.
<br>Male are keeping good balance compare to female.



















