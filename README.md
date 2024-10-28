---

# 🛒 Superstore Sales Analysis: Understanding Trends and Top Performers

In this analysis, I delved into a retail dataset to uncover customer trends, sales patterns by region, and product performance. This data provides key insights to guide business strategy, spotlight high-performing products, and identify growth opportunities. Each section here captures a unique angle of the dataset to craft a complete picture of the superstore's sales dynamics.

---

### 📌 Analysis Goals:
* **Identify** the customer base and unique regions.
* **Analyze** total sales by regions and months.
* **Highlight** top-performing products.
* **Track** sales growth trends over time.

---

## Key Insights with Screenshots

### 1. Total Number of Customers
Starting off, I checked the total number of unique customers to assess the customer base size.

```sql
SELECT COUNT(Customer_Name) AS Customers
FROM dataset_superstore;
```

![Number of Customers](https://github.com/DanieltheAnalyst1/screenshot1/blob/main/Number%20of%20Customers.png)

**Insight:** Knowing the total customer count sets a foundation for understanding the market reach and potential for customer-specific campaigns.

---

### 2. Regions Covered
Next, I identified the unique regions where sales occurred, providing a broad view of the geographic scope.

```sql
SELECT DISTINCT(Region) AS Regions
FROM dataset_superstore;
```

![Regions](https://github.com/DanieltheAnalyst1/screenshot1/blob/main/Regions.png)

**Insight:** Recognizing these regions allows for targeted regional strategies that can cater to specific preferences or needs based on geography.

---

### 3. Total Sales by Region and Month
Analyzing total sales across regions and by month reveals seasonal patterns and performance differences across areas.

```sql
SELECT Region, 
       YEAR(Order_Date) AS year,
       MONTH(Order_Date) AS month,
       SUM(Sales) AS total_sales
FROM dataset_superstore
GROUP BY Region, year, month
ORDER BY Region, year, month;
```

![Total Sales by Region and Month](https://github.com/DanieltheAnalyst1/screenshot1/blob/main/Total%20sales%20by%20region%20and%20month.png)

**Insight:** Understanding monthly performance by region helps the superstore make data-driven adjustments for regional campaigns and inventory stocking.

---

### 4. Top-Performing Products
I identified the top products by sales, highlighting best-sellers and popular items among customers.

```sql
SELECT Product_ID,
       SUM(Sales) AS total_sales
FROM dataset_superstore
GROUP BY Product_ID
ORDER BY total_sales DESC
LIMIT 10;
```

![Top-performing Products](https://github.com/DanieltheAnalyst1/screenshot1/blob/main/Top-performing%20products.png)

**Insight:** Knowing the top products can help with promotions, and also guide purchasing decisions for frequently demanded items.

---

### 5. Sales Growth Trends Over Time
I examined sales growth trends over time, looking for seasonal peaks or consistent growth patterns.

```sql
SELECT YEAR(Order_Date) AS year,
       MONTH(Order_Date) AS month,
       SUM(Sales) AS total_sales
FROM dataset_superstore
GROUP BY year, month
ORDER BY year, month DESC;
```

![Sales Growth Trends](https://github.com/DanieltheAnalyst1/screenshot1/blob/main/Sales%20growth%20trends.png)

**Insight:** Tracking monthly trends helps forecast future sales, allowing for proactive adjustments in marketing or inventory planning.

---

This documentation highlights my analytical approach to the superstore's sales data, complete with visuals that make the insights more tangible. Together, these findings reveal actionable insights that drive better strategic decision-making for sales and marketing efforts.
