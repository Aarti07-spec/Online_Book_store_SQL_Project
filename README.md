# Online_Book_store_SQL_Project

## Project Overview:
<br>This SQL project simulates a real-world online bookstore where customer behavior, book inventory, and order trends are analyzed using structured queries. It demonstrates the use of SQL for database design, data ingestion, and business insights generation.

## 🎯 Objectives:
<br>Design and create normalized relational tables for books, customers, and orders.
Import real or synthetic CSV data into PostgreSQL.
Write analytical SQL queries to extract actionable insights.
Practice advanced concepts like JOIN, GROUP BY, HAVING, and AGGREGATION.
<br>
## 🧱 Schema Design:
<br>Tables Created:
Books — Book catalog with title, genre, author, price, and stock.<br>
Customers — Customer info including location and contact.<br>
Orders — Order details including quantity and total amount.<br>
<br>
Relationships:<br>
Orders.Customer_ID → References Customers.Customer_ID<br>
Orders.Book_ID → References Books.Book_ID<br>
✔️ Normalized structure<br>
✔️ Referential integrity through foreign keys<br>
<br>
## 📊 Key Queries & Analysis Performed:<br>
🔹 Basic Insights<br>
Books in a specific genre (Fiction, Fantasy)<br>
Books published after a given year<br>
Customers from a particular country<br>
Orders in a specific date range<br>
<br>
🔹 Inventory & Sales<br>
Total stock of books<br>
Most and least expensive books<br>
Books with lowest stock<br>
<br>
🔹 Customer Behavior<br>
Customers who placed multiple orders<br>
Customers who spent the most<br>
Cities where high-value orders came from<br>
<br>
🔹 Business Metrics<br>
Revenue from all orders<br>
Total books sold per genre<br>
Top 3 most expensive fantasy books<br>
Total quantity sold by author<br>

## 💡 Advanced Highlight:<br>
sql
Copy code<br>
-- Remaining stock after fulfilling orders
SELECT b.book_id, b.title, b.stock , COALESCE(SUM(o.quantity),0) AS Order_quantity,
       b.stock - COALESCE(SUM(o.quantity),0) AS Remaining_Quantity
FROM books b
LEFT JOIN orders o ON b.book_id=o.book_id
GROUP BY b.book_id <br>
ORDER BY b.book_id;<br>
✅ This query shows real-world inventory logic – a strong touch!<br>

## 🛠️ Technologies Used:
<br>Tool	Purpose
PostgreSQL SQL engine and database<br>
pgAdmin GUI for managing PostgreSQL<br>
CSV Files Data import for books, customers<br>
SQL DDL, DML, aggregation, joins, logic<br>

## 📌 Highlights for GitHub README:<br>
📷 A screenshot of EDA for database in pgAdmin.<br>
💬 Comments in .sql files<br>
📥 Sample CSV files (with dummy data)<br>
