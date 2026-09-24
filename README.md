<div align="center">

# 🍕 Dominos SQL Analysis

**SQL analysis on pizza sales data — joins, aggregations, and window functions**

![SQL](https://img.shields.io/badge/SQL-Queries-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

</div>

---

## 📌 Overview

A SQL project analyzing pizza sales data across four related tables — orders, order details, pizzas, and pizza types. I worked through 13 business questions split into Basic, Intermediate, and Advanced tiers, using joins, aggregations, subqueries, and window functions to pull out revenue trends, top products, and order patterns.

![ER Diagram](Dominos_ER_Diagram.png)

| | |
|---|---|
| 🧾 **Orders analyzed** | 21,350 |
| 💰 **Total Revenue** | ₹8,17,860 |
| 🍕 **Pizza types** | 32, across 4 categories |
| 🗂️ **Tables** | Orders, Order_Details, Pizzas, Pizza_Types |

---

## 🗂️ Database Schema

The dataset is normalized across 4 tables, linked as shown in the ER diagram above:
- **Orders** → Order_Id, Order_Date, Order_Time
- **Order_Details** → Order_Details_Id, Order_Id, Pizza_Id, Quantity
- **Pizzas** → Pizza_Id, Pizza_Type_Id, Size, Price
- **Pizza_Types** → Pizza_Type_Id, Name, Category, Ingredients

---

## ❓ Questions Answered

**Basic**
1. Total number of orders placed
2. Total revenue from pizza sales
3. Highest-priced pizza
4. Most common pizza size ordered
5. Top 5 most ordered pizza types by quantity

**Intermediate**
6. Total quantity ordered per pizza category
7. Distribution of orders by hour of the day
8. Category-wise distribution of pizza types
9. Average number of pizzas ordered per day
10. Top 3 pizza types by revenue

**Advanced**
11. Percentage revenue contribution by category
12. Cumulative revenue over time (running total)
13. Top 3 pizza types by revenue, within each category (using `RANK() OVER PARTITION BY`)

---

## 🔍 Key Findings

- **21,350 orders** generated a total of **₹8,17,860** in revenue.
- **The Greek Pizza** is the single highest-priced item on the menu at ₹35.95.
- **Large (L)** is the most frequently ordered size, ahead of Medium and Small.
- **The Classic Deluxe, Barbecue Chicken, and Hawaiian** pizzas top the charts by quantity ordered — all clustered close together around 2,400+ orders each.
- **Classic and Supreme categories** bring in the highest share of revenue, each contributing roughly a quarter of total sales, with Chicken and Veggie close behind.
- Used a **window function** (`SUM() OVER (ORDER BY order_date)`) to track cumulative revenue growth over time, and `RANK() OVER (PARTITION BY category)` to find the top 3 revenue-generating pizzas *within* each category — not just overall.

---

## 🛠️ Skills Demonstrated

- Multi-table `JOIN`s (up to 3 tables at once)
- Aggregate functions (`SUM`, `COUNT`, `AVG`, `ROUND`)
- Subqueries & correlated subqueries
- Window functions (`RANK() OVER`, `SUM() OVER`)
- `CREATE VIEW` for reusable, organized query logic
- Date/time functions (`EXTRACT(HOUR FROM ...)`)

---

## 📁 Repository Structure

```
├── dominos.sql                       # all SQL queries (Basic → Intermediate → Advanced)
├── Dominos_sql_query_file.docx       # queries + outputs in document form
├── Dominos_SQL_Project.pptx          # presentation walkthrough of the project
├── Dominos_ER_Diagram.png            # entity-relationship diagram
├── orders.csv
├── order_details.csv
├── pizzas.csv
├── pizza_types.csv
└── README.md
```

---

## 📊 Dataset

Built on the well-known **Pizza Place Sales** dataset — a relational dataset of orders, order line items, pizza products, and pizza types, commonly used for practicing SQL joins and business-question-driven analysis.

---

## 👤 Author

**Rishi Mishra**

If you found this useful, a ⭐ on the repo is always appreciated!
