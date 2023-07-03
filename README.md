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




