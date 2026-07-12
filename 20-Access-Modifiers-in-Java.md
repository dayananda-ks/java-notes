# Access Modifiers in Java

## Overview

Access Modifiers are keywords used to control the visibility (accessibility) of classes, variables, methods, and constructors.

They determine **who can access a member** from different parts of a program.

Java provides four access modifiers:

- public
- protected
- default (no keyword)
- private

---

# Why Do We Need Access Modifiers?

Imagine a Banking Application.

```text
Bank Account
│
├── Account Number
├── Balance
├── Deposit()
├── Withdraw()
└── PIN
```

Everyone should not be allowed to access the **PIN** or directly modify the **balance**.

Access modifiers help provide **security** and **data hiding**.

---

# Types of Access Modifiers

```text
Access Modifiers
│
├── public
├── protected
├── default
└── private
```

---

# 1. public

A `public` member can be accessed from **anywhere** in the program.

### Example

```java
class Student {

    public String name = "Rahul";

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.name);

    }

}
```

Output

```text
Rahul
```

---

# 2. private

A `private` member can only be accessed **inside the same class**.

### Example

```java
class Student {

    private int marks = 90;

    void display() {

        System.out.println(marks);

    }

}
```

Correct

```java
Student s = new Student();

s.display();
```

Incorrect

```java
System.out.println(s.marks);
```

Compilation Error

---

# 3. default (Package-Private)

If no access modifier is specified, Java uses the **default** access modifier.

A default member is accessible **only within the same package**.

### Example

```java
class Student {

    String college = "KVG";

}
```

This variable is accessible only inside the same package.

---

# 4. protected

A `protected` member can be accessed:

- Inside the same class
- Inside the same package
- In subclasses (child classes) even if they are in different packages

We will understand this better after learning **Inheritance**.

Example

```java
class Student {

    protected int rollNo = 101;

}
```

---

# Access Levels

| Modifier | Same Class | Same Package | Subclass (Different Package) | Different Package |
|----------|:----------:|:------------:|:----------------------------:|:-----------------:|
| public | ✅ | ✅ | ✅ | ✅ |
| protected | ✅ | ✅ | ✅ | ❌ |
| default | ✅ | ✅ | ❌ | ❌ |
| private | ✅ | ❌ | ❌ | ❌ |

---

# Access Modifiers for Classes

Only two access modifiers are allowed for **top-level classes**.

| Modifier | Allowed |
|-----------|---------|
| public | ✅ |
| default | ✅ |
| protected | ❌ |
| private | ❌ |

Example

```java
public class Student {

}
```

or

```java
class Student {

}
```

---

# Access Modifiers for Members

Variables, methods, and constructors can use all four access modifiers.

Example

```java
public int age;

private String password;

protected void display() {

}

String college;
```

---

# Real-World Example

```text
Mobile Phone
│
├── public
│      Power Button
│
├── protected
│      Internal Features
│
├── default
│      Service Center Features
│
└── private
       Password
```

---

# How Java Checks Access

```text
Access Request
      │
      ▼
Check Access Modifier
      │
      ▼
Permission Available?
      │
   ┌──┴──┐
   │     │
 Yes     No
 │        │
 ▼        ▼
Access   Compilation Error
```

---

# Example Program

```java
class Student {

    public String name = "Rahul";

    private int marks = 95;

    void display() {

        System.out.println(name);
        System.out.println(marks);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.name);

        s.display();

    }

}
```

Output

```text
Rahul
Rahul
95
```

---

# Common Mistakes

## Accessing Private Members Outside the Class

Incorrect

```java
Student s = new Student();

System.out.println(s.marks);
```

Compilation Error

Correct

```java
s.display();
```

---

## Assuming Default Means Public

Incorrect Thinking

```text
No modifier = public
```

Correct

```text
No modifier = default (package-private)
```

---

## Using `private` for Top-Level Classes

Incorrect

```java
private class Student {

}
```

Compilation Error

Only `public` and `default` are allowed for top-level classes.

---

# Best Practices

- Use `private` for data members whenever possible.
- Expose data through public methods when needed.
- Use `public` only when members should be accessible from anywhere.
- Use `protected` mainly for inheritance.
- Use `default` for package-level access.

---

# Interview Questions

## 1. What are access modifiers?

Access modifiers control the visibility of classes, variables, methods, and constructors.

---

## 2. How many access modifiers are there in Java?

There are four:

- public
- protected
- default
- private

---

## 3. Which access modifier provides the highest accessibility?

```text
public
```

---

## 4. Which access modifier provides the lowest accessibility?

```text
private
```

---

## 5. Can a top-level class be declared as `private`?

No.

Only `public` and `default` are allowed for top-level classes.

---

## 6. Which access modifier is commonly used for data hiding?

```text
private
```

It prevents direct access from outside the class.

---

# Summary

- Access modifiers control the visibility of Java members.
- Java provides four access modifiers: `public`, `protected`, `default`, and `private`.
- `public` members are accessible from anywhere.
- `private` members are accessible only within the same class.
- `default` members are accessible only within the same package.
- `protected` members are accessible within the same package and by subclasses.
- Using appropriate access modifiers improves security, encapsulation, and maintainability.
