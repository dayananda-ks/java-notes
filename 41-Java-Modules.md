# Java Modules (JPMS - Java Platform Module System)

## Overview

The **Java Platform Module System (JPMS)** was introduced in **Java 9**.

A **Module** is a group of related packages that helps organize large Java applications.

Modules improve:

- Code organization
- Security
- Maintainability
- Performance
- Dependency management

---

# Why Do We Need Modules?

Before Java 9, applications used only packages.

Problems

- No strong encapsulation
- Difficult dependency management
- Large JAR files
- Poor scalability

With Modules

```text
Application

├── Module A
├── Module B
├── Module C
```

Each module exposes only the packages that should be accessible.

---

# What is a Module?

A module is a collection of:

- Packages
- Classes
- Interfaces
- Resources

along with a special file called:

```text
module-info.java
```

---

# Module Structure

```text
StudentApp
│
├── module-info.java
│
└── com
    └── student
        └── Main.java
```

---

# module-info.java

This file defines the module.

Example

```java
module StudentApp {

}
```

---

# Exporting Packages

By default, packages are hidden.

To make a package accessible:

```java
module StudentApp {

    exports com.student;

}
```

Now other modules can use this package.

---

# Requiring Another Module

If one module depends on another:

```java
module StudentApp {

    requires java.sql;

}
```

Now classes from `java.sql` can be used.

---

# Example

Module

```java
module StudentApp {

    requires java.sql;

    exports com.student;

}
```

Java Class

```java
package com.student;

public class Main {

    public static void main(String[] args){

        System.out.println("Hello Modules");

    }

}
```

---

# Module Dependency

```text
StudentApp
      │
      ▼
requires
      │
      ▼
java.sql
```

---

# Common Module Directives

| Directive | Purpose |
|------------|----------|
| requires | Uses another module |
| exports | Makes a package accessible |
| opens | Allows reflection |
| uses | Uses a service |
| provides | Provides a service implementation |

---

# opens

Allows reflection.

Example

```java
module StudentApp {

    opens com.student;

}
```

Frameworks like Spring and Hibernate often use reflection.

---

# uses

Declares that a module uses a service.

Example

```java
uses PaymentService;
```

---

# provides

Provides an implementation of a service.

Example

```java
provides PaymentService
with UpiPayment;
```

---

# Module Path vs Classpath

| Classpath | Module Path |
|------------|-------------|
| Java 8 and earlier | Java 9+ |
| No module support | Supports modules |
| Weak encapsulation | Strong encapsulation |

---

# Advantages

- Better security
- Better dependency management
- Strong encapsulation
- Faster startup
- Easier maintenance

---

# How Modules Work

```text
Java Application
        │
        ▼
Modules
        │
        ▼
Required Modules
        │
        ▼
JVM
```

---

# Common Mistakes

## Forgetting to Export a Package

```java
module StudentApp {

}
```

Other modules cannot access the package.

Correct

```java
module StudentApp {

    exports com.student;

}
```

---

## Forgetting Required Modules

Incorrect

```java
Connection connection;
```

without

```java
requires java.sql;
```

Compilation fails.

---

# Best Practices

- Divide large applications into modules.
- Export only necessary packages.
- Keep internal packages hidden.
- Minimize dependencies between modules.
- Use meaningful module names.

---

# Interview Questions

## 1. What is JPMS?

JPMS (Java Platform Module System) is the module system introduced in Java 9 for organizing applications into modules.

---

## 2. What is the purpose of `module-info.java`?

It defines a module and specifies its dependencies and exported packages.

---

## 3. What does `requires` do?

It declares that a module depends on another module.

---

## 4. What does `exports` do?

It makes a package accessible to other modules.

---

## 5. What is the difference between Classpath and Module Path?

| Classpath | Module Path |
|------------|-------------|
| No modules | Supports modules |
| Less secure | Strong encapsulation |

---

## 6. In which Java version were Modules introduced?

Java 9.

---

# Summary

- JPMS was introduced in Java 9.
- A module is a collection of related packages.
- `module-info.java` defines module information.
- `requires` declares dependencies.
- `exports` makes packages available to other modules.
- Modules improve security, scalability, maintainability, and dependency management.
