# 📚 Online Book Store - SQL Project  

![SQL](https://img.shields.io/badge/SQL-PostgreSQL-blue?style=for-the-badge&logo=postgresql)
![Project](https://img.shields.io/badge/Project-Data%20Analytics-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 🚀 Project Overview  
This project demonstrates the creation and analysis of an **Online Book Store database** using SQL.  
It includes database design, CSV data import, and solving real-world business queries.

---

## 📂 Dataset  
The project uses 3 CSV files:

- 📘 `Books.csv`  
- 👥 `Customers.csv`  
- 🛒 `Orders.csv`  

### 🔗 Relationships

| Table      | Key Column |
|------------|-----------|
| Books      | Book_ID   |
| Customers  | Customer_ID |
| Orders     | Book_ID, Customer_ID |

---

## 🏗️ Database Setup  

### 🔹 Create Database
```sql
CREATE DATABASE Online_Book_Store;

🔹 Connect Database
\c Online_Book_Store;
🔹 Create Tables
-- Books Table
CREATE TABLE Books (
    Book_ID SERIAL PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    Genre VARCHAR(50),
    Published_Year INT,
    Price NUMERIC(10,2),
    Stock INT
);

-- Customers Table
CREATE TABLE Customers (
    Customer_ID SERIAL PRIMARY KEY,
    Name VARCHAR(100),
    City VARCHAR(50),
    Country VARCHAR(50)
);

-- Orders Table
CREATE TABLE Orders (
    Order_ID SERIAL PRIMARY KEY,
    Book_ID INT,
    Customer_ID INT,
    Order_Date DATE,
    Quantity INT,
    Total_Amount NUMERIC(10,2),
    FOREIGN KEY (Book_ID) REFERENCES Books(Book_ID),
    FOREIGN KEY (Customer_ID) REFERENCES Customers(Customer_ID)
);
📥 Data Import (pgAdmin Method)

## Since CSV data is not inserted via SQL script, data was imported manually.

⚙️ Steps:
-Open pgAdmin
-Navigate → Schemas → Tables
-Right-click on table (Books / Customers / Orders)
-Click Import/Export Data
-Select CSV file from system
### Enable:
- Header option ON
-Click Import

📊 SQL Queries
🔹 Basic Queries
-- 1. Retrieve all books in Fiction genre
SELECT * FROM Books WHERE Genre = 'Fiction';

-- 2. Books published after 1950
SELECT * FROM Books WHERE Published_Year > 1950;

-- 3. Customers from Canada
SELECT * FROM Customers WHERE Country = 'Canada';

-- 4. Orders in November 2023
SELECT * FROM Orders 
WHERE EXTRACT(MONTH FROM Order_Date) = 11 
AND EXTRACT(YEAR FROM Order_Date) = 2023;

-- 5. Total stock of books
SELECT SUM(Stock) AS Total_Stock FROM Books;

-- 6. Most expensive book
SELECT * FROM Books ORDER BY Price DESC LIMIT 1;

-- 7. Customers who ordered more than 1 quantity
SELECT * FROM Orders WHERE Quantity > 1;

-- 8. Orders where total amount > 20
SELECT * FROM Orders WHERE Total_Amount > 20;

-- 9. List all genres
SELECT DISTINCT Genre FROM Books;

-- 10. Book with lowest stock
SELECT * FROM Books ORDER BY Stock ASC LIMIT 1;

-- 11. Total revenue
SELECT SUM(Total_Amount) AS Revenue FROM Orders;
🔹 Advanced Queries
-- 1. Total books sold per genre
SELECT b.Genre, SUM(o.Quantity) AS Total_Sold
FROM Orders o
JOIN Books b ON o.Book_ID = b.Book_ID
GROUP BY b.Genre;

-- 2. Average price of Fantasy books
SELECT AVG(Price) FROM Books WHERE Genre = 'Fantasy';

-- 3. Customers with at least 2 orders
SELECT Customer_ID, COUNT(*) AS Order_Count
FROM Orders
GROUP BY Customer_ID
HAVING COUNT(*) >= 2;

-- 4. Most frequently ordered book
SELECT Book_ID, COUNT(*) AS Order_Count
FROM Orders
GROUP BY Book_ID
ORDER BY Order_Count DESC
LIMIT 1;

-- 5. Top 3 most expensive Fantasy books
SELECT * FROM Books
WHERE Genre = 'Fantasy'
ORDER BY Price DESC
LIMIT 3;

-- 6. Total quantity sold by each author
SELECT b.Author, SUM(o.Quantity) AS Total_Sold
FROM Orders o
JOIN Books b ON o.Book_ID = b.Book_ID
GROUP BY b.Author;

-- 7. Cities with customers spending > 30
SELECT DISTINCT c.City
FROM Customers c
JOIN Orders o ON c.Customer_ID = o.Customer_ID
WHERE o.Total_Amount > 30;

-- 8. Customer who spent the most
SELECT Customer_ID, SUM(Total_Amount) AS Total_Spent
FROM Orders
GROUP BY Customer_ID
ORDER BY Total_Spent DESC
LIMIT 1;

-- 9. Remaining stock after orders
SELECT b.Book_ID, b.Title, b.Stock - COALESCE(SUM(o.Quantity),0) AS Remaining_Stock
FROM Books b
LEFT JOIN Orders o ON b.Book_ID = o.Book_ID
GROUP BY b.Book_ID, b.Title, b.Stock;

🛠️ Tech Stack
-PostgreSQL
-pgAdmin
-SQL

📸 Project Preview

📎 Files Included
-SQL Script
-CSV Dataset
-Project Questions (PDF)
📈 Key Learnings
-Database design & relationships
-CSV data import handling
-Writing optimized SQL queries
-Extracting business insights
🚀 Future Improvements
-Build Power BI Dashboard
-Add stored procedures
-Create web-based UI

👨‍💻 Author

Yogesh Gadekar

📧 yogeshgadekar141@gmail.com
🔗 https://www.linkedin.com/in/yogesh-gadekar-a1231b189

⭐ Support

If you found this project useful, please star the repository!
