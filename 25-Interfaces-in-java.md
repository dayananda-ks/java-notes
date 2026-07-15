# Interfaces in Java

## Overview

An **Interface** in Java is a blueprint that defines a set of methods that a class must implement.

It is used to achieve:

- Abstraction
- Multiple Inheritance
- Loose Coupling
- Standardization

An interface tells **what a class should do**, not **how it should do it**.

---

# Why Do We Need Interfaces?

Suppose you are developing different payment systems.

Each payment method should support:

- Pay
- Refund

Different payment methods implement them differently.

```text
Payment
│
├── UPI
├── Credit Card
└── Net Banking
```

Instead of writing the same design repeatedly, we create an interface.

---

# Real-World Example

Think about a TV Remote.

The remote has buttons like:

- Power On
- Power Off
- Volume Up
- Volume Down

Every TV brand performs these operations differently.

The **remote is the interface**, while each TV brand provides its own implementation.

---

# Syntax

```java
interface Animal {

    void sound();

}
```

An interface is declared using the `interface` keyword.

---

# Implementing an Interface

Classes implement an interface using the `implements` keyword.

Example

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

    @Override
    public void sound() {

        System.out.println("Dog Barks");

    }

}
```

---

# Complete Example

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

    @Override
    public void sound() {

        System.out.println("Dog Barks");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog dog = new Dog();

        dog.sound();

    }

}
```

Output

```text
Dog Barks
```

---

# How It Works

```text
Interface Created
        │
        ▼
Class Implements Interface
        │
        ▼
Required Methods Implemented
        │
        ▼
Object Created
        │
        ▼
Methods Execute
```

---

# Rules of Interfaces

- Interface cannot have objects.
- Interface methods are `public abstract` by default.
- Interface variables are `public static final` by default.
- A class must implement all abstract methods.
- A class can implement multiple interfaces.

---

# Interface Variables

Example

```java
interface Demo {

    int VALUE = 100;

}
```

Java automatically treats it as:

```java
public static final int VALUE = 100;
```

It behaves like a constant.

---

# Interface Methods

Example

```java
interface Demo {

    void display();

}
```

Java automatically treats it as:

```java
public abstract void display();
```

---

# Multiple Interfaces

A class can implement more than one interface.

Example

```java
interface A {

    void methodA();

}

interface B {

    void methodB();

}

class Demo implements A, B {

    public void methodA() {

        System.out.println("Method A");

    }

    public void methodB() {

        System.out.println("Method B");

    }

}
```

Output

```text
Method A
Method B
```

This is how Java supports **Multiple Inheritance**.

---

# Interface Reference

Example

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

    public void sound() {

        System.out.println("Dog Barks");

    }

}

public class Main {

    public static void main(String[] args) {

        Animal animal = new Dog();

        animal.sound();

    }

}
```

Output

```text
Dog Barks
```

The reference is of type `Animal`, but the object is `Dog`.

This is Runtime Polymorphism.

---

# Interface vs Abstract Class

| Interface | Abstract Class |
|-----------|----------------|
| Uses `interface` keyword | Uses `abstract` keyword |
| Supports multiple inheritance | Does not support multiple inheritance |
| Methods are abstract by default | Can have abstract and normal methods |
| Variables are constants | Variables can be normal |
| No constructors | Can have constructors |

---

# Default Methods (Java 8)

Interfaces can contain methods with implementation using the `default` keyword.

Example

```java
interface Vehicle {

    default void start() {

        System.out.println("Vehicle Started");

    }

}
```

---

# Static Methods in Interface

Interfaces can also contain static methods.

Example

```java
interface Utility {

    static void show() {

        System.out.println("Static Method");

    }

}
```

Call it like this:

```java
Utility.show();
```

---

# Private Methods (Java 9)

Interfaces can contain private methods.

Example

```java
interface Demo {

    private void message() {

        System.out.println("Private Method");

    }

}
```

Private methods are used internally inside the interface.

---

# Advantages

- Achieves abstraction
- Supports multiple inheritance
- Promotes loose coupling
- Makes code reusable
- Improves maintainability
- Defines a common contract

---

# Common Mistakes

## Creating an Object

Incorrect

```java
Animal animal = new Animal();
```

Correct

```java
Animal animal = new Dog();
```

---

## Forgetting `public`

Incorrect

```java
void sound() {

}
```

Correct

```java
public void sound() {

}
```

Implemented methods must remain `public`.

---

## Modifying Interface Variables

Incorrect

```java
Demo.VALUE = 200;
```

Compilation Error

Interface variables are constants.

---

# Best Practices

- Use interfaces to define behavior.
- Keep interfaces focused on one responsibility.
- Prefer interfaces when unrelated classes share the same functionality.
- Use abstract classes when common implementation needs to be shared.

---

# Interview Questions

## 1. What is an Interface?

An interface is a blueprint that defines methods which implementing classes must provide.

---

## 2. Which keyword is used to implement an interface?

```java
implements
```

---

## 3. Can we create an object of an interface?

No.

Interfaces cannot be instantiated.

---

## 4. Can a class implement multiple interfaces?

Yes.

A class can implement multiple interfaces.

---

## 5. What are interface variables?

All interface variables are automatically:

```java
public static final
```

---

## 6. What are interface methods?

By default, interface methods are:

```java
public abstract
```

---

## 7. What is the difference between an Interface and an Abstract Class?

Interfaces define a contract and support multiple inheritance.

Abstract classes provide partial implementation and common functionality.

---

# Summary

- An interface defines a contract for classes.
- Interfaces are declared using the `interface` keyword.
- Classes implement interfaces using the `implements` keyword.
- Interface methods are `public abstract` by default.
- Interface variables are `public static final`.
- Interfaces support multiple inheritance.
- Interfaces are widely used to achieve abstraction, polymorphism, and loose coupling.
