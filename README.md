# 📚 Online Book Store - SQL Project  

![SQL](https://img.shields.io/badge/SQL-PostgreSQL-blue?style=for-the-badge&logo=postgresql)
![Project](https://img.shields.io/badge/Project-Data%20Analytics-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 🚀 Project Overview  
This project demonstrates the creation and analysis of an **Online Book Store database** using SQL.  
It includes database design, CSV data import, and solving real-world business queries.

<p align="center">
  <img src="https://raw.githubusercontent.com/GADEKAR328/SQL_Project_Online_Book_Store/c4cbd3b85bfe695e54452fb4b2e89ce14e011a3f/book%20store%20banner%20SQL%20Project.jpg" width="900"/>
</p>

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

- Created database: **Online_Book_Store**
- Designed 3 main tables:
  - Books
  - Customers
  - Orders
- Established relationships using **Primary Keys & Foreign Keys**

---

## 📥 Data Import  

Data was imported from CSV files using **pgAdmin Import Tool**.

### Steps:
- Open pgAdmin  
- Navigate → Schemas → Tables  
- Right-click table → Import/Export Data  
- Select CSV file  
- Enable **Header option**  
- Import data successfully  

---

## 📊 Operations Performed  

### 🔹 Data Retrieval
- Filtered books by genre and year  
- Extracted customer location-based data  
- Retrieved time-based order records  

### 🔹 Data Analysis
- Calculated total stock and revenue  
- Identified most expensive and least stocked books  
- Analyzed customer purchase behavior  

### 🔹 Advanced Insights
- Books sold per genre  
- Most frequently ordered books  
- Top customers based on spending  
- Sales distribution by author and city  
- Remaining inventory after fulfilling orders  

---

## 🛠️ Tech Stack  
- PostgreSQL  
- pgAdmin  
- SQL  

---

## 📎 Files Included  
- SQL Script (Complete Queries)  
- CSV Dataset  
- Project Questions (PDF)  

---

## 📈 Key Learnings  
- Database design & normalization  
- Handling real-world CSV data  
- Writing efficient SQL queries  
- Generating business insights from data  

---

## 🚀 Future Improvements  
- Build interactive dashboard (Power BI / Tableau)  
- Add stored procedures & triggers  
- Deploy as web-based application  

---

## 👨‍💻 Author  

**Yogesh Gadekar**  

📧 yogeshgadekar141@gmail.com  
🔗 https://www.linkedin.com/in/yogesh-gadekar-a1231b189  

---

## ⭐ Support  
If you found this project useful, please star the repository!
