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

# There are two part for analyis:
## 1. Data Cleaning and Visualization
## 2. EDA

### TwoDotSeven-Data-Clean.ipynb file has part1 analysis
### TwoDotSeven-EDA.ipynb file has part2 analysis
### Both the dataset Card Details.csv and Customer Details.csv are suppose to be downloaded and file location should be shared in Jupyter Notebook import dataset section.


# Part1. Data Cleaning and Visualization

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
<img width="142" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/dcf755c6-d932-4c80-a413-b3c15664d71a">
<br>From the above data only "Age, Income, Limit, Rating, Balance" are quantitative continuous variables
<br>whereas "Cards, " is quantitative Discrete variables
<br>From above data CustomerID is removed from mode as there will be no repetative values and all values are unique
<br>From the data above "Marital Status, Gender, Ethnicity" are qualitative Nominal data
<br>where as "Education" is qualitative Ordinal data
<br>Above observation is done using data description given and finding value_count of the variables

## Statistic summary of numerical data
![image](https://github.com/nayankm/Capstone/assets/122444022/3c104203-fc8a-42c9-bb1e-04a1d120de87)
<img width="451" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/c146223a-2c50-456f-be5f-6f2dfbb8bac2">
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
<img width="286" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/543289dd-812d-44cf-99cd-ca579f004435">
<br>From the statistics summary, we can infer the below findings :
<br>1. Similar card holder names are existing where Claude appears 9 times.
<br>2. Dataset data is unique as each card holder has unique Customer ID.
<br>3. Most of the customer are Unmarried, Female and from Caucasian.
<br>4. Most of the customer are highly educated holding Master degree.

## The measures of central tendency for all the variables
<img width="182" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/b653629d-fd4f-4be0-afbe-0d4b5f8513d5">

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


# Part2. Exploratory Data Analysis
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
<br>We can infer following findings:
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
<br>We can infer following findings:
<br>Female card holders are slightly higher compare to Male in all the parameters.
<br>Maximum female card holders are at lower as well as higher income braket.
<br>Male card holders have better limit.
<br>Female card holders have better rating.
<br>Both stands at same for maximum number of cards are held.
<br>Male are keeping good balance compare to female.

## Relationship of Ethnicity with Numerical data
<img width="869" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/1e654bf2-ccdb-4194-8d3e-5f280bfe17e3">
<img width="871" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/62bdad00-644f-4fc4-8155-a41147024ef1">
<img width="868" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/8115ef5a-a5c0-4cf1-955b-b7863a2eb00b">
<img width="371" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/8bbdd2e3-0ac4-4f33-ab16-867c6280c8bd">
<br>50% of card holders are from Caucasian.
<br>African American are higher in income, limit, rating and balance.
<br>African American are comparitively younger.

## Relationship of Education with Numerical data
<img width="869" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/512aa5ed-33eb-4c9e-b458-f2bbd8898987">
<img width="872" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/297555d6-b5ce-42e5-9b10-26f12b37122a">
<img width="871" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/7eac909f-5c29-4bc9-9442-7f03a6f5314f">
<img width="380" alt="image" src="https://github.com/nayankm/Capstone/assets/122444022/cfc3aae5-5155-40e7-8c79-75590979eaea">
<br>Most card holders are Highly educated, among them Master degree holder are max.
<br>High School are younger among all.
<br>Elementary are higher in earning.
<br>Secondary holds good limit.
<br>Elementary has good rating.
<br>High School has better balance.

## Observe Bi-variate distributions
![image](https://github.com/nayankm/Capstone/assets/122444022/e8be09f6-cbd2-4529-920c-04af99b1a8aa)
![image](https://github.com/nayankm/Capstone/assets/122444022/7c1735fd-5104-4430-b277-0774d3b23378)
![image](https://github.com/nayankm/Capstone/assets/122444022/d4c7c9b6-23ee-4f78-b581-c43617e9634f)
<br>We can infer following finding:
<br>Age is negatively correlated with Income, Card Limit, Rating.
<br>Income is positively correlated with Card Limit, Rating and Balance.
<br>Card Limit is positively correlated with Rating and Balance.
<br>Rating is positively correlated with Card Balance.

## Creating bins for Income
![image](https://github.com/nayankm/Capstone/assets/122444022/ce82807c-5a4d-40f8-a4c1-472c410de8df)
![image](https://github.com/nayankm/Capstone/assets/122444022/f5502066-1361-4e99-a43b-e9a63e9d154e)
![image](https://github.com/nayankm/Capstone/assets/122444022/77ab699e-4c59-42cb-9c09-873a781b24d0)
![image](https://github.com/nayankm/Capstone/assets/122444022/feda8286-f115-48b9-994f-ab94c560f36a)
![image](https://github.com/nayankm/Capstone/assets/122444022/5c67a2bd-0ca6-4101-911b-ee604bd3d769)
![image](https://github.com/nayankm/Capstone/assets/122444022/3bddbc54-9725-4e06-a21f-d07610f69348)
![image](https://github.com/nayankm/Capstone/assets/122444022/641b29d8-0179-43fb-b666-ab73b9724444)
![image](https://github.com/nayankm/Capstone/assets/122444022/fd5e82ab-ac7e-43c5-9068-f34dea11dff5)

## Creating bins for Rating
![image](https://github.com/nayankm/Capstone/assets/122444022/91970ae3-78f4-456e-b557-ab600499dea4)
![image](https://github.com/nayankm/Capstone/assets/122444022/c6ed8aca-0e6b-44f2-a710-f1b0c94deadb)

## Creating bins for Limit
![image](https://github.com/nayankm/Capstone/assets/122444022/c4c3cbaf-a4d5-405b-b860-12ab756d42aa)
![image](https://github.com/nayankm/Capstone/assets/122444022/14d14564-95cb-4ee2-958b-5ced48c3f656)

## Analysis on relation between Income, Rating and Limit
![image](https://github.com/nayankm/Capstone/assets/122444022/6c458dbf-5349-4231-8b40-6b77648d9a37)

<br>Relationship of Limit with Income is positive. However, High and Very High Income need to be consider for Limit enhancement.
<br>Low Income <--> Low Limit
<br>Average Income <--> Low Limit
<br>High Income <--> Average Limit
<br>Very High Income <--> Average Limit<br>
<br>Limit given to card holder as per their ratings.
<br>Low rating       <--> Low limit
<br>Average rating   <--> Average limit
<br>High rating      <--> High limit
<br>Very high rating <--> Very high limit

![image](https://github.com/nayankm/Capstone/assets/122444022/c77fbf21-960a-4edf-9b18-08c06c6ff8ad)
<br>High and Very High Income customer have poor rating compare to Low and Average Income customer.

## Potentential Customer for limit enhancement
(Income Range = Very High & Limit Range = Low | Average | High) & (Income Range = High & Limit Range = Low | Average)

# Conclusion
Potential Customers should be assigned with dedicated CRM(Customer Relationship Manager).
<br>They should be pushed for premium charged cards and should be guided for its benefit and waiver plans.
<br>Charged cards are beneficial specially for customers with high and very high income as they comes with bundles of membership in travels, accommodations, dinning, etc.
<br>Although revenue is generated through interest on amount utilized. However, Customers with balance = 0 should be given attention for converting their outstanding to EMI and scope of Limit enhancement if possible.




