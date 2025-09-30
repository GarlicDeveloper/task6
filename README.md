# 📊 Task 6: Sales Trend Analysis Using Aggregations

**Internship Role:** Data Analyst  
**Objective:** Analyze monthly and quarterly sales trends to uncover revenue patterns and order volume across 2021–2023.

---

### 🗂️ Dataset Overview

- **File Name:** `online_sales_orders.csv`  
- **Records:** 1000+  
- **Key Columns:**  
  - `order_id`, `order_date`, `customer_id`, `product_id`, `amount`, `quantity`  
  - `category`, `payment_method`, `region`, `order_status`  
- **Description:** Simulated realistic sales data with seasonal trends and diverse product categories.

---

### ⚙️ Tools & Techniques

- **SQL Dialect:** MySQL  
- **Functions Used:**  
  - Aggregations: `SUM()`, `COUNT(DISTINCT)`  
  - Date Functions: `YEAR()`, `MONTHNAME()`, `QUARTER()`  
  - Filtering: `WHERE`, `ORDER BY`, `LIMIT`  
- **AI Support:** ChatGPT (for dataset generation and query refinement)

---

### ✅ Task Breakdown

#### 1. 📈 Total Revenue (Completed Orders Only)
```sql
SELECT YEAR(order_date) AS Years,
       ROUND(SUM(amount)) AS total_revenue
FROM online_sales_orders
WHERE order_status = 'Completed'
GROUP BY YEAR(order_date);
```
**Insight:** Tracked year-over-year revenue growth from completed transactions.

#### 2. 📅 Quarterly Revenue Across All Years
```sql
SELECT YEAR(order_date) AS Year,
       QUARTER(order_date) AS Quarter,
       ROUND(SUM(amount)) AS total_revenue
FROM online_sales_orders
GROUP BY YEAR(order_date), QUARTER(order_date)
ORDER BY Year, Quarter;
```
**Insight:** Identified seasonal performance spikes and quarterly trends.

#### 3. 📦 Yearly Order Volume
```sql
SELECT YEAR(order_date) AS Years,
       COUNT(DISTINCT order_id) AS Total_volume
FROM online_sales_orders
GROUP BY YEAR(order_date);
```
**Insight:** Measured customer engagement and order frequency annually.

---

### 🚀 Bonus Explorations

- Top 3 Revenue Months  
- Revenue by Product Category  
- Revenue by Payment Method  
- Impact of Cancelled Orders  
- Monthly Order Volume Trends

---

### 📂 Repository Contents

- `online_sales_order.sql`: All SQL queries  
- 📸 Screenshots: Query results and sample visuals  
- 📈 Visualizations: (Add charts if available)

---

### 🧠 Key Learnings

- Time-based grouping using `YEAR()`, `MONTHNAME()`, `QUARTER()`  
- Effective use of aggregate functions for business insights  
- Structuring SQL for clarity and storytelling  
- Filtering and ordering for targeted analysis

---
