# User Management in PostgreSQL: Creating a New User as Database Owner

## Aim

To create a new PostgreSQL user and assign that user as the owner of a newly created database.

---

## Requirements

- Ubuntu/Linux operating system
- PostgreSQL installed and properly configured
- `psql` command-line tool
- Access to the PostgreSQL administrative account

---

# Procedure

## 1. Access PostgreSQL

Launch the PostgreSQL interactive terminal using the PostgreSQL administrative user.

```bash
sudo -u postgres psql
```

After successful login, the PostgreSQL prompt will appear.

---

## 2. Create a New User

Create a new PostgreSQL user named `sum` and assign a password.

```bash
CREATE USER sum WITH PASSWORD 'YOUR_PASSWORD';
```

A successful operation returns:

```bash
CREATE ROLE
```

The newly created user can be verified using the PostgreSQL role list.

```bash
\du
```

The user `sum` should appear in the list of available roles.

### Screenshot — User Creation and Role Verification
![alt text](<Screenshot (503).png>)
---

## 3. Create the Database

Create a database named `organization` and assign `sum` as its owner.

```bash
CREATE DATABASE organization OWNER sum;
```

A successful operation returns:

```bash
CREATE DATABASE
```

The `OWNER sum` clause assigns the user `sum` as the owner of the `organization` database.

### Screenshot  — Database Creation

![alt text](<Screenshot (505).png>)

---

## 4. Verify Database Ownership

List the available databases using:

```bash
\l
```

Locate the `organization` database and verify that `sum` is shown as its owner.

This confirms that the database was created successfully and that ownership was assigned correctly.

### Screenshot  — Database Ownership Verification

![alt text](<Screenshot (506).png>)

---

## 5. Connect Using the New User

Exit the PostgreSQL administrative session:

```bash
\q
```

Connect to the `organization` database using the newly created `sum` user:

```bash
psql -U sum -d organization -h localhost
```

A successful connection indicates that the new user can access the database.

---

## 6. Verify the Current User

After connecting to the database, verify the user associated with the current session.

```bash
SELECT current_user;
```

The expected result is:

```bash
current_user
------------
sum
```

This confirms that the session is running under the `sum` user.

---

## 7. Verify the Current Database

Verify the database being used by the current session.

```bash
SELECT current_database();
```

The expected result is:

```bash
current_database
-----------------
organization
```

This confirms that the connection has been established to the `organization` database.

### Screenshot — Final User and Database Verification

![alt text](<Screenshot (510).png>)
---

# Verification

The following points were successfully verified:

- PostgreSQL user `sum` was created successfully.
- Database `organization` was created successfully.
- `sum` was assigned as the owner of the `organization` database.
- The `organization` database was accessed using the `sum` user.
- The current PostgreSQL user was verified using `current_user`.
- The current database was verified using `current_database()`.

---

# Result

The PostgreSQL user `sum` was successfully created and assigned as the owner of the `organization` database.

The configuration was successfully tested by connecting to the database using the newly created user and verifying the current user and database.

---

