## JDBC Architecture

- Let us consider a simple example for understanding.
- Imagine you want to order food at a restaurant.
- Then the following is the hierarchy:
    - Waiter : JDBC API
    - Restaurant manager : JDBC Driver manager
    - Food order : SQL Query
    - Prepared food : Result
    - Kitchen : database
    - You(customer) : Java application
    - chef : Database driver
- Now look at the following architecture diagram : 

```
  ┌─────────────────────────────────────────┐
  │         Java Application Layer          │
  └────────────────────┬────────────────────┘
                       │ (Uses standard API interfaces)
  ┌────────────────────▼────────────────────┐
  │              JDBC API Layer             │
  │     (Connection, Statement, etc.)       │
  └────────────────────┬────────────────────┘
                       │ (Manages drivers)
  ┌────────────────────▼────────────────────┐
  │           JDBC Driver Manager           │
  └────────────────────┬────────────────────┘
                       │ (Translates calls)
  ┌────────────────────▼────────────────────┐
  │            JDBC Driver Layer            │
  │  (MySQL Driver, Oracle Driver, etc.)    │
  └────────────────────┬────────────────────┘
                       │ (Database specific protocol)
  ┌────────────────────▼────────────────────┐
  │             Database Layer              │
  └─────────────────────────────────────────┘
```

### 1. Java Application Layer

- This is the program that you write in Java.
- The application wants to reads or store data, but doesn't know how to communicate with a database.

### 2. JDBC API Layer

- JDBC (Java Database Connectivity) is a collection of Java interfaces and classes that provide a standard way to interact with databases.
- The JDBC API doesn't perform database operations itself. Instead, it defines how Java code should ask for them.
- Provides a standard language for Java programs to request database operations.

### 3. JDBC Driver Manager

- DriverManager decides which JDBC driver should be used to connect to the requested database.
- Finds the correct driver and establishes the connection.

### 4. JDBC Driver Layer

- A JDBC driver is software supplied for a specific database. It converts JDBC calls into commands that the target database understands.
- Translates JDBC requests into database-specific communication.

### 5. Database layer

- The database stores information such as users, products, employees, or orders.
- The database is like a warehouse where all inventory is stored.
- Stores, retrieves, updates, and deletes data.
