# 🛒 Zepto Product Analytics SQL Project

## Overview

This project is an end-to-end SQL analytics project built using a real-world Zepto e-commerce inventory dataset. The project simulates the workflow of a product/data analyst by performing database setup, exploratory data analysis, data cleaning, and business-focused SQL analysis.

The goal of this project is to transform raw inventory data into actionable business insights using SQL.

---

# Project Objectives

* Build and structure an e-commerce inventory database
* Explore and understand raw business data
* Clean inconsistent and invalid records
* Perform business-driven SQL analysis
* Generate insights around pricing, inventory, discounts, and product categories

---

# Dataset Information

Each row represents a product SKU from Zepto inventory.

### Dataset Columns

| Column                   | Description                  |
| ------------------------ | ---------------------------- |
| `sku_id`                 | Unique product identifier    |
| `category`               | Product category             |
| `name`                   | Product name                 |
| `mrp`                    | Maximum Retail Price         |
| `discountPercent`        | Discount percentage          |
| `availableQuantity`      | Inventory quantity           |
| `discountedSellingPrice` | Selling price after discount |
| `weightInGms`            | Product weight               |
| `outOfStock`             | Stock availability           |
| `quantity`               | Units/package size           |

---

# Database Schema

```sql
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
```

---

# Exploratory Data Analysis (EDA)

Performed analysis to understand dataset quality and structure:

* Counted total records
* Displayed sample records
* Checked null values
* Identified product categories
* Compared in-stock vs out-of-stock products
* Identified duplicate product names with multiple SKUs

---

# Data Cleaning

Cleaning steps performed:

* Identified products with invalid pricing
* Removed rows with zero MRP values
* Converted pricing from paise to rupees
* Standardized pricing data for analysis

Example:

```sql
UPDATE zepto
SET mrp = mrp / 100.0,
discountedSellingPrice = discountedSellingPrice / 100.0;
```

---

# Business Questions Solved

### 1. Top discounted products

Identified products offering the highest discounts.

### 2. High-value products out of stock

Found expensive products unavailable for customers.

### 3. Revenue estimation by category

Calculated category-wise revenue potential.

### 4. Expensive products with low discounts

Detected premium products with minimal discounting.

### 5. Categories with highest average discounts

Ranked categories by average discount percentage.

### 6. Best value products by price per gram

Calculated price efficiency using product weight.

### 7. Product segmentation by weight

Products grouped into:

* Low
* Medium
* Bulk

### 8. Inventory distribution analysis

Calculated total inventory weight by category.



# Skills Demonstrated

* SQL Querying
* PostgreSQL
* Data Cleaning
* Exploratory Data Analysis
* Product Analytics
* Inventory Analytics
* Business Analysis
* Data Transformation

# Key Takeaways

This project demonstrates how SQL can be used to solve real-world business problems by transforming raw e-commerce inventory data into actionable product and business insights.
