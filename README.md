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


