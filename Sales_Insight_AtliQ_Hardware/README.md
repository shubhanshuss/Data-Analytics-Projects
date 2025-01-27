# Sales Insights Data Analysis Project

### 1. Introduction

This project is designed to simulate a real-world data analysis scenario aimed at generating actionable sales insights for AtliQ Hardware, a computer hardware manufacturer. The project is ideal for aspiring data analysts and data scientists to gain practical exposure to data analytics workflows, project management methodologies, and corporate problem-solving techniques.

This project was completed as part of an assisted learning program, following a step-by-step guide from a YouTube tutorial. It provided an excellent opportunity to apply theoretical knowledge in a guided, practical context.

The end goal is to create a Power BI dashboard that provides detailed sales insights, empowering stakeholders to make data-driven decisions to enhance business performance.

### 2. Problem Statement

AtliQ Hardware, headquartered in Delhi, India, supplies computer hardware to various clients, including Excel Stores across India. However, the sales director, Bhavin Patel, faces significant challenges:

2.1. Difficulty tracking sales trends in a dynamically evolving market.

2.2. Inconsistent and often overly optimistic verbal reports from regional managers.

2.3. Excessive manual work involving multiple Excel files for consolidating sales data.

2.4. Lack of centralized, easily interpretable insights for quick decision-making.

Objective: To provide Bhavin Patel with a centralized dashboard that offers real-time, accurate, and visually intuitive insights into sales performance across regions, products, and timelines.

### 3. Data Workflow and Tools

3.1. Data Sources

- Sales Management System: Records sales transactions.

- Supplementary Data: Additional details like product codes and regional sales data.

3.2. Data Wrangling in Power BI

- Clean and merge datasets.

- Perform transformations like currency conversion and filtering irrelevant columns.

### 4. SQL Queries for Data Analysis

To prepare the data for visualization, the following SQL queries are used:

4.1. Show all customer records:  
   ```SELECT * FROM customers;```

4.2. Count total customers:  
   ```SELECT count(*) FROM customers;```

4.3. Transactions for Chennai market:   
   ```SELECT * FROM transactions WHERE market_code='Mark001';```

4.4. Distinct products sold in Chennai:    
   ```SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';```

4.5. Transactions in USD currency:    
   ```SELECT * FROM transactions WHERE currency="USD";```

4.6. Total revenue in 2020: 
```
   SELECT SUM(transactions.sales_amount)      
   FROM transactions      
   INNER JOIN date       
   ON transactions.order_date=date.date       
   WHERE date.year=2020        
   AND (transactions.currency="INR" OR transactions.currency="USD");       
```
4.7. Total revenue in Chennai for 2020:   
```
   SELECT SUM(transactions.sales_amount)     
   FROM transactions
   INNER JOIN date   
   ON transactions.order_date=date.date    
   WHERE date.year=2020   
   AND transactions.market_code="Mark001";  
```
### 5. Dashboard Features

The Power BI dashboard was designed with the following features, incorporating key steps I personally executed:

- Data Transformation:
  - Merged multiple datasets to create a unified data model.
  - Performed data cleaning tasks, including handling null values, correcting data types, and removing duplicates.
  - Created calculated columns and measures for metrics like total revenue, profit margin, and growth rate.
 
   ![image](https://github.com/user-attachments/assets/e8cc9858-8f74-4da9-a627-1eb5143ddbb6)

- Visualizations:
  - Designed visuals such as bar charts, line graphs, and pie charts to display key metrics like revenue trends, sales by region, and product performance.
  - Incorporated slicers for filtering data by year, region, and product category.
  
![image](https://github.com/user-attachments/assets/0a240df2-dc32-4ef9-bfdc-5deb62508f47)


- Dashboard Layout:
  - Structured the dashboard into intuitive sections, including overall performance, regional breakdowns, and top-performing products.
  - Applied consistent color themes and formatting for better readability.

![image](https://github.com/user-attachments/assets/7e5ea031-5bcd-43f8-adc6-ccafe451d7a1)


- DAX Formulas:
  - Used DAX to create measures for calculating year-over-year growth, running totals, and percentage contributions.
 
![image](https://github.com/user-attachments/assets/39b9e005-b636-4b69-8dc6-6d8320470285)
