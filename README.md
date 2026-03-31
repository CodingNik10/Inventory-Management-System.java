# Inventory-Management-System.java
This project is a JavaFX-based Inventory Management System that connects to a MySQL database and displays product details (ID, price, stock) in a table using a clean UI.

# Project Overview

The Inventory Management System is a desktop application built using:
  -JavaFX (for UI)
  -JDBC (for database connectivity)
  -MySQL (for storing inventory data)
It retrieves product data from a database and displays it in a structured table format.

# Features
View all inventory items
Displays:
   -Product ID
   -Price
   -Stock Quantity
   -Real-time database fetching
   -Simple and clean UI

# Requirements
Software Required:
  -Java JDK 8 or above
  -JavaFX SDK
  -MySQL Server
  -MySQL Workbench (optional)
  -IDE (IntelliJ / Eclipse / VS Code)

# Database Setup
Step 1: Create Database
CREATE DATABASE inventory;
USE inventory;

Step 2: Create Table
CREATE TABLE products (
    product_id VARCHAR(50),
    price DOUBLE,
    stock INT
);

Step 3: Insert Sample Data
INSERT INTO products VALUES
('P101', 500.0, 10),
('P102', 1200.5, 5),
('P103', 300.75, 20);

# Configure Database Connection

In InventoryDAO.java, update:

private static final String DB_URL = "jdbc:mysql://localhost:3306/inventory";
private static final String USER = "root";
private static final String PASS = "";

✔ Set your MySQL username & password

# How to Run
Step 1:
Add JavaFX SDK to your project

Step 2:
Add MySQL Connector JAR

Step 3:
Run MainApp.java

Step 4:
Application window opens → data loads automatically

#  Code Architecture

📦 Project Structure
│
├── InventoryItem.java     → Model Class
├── InventoryDAO.java      → Database Access Layer
├── MainApp.java           → UI & Controller


🔹 Explanation:
1. InventoryItem (Model)
 -Represents a product
 -Uses JavaFX properties:
      -id
      -price
      -stock
   
2. InventoryDAO (Data Access Object)
 -Handles database operations
 -Connects to MySQL
 -Fetches product data

3. MainApp (UI Layer)
 -Builds JavaFX UI
 -Displays data in TableView
 -Calls DAO to fetch data

# Application Flow

Start Application
       ↓
Initialize UI (TableView)
       ↓
Call loadData()
       ↓
DAO connects to DB
       ↓
Execute SQL Query
       ↓
Fetch ResultSet
       ↓
Convert to Objects
       ↓
Display in Table

# Flowchart

+------------------+
|  Start Program   |
+------------------+
         ↓
+------------------+
| Initialize UI    |
+------------------+
         ↓
+------------------+
| Call loadData()  |
+------------------+
         ↓
+----------------------+
| Connect to Database  |
+----------------------+
         ↓
+----------------------+
| Execute SQL Query    |
+----------------------+
         ↓
+----------------------+
| Fetch Data (Result)  |
+----------------------+
         ↓
+----------------------+
| Convert to Objects   |
+----------------------+
         ↓
+----------------------+
| Display in Table     |
+----------------------+
         ↓
+------------------+
|      End         |
+------------------+

# Pseudocode

CLASS InventoryItem
    DEFINE id, price, stock
    CONSTRUCTOR initialize values

CLASS InventoryDAO
    FUNCTION getItems()
        CONNECT to database
        EXECUTE query "SELECT * FROM products"
        FOR each record
            CREATE InventoryItem object
            ADD to list
        RETURN list

CLASS MainApp
    FUNCTION start()
        CREATE table columns
        ADD columns to table
        DISPLAY UI
        CALL loadData()

    FUNCTION loadData()
        CALL DAO.getItems()
        SET table data

        
# Error Handling
-If database fails → error dialog shown
-Handles SQL exceptions properly

# Future Improvements
-Add product (Insert)
-Update product
-Delete product
-Search functionality
-Dashboard with analytics

# Author
Nikhil Kumar
22BME10002


 
