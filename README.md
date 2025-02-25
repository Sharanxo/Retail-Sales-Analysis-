# Retail-Sales-Analysis-

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


