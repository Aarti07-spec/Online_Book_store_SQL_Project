# Online_Book_store_SQL_Project

##Project Overview:<br/ >
This SQL project simulates a real-world online bookstore where customer behavior, book inventory, and order trends are analyzed using structured queries. It demonstrates the use of SQL for database design, data ingestion, and business insights generation.

## 🎯 Objectives: <br/ >
Design and create normalized relational tables for books, customers, and orders.

Import real or synthetic CSV data into PostgreSQL.

Write analytical SQL queries to extract actionable insights.

Practice advanced concepts like JOIN, GROUP BY, HAVING, and AGGREGATION.

## 🧱 Schema Design: <br/ >
Tables Created:
Books — Book catalog with title, genre, author, price, and stock.

Customers — Customer info including location and contact.

Orders — Order details including quantity and total amount.

Relationships:
Orders.Customer_ID → References Customers.Customer_ID

Orders.Book_ID → References Books.Book_ID

✔️ Normalized structure
✔️ Referential integrity through foreign keys

## 📊 Key Queries & Analysis Performed: <br/ >
🔹 Basic Insights
Books in a specific genre (Fiction, Fantasy)

Books published after a given year

Customers from a particular country

Orders in a specific date range

🔹 Inventory & Sales
Total stock of books

Most and least expensive books

Books with lowest stock

🔹 Customer Behavior
Customers who placed multiple orders

Customers who spent the most

Cities where high-value orders came from

🔹 Business Metrics
Revenue from all orders

Total books sold per genre

Top 3 most expensive fantasy books

Total quantity sold by author

## 💡 Advanced Highlight: <br/ >
sql
Copy code
-- Remaining stock after fulfilling orders
SELECT b.book_id, b.title, b.stock , COALESCE(SUM(o.quantity),0) AS Order_quantity,
       b.stock - COALESCE(SUM(o.quantity),0) AS Remaining_Quantity
FROM books b
LEFT JOIN orders o ON b.book_id=o.book_id
GROUP BY b.book_id 
ORDER BY b.book_id;
✅ This query shows real-world inventory logic – a strong touch!

## 🛠️ Technologies Used: <br/ >
Tool	Purpose
PostgreSQL SQL engine and database
pgAdmin GUI for managing PostgreSQL
CSV Files Data import for books, customers
SQL DDL, DML, aggregation, joins, logic

## 📌 Highlights for GitHub README:
📷 A screenshot of EDA for database in pgAdmin.
💬 Comments in .sql files
📥 Sample CSV files (with dummy data)
