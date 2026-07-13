# Encapsulation in Java

## Overview

Encapsulation is one of the four pillars of Object-Oriented Programming (OOP).

It is the process of **wrapping data (variables) and methods (functions) into a single unit (class)** while restricting direct access to the data.

In Java, encapsulation is achieved by:

- Making variables `private`
- Providing `public` Getter and Setter methods

---

# Why Do We Need Encapsulation?

Without encapsulation, anyone can directly modify object data.

Example

```java
Student s = new Student();

s.age = -10;
```

An age of `-10` is invalid.

With encapsulation, we can validate data before updating it.

This improves:

- Data Security
- Data Validation
- Code Maintainability
- Flexibility

---

# Real-World Example

Think of an **ATM Machine**.

```text
ATM
│
├── Cash
├── PIN
└── Balance
```

You cannot directly access the cash or change the balance.

You must use operations like:

```text
Withdraw()
Deposit()
CheckBalance()
```

Similarly, in Java we hide variables and access them through methods.

---

# How Encapsulation Works

```text
Private Variables
        │
        ▼
Getter / Setter Methods
        │
        ▼
Controlled Access
```

---

# Steps to Achieve Encapsulation

### Step 1: Declare Variables as `private`

```java
private String name;

private int age;
```

---

### Step 2: Create Getter Methods

Getter methods return the value of private variables.

Example

```java
public String getName() {

    return name;

}
```

---

### Step 3: Create Setter Methods

Setter methods update private variables.

Example

```java
public void setName(String name) {

    this.name = name;

}
```

---

# Complete Example

```java
class Student {

    private String name;

    public void setName(String name) {

        this.name = name;

    }

    public String getName() {

        return name;

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.setName("Rahul");

        System.out.println(s.getName());

    }

}
```

Output

```text
Rahul
```

---

# Encapsulation with Validation

One of the biggest advantages of encapsulation is validation.

Example

```java
class Student {

    private int age;

    public void setAge(int age) {

        if (age > 0) {

            this.age = age;

        } else {

            System.out.println("Invalid Age");

        }

    }

    public int getAge() {

        return age;

    }

}
```

Output

```text
Invalid Age
```

The object remains safe because invalid data is rejected.

---

# Behind the Scenes

Example

```java
Student s = new Student();

s.setName("Rahul");

String value = s.getName();
```

Execution Flow

```text
Object Created
      │
      ▼
Private Variable Exists
      │
      ▼
Setter Updates Variable
      │
      ▼
Getter Returns Value
      │
      ▼
Value Printed
```

---

# Getter and Setter Naming Convention

For variable

```java
private String name;
```

Getter

```java
getName()
```

Setter

```java
setName()
```

For boolean variables

```java
private boolean active;
```

Getter

```java
isActive()
```

Setter

```java
setActive()
```

---

# Advantages of Encapsulation

- Provides data hiding.
- Prevents unauthorized access.
- Allows validation before updating data.
- Improves maintainability.
- Makes code flexible and reusable.
- Increases application security.

---

# Disadvantages of Encapsulation

- Requires writing additional Getter and Setter methods.
- Slightly increases code size.

---

# Encapsulation vs Data Hiding

These terms are related but not identical.

| Encapsulation | Data Hiding |
|--------------|-------------|
| Wrapping data and methods into one unit | Restricting direct access to data |
| Achieved using classes | Achieved using `private` access modifier |
| Focuses on structure | Focuses on security |

---

# Common Mistakes

## Making Variables Public

Incorrect

```java
public String name;
```

Anyone can modify it.

Correct

```java
private String name;
```

---

## Returning Wrong Variable

Incorrect

```java
public String getName() {

    return "Java";

}
```

Correct

```java
return name;
```

---

## Not Validating Input

Incorrect

```java
public void setAge(int age) {

    this.age = age;

}
```

Better

```java
if (age > 0) {

    this.age = age;

}
```

---

# Best Practices

- Keep instance variables `private`.
- Use Getter methods to read values.
- Use Setter methods to update values.
- Validate input inside Setter methods.
- Expose only the methods that are necessary.

---

# Interview Questions

## 1. What is encapsulation?

Encapsulation is the process of wrapping data and methods into a single unit (class) while restricting direct access to the data.

---

## 2. How is encapsulation achieved in Java?

By declaring variables as `private` and accessing them through `public` Getter and Setter methods.

---

## 3. Why are Getter and Setter methods used?

Getter methods read private data, while Setter methods update private data in a controlled manner.

---

## 4. What are the advantages of encapsulation?

- Data hiding
- Better security
- Data validation
- Improved maintainability
- Flexibility

---

## 5. Is encapsulation one of the four pillars of OOP?

Yes.

The four pillars are:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

# Summary

- Encapsulation is the process of combining data and methods into a single class.
- It protects data by making variables `private`.
- Getter methods are used to read private data.
- Setter methods are used to update private data.
- Encapsulation improves security, validation, and maintainability.
- It is one of the four fundamental principles of Object-Oriented Programming (OOP).
