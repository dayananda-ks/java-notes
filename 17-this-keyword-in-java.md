# `this` Keyword in Java

## Overview

The `this` keyword is a reference variable that refers to the **current object**.

It is used inside a class to access the current object's variables, methods, and constructors.

Whenever an object calls a method, Java automatically passes the reference of that object using `this`.

---

# Why Do We Need `this`?

Sometimes, local variables (parameters) and instance variables have the same name.

Without `this`, Java cannot distinguish between them.

Example

```java
class Student {

    String name;

    Student(String name) {

        name = name;

    }

}
```

Here,

```java
name = name;
```

Both `name` refer to the constructor parameter.

The instance variable never gets updated.

---

# How `this` Solves the Problem

```java
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

}
```

Here,

```java
this.name
```

refers to the object's variable.

```java
name
```

refers to the constructor parameter.

---

# Syntax

```java
this.variableName
```

```java
this.methodName();
```

```java
this();
```

---

# Behind the Scenes

Example

```java
Student s1 = new Student("Rahul");
```

Execution Flow

```text
Object Created
       │
       ▼
Constructor Called
       │
       ▼
this → s1 Object
       │
       ▼
this.name = "Rahul"
       │
       ▼
Object Initialized
```

During constructor execution,

```text
this
```

points to

```text
s1
```

---

# Use 1: Access Instance Variables

Example

```java
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

    void display() {

        System.out.println(name);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student("Rahul");

        s1.display();

    }

}
```

Output

```text
Rahul
```

---

# Use 2: Call Current Class Method

Example

```java
class Student {

    void display() {

        System.out.println("Display Method");

    }

    void show() {

        this.display();

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.show();

    }

}
```

Output

```text
Display Method
```

> Writing `display();` and `this.display();` has the same effect here, but `this` makes it explicit that you're calling a method on the current object.

---

# Use 3: Call Another Constructor

A constructor can call another constructor in the same class using `this()`.

Example

```java
class Student {

    Student() {

        this("Rahul");

        System.out.println("Default Constructor");

    }

    Student(String name) {

        System.out.println(name);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

    }

}
```

Output

```text
Rahul
Default Constructor
```

---

# Rule for `this()`

If `this()` is used inside a constructor,

it **must be the first statement**.

Correct

```java
Student() {

    this("Rahul");

}
```

Incorrect

```java
Student() {

    System.out.println("Hello");

    this("Rahul");

}
```

Compilation Error

---

# Use 4: Pass Current Object as an Argument

Example

```java
class Student {

    void display(Student obj) {

        System.out.println("Object Received");

    }

    void show() {

        display(this);

    }

}
```

Here,

```java
this
```

represents the current object.

---

# Use 5: Return Current Object

Example

```java
class Student {

    Student getObject() {

        return this;

    }

}
```

This is commonly used in **method chaining** and **builder patterns**.

---

# Memory Representation

```text
Student s1
      │
      ▼
 -----------------
| name = Rahul    |
| age = 20        |
 -----------------
        ▲
        │
      this
```

While executing methods of `s1`, `this` points to the same object.

---

# `this` vs Local Variable

```java
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

}
```

| Expression | Refers To |
|------------|-----------|
| `this.name` | Instance variable |
| `name` | Constructor parameter |

---

# Common Mistakes

## Forgetting `this`

Incorrect

```java
Student(String name) {

    name = name;

}
```

The instance variable remains unchanged.

Correct

```java
Student(String name) {

    this.name = name;

}
```

---

## Calling `this()` Incorrectly

Incorrect

```java
Student() {

    System.out.println("Hello");

    this("Rahul");

}
```

Compilation Error

Correct

```java
Student() {

    this("Rahul");

}
```

---

# Best Practices

- Use `this` when instance variables and parameters have the same name.
- Use `this()` for constructor chaining.
- Avoid unnecessary use of `this` when there is no ambiguity.
- Keep constructor chaining simple and readable.

---

# Interview Questions

## 1. What is the `this` keyword?

`this` is a reference variable that refers to the current object.

---

## 2. Why is `this` used?

It is used to distinguish instance variables from local variables, call current class methods, call another constructor, pass the current object, and return the current object.

---

## 3. Can `this()` and `super()` be used together in the same constructor?

No. Both must be the first statement, so only one of them can be used.

---

## 4. Can `this` be used inside a static method?

No.

`this` refers to the current object, but static methods belong to the class, not to any object.

---

## 5. What is constructor chaining?

Constructor chaining is the process of calling one constructor from another constructor using `this()`.

---

# Summary

- `this` refers to the current object.
- It is mainly used to resolve naming conflicts between instance variables and parameters.
- `this` can call current class methods.
- `this()` is used for constructor chaining.
- `this` can be passed as an argument or returned from a method.
- `this` cannot be used inside a static method.
