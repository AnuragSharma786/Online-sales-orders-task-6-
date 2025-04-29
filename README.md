## 📊 Task 6: Sales Trend Analysis Using Aggregations

**Internship Role:** Data Analyst  
**Objective:** Analyze monthly and quarterly sales trends to identify revenue patterns and order volume over a span of 3 years.

---

### 🗂️ Dataset Used
**File Name:** `online_sales_orders.csv`  
**Records:** 1000+  
**Columns:**
- `order_id`, `order_date`, `customer_id`, `product_id`, `amount`, `quantity`
- `category`, `payment_method`, `region`, `order_status`

Simulated realistic sales data for the years 2021–2023 with seasonal trends and diverse categories.

---

### ⚙️ Tools & Skills Used
- **SQL (MySQL)** for data aggregation and time-series analysis
- **Aggregations:** `SUM()`, `COUNT(DISTINCT)`, `GROUP BY`
- **Date Functions:** `YEAR()`, `MONTHNAME()`, `QUARTER()`
- **ChatGPT** *(For dataset)*

---

### ✅ Task Breakdown & What I Did

#### 1. **Total Revenue (Completed Orders Only)**
```sql
SELECT YEAR(order_date) AS Years, ROUND(SUM(amount)) AS total_revenue
FROM online_sales_orders
WHERE order_status = 'Completed'
GROUP BY YEAR(order_date);
```
**Insight:** Tracked revenue growth year over year, considering only successfully completed orders.

---

#### 2. **Quarterly Revenue Across All Years**
```sql
SELECT YEAR(order_date) AS Year, QUARTER(order_date) AS Quarter, ROUND(SUM(amount)) AS total_revenue
FROM online_sales_orders
GROUP BY YEAR(order_date), QUARTER(order_date)
ORDER BY Year, Quarter;
```
**Insight:** Identified sales performance trends across quarters and seasonal spikes.

---

#### 3. **Yearly Order Volume**
```sql
SELECT YEAR(order_date) AS Years, COUNT(DISTINCT order_id) AS Total_volume
FROM online_sales_orders
GROUP BY YEAR(order_date);
```
**Insight:** Analyzed customer activity and order trends on a yearly basis.

---

### 🚀 Bonus Explorations

> These queries go beyond the task requirements to show deeper insights.

- **Top 3 Revenue Months**
- **Revenue by Product Category**
- **Revenue by Payment Method**
- **Cancelled Orders Impact**
- **Monthly Order Volume Trends**

📂 You can find all the queries in repository
📸 Result screenshots are saved in repository

---

### 📈 Sample Visuals

*(Include screenshots here if you have visualizations or query results)*
---

### 🧠 Key Learnings

- Grouping data by time periods using `YEAR()`, `MONTHNAME()`, and `QUARTER()`
- Using aggregate functions effectively (`SUM()`, `COUNT()`)
- Ordering and filtering to get meaningful business insights
- Structuring SQL scripts clearly for analysis and storytelling

---
