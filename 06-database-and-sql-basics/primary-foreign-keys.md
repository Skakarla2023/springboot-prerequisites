## Primary Key

- A **primary key** is a column (or combination of columns) whose value uniquely identifies each row in a table.

It’s like:

- Aadhaar number for citizens
- Roll number for students
- Employee ID in a company

> No two rows can have the same primary key value.

- observe the following table:

| StudentID | Name  | Age |
| --------- | ----- | --- |
| 101       | Ravi  | 20  |
| 102       | Priya | 21  |
| 103       | Arjun | 19  |

- here **StudentID** is the primary key
- Every student has a unique ID.


### Rules for primary key

- Primary key can't be null.
- It must be unique.
- It should not change frequently.


```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Gender VARCHAR(20)
);
```

- Here studentID is the primary key of the table.


## Foreign Key

- A **foreign key** is a column in one table that refers to the primary key in another table.
- It creates a relationship between tables.
- Think of it like:
  - a reference
  - a link
  - a connection
 
**Example:**


Imagine:
  - One table stores students
  - Another table stores courses

Instead of writing full student details repeatedly, we use the student’s ID.


#### Student's table

| StudentID | Name  |
| --------- | ----- |
| 101       | Ravi  |
| 102       | Priya |

here `StudentID` is the primary key.


#### Courses table

| CourseID | CourseName | StudentID |
| -------- | ---------- | --------- |
| C1       | Java       | 101       |
| C2       | Python     | 102       |
| C3       | DBMS       | 101       |

- In this table `StudentID` is the foreign key.
- It points to `Student.StudentID`.
- Observe the following SQL code:

```sql
CREATE TABLE Courses (
    CourseID VARCHAR(10) PRIMARY KEY,
    CourseName VARCHAR(50),
    StudentID INT,
    FOREIGN KEY (StudentID)
        REFERENCES Students(StudentID)
);
```

#### Primary key VS Foreign key

| Feature             | Primary Key              | Foreign Key           |
| ------------------- | ------------------------ | --------------------- |
| Purpose             | Uniquely identifies rows | Connects tables       |
| Duplicates Allowed? | ❌ No                     | ✅ Yes                 |
| NULL Allowed?       | ❌ No                     | ✅ Usually yes         |
| Number per Table    | Usually one PK           | Multiple FKs possible |
| Exists In           | Parent table             | Child table           |
