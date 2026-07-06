# Classes and Objects in Java

## Overview

A **Class** is a blueprint that defines the properties (variables) and behaviors (methods) of an object.

An **Object** is a real instance of a class. It occupies memory and can access the properties and methods defined in the class.

In Java, every object is created from a class.

---

# Why Do We Need Classes and Objects?

Without classes, we would need separate variables and methods for every real-world entity.

Example:

```text
Student 1
Name = Rahul
Age = 20

Student 2
Name = Priya
Age = 21

Student 3
Name = John
Age = 22
```

Instead, we create one **Student** class and then create multiple student objects.

This reduces code duplication and improves maintainability.

---

# Class

A class is a blueprint or template used to create objects.

A class contains:

- Variables (Fields)
- Methods (Functions)
- Constructors (covered later)

---

## Syntax

```java
class ClassName {

    // Variables

    // Methods

}
```

---

## Example

```java
class Student {

    String name;
    int age;

    void study() {
        System.out.println("Studying...");
    }

}
```

Here,

- `Student` is a class.
- `name` and `age` are variables.
- `study()` is a method.

---

# Object

An object is an instance of a class.

Objects are created using the `new` keyword.

---

## Syntax

```java
ClassName objectName = new ClassName();
```

---

## Example

```java
Student student1 = new Student();
```

Here,

- `Student` → Class
- `student1` → Object
- `new` → Allocates memory
- `Student()` → Constructor

---

# Creating Multiple Objects

```java
Student student1 = new Student();
Student student2 = new Student();
Student student3 = new Student();
```

Each object has its own memory.

---

# Accessing Variables

Use the **dot (`.`) operator**.

Example

```java
student1.name = "Rahul";
student1.age = 20;

System.out.println(student1.name);
System.out.println(student1.age);
```

Output

```text
Rahul
20
```

---

# Accessing Methods

Methods are also accessed using the dot (`.`) operator.

Example

```java
student1.study();
```

Output

```text
Studying...
```

---

# Complete Program

```java
class Student {

    String name;
    int age;

    void display() {

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);

    }

}

public class Main {

    public static void main(String[] args) {

        Student student1 = new Student();

        student1.name = "Rahul";
        student1.age = 20;

        student1.display();

    }

}
```

Output

```text
Name: Rahul
Age: 20
```

---

# Memory Representation

```text
Class

Student
│
├── name
├── age
└── display()

        │
        ▼

Objects

student1
│
├── name = Rahul
└── age = 20

student2
│
├── name = Priya
└── age = 21
```

Each object stores its own data.

---

# Object Creation Flow

```text
Write Class
      │
      ▼
Compile Program
      │
      ▼
Create Object using new
      │
      ▼
Memory Allocated in Heap
      │
      ▼
Reference Variable Stores Address
      │
      ▼
Access Variables and Methods
```

---

# `new` Keyword

The `new` keyword is used to create an object.

When `new` is used:

1. Memory is allocated in the Heap.
2. The constructor is called.
3. A reference to the object is returned.

Example

```java
Student student1 = new Student();
```

---

# Reference Variable

```java
Student student1 = new Student();
```

Here,

```text
Student
```

is the class.

```text
student1
```

is the reference variable.

It stores the address (reference) of the object, not the object itself.

---

# Dot (`.`) Operator

The dot operator is used to access object members.

Example

```java
student1.name

student1.age

student1.display();
```

---

# Class vs Object

| Class | Object |
|--------|---------|
| Blueprint | Instance of a class |
| Logical entity | Physical entity |
| No memory for object data | Occupies memory |
| Defined once | Can create many |

---

# Real-World Example

```text
Blueprint
        │
        ▼
House
```

Similarly,

```text
Class
        │
        ▼
Objects
```

Example

```text
Car (Class)

↓

Car1
Car2
Car3
```

All cars are created from the same blueprint.

---

# Common Mistakes

## Forgetting `new`

Incorrect

```java
Student s;

s.name = "Rahul";
```

Result

```text
NullPointerException
```

Correct

```java
Student s = new Student();

s.name = "Rahul";
```

---

## Accessing Members Without Object

Incorrect

```java
name = "Rahul";
```

Correct

```java
student1.name = "Rahul";
```

---

## Confusing Class and Object

Incorrect Thinking

```text
Class = Object
```

Correct

```text
Class = Blueprint

Object = Real Instance
```

---

# Best Practices

- Use meaningful class names (Student, Car, Employee).
- Use camelCase for object names.
- Create multiple objects instead of duplicate variables.
- Keep one responsibility for each class.

---

# Interview Questions

## 1. What is a class?

A class is a blueprint used to create objects.

---

## 2. What is an object?

An object is an instance of a class that stores data and can perform actions.

---

## 3. What is the purpose of the `new` keyword?

It creates an object by allocating memory and calling the constructor.

---

## 4. What is a reference variable?

A reference variable stores the address of an object in memory.

---

## 5. What is the difference between a class and an object?

A class is a blueprint, while an object is a real instance created from that blueprint.

---

# Summary

- A class is a blueprint for creating objects.
- An object is an instance of a class.
- Objects are created using the `new` keyword.
- Variables and methods are accessed using the dot (`.`) operator.
- Each object has its own memory and data.
- A reference variable stores the address of an object.
- Classes and objects are the foundation of Object-Oriented Programming in Java.