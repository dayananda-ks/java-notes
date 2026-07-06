# Object-Oriented Programming (OOP) Fundamentals

## Overview
Object-Oriented Programming (OOP) is a programming paradigm that organizes programs around **objects** instead of functions.

An object represents a real-world entity with **data (properties)** and **behavior (methods)**.

Java is primarily an Object-Oriented Programming language.

---

## Why Do We Need OOP?

As software grows larger, writing everything in a single file becomes difficult to manage.

OOP helps to:

- Organize code into reusable components.
- Reduce code duplication.
- Improve readability.
- Improve maintainability.
- Make programs easier to scale.

Example:

Instead of writing separate code for every student,

```text
Student 1
Student 2
Student 3
```

We create one **Student class** and then create multiple student objects.

---

# Real-World Analogy

Think of a **Car**.

Every car has:

Properties

- Color
- Brand
- Speed

Behaviors

- Start
- Stop
- Accelerate

In Java,

```text
Car
│
├── Properties
│     ├── color
│     ├── brand
│     └── speed
│
└── Behaviors
      ├── start()
      ├── stop()
      └── accelerate()
```

---

# Core Concepts of OOP

Java OOP is based on four main principles.

```text
Object-Oriented Programming
│
├── Encapsulation
├── Inheritance
├── Polymorphism
└── Abstraction
```

These concepts will be covered in detail in later chapters.

---

# Class and Object

Everything in Java OOP revolves around **Classes** and **Objects**.

```text
Class
   │
   ▼
Object
```

A **Class** is a blueprint.

An **Object** is a real instance created from that blueprint.

Example

Blueprint

```text
House Plan
```

Real House

```text
House
```

Similarly,

```text
Student (Class)
        │
        ▼
Rahul (Object)

Priya (Object)

John (Object)
```

---

# How OOP Works

```text
Write a Class
        │
        ▼
Create Objects
        │
        ▼
Objects Store Data
        │
        ▼
Objects Perform Actions
```

---

# OOP Terminology

| Term | Meaning |
|------|---------|
| Class | Blueprint for creating objects |
| Object | Instance of a class |
| Property | Variable inside a class |
| Method | Function inside a class |
| Instance | Another name for an object |

---

# Example

Imagine a Student.

Properties

```text
Name
Age
USN
```

Behaviors

```text
Study()
AttendClass()
WriteExam()
```

This can be represented as

```text
Student
│
├── Name
├── Age
├── USN
│
├── Study()
├── AttendClass()
└── WriteExam()
```

---

# Advantages of OOP

- Code Reusability
- Better Organization
- Easy Maintenance
- Easy Debugging
- Scalability
- Real-world Modeling
- Better Security through Encapsulation

---

# Disadvantages of OOP

- More memory usage.
- Learning curve for beginners.
- Small programs may become more complex.

---

# Where is OOP Used?

OOP is widely used in:

- Desktop Applications
- Android Development
- Enterprise Applications
- Banking Systems
- Hospital Management Systems
- E-commerce Applications
- Game Development

---

# Common Mistakes

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

## Thinking OOP Means Only Classes

Classes are only one part of OOP.

The main concepts are:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

# Best Practices

- Design classes around real-world entities.
- Keep one responsibility per class.
- Use meaningful class names.
- Reuse classes whenever possible.
- Follow OOP principles while designing applications.

---

# Interview Questions

## 1. What is Object-Oriented Programming?

Object-Oriented Programming (OOP) is a programming paradigm that organizes programs using objects containing data and methods.

---

## 2. Why is OOP important?

It improves code organization, reusability, maintainability, and scalability.

---

## 3. What are the four pillars of OOP?

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

---

## 4. What is the difference between procedural programming and OOP?

Procedural programming focuses on functions, while OOP focuses on objects.

---

## 5. What is an object?

An object is an instance of a class that contains data and behavior.

---

# Summary

- OOP stands for Object-Oriented Programming.
- OOP organizes programs using objects.
- Objects contain properties and methods.
- Classes act as blueprints for creating objects.
- Java is primarily an Object-Oriented Programming language.
- The four pillars of OOP are Encapsulation, Inheritance, Polymorphism, and Abstraction.
