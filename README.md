# Car Wash Database Management System

# Overview
The Car Wash Data Management System was designed to help Terrible's car wash business expanding into a new location. 
The system assists day-to-day operations by handling customer information, transactions, and inventory management. In conjunction with 
SQL, the data management system will be able to provide real-time insights through reports. 

_Note: All data used in this project is fictional and created soley for demonstration purposes._

# Tools and Techniques Used
- MySQL (Database design & SQL Queries)
- Lucid (Entity Relationship Modeling)

# Logical Schema

The system is designed with a relational database using SQL. Key entities include:

- **Customer** (Cusomter_ID, First_Name, Last_Name, Email, Phone_No)

- **Vehicle** (License_Plate, Make, Model, Year, Color, Customer_ID)

- **Employee** (Emp_ID, Name, Address, Phone_No, Salary)

- **Location** (Store_No, Address, Phone_No)

- **Service** (Service_ID, Wash_Type, Price)

- **Supplies** (Item_No, Item_Name, Quantity)

- **Transaction** (Trans_ID, Date, Total_Cost, Emp_ID, Store_No)

# Acknowledgements
This project was developed as part of IS 475. Special thanks to the team for their contributions:
- Anabel Aguilar
- Benjamin Oliphant
- Meagan Timmons

# Further Exploration
This segment further explores the DBMS using MySQL, Python, and data visualization tools. The goal is to query, clean, and visualize data efficiently and
compile graphs into a PDF report. 

# Highlights
- Connected to a local MySQL server using the MySQL extention in VSCode.
- Queried data into Pandas DataFrames for analysis and visualization.
- Performed data cleaning to prepare datasets for visualization.
- Created visualizations using Matplotlib.
- Compiled graphs and results into a PDF report using FPDF.


# Sample Querie
**Outputs the most popular service by year**
```
SELECT 
    YEAR(t.Date) AS Year, 
    s.Wash_Type, 
    COUNT(ts.Service_ID) AS Times_Bought
FROM `TRANSACTION` t
JOIN TRANSACTION_SERVICE ts ON t.Trans_ID = ts.Trans_ID
JOIN SERVICE s ON ts.Service_ID = s.Service_ID
GROUP BY YEAR(t.Date), s.Wash_Type
ORDER BY Year, Times_Bought DESC;
```
![Wash Type Comparison](https://github.com/user-attachments/assets/9def42b6-f0db-4215-b5e6-922abae7b7a4)


