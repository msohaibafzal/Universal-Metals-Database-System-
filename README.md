# Universal Metals Ltd. — Database Management System

A relational **Database Management System (DBMS)** developed for **Universal Metals Ltd.** to organize, manage, and retrieve business data efficiently.

The system is designed to handle core business operations including **customers, suppliers, employees, products, purchases, sales, inventory, and payments** through a structured relational database.

---

## 📌 Project Overview

Universal Metals Ltd. requires an organized system for managing its day-to-day business information. Managing customers, suppliers, products, inventory, sales, purchases, and financial transactions manually can lead to data redundancy, inconsistencies, and difficulties in retrieving information.

This project addresses these challenges by designing and implementing a **relational database system** that centralizes business data and establishes relationships between different entities.

The database provides a structured foundation for:

* Customer management
* Supplier management
* Employee management
* Product management
* Inventory tracking
* Purchase management
* Sales management
* Payment and transaction management
* Data retrieval through SQL queries
* Maintaining relationships between business entities

---

## 🎯 Objectives

The main objectives of this project are to:

* Design a structured relational database for Universal Metals Ltd.
* Reduce data redundancy and improve data consistency.
* Maintain accurate records of business entities and transactions.
* Establish appropriate relationships between database tables.
* Implement primary and foreign key constraints.
* Support efficient insertion, modification, deletion, and retrieval of data.
* Provide meaningful SQL queries for business-related information.
* Demonstrate practical application of database design concepts.
* Create a scalable foundation that can be extended into a complete business management system.

---

## 🏢 Business Scenario

The database represents the operations of a metals-related business where different entities interact with one another.

The system maintains information about:

### Customers

Stores customer information and allows sales transactions to be associated with the appropriate customers.

### Suppliers

Maintains supplier records and connects suppliers with purchased products or materials.

### Products

Stores information about products/materials handled by the company, including relevant product details.

### Employees

Maintains employee information and allows business transactions to be associated with responsible employees.

### Purchases

Records purchases made from suppliers and maintains information about purchased products.

### Sales

Records sales made to customers and maintains information about sold products.

### Inventory

Tracks the availability of products/materials within the company.

### Payments

Maintains payment-related information associated with business transactions.

---

## 🗄️ Database Design

The system follows a **relational database model**, where information is divided into logically related tables.

Relationships between entities are implemented using:

* **Primary Keys (PK)**
* **Foreign Keys (FK)**
* **One-to-One relationships**
* **One-to-Many relationships**
* **Many-to-Many relationships**, where applicable through associative tables

This structure helps maintain **referential integrity** and prevents unnecessary duplication of data.

---

## 🔗 Entity Relationships

The major relationships within the system can be summarized as follows:

```text
Customers
    │
    │
    ▼
   Sales ───────────► Products
    │                   │
    │                   │
    ▼                   ▼
Payments             Inventory


Suppliers
    │
    │
    ▼
 Purchases ─────────► Products


Employees
    │
    ├──────────────► Sales
    │
    └──────────────► Purchases
```

The exact relationships and cardinalities are implemented according to the database schema and ER design included in the project.

---

## 🧩 Main Database Components

### 1. Customer Management

Customer records allow the company to maintain important customer information and associate customers with their sales transactions.

Typical operations include:

* Adding customers
* Updating customer information
* Searching customers
* Retrieving customer transaction history

---

### 2. Supplier Management

Supplier records allow the organization to maintain information about businesses or individuals supplying products/materials.

The supplier data can be used to:

* Track suppliers
* Associate suppliers with purchases
* Retrieve supplier-related transactions
* Maintain supplier information

---

### 3. Product Management

Products represent the materials or goods handled by Universal Metals Ltd.

The product component supports:

* Product identification
* Product information storage
* Product pricing
* Inventory association
* Sales and purchase relationships

---

### 4. Inventory Management

Inventory records allow the company to track the availability of products/materials.

Inventory-related operations can include:

* Checking available stock
* Updating quantities
* Identifying products
* Monitoring inventory levels

---

### 5. Sales Management

The sales component records transactions involving customers.

A sales transaction can be associated with:

* Customer
* Employee
* Product
* Quantity
* Price
* Transaction date
* Payment information

This provides a structured way to maintain sales history.

---

### 6. Purchase Management

Purchase records represent transactions made with suppliers.

Purchases can be associated with:

* Supplier
* Employee
* Product
* Quantity
* Purchase price
* Purchase date

This allows the organization to maintain a history of procurement activities.

---

### 7. Employee Management

Employee information allows transactions to be associated with the employee responsible for a particular business operation.

Employee records can include relevant identification and organizational information.

---

### 8. Payment Management

The payment component maintains financial transaction information and provides a relationship between payments and relevant business transactions.

---

# 🛠️ Technologies Used

| Technology                    | Purpose                                         |
| ----------------------------- | ----------------------------------------------- |
| **SQL**                       | Database creation, manipulation, and querying   |
| **Relational Database Model** | Structured storage of business data             |
| **ER Modeling**               | Database design and relationship modeling       |
| **Primary & Foreign Keys**    | Entity identification and referential integrity |
| **SQL Queries**               | Data retrieval and analysis                     |
| **Normalization**             | Reducing redundancy and improving consistency   |

---

# 📂 Repository Structure

```text
Universal-Metals-Database-System/
│
├── README.md
│
├── database/
│   ├── schema.sql
│   ├── tables.sql
│   ├── data.sql
│   └── queries.sql
│
├── diagrams/
│   └── ERD.png
│
└── documentation/
    └── Database_Report.pdf
```

> The exact filenames may vary depending on the files included in the repository.

---

# 🧱 Database Implementation

The database implementation follows a structured workflow.

### Step 1 — Database Creation

The required database environment is created before defining the tables.

### Step 2 — Table Creation

Tables are created according to the designed relational schema.

### Step 3 — Constraints

Constraints are used to maintain data integrity, including:

* Primary keys
* Foreign keys
* Unique constraints
* NOT NULL constraints
* Other appropriate validation rules

### Step 4 — Data Population

Sample records are inserted into the database to demonstrate how the system operates with realistic business data.

### Step 5 — SQL Queries

SQL queries are used to retrieve useful business information from the database.

---

# 🔍 SQL Query Examples

The project demonstrates different categories of SQL operations.

### Basic Retrieval

```sql
SELECT *
FROM Customers;
```

### Filtering

```sql
SELECT *
FROM Products
WHERE Price > 1000;
```

### Sorting

```sql
SELECT *
FROM Products
ORDER BY Price DESC;
```

### Aggregation

```sql
SELECT SUM(Amount) AS TotalSales
FROM Sales;
```

### Grouping

```sql
SELECT CustomerID, SUM(Amount) AS TotalSpent
FROM Sales
GROUP BY CustomerID;
```

### Joining Tables

```sql
SELECT
    c.CustomerName,
    s.SaleDate,
    s.Amount
FROM Customers c
JOIN Sales s
    ON c.CustomerID = s.CustomerID;
```

These examples illustrate how relational data can be combined to generate useful business information.

---

# 📊 Business Questions Supported

The database can be queried to answer questions such as:

* What products are currently available?
* Which customers have made purchases?
* What are the company's sales transactions?
* Which suppliers provide particular products?
* How much has been sold during a given period?
* Which products have the highest sales?
* What is the purchase history of a supplier?
* What is the transaction history of a customer?
* How much inventory is available?
* What payments have been recorded?
* Which employees are associated with particular transactions?

---

# 🔐 Data Integrity

Data integrity is maintained through appropriate database constraints and relationships.

### Entity Integrity

Each major entity has a unique identifier implemented through a primary key.

### Referential Integrity

Foreign keys connect related entities and prevent invalid references between tables.

### Domain Integrity

Appropriate data types and constraints are used to ensure that stored values follow the intended structure.

---

# 📐 Database Normalization

The database design applies relational database normalization principles to reduce:

* Data redundancy
* Update anomalies
* Insertion anomalies
* Deletion anomalies

Related information is separated into appropriate entities while relationships between those entities are maintained using keys.

The design aims to keep each table focused on a specific type of business information.

---

# 🚀 How to Use

## 1. Clone the Repository

```bash
git clone https://github.com/msohaibafzal/Universal-Metals-Database-System-.git
```

## 2. Open the Project

```bash
cd Universal-Metals-Database-System-
```

## 3. Set Up the Database

Open the SQL files provided in the repository using your supported database management system.

Execute the database/schema scripts in the appropriate order.

## 4. Insert Sample Data

Run the provided data insertion scripts to populate the database with sample records.

## 5. Run Queries

Execute the SQL queries provided in the project to test database functionality and retrieve business information.

---

# 💡 Key Database Concepts Demonstrated

This project demonstrates practical understanding of:

* Relational database design
* Entity-Relationship modeling
* Database normalization
* Primary keys
* Foreign keys
* Referential integrity
* SQL DDL
* SQL DML
* SELECT queries
* WHERE conditions
* ORDER BY
* GROUP BY
* Aggregate functions
* JOIN operations
* Database constraints
* Business-oriented data modeling
* Transactional data management

---

# 🎓 Project Context

This project was developed as a practical implementation of **Database Management System** concepts, focusing on applying relational database principles to a realistic business scenario.

Rather than treating the database as an isolated collection of tables, the project models relationships between customers, suppliers, products, employees, transactions, inventory, and payments to represent a connected business environment.

---

# 👨‍💻 Author

**Muhammad Sohaib Afzal**

Computer Engineer | Automation & Intelligent Systems | AI/ML/DL

* GitHub: [msohaibafzal](https://github.com/msohaibafzal)
* LinkedIn: [Muhammad Sohaib Afzal](https://www.linkedin.com/in/msohaibafzal/)

---
