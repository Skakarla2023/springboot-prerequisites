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


### 2. Manual Resource Management

- JDBC does not automatically close database resources.
- The programmer must manually close:
  - Connection
  - Statement
  - PreparedStatement
  - ResultSet
 
- If resources are not closed properly, memory leaks can occur.


**Why is it a Problem?**

- Memory leaks happen.
- Connection leaks happen.
- Application crashes under heavy load.


### 3. Poor Exception Handling

- JDBC throws checked exceptions like: SQLException.
- Developer must handle every possible daabase error manually.
- Sometimes multiple nested try-catch blocks are required.


**Why is it a Problem?**

- Complex error handling.
- Difficult debugging.

### 4. Database Dependency

- Different databases use different SQl syntax.
- Although SQL is standardised, many commands differ between databases.
- A JDBC application written for one database may require changes to work with another.
- Database specific functions or comands may differ.
