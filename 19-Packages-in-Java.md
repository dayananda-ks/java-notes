# Packages in Java
## Overview

A **Package** in Java is a mechanism used to organize related classes, interfaces, enums, and sub-packages into a single namespace.

Packages help developers organize large projects, avoid naming conflicts, and control access.

Think of a package like a **folder** in your computer.
```text
Folder
│
├── File1
├── File2
└── File3
```

Similarly,

```text
Package
│
├── Class1
├── Class2
└── Class3
```

---

# Why Do We Need Packages?

Packages help to:

- Organize Java classes.
- Avoid class name conflicts.
- Improve code readability.
- Improve project maintainability.
- Control access using access modifiers.

Without Packages

```text
Student.java
Employee.java
Car.java
Book.java
Order.java
Product.java
```

Everything is stored together.

With Packages

```text
com.company.student
com.company.employee
com.company.product
```

Classes are organized logically.

---

# Types of Packages

Java provides two types of packages.

## 1. Built-in Packages

Packages provided by Java.

Examples

```java
java.lang
java.util
java.io
java.sql
java.time
```

Example

```java
import java.util.Scanner;
```

---

## 2. User-Defined Packages

Packages created by programmers.

Example

```java
package com.company.student;
```

---

# Package Syntax

The package declaration must be the **first statement** in a Java file.

Syntax

```java
package packageName;
```

Example

```java
package com.company.student;

public class Student {

}
```

---

# Creating a Package

Example

```java
package college;

public class Student {

    public void display() {

        System.out.println("Student Class");

    }

}
```

Save the file inside

```text
college/
    Student.java
```

---

# Importing a Package

To use a class from another package, use the `import` statement.

Syntax

```java
import packageName.ClassName;
```

Example

```java
import college.Student;

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.display();

    }

}
```

---

# Importing All Classes

Syntax

```java
import packageName.*;
```

Example

```java
import java.util.*;
```

This imports all classes from the package.

---

# Common Built-in Packages

| Package | Purpose |
|---------|---------|
| `java.lang` | Core Java classes |
| `java.util` | Utility classes like Scanner, ArrayList |
| `java.io` | Input and Output |
| `java.sql` | Database connectivity |
| `java.time` | Date and Time API |

---

# `java.lang` Package

The `java.lang` package is imported automatically.

Example

```java
String name = "Java";

System.out.println(name.length());
```

No import statement is required.

---

# Package Structure

Example Project

```text
Project
│
├── Main.java
│
└── college
      │
      ├── Student.java
      └── Teacher.java
```

---

# Package Naming Convention

Package names are usually written in **lowercase**.

Examples

```text
com.company.student

com.amazon.payment

com.google.maps

org.example.project
```

---

# Compilation

Compile the package

```bash
javac -d . Student.java
```

The `-d` option creates the required package directory.

---

# Running the Program

```bash
java college.Student
```

For a class inside a package, always use its **fully qualified name**.

---

# Package Execution Flow

```text
Write Class
      │
      ▼
Add Package Declaration
      │
      ▼
Compile
      │
      ▼
Package Folder Created
      │
      ▼
Import Package
      │
      ▼
Use Classes
```

---

# Package vs Folder

| Package | Folder |
|----------|---------|
| Java namespace | Operating system directory |
| Organizes Java classes | Organizes files |
| Prevents naming conflicts | Stores files |

Usually, one package corresponds to one folder.

---

# Common Mistakes

## Package Statement Not First

Incorrect

```java
import java.util.Scanner;

package college;
```

Correct

```java
package college;

import java.util.Scanner;
```

---

## Wrong Folder Structure

Incorrect

```text
Student.java
```

Correct

```text
college/
    Student.java
```

---

## Forgetting to Import

Incorrect

```java
Student s = new Student();
```

Compilation Error

Correct

```java
import college.Student;
```

---

# Best Practices

- Use meaningful package names.
- Always use lowercase package names.
- Group related classes into the same package.
- Follow the reverse domain naming convention for large projects.

Example

```text
com.company.project
```

---

# Interview Questions

## 1. What is a package in Java?

A package is a namespace used to organize related classes and interfaces.

---

## 2. Why are packages used?

Packages organize code, avoid naming conflicts, and improve maintainability.

---

## 3. What are the two types of packages?

- Built-in Packages
- User-Defined Packages

---

## 4. Which package is imported automatically?

```text
java.lang
```

---

## 5. What is the purpose of the `import` statement?

The `import` statement allows one class to use classes from another package without writing the fully qualified class name.

---

# Summary

- A package is used to organize related Java classes.
- Java provides built-in and user-defined packages.
- The `package` statement must be the first statement in a Java file.
- The `import` statement is used to access classes from other packages.
- `java.lang` is imported automatically.
- Packages improve organization, readability, and scalability of Java projects.
