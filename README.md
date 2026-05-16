# 🛒 Zepto E-commerce Inventory Analysis | PostgreSQL SQL Project

## 📌 Project Overview
This project is an end-to-end SQL Data Analysis project built using PostgreSQL on a real-world e-commerce inventory dataset inspired by Zepto, one of India’s fastest-growing quick-commerce platforms.

The project demonstrates how data analysts work with raw inventory data to perform:

- Data Exploration
- Data Cleaning
- Inventory Analysis
- Pricing & Discount Analysis
- Business Insights Generation

The dataset contains product-level information such as category, MRP, discounts, stock availability, product weight, and inventory quantity.

---

# 🛠️ Tech Stack

- PostgreSQL
- SQL
- pgAdmin
- CSV Dataset

---

# 📂 Dataset Information

Each row in the dataset represents a unique product SKU.

### Dataset Columns

| Column Name | Description |
|---|---|
| sku_id | Unique product identifier |
| category | Product category |
| name | Product name |
| mrp | Maximum Retail Price |
| discountPercent | Discount percentage |
| availableQuantity | Inventory quantity available |
| discountedSellingPrice | Final selling price |
| weightInGms | Product weight |
| outOfStock | Product stock status |
| quantity | Units per package |

---

# 🔧 Database Setup

## Create Table

```sql
DROP TABLE IF EXISTS zepto;

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
🔍 Data Exploration

Performed exploratory data analysis to understand the dataset structure and identify inconsistencies.

Exploration Tasks
Counted total records
Viewed sample records
Checked for null values
Identified unique product categories
Compared in-stock vs out-of-stock products
Identified duplicate product names across SKUs
🧹 Data Cleaning

Performed data cleaning and transformation to improve data quality.

Cleaning Steps
Removed rows with zero MRP
Converted prices from paise to rupees
DELETE FROM zepto
WHERE mrp = 0;

UPDATE zepto
SET mrp = mrp / 100.0,
    discountedSellingPrice = discountedSellingPrice / 100.0;
📊 Business Analysis

Performed SQL-based business analysis to generate actionable insights.

Business Questions Solved
Top 10 products with highest discounts
High MRP products currently out of stock
Estimated revenue by category
Expensive products with low discounts
Categories offering highest average discounts
Best value products using price-per-gram analysis
Product segmentation by weight category
Total inventory weight by category
📈 Sample Query
SELECT category,
SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category
ORDER BY total_revenue DESC;
🚀 Key Insights
Some categories provide significantly higher discounts than others
Premium products frequently face stock shortages
Inventory value differs greatly across product categories
Price-per-gram analysis helps identify value-for-money products
Bulk inventory contributes the highest overall stock weight
💡 Skills Demonstrated
SQL Querying
PostgreSQL
Data Cleaning
Exploratory Data Analysis (EDA)
Business KPI Analysis
Aggregate Functions
CASE Statements
Retail & Inventory Analytics

