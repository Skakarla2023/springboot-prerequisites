## JDBC CRUD

### What is JDBC?

- JDBC stands for Java Database Connectivity.
- It is a Java API, that allows a Java program to connect with the database and perform operations like storing, updating, reading and deleting data.
- It acts like a bridge that connects Java program with the database.

### Why do we need JDBC?

**Without JDBC:**

- Java cannot communicate with the databases.
- Everytime the program closes, all data would be lost.
- We cannot store permanent data.

**With JDBC:**

- Save and store every record.
- Login using username and password.
- Manage bank accounts.


## What is CRUD?

- `CRUD` is a shortform for four basic operations.

| Letter | Meaning | Purpose              |
| ------ | ------- | -------------------- |
| C      | Create  | Add new data         |
| R      | Read    | View existing data   |
| U      | Update  | Modify existing data |
| D      | Delete  | Remove data          |

## CRUD using JDBC

- Using JDBC, java performs CRUD operations by sending SQL queries to the database.

```
Java Program
      │
      ▼
    JDBC
      │
      ▼
  SQL Database
```

### Create

- `create` means inserting new data into the database.
- SQL used : `INSERT INTO`.

**Eg:**
```sql
INSERT INTO Student(id, name, age)
VALUES(2, 'Priya', 21);
```

**What happens inside?**

1. Java connects to the database.
2. SQL query is created.
3. JDBC sends the query.
4. Query is executed at the database(new record is created).
5. New record is successfully added.

### Read

- `Read` means retreiving data from the database.
- SQL used : `SELECT`

**Eg**: 
```sql
SELECT * FROM student;
```

**What happens?**

1. Java sends a SELCT query.
2. Database returns matching rows.
3. ResultSet stores those rows.
4. Java reads one row at a time.
5. Data is displayed.


### Update

- `Update` means modifying existing data.
- SQL used : `UPDATE`.

**Eg**:

```sql
UPDATE Student
SET age = 21
WHERE id = 1;
```

**What happens?**

1. Java connects to the database.
2. SQL UPDATE query is prepared.
3. Database finds the matching record.
4. Database changes the value.
5. Updated record is saved.

### Delete

- `Delete` means removing exisitng data from the database.
- SQL used: `DELETE`.

**Eg:**

```sql
DELETE FROM Student
WHERE id = 1;
```

**What happens?**

1. Java connects to the database.
2. Delete query is send.
3. Database searches for the record.
4. It deletes the matching record.
5. Changes are saved.

### Common JDBC Classes used in CRUD

| Class/Interface     | Purpose                                                   |
| ------------------- | --------------------------------------------------------- |
| `DriverManager`     | Establishes a connection with the database                |
| `Connection`        | Represents the connection between Java and the database   |
| `Statement`         | Executes simple SQL queries                               |
| `PreparedStatement` | Executes parameterized SQL queries safely and efficiently |
| `ResultSet`         | Stores the data returned by a `SELECT` query              |


### JDBC CRUD flow

```
Java Program
      │
      ▼
Load JDBC Driver (optional for modern JDBC)
      │
      ▼
Create Connection
      │
      ▼
Create Statement / PreparedStatement
      │
      ▼
Write SQL Query
      │
      ▼
Execute SQL Query
      │
      ▼
Receive Result (if SELECT)
      │
      ▼
Close Resources
```



### Why is `PreparedStatement` preferred over `Statement`?

- Although the examples above use Statement because they are easy to understand, in real applications PreparedStatement is **preferred**.

**Advantages** of PreparedStatement
- Prevents **SQL Injection** attacks.
- Executes faster when the same query runs multiple times.
- Easier to pass user input into SQL queries.
- Automatically handles proper formatting of values.




### JDBC CRUD Program

```java
import java.sql.*;

public class JDBCCRUDExample {

    public static void main(String[] args) {

        // Database details
        String url = "jdbc:mysql://localhost:3306/college";
        String username = "root";
        String password = "password";

        try {

            // Step 1: Establish Connection
            Connection con = DriverManager.getConnection(url, username, password);

            // Step 2: Create Statement
            Statement st = con.createStatement();



            // ==========================================================
            // CREATE OPERATION
            // Used to insert (add) a new record into the database.
            // SQL Command Used : INSERT
            // ==========================================================

            String insertQuery =
                    "INSERT INTO Student(id, name, age) VALUES(3, 'Amit', 22)";

            st.executeUpdate(insertQuery);

            System.out.println("Record Inserted Successfully.");




            // ==========================================================
            // READ OPERATION
            // Used to retrieve (display) records from the database.
            // SQL Command Used : SELECT
            // ==========================================================

            String selectQuery = "SELECT * FROM Student";

            ResultSet rs = st.executeQuery(selectQuery);

            System.out.println("\nStudent Records:");

            while (rs.next()) {
                System.out.println(
                        rs.getInt("id") + "  " +
                        rs.getString("name") + "  " +
                        rs.getInt("age")
                );
            }




            // ==========================================================
            // UPDATE OPERATION
            // Used to modify existing records in the database.
            // SQL Command Used : UPDATE
            // ==========================================================

            String updateQuery =
                    "UPDATE Student SET age = 23 WHERE id = 3";

            st.executeUpdate(updateQuery);

            System.out.println("\nRecord Updated Successfully.");




            // ==========================================================
            // DELETE OPERATION
            // Used to remove records from the database.
            // SQL Command Used : DELETE
            // ==========================================================

            String deleteQuery =
                    "DELETE FROM Student WHERE id = 3";

            st.executeUpdate(deleteQuery);

            System.out.println("Record Deleted Successfully.");



            // Step 3: Close Resources
            rs.close();
            st.close();
            con.close();

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Output:

```
Record Inserted Successfully.

Student Records:
1 Rahul 20
2 Priya 21
3 Amit 22

Record Updated Successfully.
Record Deleted Successfully.
```
