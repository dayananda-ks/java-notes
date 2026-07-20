# JDBC (Java Database Connectivity)

## Overview

JDBC (Java Database Connectivity) is a Java API that allows Java applications to communicate with databases.

Using JDBC, a Java program can:

- Connect to a database
- Execute SQL queries
- Insert records
- Update records
- Delete records
- Retrieve data

JDBC acts as a bridge between Java applications and relational databases.

---

# Why Do We Need JDBC?

Suppose we have a Java application that manages student information.

Without JDBC

```text
Java Program

↓

Cannot communicate with Database
```

With JDBC

```text
Java Program

↓

JDBC API

↓

Database Driver

↓

MySQL Database
```

JDBC enables communication between Java and the database.

---

# JDBC Architecture

```text
Java Application
        │
        ▼
     JDBC API
        │
        ▼
   JDBC Driver
        │
        ▼
    Database
```

---

# JDBC Components

- DriverManager
- Connection
- Statement
- PreparedStatement
- ResultSet
- SQLException

---

# JDBC Driver

A JDBC Driver is software that enables Java to communicate with a specific database.

Examples

- MySQL Driver
- Oracle Driver
- PostgreSQL Driver
- SQL Server Driver

---

# JDBC Workflow

```text
Load JDBC Driver
        │
        ▼
Create Connection
        │
        ▼
Create Statement
        │
        ▼
Execute SQL Query
        │
        ▼
Process Result
        │
        ▼
Close Resources
```

---

# Step 1: Import JDBC Package

```java
import java.sql.*;
```

---

# Step 2: Load the Driver

Modern JDBC drivers are loaded automatically.

Older versions used:

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

---

# Step 3: Create a Connection

Example

```java
Connection connection =
DriverManager.getConnection(
"jdbc:mysql://localhost:3306/studentdb",
"root",
"password"
);
```

Explanation

- `jdbc:mysql://` → JDBC protocol
- `localhost` → Database server
- `3306` → MySQL default port
- `studentdb` → Database name

---

# Step 4: Create a Statement

```java
Statement statement =
connection.createStatement();
```

A Statement executes SQL queries.

---

# Step 5: Execute Query

Example

```java
ResultSet result =
statement.executeQuery(
"SELECT * FROM students");
```

`executeQuery()` is used for SELECT statements.

---

# Step 6: Read Data

```java
while(result.next()){

    System.out.println(
        result.getInt("id")
    );

    System.out.println(
        result.getString("name")
    );

}
```

---

# Step 7: Close Resources

```java
result.close();

statement.close();

connection.close();
```

Always close resources after use.

---

# Complete Example

```java
import java.sql.*;

public class Main {

    public static void main(String[] args)
    throws Exception {

        Connection connection =
        DriverManager.getConnection(
        "jdbc:mysql://localhost:3306/studentdb",
        "root",
        "password"
        );

        Statement statement =
        connection.createStatement();

        ResultSet result =
        statement.executeQuery(
        "SELECT * FROM students"
        );

        while(result.next()){

            System.out.println(
            result.getInt("id")
            );

            System.out.println(
            result.getString("name")
            );

        }

        result.close();

        statement.close();

        connection.close();

    }

}
```

---

# Statement vs PreparedStatement

## Statement

```java
Statement statement =
connection.createStatement();
```

Query

```java
String sql =
"SELECT * FROM students WHERE id = 1";
```

Problems

- Slower
- Vulnerable to SQL Injection

---

## PreparedStatement

```java
PreparedStatement ps =
connection.prepareStatement(
"SELECT * FROM students WHERE id = ?"
);
```

```java
ps.setInt(1, 1);

ResultSet rs = ps.executeQuery();
```

Advantages

- Faster
- Prevents SQL Injection
- Reusable

PreparedStatement is preferred.

---

# Insert Data

```java
PreparedStatement ps =
connection.prepareStatement(
"INSERT INTO students(name) VALUES(?)"
);

ps.setString(1, "Ashu");

ps.executeUpdate();
```

---

# Update Data

```java
PreparedStatement ps =
connection.prepareStatement(
"UPDATE students SET name=? WHERE id=?"
);

ps.setString(1, "Rahul");

ps.setInt(2, 1);

ps.executeUpdate();
```

---

# Delete Data

```java
PreparedStatement ps =
connection.prepareStatement(
"DELETE FROM students WHERE id=?"
);

ps.setInt(1, 1);

ps.executeUpdate();
```

---

# Execute Methods

| Method | Purpose |
|----------|----------|
| executeQuery() | SELECT |
| executeUpdate() | INSERT, UPDATE, DELETE |
| execute() | Any SQL statement |

---

# ResultSet

`ResultSet` stores the data returned by a SELECT query.

Example

```java
while(result.next()){

    System.out.println(
    result.getString("name")
    );

}
```

Common Methods

| Method | Description |
|----------|-------------|
| next() | Moves to next row |
| getInt() | Reads integer |
| getString() | Reads string |
| getDouble() | Reads double |

---

# SQLException

Database errors generate `SQLException`.

Example

```java
try{

    Connection connection =
    DriverManager.getConnection(...);

}catch(SQLException e){

    System.out.println(e.getMessage());

}
```

---

# How JDBC Works

```text
Java Program
      │
      ▼
DriverManager
      │
      ▼
Connection
      │
      ▼
Statement / PreparedStatement
      │
      ▼
SQL Query
      │
      ▼
Database
      │
      ▼
ResultSet
      │
      ▼
Java Program
```

---

# Common Mistakes

## Forgetting to Close Connection

Incorrect

```java
Connection connection =
DriverManager.getConnection(...);
```

Always close the connection.

---

## Using Statement Instead of PreparedStatement

Incorrect

```java
Statement statement =
connection.createStatement();
```

Preferred

```java
PreparedStatement ps =
connection.prepareStatement(...);
```

---

## Ignoring SQL Exceptions

Always handle database exceptions properly.

---

# Best Practices

- Always use `PreparedStatement` instead of `Statement`.
- Close database resources after use.
- Handle `SQLException`.
- Store database credentials securely.
- Use connection pooling in large applications.

---

# Interview Questions

## 1. What is JDBC?

JDBC is a Java API used to connect Java applications with relational databases.

---

## 2. What are the main JDBC components?

- DriverManager
- Connection
- Statement
- PreparedStatement
- ResultSet

---

## 3. What is the difference between Statement and PreparedStatement?

| Statement | PreparedStatement |
|-----------|-------------------|
| Slower | Faster |
| SQL Injection Risk | Prevents SQL Injection |
| Not Precompiled | Precompiled |
| Less Efficient | More Efficient |

---

## 4. What is ResultSet?

`ResultSet` stores the data returned from a SELECT query.

---

## 5. What is executeUpdate() used for?

It executes:

- INSERT
- UPDATE
- DELETE

statements.

---

## 6. Why is PreparedStatement preferred?

Because it:

- Improves performance
- Prevents SQL Injection
- Supports parameterized queries
- Can be reused

---

# Summary

- JDBC enables Java applications to communicate with relational databases.
- It acts as a bridge between Java and the database.
- The JDBC workflow includes creating a connection, executing SQL, processing results, and closing resources.
- `PreparedStatement` is preferred over `Statement` because it is safer and more efficient.
- `ResultSet` is used to read query results.
- Proper resource management and exception handling are essential for reliable database applications.
