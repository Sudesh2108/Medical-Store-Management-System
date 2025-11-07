# Real-Time Pharmaceutical Inventory System 

# 💊 Real-Time Pharmaceutical Inventory System 

A desktop application built in Java for managing stock, sales, and reporting for a medical store.

---

## ✨ Features

* **Stock Management:** Track inventory with details like product code, name, quantity, rate, MRP, and expiry date.
* **Sales/Billing:** Functionality to add items to a cart, calculate total price, and manage sales.
* **Reporting:** Generate reports on sales transactions.
* **User Authentication:** Secure login system with an **Admin** user.
* **Database Integration:** Uses Oracle SQL for persistent data storage.

---

## 💻 Technologies Used

* **Language:** Java
* **Database:** Oracle SQL
* **Libraries:** Java Swing (for GUI), JDBC (`ojdbc8.jar`)

---

## 🛠️ Project Setup and Installation

Follow these steps to get the project running locally.

### 1. Database Setup

This project requires an Oracle database instance.

1.  **Run the SQL Scripts:** Connect to your Oracle database using a tool like SQL Developer or SQL*Plus. Execute the DDL (Data Definition Language) statements found in the **`Table.lst`** file to create the necessary tables.
    ```sql
    -- Example from Table.lst
    Create table StockTable
    (
    	code varchar2(20) primary key,
    	name varchar2(40),
    	quant number(5),
    	rate number(5,2),
    	mrp number(5,2),
    	exp varchar2(20)
    );
    -- ... and other tables
    ```
2.  **Update Connection Details:** Open **`Medical.java`** and modify the `connect` class's `aconnect()` method to use your specific Oracle database connection URL, username, and password.

### 2. Compilation and Execution

1.  **Ensure JDBC Driver:** Make sure the **`ojdbc8.jar`** file is included in your Java project's classpath during compilation and execution.
    * *If using a simple command line:*
        ```bash
        javac -cp ".;ojdbc8.jar" Medical.java
        ```
        (Note: The classpath separator might be different on Linux/macOS, usually a colon `:`)
2.  **Run the Application:**
    * *If using a simple command line:*
        ```bash
        java -cp ".;ojdbc8.jar" Medical
        ```
    * *Alternatively, use the batch file:* You can run the **`p.bat`** file if your setup matches the paths specified within it.

---

## 🔑 Default Credentials

The initial Admin user credentials for testing are defined in the source code:

| Role | Username | Password | Auth Number |
| :--- | :--- | :--- | :--- |
| **Admin** | `superuser` | `medicaluser` | `Medical1234` |

---

## 📁 File Structure Overview

| File Name | Description |
| :--- | :--- |
| **`Medical.java`** | The main Java source file containing the application logic, GUI classes, and database connection logic. |
| **`Table.lst`** | Contains all the SQL DDL statements to create the necessary tables (e.g., `StockTable`, `InsertCart`, `SignUpTable`). |
| **`ojdbc8.jar`** | The **Oracle JDBC Driver** needed for Java to connect and interact with the Oracle database. |
| **`p.bat`** | A simple Windows batch script to compile and run the Java application (may need path adjustments). |
| **`Picture1.jpg`** | An image file, likely used for the application's GUI or as a placeholder. |
