DDL, DML & DQL Commands

DDL

DDL (Data Definition Language) is used to define, create, and modify the structure of database objects.

1. "CREATE"

Used to create a new database or table.

CREATE TABLE students (
    id INT,
    name VARCHAR(50)
);

Example: Creates a "students" table.

2. "ALTER"

Used to modify the structure of an existing table.

ALTER TABLE students ADD email VARCHAR(100);

Example: Adds an "email" column to the "students" table.

3. "DROP"

Used to permanently delete a table or database.

DROP TABLE students;

Example: Deletes the "students" table.

4. "TRUNCATE"

Used to remove all records from a table while preserving its structure.

TRUNCATE TABLE students;

Example: Removes all records from the "students" table.

---

DML

DML (Data Manipulation Language) is used to insert, update, and delete data within tables.

5. "INSERT"

Used to add new records to a table.

INSERT INTO students (id, name)
VALUES (1, 'Ali');

Example: Inserts a new student record for "Ali".

6. "UPDATE"

Used to modify existing records in a table.

UPDATE students
SET name = 'Ahmed'
WHERE id = 1;

Example: Updates the name of the student with ID "1" to "Ahmed".

7. "DELETE"

Used to remove records from a table.

DELETE FROM students
WHERE id = 1;

Example: Deletes the record of the student with ID "1".

---

DQL

DQL (Data Query Language) is used to retrieve data from a database.

8. "SELECT"

Used to retrieve data from one or more tables.

SELECT * FROM students;

Example: Retrieves all records from the "students" table.

9. "WHERE"

Used to filter records based on specified conditions.

SELECT * FROM students
WHERE id = 1;

Example: Retrieves the record of the student with ID "1".

10. "ORDER BY"

Used to sort query results in ascending or descending order.

SELECT * FROM students
ORDER BY name;

Example: Displays students sorted alphabetically by name.

11. "DISTINCT"

Used to return only unique values by eliminating duplicates.

SELECT DISTINCT name
FROM students;

Example: Returns each student name only once.

12. "LIMIT"

Used to restrict the number of records returned by a query.

SELECT * FROM students
LIMIT 5;

Example: Returns only the first 5 records.