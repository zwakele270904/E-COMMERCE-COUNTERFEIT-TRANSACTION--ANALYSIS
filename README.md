# E-COMMERCE-COUNTERFEIT-ANALYSIS

## Table of Contents

 - [Project Overview](#project-overview)
 - [Data Source](#data-source)
 - [Tools used](#tools-used)
 - [Data Cleaning](#data-cleaning)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Data Analysis](#data-analysis)
 - [Findings](#findings)
 - [Recomendations](#recomendations)

### Project Overview

An in-depth analysis of e-commerce counterfeit products and transactions to uncover trends, patterns, and insights that can inform strategies to combat counterfeiting. The analysis examined the prevalence of counterfeit products across various e-commerce platforms.


<img width="928" height="495" alt="Screenshot 2025-11-08 123442" src="https://github.com/user-attachments/assets/98c61de9-2ee5-4923-8a41-61006ab93d2b" />

### Data Source

Transaction data: The Dataset used for this analysis is "" which we will later upload in our repository contains the detailed transaction made  

### Tools used 
- Excel - Data Cleaning
- SQL Snowflake -  analysis and data Loading
- Power BI - Further analysis and Report


### Data Cleaning
In the initial Data Preparation phase ,we Perfomed the following tasks:
1. Data Loading and Inspection
2. Check for Duplicates
3. Check for Null values
   


### Exploratory Data Analysis
 - Which payment method used in transactions  produce more Revenue between Counterfeit and Non counterfeit
 - How are the sales during each day between counterfeit and non counterfeit
 - How are the Annual sales trends
 - Which customer location makes more revenue if counterfeit or if non counterfeit
 - Which age Group is dominantly involved in counterfeit trnsactions
 - What is the dominant shipping speed


### Data Analysis
```SQL
SELECT * FROM TRANSACTIONS;
 CREATE OR REPLACE TEMP TABLE AGE AS(
  SELECT CUSTOMER_AGE,CUSTOMER_LOCATION,TOTAL_AMOUNT,CUSTOMER_ID,TRANSACTION_ID,
  CASE 
  WHEN CUSTOMER_AGE BETWEEN 18 AND 25 THEN 'Young Adults'
  WHEN CUSTOMER_AGE BETWEEN 26 AND 35 THEN 'Adults'
  WHEN CUSTOMER_AGE BETWEEN 36 AND 45 THEN 'Seniors'
  WHEN CUSTOMER_AGE BETWEEN 46 AND 55 THEN 'Post Seniors'
  WHEN CUSTOMER_AGE BETWEEN 56 AND 65 THEN 'Pre Pensioners'
  WHEN CUSTOMER_AGE BETWEEN 66 AND 80 THEN 'Pensioners'
  END AS AGE_GROUPS 
  FROM TRANSACTIONS
  );


SELECT * FROM AGE;


```

### Findings
- Credit card Payment method was the most preffered payment method for counterfeit transactions contributing more than 10% of Total revenue generated, while Paypal was the prefered payment method for non counterfeit transactions contributing 23% of the total revenue
- Counterfeit transactions were happening mostly on Monday than any other day of the week, While Tuesday was the most busy day for non counterfeit
- June was the most busy month for counterfeit transactions ,while January was the most busy month for non counterfeit transactions
- DE cutomer location was the one that dominated the counterfeit transactions ,while GB dominated the non counterfeit transactions
- Pensioners an age from 66 to 80 years dominated both counterfeit and non counterfeit transactions contributing more than 50 % than any other age group 
- Standard shipping speed was the most used shipping speed for counterfeit transactions contributing 54.3%, while express shipping speed dominated the non counterfeit  with 35.2% 

### Recomendations
 - Use blockchain producuts technology to track and verify transactions authenticty
 - Provide increased subscription fees for shipping speeds like standard which are mostly used by counterfeit transactions
 - Increase education measures for about the negativity of counterfeit transactions

### Limitations
- I had to group and bucket the ages using SQL snowflake to ensure the accuracy of my analysis



   
