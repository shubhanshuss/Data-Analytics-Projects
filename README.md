# Sales Insights Data Analysis Project

### Introduction

This project is designed to simulate a real-world data analysis scenario aimed at generating actionable sales insights for AtliQ Hardware, a computer hardware manufacturer. The project is ideal for aspiring data analysts and data scientists to gain practical exposure to data analytics workflows, project management methodologies, and corporate problem-solving techniques.

This project was completed as part of an assisted learning program, following a step-by-step guide from a YouTube tutorial. It provided an excellent opportunity to apply theoretical knowledge in a guided, practical context.

The end goal is to create a Power BI dashboard that provides detailed sales insights, empowering stakeholders to make data-driven decisions to enhance business performance.

### Problem Statement

AtliQ Hardware, headquartered in Delhi, India, supplies computer hardware to various clients, including Excel Stores across India. However, the sales director, Bhavin Patel, faces significant challenges:

1. Difficulty tracking sales trends in a dynamically evolving market.

2. Inconsistent and often overly optimistic verbal reports from regional managers.

3. Excessive manual work involving multiple Excel files for consolidating sales data.

4. Lack of centralized, easily interpretable insights for quick decision-making.

Objective: To provide Bhavin Patel with a centralized dashboard that offers real-time, accurate, and visually intuitive insights into sales performance across regions, products, and timelines.

### Data Workflow and Tools

1. Data Sources

- Sales Management System: Records sales transactions.

- Supplementary Data: Additional details like product codes and regional sales data.

2. Data Wrangling in Power BI

- Clean and merge datasets.

- Perform transformations like currency conversion and filtering irrelevant columns.

### SQL Queries for Data Analysis

To prepare the data for visualization, the following SQL queries are used:

1. Show all customer records:  
   SELECT * FROM customers;

2. Count total customers:  
   SELECT count(*) FROM customers;

3. Transactions for Chennai market:   
   SELECT * FROM transactions WHERE market_code='Mark001';

4. Distinct products sold in Chennai:    
   SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';

5. Transactions in USD currency:    
   SELECT * FROM transactions WHERE currency="USD";

6. Total revenue in 2020:    
   SELECT SUM(transactions.sales_amount)    
   FROM transactions    
   INNER JOIN date     
   ON transactions.order_date=date.date     
   WHERE date.year=2020     
   AND (transactions.currency="INR" OR transactions.currency="USD");
     
8. Total revenue in Chennai for 2020:   
   SELECT SUM(transactions.sales_amount)   
   FROM transactions  
   INNER JOIN date   
   ON transactions.order_date=date.date    
   WHERE date.year=2020   
   AND transactions.market_code="Mark001";   
