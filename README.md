# SQL Programming

## Fundamentals

### Constraints

- **NOT NULL Constraint:** Ensures that a column cannot have NULL value.
- **DEFAULT Constraint:** Provides a default value for a column when none is
specified.
- **UNIQUE Constraint:** Ensures that all values in a column are different.
- **CHECK Constraint:** Makes sure that all values in a column satisfy certain
criteria.
- **Primary Key Constraint:** Used to uniquely identify a row in the table.
- **Foreign Key Constraint:** Used to ensure referential integrity of the data.

### Keys

- A ***primary key*** is used to uniquely identify each row in a table.
- A ***primary key*** can consist of one or more columns on a table.
- When multiple columns are used as a primary key, they are called a
  ***composite key***.
- A ***foreign key*** is a column (or columns) that references a column (most often
the primary key) of another table.
- The purpose of the ***foreign key*** is to ensure referential integrity of the data.

### Create table

``` sql
create table science_class (enrollment_no integer, name varchar, science_mark int);
```

### Table information
```postgres-psql
SELECT table_name, column_name, data_type
FROM information_schema.columns
WHERE table_name = 'customer_table';
```

### Insert into table

#### Single row without column name specified
```postgres-psql
INSERT INTO customer_table 
VALUES (23, 'Sanjiv', 'Katiyar', 123, 'sanjiv.katiyar@gmail.com' );
```

#### Single row with column name specified
```postgres-psql
INSERT INTO customer_table ("age", cust_id, email_id, first_name, last_name)
values ( '23', 234, 'sanjiv.katiyar@gmail.com', 'Sanjiv', 'Katiyar');
```

#### Multiple rows
```postgres-psql
INSERT INTO customer_table 
VALUES (23, 'Sanjiv', 'Katiyar', 123, 'sanjiv.katiyar@gmail.com' ),
(24, 'Sanjiv', 'Katiyar', 123, 'sanjiv.katiyar@gmail.com' ),
(25, 'Sanjiv', 'Katiyar', 123, 'sanjiv.katiyar@gmail.com' ),
(26, 'Sanjiv', 'Katiyar', 123, 'sanjiv.katiyar@gmail.com' );
```

### Import data

#### Import from CSV file

```postgres-psql
COPY customer_table 
FROM 'C:\MyLearning\copy.csv' 
DELIMITER ',' csv header;
```

#### Import from text file

```postgres-psql

COPY customer_table 
FROM 'C:\MyLearning\copytext.txt' 
DELIMITER ',';

```

### Fetch records from table

#### Select all records 
```postgres-psql
SELECT * FROM customer_table;
SELECT first_name FROM customer_table;
SELECT first_name, last_name FROM customer_table;
```

