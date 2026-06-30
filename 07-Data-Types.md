# Data Types in Java

## Overview

A data type specifies the type of data a variable can store. Every variable in Java must have a data type.

Data types help the compiler allocate memory efficiently and ensure that variables store only valid values.

---

# Why Do We Need Data Types?

Data types are used to:

- Specify the type of data.
- Allocate memory efficiently.
- Prevent invalid data assignments.
- Improve program reliability.

Example:

```java
int age = 21;
```

Here, `int` specifies that the variable `age` can store only integer values.

---

# Types of Data Types

Java has two categories of data types:

1. Primitive Data Types
2. Non-Primitive (Reference) Data Types

```text
Data Types
│
├── Primitive
│     ├── byte
│     ├── short
│     ├── int
│     ├── long
│     ├── float
│     ├── double
│     ├── char
│     └── boolean
│
└── Non-Primitive
      ├── String
      ├── Arrays
      ├── Classes
      ├── Interfaces
      └── Objects
```

---

# Primitive Data Types

Primitive data types are predefined by Java and store simple values.

There are **8 primitive data types**.

| Data Type | Size | Description | Example |
|-----------|------|-------------|---------|
| byte | 1 Byte | Small integer | `byte age = 20;` |
| short | 2 Bytes | Small integer | `short marks = 500;` |
| int | 4 Bytes | Integer | `int salary = 50000;` |
| long | 8 Bytes | Large integer | `long population = 8000000000L;` |
| float | 4 Bytes | Decimal number | `float price = 99.5f;` |
| double | 8 Bytes | Large decimal number | `double pi = 3.14159;` |
| char | 2 Bytes | Single character | `char grade = 'A';` |
| boolean | 1 Bit (logical) | True or False | `boolean isJavaFun = true;` |

---

# Integer Data Types

## byte

Range:

```text
-128 to 127
```

Example:

```java
byte age = 25;
```

---

## short

Example:

```java
short marks = 2500;
```

---

## int

The most commonly used integer data type.

Example:

```java
int salary = 50000;
```

---

## long

Used for very large integer values.

Example:

```java
long population = 8000000000L;
```

---

# Decimal Data Types

## float

Used for decimal values.

Example:

```java
float price = 99.99f;
```

> **Note:** Always use `f` or `F` with float values.

---

## double

More precise than `float`.

Example:

```java
double pi = 3.14159265359;
```

---

# Character Data Type

## char

Stores a single character.

Example:

```java
char grade = 'A';
```

Characters are enclosed in **single quotes**.

---

# Boolean Data Type

Stores only two values:

- true
- false

Example:

```java
boolean isPassed = true;
```

---

# Non-Primitive Data Types

Non-primitive data types are created by programmers or provided by Java.

Examples:

- String
- Arrays
- Classes
- Interfaces
- Objects

Example:

```java
String name = "Alice";
```

Strings are enclosed in **double quotes**.

---

# Example Program

```java
public class Main {

    public static void main(String[] args) {

        byte age = 20;
        int salary = 50000;
        float price = 99.99f;
        double pi = 3.14159;
        char grade = 'A';
        boolean isPassed = true;
        String name = "Alice";

        System.out.println(age);
        System.out.println(salary);
        System.out.println(price);
        System.out.println(pi);
        System.out.println(grade);
        System.out.println(isPassed);
        System.out.println(name);

    }

}
```

---

# Output

```text
20
50000
99.99
3.14159
A
true
Alice
```

---

# Primitive vs Non-Primitive

| Primitive | Non-Primitive |
|------------|---------------|
| Predefined by Java | Created by Java or Programmer |
| Stores actual values | Stores references to objects |
| Fixed size | Size varies |
| Faster | Slightly slower |
| Cannot call methods | Can call methods |

---

# Common Mistakes

## Missing `L` for long

Incorrect:

```java
long population = 8000000000;
```

Correct:

```java
long population = 8000000000L;
```

---

## Missing `f` for float

Incorrect:

```java
float price = 99.99;
```

Correct:

```java
float price = 99.99f;
```

---

## Using Double Quotes for char

Incorrect:

```java
char grade = "A";
```

Correct:

```java
char grade = 'A';
```

---

## Using Single Quotes for String

Incorrect:

```java
String name = 'Alice';
```

Correct:

```java
String name = "Alice";
```

---

# Best Practices

- Use `int` for most integer values.
- Use `double` for decimal values unless memory is critical.
- Use meaningful variable names.
- Choose the appropriate data type based on the data being stored.

---

# Interview Questions

## 1. What is a data type?

A data type specifies the type of data that a variable can store.

---

## 2. How many primitive data types are there in Java?

There are **8 primitive data types**.

---

## 3. What are primitive data types?

Primitive data types store simple values directly.

Examples:

- byte
- short
- int
- long
- float
- double
- char
- boolean

---

## 4. What is the difference between `float` and `double`?

- `float` uses 4 bytes and requires the `f` suffix.
- `double` uses 8 bytes and provides greater precision.

---

## 5. What is the difference between `char` and `String`?

- `char` stores a single character.
- `String` stores a sequence of characters.

---

# Summary

- Every variable in Java must have a data type.
- Java has two categories of data types: Primitive and Non-Primitive.
- There are 8 primitive data types.
- Primitive types store values directly.
- Non-primitive types store references to objects.
- Choose the appropriate data type based on the data you want to store.
