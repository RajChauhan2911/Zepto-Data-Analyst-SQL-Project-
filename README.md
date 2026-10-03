# Zepto Inventory Data Analysis Using PostgreSQL

## Project Overview

This project focuses on analyzing Zepto's inventory dataset using PostgreSQL. The objective is to explore product pricing, discount percentages, stock availability, estimated inventory value, and product weight to derive useful business insights.

The project involves data exploration, data cleaning, and SQL-based analysis to understand inventory distribution and product pricing trends.

## Dataset

* Dataset Name: Zepto Inventory Dataset
* Source: https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv
* File Name: zepto_v2.csv
* Database: PostgreSQL

Download the dataset from the Kaggle link above. Sign in if required and download zepto_v2.csv.

The dataset is hosted on Kaggle and is not included in this repository. Download it separately before running the SQL queries.

## Tools and Technologies

* PostgreSQL – Database management and SQL analysis
* pgAdmin 4 – SQL query execution and database administration
* SQL – Data exploration, cleaning, transformation, and aggregation

## Database Schema

The project uses a table named zepto with the following columns:

| Column                 | Description                                 |
| ---------------------- | ------------------------------------------- |
| sku_id                 | Unique product SKU identifier               |
| category               | Product category                            |
| name                   | Product name                                |
| mrp                    | Maximum Retail Price                        |
| discountPercent        | Discount percentage                         |
| availableQuantity      | Available inventory quantity                |
| discountedSellingPrice | Selling price after discount                |
| weightInGms            | Product weight in grams                     |
| outOfStock             | Indicates whether a product is out of stock |
| quantity               | Product quantity field                      |

## Project Workflow

### 1. Data Exploration

* Counted the total number of records.
* Examined sample records using LIMIT.
* Checked for missing values across relevant columns.
* Identified distinct product categories.
* Analyzed in-stock and out-of-stock product counts.
* Identified product names associated with multiple SKUs.

### 2. Data Cleaning

* Identified products with zero MRP or discounted selling price.
* Removed records where MRP was zero.
* Converted MRP and discounted selling prices from paise to rupees.

### 3. Data Analysis

The project addresses the following business questions:

1. Top 10 highest-discount products: Identified products offering the highest discount percentages.
2. High-MRP out-of-stock products: Found out-of-stock products with an MRP above ₹300.
3. Estimated inventory value by category: Calculated category-wise value using discounted selling price and available quantity.
4. High-MRP, low-discount products: Identified products with an MRP above ₹500 and a discount below 10%.
5. Categories with the highest average discounts: Identified the top five categories by average discount percentage.
6. Price per gram analysis: Calculated the price per gram for products weighing at least 100 grams to compare value for money.
7. Product weight classification: Categorized products as Low, Medium, or Bulk based on their weight.
8. Total inventory weight by category: Calculated the estimated total weight of available inventory for each category.

## SQL Concepts Used

* SELECT, WHERE, and DISTINCT
* ORDER BY and LIMIT
* Aggregate functions: COUNT(), SUM(), and AVG()
* GROUP BY and HAVING
* Data modification using DELETE and UPDATE
* Conditional expressions using CASE
* NULL value checks
* Numeric calculations and ROUND()

## How to Run the Project

1. Install PostgreSQL and pgAdmin 4.
2. Download zepto_v2.csv from the Kaggle dataset:
   https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv
3. Create a database in PostgreSQL.
4. Open pgAdmin 4 and connect to your database.
5. Execute the table creation query from zepto_analysis.sql.
6. Import the CSV file into the zepto table, ensuring the columns are mapped correctly.
7. Execute the SQL queries in sequence: data exploration, data cleaning, and data analysis.
8. Review the query results to understand product discounts, pricing, stock availability, and inventory distribution.

Note: The SQL script drops and recreates the zepto table. Run the table creation section carefully, as it will remove the existing table and its data.

## Key Business Insights

This analysis can help investigate:

* Which products offer the highest discounts.
* Which categories have higher average discount percentages.
* Which high-MRP products are currently out of stock.
* How product prices compare relative to product weight.
* How inventory value and weight are distributed across categories.

Actual findings should be added after reviewing the results produced by the SQL queries.

The category-wise calculation using discountedSellingPrice multiplied by availableQuantity estimates the value of available inventory, not actual sales revenue. Total inventory weight is estimated using weightInGms multiplied by availableQuantity, assuming the quantity represents the number of product units.

## Future Improvements

* Create an interactive dashboard using Power BI or Tableau.
* Visualize category-wise discounts and inventory distribution.
* Analyze relationships between discount percentages and stock availability.
* Add data quality checks and validation for missing or inconsistent values.

## Author

Raj Chauhan

Data Analyst | PostgreSQL | SQL | Data Exploration and Cleaning
