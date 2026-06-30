# Variables in Java

## Overview

A variable is a named memory location used to store data. The value stored in a variable can change during program execution.

Variables make it possible to store, retrieve, and manipulate data in a program.

---

# Why Do We Need Variables?

Variables are used to:

- Store data.
- Reuse values.
- Perform calculations.
- Improve code readability.

Example:

```java
int age = 21;
```

Here, `age` is a variable that stores the value `21`.

---

# Syntax

```java
dataType variableName = value;
```

Example:

```java
int age = 21;
```

---

# Variable Declaration

Variable declaration means creating a variable by specifying its data type and name.

Syntax:

```java
dataType variableName;
```

Example:

```java
int age;
```

Here:

- `int` → Data Type
- `age` → Variable Name

---

# Variable Initialization

Initialization means assigning a value to a variable.

Example:

```java
int age = 21;
```

---

# Variable Assignment

A variable's value can be changed.

Example:

```java
int age = 21;

age = 22;
```

Output:

```text
22
```

---

# Example Program

```java
public class Main {

    public static void main(String[] args) {

        int age = 21;

        System.out.println(age);

    }

}
```

Output:

```text
21
```

---

# Multiple Variables

```java
public class Main {

    public static void main(String[] args) {

        String name = "John";
        int age = 21;
        double salary = 45000.50;

        System.out.println(name);
        System.out.println(age);
        System.out.println(salary);

    }

}
```

Output:

```text
John
21
45000.5
```

---

# Rules for Naming Variables

- Variable names are case-sensitive.
- Must begin with a letter, `_`, or `$`.
- Cannot begin with a number.
- Cannot contain spaces.
- Cannot use Java keywords.
- Use meaningful names.

Valid Examples:

```java
age
studentName
salary
_marks
$price
```

Invalid Examples:

```java
2age
student name
class
```

---

# Java Naming Convention

Use **camelCase** for variable names.

Examples:

```java
studentName
firstName
employeeSalary
totalMarks
```

---

# Types of Variables

Java has three types of variables.

## 1. Local Variable

Declared inside a method.

Example:

```java
public class Main {

    public static void main(String[] args) {

        int age = 21;

        System.out.println(age);

    }

}
```

---

## 2. Instance Variable

Declared inside a class but outside methods.

Each object has its own copy.

Example:

```java
public class Student {

    String name;

}
```

---

## 3. Static Variable

Declared using the `static` keyword.

Shared by all objects of the class.

Example:

```java
public class Student {

    static String college = "ABC College";

}
```

---

# Printing Variables

```java
String name = "Alice";

System.out.println(name);
```

Output:

```text
Alice
```

---

# Printing Text and Variables Together

```java
String name = "Alice";
int age = 20;

System.out.println("Name: " + name);
System.out.println("Age: " + age);
```

Output:

```text
Name: Alice
Age: 20
```

---

# Updating a Variable

```java
int marks = 80;

marks = 90;

System.out.println(marks);
```

Output:

```text
90
```

---

# Common Mistakes

## Using an Uninitialized Variable

Incorrect:

```java
int age;

System.out.println(age);
```

Result:

```text
Compilation Error
```

Correct:

```java
int age = 21;

System.out.println(age);
```

---

## Redeclaring a Variable

Incorrect:

```java
int age = 20;
int age = 25;
```

Correct:

```java
int age = 20;

age = 25;
```

---

## Using an Invalid Variable Name

Incorrect:

```java
int 1age = 20;
```

Correct:

```java
int age = 20;
```

---

# Best Practices

- Use meaningful variable names.
- Follow camelCase naming convention.
- Initialize variables before using them.
- Keep variable names short but descriptive.

---

# Interview Questions

## 1. What is a variable?

A variable is a named memory location used to store data.

---

## 2. Why are variables used?

Variables are used to store, retrieve, and manipulate data.

---

## 3. What are the types of variables in Java?

- Local Variable
- Instance Variable
- Static Variable

---

## 4. What is variable initialization?

Assigning a value to a variable.

Example:

```java
int age = 21;
```

---

## 5. What naming convention is used for variables?

Java uses the **camelCase** naming convention.

Example:

```java
studentName
employeeSalary
```

---

# Summary

- A variable is a named memory location used to store data.
- Variables have a data type, name, and value.
- Variables can be declared, initialized, and updated.
- Java supports Local, Instance, and Static variables.
- Variable names should follow the camelCase naming convention.
- Variables improve code readability and make programs more flexible.
