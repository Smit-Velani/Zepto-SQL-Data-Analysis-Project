# 🛒 Zepto E-Commerce SQL Data Analysis
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![pgAdmin](https://img.shields.io/badge/pgAdmin-336791?style=flat&logo=postgresql&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)

> **Academic Project — SQL Data Analysis on Real-World E-Commerce Inventory Data**

An end-to-end SQL data analysis project on **Zepto product inventory data** using **PostgreSQL**. Covers data exploration, cleaning and 10 business analytical queries to extract insights on pricing, discounts, inventory availability and revenue potential across 14 product categories.

---

## 📊 Key Numbers

| Metric | Value |
|--------|-------|
| Total Products | 3,732 |
| Product Categories | 14 |
| In-Stock Products | 3,279 |
| Out-of-Stock Products | 453 |
| Top Discount | 51% |
| Highest Avg Discount Category | Fruits & Vegetables (15.46%) |
| Top Out-of-Stock Categories | Munchies & Cooking Essentials (64 each) |

---

## 🚀 Quick Start

```sql
-- 1. Create the database table
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

-- 2. Import dataset
-- Load zepto_v2.csv into the table via pgAdmin

-- 3. Run the analysis
-- Execute Zepto_SQL_data_analysis.sql
```

---

## 📁 Project Structure

```
zepto-sql-analysis/
│
├── zepto_v2.csv                        ← Raw dataset
├── Zepto_SQL_data_analysis.sql         ← All SQL queries
├── Zepto_SQL_Data_Analysis_Project.pdf ← Full project report
├── LICENSE.txt
└── README.md
```

---

## ⚙️ Project Workflow

### 1️⃣ Data Exploration
| Query | Purpose |
|-------|---------|
| COUNT total records | 3,732 products found |
| DISTINCT categories | 14 unique categories |
| NULL value check | No missing values |
| In-stock vs Out-of-stock | 3,279 in-stock · 453 out-of-stock |
| Duplicate product names | Products with multiple SKUs identified |

### 2️⃣ Data Cleaning
- Removed products where **MRP = 0**
- Converted price values from **paise → rupees** (`mrp / 100.0`)
- Verified price consistency after conversion

### 3️⃣ Data Analysis — 10 Business Queries

| # | Query | Insight |
|---|-------|---------|
| Q1 | Top 10 Best Value Products by Discount | Max discount up to **51%** |
| Q2 | High MRP Products Out of Stock | Products >₹300 unavailable |
| Q3 | Estimated Revenue per Category | Munchies top revenue: **₹337,369** |
| Q4 | Expensive Products with Low Discounts | MRP >₹500, discount <10% |
| Q5 | Categories with Highest Avg Discounts | Fruits & Veg: **15.46%** avg discount |
| Q6 | Price per Gram Analysis | Best value products identified |
| Q7 | Product Weight Classification | Low / Medium / Bulk using CASE |
| Q8 | Total Inventory Weight by Category | Weight distribution across categories |
| Q9 | Top 10 Revenue Generating Products | Borges Olive Oil: **₹8,394** top revenue |
| Q10 | Categories with Most Out-of-Stock | Munchies & Cooking Essentials: **64 each** |

---

## 📐 Dataset Description

| Column | Type | Description |
|--------|------|-------------|
| `sku_id` | SERIAL | Unique product identifier |
| `category` | VARCHAR | Product category |
| `name` | VARCHAR | Product name |
| `mrp` | NUMERIC | Maximum retail price (₹) |
| `discountPercent` | NUMERIC | Discount percentage |
| `availableQuantity` | INTEGER | Available stock |
| `discountedSellingPrice` | NUMERIC | Final selling price (₹) |
| `weightInGms` | INTEGER | Product weight in grams |
| `outOfStock` | BOOLEAN | Stock availability status |
| `quantity` | INTEGER | Pack quantity |

---

## 🔑 Key Insights

- **Munchies** and **Cooking Essentials** face highest out-of-stock issues (64 products each) — indicating strong demand
- **Fruits & Vegetables** offers highest average discount at **15.46%**
- **Price-per-gram analysis** reveals fresh produce as best value for consumers
- Top discount products reach up to **51% off** — driven by dairy and snack categories
- A small group of products contributes majority of estimated revenue

---

## 💡 SQL Techniques Used

| Technique | Usage |
|-----------|-------|
| `GROUP BY` + `ORDER BY` | Revenue and discount aggregation |
| `CASE WHEN` | Weight classification (Low/Medium/Bulk) |
| `HAVING` | Filtering duplicate SKUs |
| `DISTINCT` | Unique product analysis |
| `WHERE` subquery | Filtering high-value out-of-stock items |
| `ROUND(AVG())` | Average discount per category |
| `SUM(price * qty)` | Estimated revenue calculation |
| `DELETE` + `UPDATE` | Data cleaning operations |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| `PostgreSQL` | Database engine |
| `pgAdmin` | Query execution & management |
| `SQL` | Data exploration, cleaning & analysis |
| `GitHub` | Version control & project hosting |

---

## 👤 Author

**Smit Velani**
Data Science MS — Northeastern University

---

*Built with PostgreSQL · SQL · pgAdmin*
