Zepto SQL Data Analysis Project

Project Overview

This project performs data exploration, cleaning, and analysis on Zepto product inventory data using SQL.
The goal is to extract business insights related to product pricing, discounts, inventory availability, and revenue potential.

The analysis simulates a real-world e-commerce retail dataset where SQL is used to understand product performance and inventory patterns.


Dataset Description

The dataset contains information about products sold on Zepto, including:

| Column                 | Description               |
| ---------------------- | ------------------------- |
| sku_id                 | Unique product identifier |
| category               | Product category          |
| name                   | Product name              |
| mrp                    | Maximum retail price      |
| discountPercent        | Discount applied          |
| availableQuantity      | Available stock quantity  |
| discountedSellingPrice | Final selling price       |
| weightInGms            | Product weight            |
| outOfStock             | Product stock status      |
| quantity               | Pack quantity             |

Database Schema:

CREATE TABLE zepto (
sku_id SERIAL PRIMARY KEY,
category VARCHAR(120),
name VARCHAR(150) NOT NULL,
mrp NUMERIC(8,2),
discountPercent NUMERIC(5,2),
availableQuantity INTEGER,
discountedSellingPrice NUMERIC(8,2),
weightInGms INTEGER,
outOfStock BOOLEAN,
quantity INTEGER
);


Project Workflow

The project is divided into three main stages:

1️⃣ Data Exploration

Initial queries were used to understand the dataset.
Count total records
View sample data
Check for null values
Identify unique product categories
Compare in-stock vs out-of-stock products
Detect duplicate product names

2️⃣ Data Cleaning

Data cleaning ensures accurate analysis.
Removed products where MRP = 0
Converted price values from paise to rupees
Verified price consistency after conversion

3️⃣ Data Analysis

The following analytical SQL queries were performed:

Q1. Top 10 Best Value Products by Discount
Identify products offering the highest discounts.

Q2. High MRP Products that are Out of Stock
Find expensive products currently unavailable.

Q3. Estimated Revenue per Category
Calculate potential revenue using price and available quantity.

Q4. Expensive Products with Low Discounts
Identify high priced products with minimal discounts.

Q5. Categories with Highest Average Discounts
Analyze which product categories provide the best deals.

Q6. Price per Gram Analysis
Calculate the best value products based on price per gram.

Q7. Product Weight Classification
Classify products into:
Low weight
Medium weight
Bulk weight

Q8. Total Inventory Weight by Category
Calculate total inventory weight available for each category.

Q9. Top Revenue Generating Products
Identify products contributing the most potential revenue.

Q10. Categories with Highest Out-of-Stock Products
Highlight categories facing inventory shortages.

Key Insights

Some important insights derived from the analysis:
Certain categories offer significantly higher average discounts.
Some high-MRP products are frequently out of stock, indicating strong demand.
Price-per-gram analysis reveals better value products for consumers.
Inventory weight distribution varies significantly across categories.
A small group of products contributes a large portion of potential revenue.

Tools & Technologies Used

PostgreSQL
SQL
pgAdmin
GitHub

Skills Demonstrated

This project demonstrates the following data skills:

SQL Data Exploration
Data Cleaning
Business Data Analysis
Aggregations and Grouping
Analytical Query Design
Retail Data Insights

Project Structure


zepto-analysis

├── LICENSE.txt

├── README.md

├── zepto_v2.csv

├──Zepto SQL Data Analysis Project.pdf

└──Zepto_SQL_data_analysis.sql

Future Improvements

- Possible improvements for the project:
- Build a Power BI dashboard
- Add sales trend analysis
- Perform customer purchase analysis
- Implement predictive inventory forecasting

Author

Smitkumar Velani

Master's Student in Data Science

Northeastern University, Boston
