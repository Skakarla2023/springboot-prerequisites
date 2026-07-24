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


### 5. Manual Mapping Between Database and Java Objects

- JDBC returns query results as a ResultSet.
- Developers must manually extract each column and assign it to Java object fields.
- Every column has to be mapped using methods like:
  - `getInt()`
  - `getString()`
  - `getDouble()`
  - `getDate()`
- This mapping code must be written for every query.


### 6. No Object-Oriented Support

- Relational databases store data in tables.
- Java applications work with objects.
- JDBC deals only with SQL and `ResultSet` objects.
- It does not automatically convert database records into Java objects.



### 7. Difficult Transaction Management

- In transactions multile database operations are executed as a single unit.
- In JDBC, the developer has to manually:
  - Disable auto-commit.
  - Save the transaction automatically.
  - Rollback the transaction if any error occurs.
- Proper transaction handling requires additional code.


 ### 8. Difficult to Manage large applications

 - As the application size increases, code becomes scattered in multiple classes.
 - 
