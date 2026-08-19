# SETUP POSTGRESQL AND CREATE A COLLEGE DATABASE WITH STUDENT TABLE

---

# AIM

To install and configure PostgreSQL, create a database for a college, and define a `student` table for storing student records.

---

# REQUIREMENTS

* Ubuntu/Linux operating system
* PostgreSQL database system
* `psql` command-line utility
* Administrative (`sudo`) privileges

---

# PROCEDURE

# 1. UPDATE THE PACKAGE REPOSITORY

---

Before installing PostgreSQL, update the system’s package index to ensure the latest versions are available.

```bash
sudo apt update
```

Wait for the update process to complete successfully.

**Screenshot: Package Repository Update** 

![alt text](<Screenshot (496).png>)

---

# 2. INSTALL POSTGRESQL

---

Install PostgreSQL along with additional contributed modules.

```bash
sudo apt install postgresql postgresql-contrib
```

Upon successful installation, PostgreSQL will be available on the system.

**Screenshot: PostgreSQL Installation**

![alt text](<Screenshot (497).png>)

---

# 3. VERIFY POSTGRESQL SERVICE STATUS

---

Check whether the PostgreSQL service is active and running:

```bash
sudo systemctl status postgresql
```

The service should display an **active (running)** status.

**Screenshot: PostgreSQL Service Status**

![alt text](<Screenshot (498).png>)

---

# 4. ACCESS THE POSTGRESQL SHELL

---

Log in to the PostgreSQL interactive terminal using the default administrative user:

```bash
sudo -u postgres psql
```

After successful login, the prompt will appear as:

```text
postgres=#
```

**Screenshot: PostgreSQL Shell**

![alt text](<Screenshot (499).png>)

---

# 5. CREATE THE COLLEGE DATABASE

---

Create a new database named `college`:

```sql
CREATE DATABASE college;
```

A successful execution will return:

```text
CREATE DATABASE
```

**Screenshot: College Database Creation**

![alt text](<Screenshot (500).png>)

---

# 6. CONNECT TO THE COLLEGE DATABASE

---

Switch to the newly created database:

```sql
\c college
```

A successful connection message confirms that the session is now using the `college` database.

**Screenshot: Database Connection**

![alt text](<Screenshot (500)-1.png>)
---

# 7. CREATE THE STUDENT TABLE

---

Create a table named `student` to store student-related information.

The table includes the following fields:

* `student_id` – Unique identifier (Primary Key)
* `name` – Name of the student
* `age` – Age of the student
* `course` – Enrolled course
* `email` – Email address (Unique)

Execute the following SQL command:

```sql
CREATE TABLE student (
    student_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT,
    course VARCHAR(100),
    email VARCHAR(100) UNIQUE
);
```

A successful execution will return:

```text
CREATE TABLE
```

**Screenshot: Student Table Creation**

![alt text](<Screenshot (502).png>)

---

# 8. VERIFY THE STUDENT TABLE

---

List all tables in the current database:

```sql
\dt
```

The `student` table should be visible in the output.

To view the table structure:

```sql
\d student
```

This displays all columns, data types, and constraints defined for the table.

**Screenshot: Student Table Verification**

![alt text](<Screenshot (502)-1.png>)

---

# VERIFICATION

The following outcomes were successfully verified:

* PostgreSQL was installed and configured successfully.
* PostgreSQL service was active and running.
* The `college` database was created successfully.
* Connection to the `college` database was established.
* The `student` table was created successfully.
* Table structure and constraints were verified.

---

# RESULT

PostgreSQL was successfully installed and configured. A database named `college` was created, and a `student` table with appropriate attributes and constraints was implemented for managing student records.

---

