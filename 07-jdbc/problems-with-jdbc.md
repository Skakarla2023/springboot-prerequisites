# Problems with JDBC

- JDBC(Java Database Connectivity) is a Java API that acts as a translator between the application and the database.
- It converts java program into database specific commands that the database can understand.
- It provides methods to establish database connections, execute SQL queries, retrieve results, and manage transactions.
- Although JDBC is powerful, flexible and widely used, it has several limitations.
- These limitations become more noticeable while developing large scale applications.



### 1. Boilerplate(Repetitive Code) Code

- One of the biggest problems with JDBC is that you have to write repetitive code for every single database operation.
- Which means for every operation, you have to:
  - Establish JDBC Connection.
  - Create a Statement or PreparedStatement.
  - Prepare the SQL query.
  - Execute the SQL query.
  - Create a ResultSet.
  - Process the Resultset.
  - Close all resources.
 

**Why is it a Problem?**

1. Makes problems lengthy.
2. Increases development time.
3. Same code is repeated everywhere.
