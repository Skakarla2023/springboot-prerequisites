# SQL CRUD Queries


- CRUD stands for create, read, update, delete.
- Every operation that you do with data in the database maps to one of these four actions.
- SQL CRUD operations are:
  - create : insert
  - read : select
  - update
  - delete
 

- Observe the following SQL Codes:


### 1. CREATE

```sql
create table students(name varchar, age int, gender varchar);
insert into students values('Satwika',19,'female');
insert into students values('Ram',20,'male');
insert into students values('Anikha',18,'female'),('Arya',22,'male');

select * from students;
```

Output:

<img width="904" height="298" alt="image" src="https://github.com/user-attachments/assets/f08a391d-bf8a-4ca7-a079-a4333d3bb44d" />



### 2.READ

```sql
select * from students;
```

Output:

<img width="911" height="309" alt="image" src="https://github.com/user-attachments/assets/1059077d-7cbf-48ff-a786-3248273e86ca" />


### 3. UPDATE

```sql
UPDATE students set age=22 WHERE name='Anikha';
select * from students;
```

Output:

<img width="905" height="296" alt="image" src="https://github.com/user-attachments/assets/1c6f7fac-aee8-4e7c-9ed0-01d50522cb2c" />


### 4.DELETE

```sql
DELETE FROM students WHERE name = 'Ram';
select * from students;
```

Output:

<img width="902" height="258" alt="image" src="https://github.com/user-attachments/assets/c84c50c4-c4bd-40c9-9c8b-9e0912b9e747" />
