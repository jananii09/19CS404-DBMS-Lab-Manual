# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

## Question 1

<img width="1208" height="286" alt="image" src="https://github.com/user-attachments/assets/f0f9f557-ede4-4b81-ab89-5d0257077f1b" />

## Syntax
```
create table Attendance (AttendanceID integer primary key,EmployeeID integer,
AttendanceDate date,Status TEXT CHECK (Status IN ('Present','Absent','Leave')),foreign key(EmployeeID)REFERENCES Employees(EmployeeID))
```

## Output:

<img width="787" height="182" alt="image" src="https://github.com/user-attachments/assets/9a01e6ed-f25f-43c1-a1d6-10ab5a6428fe" />


## Question 2

<img width="927" height="356" alt="image" src="https://github.com/user-attachments/assets/aadd65c3-b51e-444b-b67e-d29cb437d6d4" />

## Syntax
```
create table Locations(LocationID  INTEGER,LocationName TEXT,Address TEXT);
```
## Output:

<img width="1210" height="326" alt="image" src="https://github.com/user-attachments/assets/dd9ee074-ed0f-4fbb-ab4c-bd55c4259f20" />


## Question 3

<img width="1133" height="273" alt="image" src="https://github.com/user-attachments/assets/261cc9ea-548f-46dc-b62b-b6c027767405" />

## Syntax
```
create table Shipments(ShipmentID INTEGER primary key, ShipmentDate DATE,SupplierID INTEGER,OrderID INTEGER, 
foreign key(SupplierID) references Suppliers(SupplierID), foreign key (OrderID) references Orders(OrderID));
```
## Output:

<img width="638" height="142" alt="image" src="https://github.com/user-attachments/assets/75392f06-298d-4d8c-b03d-7453aa924ef5" />


## Question 4

<img width="1236" height="426" alt="image" src="https://github.com/user-attachments/assets/07f16a4b-bb8b-4d3d-9013-2af9b2d56472" />

## Syntax
```
ALTER table Companies
add column designation varchar(50);
alter table Companies
add column net_salary number;
```

## Output:

<img width="1165" height="317" alt="image" src="https://github.com/user-attachments/assets/245d2e4f-a10e-4cf5-93cf-b8d5ac2cec4f" />


## Question 5

<img width="1028" height="204" alt="image" src="https://github.com/user-attachments/assets/22c5e67b-02fc-48c2-934a-8c65a05af6b8" />

## Syntax
```
insert into Customers(CustomerID , Name ,Address, City ,ZipCode)values(301,'Michael Jordan','123 Maple St','Chicago',60616);
```

## Output:

<img width="1074" height="140" alt="image" src="https://github.com/user-attachments/assets/2798331f-ee45-4703-96f8-4c9cccf7d9ce" />


## Question 6

<img width="1237" height="277" alt="image" src="https://github.com/user-attachments/assets/64629d1d-6dfd-4c68-9686-0b34ca014953" />

## Syntax
```
create table ProjectAssignments(AssignmentID  INTEGER primary key,EmployeeID INTEGER,ProjectID INTEGER,AssignmentDate DATE not null,
foreign key(EmployeeId) references Employees(EmployeeID),foreign key(ProjectID) references  Projects(ProjectID));
```

## Output:

<img width="887" height="178" alt="image" src="https://github.com/user-attachments/assets/1334595d-a314-4533-b3d4-bb21f649f971" />


## Question 7

<img width="1037" height="474" alt="image" src="https://github.com/user-attachments/assets/123e4dac-aebf-49a9-88bd-2eddc6e49214" />

## Syntax
```
alter table customer
rename column city to location;
```
## Output:

<img width="1188" height="250" alt="image" src="https://github.com/user-attachments/assets/9033f8f7-4976-4a40-bbc7-f920ab525f51" />


## Question 8

<img width="1267" height="363" alt="image" src="https://github.com/user-attachments/assets/dee229b8-e9c5-4098-9923-152db9dd5715" />

 ## Syntax
```
insert into Student_details(RollNo  ,    Name  ,        Gender   ,   Subject  ,   MARKS)
values(205 ,        'Olivia Green',    'F',null,null);
insert into Student_details(RollNo  ,    Name  ,        Gender   ,   Subject  ,   MARKS)
values(207 ,        'Liam Smith',      'M' ,          'Mathematics',  85);
insert into Student_details(RollNo  ,    Name  ,        Gender   ,   Subject  ,   MARKS)
values(208 ,        'Sophia Johnson',  'F',           'Science',null);
```
## Output:

<img width="938" height="183" alt="image" src="https://github.com/user-attachments/assets/92feb2ce-6a2e-4acf-a853-db1acef1c1a1" />


## Question 9

<img width="1085" height="285" alt="image" src="https://github.com/user-attachments/assets/c0e79b2d-102c-4969-b3de-678adf0e3aaf" />

## Syntax
```
create table Products(
ProductID  INTEGER primary key,
ProductName TEXT not null unique,
Price real check (Price>0),
StockQuantity INTEGER check (StockQuantity>=0)
);
```

## Output:

<img width="800" height="152" alt="image" src="https://github.com/user-attachments/assets/8d7dd32a-4293-43b6-a442-15bc1c5609d0" />


## Question 10

<img width="573" height="263" alt="image" src="https://github.com/user-attachments/assets/f75ae209-db1a-45bb-826f-72e580619731" />

## Syntax
```
insert into Products(ProductID  , ProductName ,    Price    ,   Stock)
select ProductID  , ProductName  ,   Price    ,   Stock
from Discontinued_products;
```
## Output:

<img width="769" height="173" alt="image" src="https://github.com/user-attachments/assets/fdebcb0a-7d5e-42a1-9af2-89c07a993058" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
