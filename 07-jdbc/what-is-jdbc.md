# JDBC

- JDBC stands for Java Database Connectivity.
- It is a Standard Java API that allows applications to communicate with the database.
- It provides the classes and interfaces needed to update tables,establish connections and excute SQL queries.


<img width="400" height="328" alt="image" src="https://github.com/user-attachments/assets/dfa17b36-1d56-44cb-a611-04a2786b012a" />



<img width="318" height="159" alt="image" src="https://github.com/user-attachments/assets/d2b9688d-96d0-4661-a2c7-aeeb63b42194" />


- It is a way for Java program to talk with the database.
- JDBC is like a **translator** between your Java application and the database(MySQL, PostgreSQL etc).


#### Real Life Example

Imagine:
- Java Application = Customer
- Database = Restaurant Kitchen
- JDBC = Waiter


The Customer(Java application) cannot directly go into the kitchen(database) for food(data).

so, the waiter(JDBC):
1. Takes the order
2. gives it to kitchen
3. brings back the food


- Same thing happens in Software:
  1. Java sends query using JDBC.
  2. JDBC sends it to the database.
  3. The Database processes it.
  4. JDBC returns the result to Java.


### Why do we need JDBC?

Suppose you are building:
- Banking app
- Student management system
- E-commerce website
- Instagram clone

You need to:
- save data
- read data
- update data
- delete data

This entire data is stored in a database.

Java app or Java cannot directly communicate with databases.

SO JDBC helps Java :
- connect to the database.
- run SQL queries.

### What JDBC Actually Does

Using JDBC, Java can:
  - Connect to database
  - Insert data
  - Fetch data
  - Update data
  - Delete data

These are called CRUD operations:

| Operation | Meaning     |
| --------- | ----------- |
| Create    | Insert data |
| Read      | Fetch data  |
| Update    | Modify data |
| Delete    | Remove data |


### Simple Flow of JDBC

The flow looks like this:

```
Java Application
       ↓
      JDBC
       ↓
 Database
```



> A database driver is a software component that acts as a translator and bridge between your application and a database.




## Main Components of JDBC 

## JDBC – Interview-Ready Definitions

---

### 1. 🚗 Driver

> **"A Driver is a software component that acts as a bridge between a Java application and a specific database by translating JDBC calls into database-specific calls."**

- Implemented by the database vendor (MySQL, Oracle, etc.)
- Loaded using `Class.forName()` or automatically in modern JDBC
- Without it, Java has no idea how to talk to any database

---

### 2. 🔌 Connection

> **"A Connection is an object that represents an active session between the Java application and the database, through which all communication happens."**

- Created via `DriverManager.getConnection(url, user, password)`
- Holds the database URL, credentials, and session state
- Must always be **closed after use** to avoid memory/resource leaks
- One connection = one open channel to the DB

---

### 3. 📝 Statement

> **"A Statement is an interface used to execute SQL queries against the database through an active Connection."**

Three types — know these cold:

| Type | Use Case |
|---|---|
| `Statement` | Static SQL, no parameters |
| `PreparedStatement` | Parameterized SQL, prevents SQL injection ✅ |
| `CallableStatement` | Calls stored procedures in DB |

- `executeQuery()` → for SELECT (returns ResultSet)
- `executeUpdate()` → for INSERT, UPDATE, DELETE (returns int)

---

### 4. 📦 ResultSet

> **"A ResultSet is an object that holds the data returned by a SELECT query, allowing row-by-row iteration using a cursor."**

- Cursor starts **before the first row**
- `rs.next()` moves to the next row, returns `false` when done
- Data is fetched column-wise: `rs.getString("name")`, `rs.getInt("age")`
- By default it is **forward-only** and **read-only**

---

### 🎯 One-line Summary for Each

| Component | One Line |
|---|---|
| **Driver** | Translates Java ↔ Database |
| **Connection** | Opens the session/channel |
| **Statement** | Sends the SQL query |
| **ResultSet** | Holds the query result |

---

### 🔁 The Flow 
*"The Driver registers itself, `DriverManager` uses it to create a `Connection`, a `Statement` is created from that Connection to execute SQL, and the output of a SELECT query is captured in a `ResultSet` which is iterated row by row."*


