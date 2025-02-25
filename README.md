# Retail-Sales-Analysis

## Project Overview

**Project Title**: Retail Sales Analysis  

The project aims to prove SQL abilities and methods usually employed by data analysts in order to investigate, preprocess, and analyze retail sales data. The project includes creating a retail sales database, conducting exploratory data analysis (EDA), and responding to certain business questions using SQL queries. The project is suitable for the beginners in data analysis who want to lay a strong foundation in SQL.

## Objectives

1. **Establish a retail sales database**: Develop and load a retail sales database with the given sales data.
2. **Data Cleaning**: Check and delete all records with missing or null data.
3. **Exploratory Data Analysis (EDA)**: Conduct simple exploratory data analysis to get familiar with the dataset.
4. **Business Analysis**: Answer particular business queries and draw conclusions from the sales data using SQL.

5. ## Project Structure

### 1. Database Setup

- **Database Creation**: The project begins by creating a database with the name `retail_db`.
- **Creation of Table**: A table with the name `retail_sales` is used to hold the sales information. The table layout consists of columns for transaction number, sale date, sale time, customer number, gender, age, product category, number sold, price per unit, cost of goods sold (COGS), and total amount sold.
 ```sql
CREATE DATABASE p1_retail_db;

CREATE TABLE retail_sales
(
    transactions_id INT PRIMARY KEY,
    sale_date DATE,	
    sale_time TIME,
    customer_id INT,	
    gender VARCHAR(10),
    age INT,
    category VARCHAR(35),
    quantity INT,
    price_per_unit FLOAT,	
    cogs FLOAT,
    total_sale FLOAT
);
```
### 2. Data Exploration & Cleaning

- **Record Count**: Calculate the number of records in the dataset.
- **Customer Count**: Determine the number of unique customers within the dataset.
- **Category Count**: Count all distinct product categories in the data set.
- **Null Value Check**: Eliminate any null values in the data set and remove records for missing data.
 ```sql
SELECT COUNT(*) FROM retail_sales;

SELECT * FROM retail_sales
WHERE 
    sale_date IS NULL
    OR
    sale_time IS NULL
    OR
    customer_id IS NULL
    OR 
    gender IS NULL
    OR
    age IS NULL
    OR
    category IS NULL
    OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;

DELETE FROM retail_sales
WHERE 
    sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL OR 
    gender IS NULL OR age IS NULL OR category IS NULL OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;
```
### 3. Data Analysis & Findings

The below SQL queries were created to provide answers to particular business questions:

1. **Write a SQL query to fetch all columns for sales done on '2022-11-05**:
```sql
SELECT * FROM retail_sales WHERE sale_date = '2022-11-05';
```
2. **Write a SQL query to bring all transactions wherein the category is 'Clothing' and quantity sold is greater than 4 in Nov-2022**:
```sql
SELECT * FROM retail_sales
WHERE 
    category = 'Clothing'
    AND 
    TO_CHAR(sale_date, 'YYYY-MM') = '2022-11'
    AND
    quantity >= 4
```
3. **Write a SQL query to find the total sales (total_sale) for each category.**:
```sql
SELECT category,
    SUM(total_sale) as net_sale,
    COUNT(*) as total_orders
FROM retail_sales
GROUP BY 1
```
4. **Create a SQL query to determine the average age of customers who made purchases in the 'Beauty' category.**:
```sql
SELECT ROUND(AVG(age), 2) as avg_age
FROM retail_sales
WHERE category = 'Beauty'
```
5. **Write a SQL query to retrieve all the transactions in which total_sale is more than 1000.**
```sql
SELECT * FROM retail_sales WHERE total_sale > 1000
```
