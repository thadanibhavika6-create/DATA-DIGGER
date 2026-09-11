<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:6a11cb,100:2575fc&height=200&section=header&text=DATA%20DIGGER&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Database%20Design%20%7C%20CRUD%20%7C%20Aggregates%20%7C%20Analytics&descAlignY=58&descSize=18" width="100%"/>

<img src="https://readme-typing-svg.demolab.com/?lines=Customer+%E2%86%92+Order+%E2%86%92+Product+relational+design;CRUD+operations+in+pure+SQL;Aggregate+%26+analytical+queries;Beginner-friendly+SQL+practice+project&font=Fira+Code&center=true&width=650&height=45&color=2575fc&vCenter=true&size=22&pause=1200"/>

<br/>

![SQL](https://img.shields.io/badge/SQL-PostgreSQL%2FMySQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

</div>

---

## 📌 Project Overview

This project simulates the backend database of a simple **e-commerce platform**. It covers database design, CRUD operations, foreign-key relationships, aggregate functions, and analytical queries across four related tables — **Customers, Orders, Products, and OrderDetails**.

It's a great practice project for learning **DDL**, **DML**, and **aggregate/analytical SQL queries**.

<img width="3640" height="2600" alt="data_digger_output_infographic (1)" src="https://github.com/user-attachments/assets/1d03c7f0-0246-45f0-96ca-f38fbc9f355d" />

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:2575fc,100:6a11cb&height=3&section=header" width="100%"/>
</div>

## 🗂️ Database Schema

### 1️⃣ `customers`
| Column | Type | Description |
|---|---|---|
| CustomerID | INT (PK) | Unique ID for each customer |
| Name | VARCHAR(50) | Customer's name |
| Email | VARCHAR(50) | Customer's email address |
| Address | VARCHAR(100) | Customer's address/city |

### 2️⃣ `Orders`
| Column | Type | Description |
|---|---|---|
| OrderID | INT (PK) | Unique ID for each order |
| CustomerID | INT (FK) | References `customers(CustomerID)` |
| OrderDate | DATE | Date the order was placed |
| TotalAmount | DECIMAL(10,2) | Total value of the order |

### 3️⃣ `Products`
| Column | Type | Description |
|---|---|---|
| ProductID | INT (PK) | Unique ID for each product |
| ProductName | VARCHAR(100) | Name of the product |
| Price | DECIMAL(10,2) | Price per unit |
| Stock | INT | Units available in stock |

### 4️⃣ `OrderDetails`
| Column | Type | Description |
|---|---|---|
| Order_Detail_ID | INT (PK) | Unique ID for each order line item |
| OrderID | INT (FK) | References `Orders(OrderID)` |
| ProductID | INT (FK) | References `Products(ProductID)` |
| Quantity | INT | Quantity of product ordered |
| Sub_Total | DECIMAL(10,2) | Line-item subtotal |

**Relationships**
```
customers 1───N Orders 1───N OrderDetails N───1 Products
```

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:2575fc,100:6a11cb&height=3&section=header" width="100%"/>
</div>

## ⚙️ Features / Operations Covered

<table>
<tr>
<td width="50%" valign="top">

**🔹 CRUD Operations**
- Create tables with PK & FK constraints
- Insert sample records into all tables
- Retrieve with `SELECT` + `WHERE`
- Update existing records
- Delete records conditionally

</td>
<td width="50%" valign="top">

**🔹 Filtering & Sorting**
- Filter customers by name
- Orders placed in the **last 30 days**
- Products within a **price range**
- Sort products by price (DESC)

</td>
</tr>
<tr>
<td width="50%" valign="top">

**🔹 Aggregate Functions**
- `MAX()`, `MIN()`, `AVG()` on order amounts
- `MAX()`, `MIN()` on product prices
- `SUM()` for total revenue
- `COUNT()` for product sales frequency

</td>
<td width="50%" valign="top">

**🔹 Grouping & Ranking**
- `GROUP BY` + `ORDER BY` + `LIMIT`
- **Top 3 most ordered products**

</td>
</tr>
</table>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:2575fc,100:6a11cb&height=3&section=header" width="100%"/>
</div>

## 🛠️ Tech Stack

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![pgAdmin](https://img.shields.io/badge/pgAdmin-336791?style=flat-square&logo=postgresql&logoColor=white)

> ⚠️ **Note:** The query using `CURRENT_DATE - INTERVAL '30 days'` is PostgreSQL syntax.
> For MySQL, use: `WHERE OrderDate >= CURDATE() - INTERVAL 30 DAY;`

<br/>

## ▶️ How to Run

```bash
1. Open your SQL client (pgAdmin / MySQL Workbench / DBeaver)
2. CREATE DATABASE ecommerce_db;
3. Run PR1_sql_new.sql — it creates tables, inserts data, and runs all queries
4. Check results in your SQL client's output panel
```

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:2575fc,100:6a11cb&height=3&section=header" width="100%"/>
</div>

## 📊 Sample Insights You Can Derive

- 💰 Total revenue generated across all orders
- 🏆 Top 3 best-selling products by quantity
- 📈 Highest, lowest, and average order value
- 🕒 Orders placed in the last 30 days
- 🧾 Number of times a specific product has been sold

<br/>

## 📁 File Structure

```
├── PR1_sql_new.sql   # Main SQL script (tables + queries)
└── README.md         # Project documentation
```

## 🚀 Future Improvements

- [ ] Add `JOIN` queries across all 4 tables
- [ ] Add a `Categories` table for product categorization
- [ ] Add views for common reports (monthly revenue, etc.)
- [ ] Add indexes for performance optimization

<br/>

## 🖼️ Sample Output

<img width="1500" height="1656" alt="data_digger_dashboard" src="https://github.com/user-attachments/assets/76b493f2-2f54-45fa-9ecc-cef0acf5d29d" />

<br/>

<div align="center">

### 👤 Author

**Bhavika Thadani
📍Ahmedanad**


Made with ❤️ to strengthen SQL fundamentals — DDL, DML & aggregate query concepts.

⭐ **If you found this project useful, consider giving it a star!**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2575fc,100:6a11cb&height=100&section=footer" width="100%"/>

</div>
