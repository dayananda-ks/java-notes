# Java Design Patterns

## Overview

A **Design Pattern** is a proven and reusable solution to a commonly occurring software design problem.

Design patterns are **not ready-made code**. They are templates or best practices that help developers write clean, maintainable, and scalable software.

Design Patterns became popular through the book:

**"Design Patterns: Elements of Reusable Object-Oriented Software"** (Gang of Four - GoF)

---

# Why Do We Need Design Patterns?

Suppose every developer solves the same problem differently.

Problems

- Difficult to maintain
- Hard to understand
- Code duplication
- Poor scalability

Using Design Patterns

- Reusable solutions
- Better code organization
- Easier maintenance
- Improved scalability

---

# Categories of Design Patterns

There are **23 GoF Design Patterns**, divided into three categories.

```text
Design Patterns
       │
       ├──────────────┬──────────────┐
       │              │              │
   Creational     Structural     Behavioral
```

---

# 1. Creational Patterns

Creational patterns deal with **object creation**.

Examples

- Singleton
- Factory Method
- Abstract Factory
- Builder
- Prototype

---

# Singleton Pattern

Ensures that **only one object** of a class exists.

Example

```java
class Database {

    private static Database instance;

    private Database() {

    }

    public static Database getInstance() {

        if(instance == null){

            instance = new Database();

        }

        return instance;

    }

}
```

Usage

```java
Database db = Database.getInstance();
```

Common Uses

- Logger
- Configuration
- Database Connection Manager

---

# Factory Pattern

Creates objects without exposing the object creation logic.

Example

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

    public void sound() {

        System.out.println("Bark");

    }

}

class Cat implements Animal {

    public void sound() {

        System.out.println("Meow");

    }

}
```

Factory

```java
class AnimalFactory {

    public Animal getAnimal(String type){

        if(type.equals("Dog")){

            return new Dog();

        }

        return new Cat();

    }

}
```

---

# Builder Pattern

Used to create complex objects step by step.

Example

```java
Student student =
new StudentBuilder()
.setName("Ashu")
.setAge(21)
.build();
```

Useful when a class has many optional fields.

---

# Prototype Pattern

Creates new objects by copying existing ones.

Example

```java
Student copy =
original.clone();
```

---

# 2. Structural Patterns

Structural patterns explain how classes and objects are organized.

Examples

- Adapter
- Decorator
- Facade
- Proxy
- Composite
- Bridge
- Flyweight

---

# Adapter Pattern

Allows incompatible classes to work together.

Example

```text
Old System

↓

Adapter

↓

New System
```

Real-world Example

- Mobile charger adapter

---

# Decorator Pattern

Adds new functionality without changing existing code.

Example

```text
Coffee

↓

Milk

↓

Chocolate

↓

Final Coffee
```

---

# Facade Pattern

Provides a simple interface to a complex system.

Example

```java
Computer.start();
```

Internally it performs many operations.

---

# Proxy Pattern

A proxy controls access to another object.

Uses

- Security
- Caching
- Lazy Loading

---

# 3. Behavioral Patterns

Behavioral patterns define how objects communicate.

Examples

- Observer
- Strategy
- Command
- Iterator
- State
- Template Method
- Visitor
- Mediator
- Chain of Responsibility
- Memento

---

# Observer Pattern

One object notifies multiple objects when its state changes.

Example

```text
YouTube Channel

↓

Subscribers Receive Notification
```

Common Uses

- Event handling
- Notifications

---

# Strategy Pattern

Allows selecting an algorithm at runtime.

Example

```text
Payment

↓

Credit Card

UPI

PayPal
```

Each payment method is a strategy.

---

# Command Pattern

Encapsulates a request as an object.

Example

```text
Remote Control

↓

Turn On TV
```

---

# Iterator Pattern

Provides sequential access to collection elements.

Example

```java
Iterator<String> iterator =
list.iterator();

while(iterator.hasNext()){

    System.out.println(iterator.next());

}
```

---

# Design Pattern Classification

| Category | Purpose |
|-----------|---------|
| Creational | Object Creation |
| Structural | Class/Object Structure |
| Behavioral | Object Communication |

---

# Most Common Patterns in Spring Boot

| Pattern | Usage |
|-----------|-------|
| Singleton | Spring Beans |
| Factory | Bean Creation |
| Builder | Lombok Builder |
| Proxy | Spring AOP |
| Observer | Event Handling |
| Template | JdbcTemplate, RestTemplate |

---

# Real-World Examples

| Pattern | Example |
|-----------|----------|
| Singleton | Logger |
| Factory | Notification Service |
| Builder | User Registration |
| Observer | YouTube Notifications |
| Strategy | Payment Gateway |
| Proxy | Authentication |
| Adapter | Mobile Charger |
| Decorator | Coffee Toppings |

---

# How Design Patterns Work

```text
Problem
    │
    ▼
Choose Pattern
    │
    ▼
Apply Pattern
    │
    ▼
Reusable & Maintainable Code
```

---

# Advantages

- Reusable solutions
- Cleaner architecture
- Easier maintenance
- Better scalability
- Reduced code duplication
- Easier teamwork

---

# Common Mistakes

## Using Design Patterns Everywhere

Design patterns solve specific problems.

Do not use them unless they are needed.

---

## Choosing the Wrong Pattern

Example

Using Singleton where multiple objects are required.

---

## Ignoring SOLID Principles

Design patterns work best when combined with SOLID principles.

---

# Best Practices

- Understand the problem before choosing a pattern.
- Prefer simple solutions over unnecessary patterns.
- Follow SOLID principles.
- Use composition instead of inheritance when appropriate.
- Learn commonly used patterns before advanced ones.

---

# Interview Questions

## 1. What is a Design Pattern?

A Design Pattern is a reusable solution to a commonly occurring software design problem.

---

## 2. How many GoF Design Patterns are there?

There are **23 Gang of Four (GoF)** Design Patterns.

---

## 3. What are the three categories of Design Patterns?

- Creational
- Structural
- Behavioral

---

## 4. What is the Singleton Pattern?

It ensures that only one instance of a class exists throughout the application.

---

## 5. What is the Factory Pattern?

It creates objects without exposing the object creation logic.

---

## 6. Which Design Pattern is used for event notifications?

The **Observer Pattern**.

---

## 7. Which Design Pattern is commonly used in Spring Boot?

- Singleton
- Factory
- Proxy
- Builder
- Observer
- Template

---

# Summary

- Design Patterns are proven solutions to common software design problems.
- The 23 GoF Design Patterns are grouped into Creational, Structural, and Behavioral categories.
- Creational patterns focus on object creation.
- Structural patterns organize classes and objects.
- Behavioral patterns define communication between objects.
- Common patterns like Singleton, Factory, Builder, Observer, and Strategy are widely used in real-world Java and Spring Boot applications.
- Choosing the right design pattern improves code quality, scalability, and maintainability.
