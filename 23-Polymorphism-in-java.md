# Polymorphism in Java

## Overview

Polymorphism is one of the four pillars of Object-Oriented Programming (OOP).

The word **Polymorphism** comes from two Greek words:

- **Poly** = Many
- **Morph** = Forms

Polymorphism means **"one interface, many forms."**

It allows the same method or object to behave differently depending on the situation.

---

# Why Do We Need Polymorphism?

Without polymorphism, we would need different method names for similar operations.

Example

Without Polymorphism

```java
addInt()
addDouble()
addFloat()
```

With Polymorphism

```java
add()
```

The same method name performs different operations based on the arguments or the object.

This makes code:

- More reusable
- Easier to understand
- Easier to maintain

---

# Types of Polymorphism

Java supports two types of polymorphism.

```text
Polymorphism
│
├── Compile-Time Polymorphism
│      (Method Overloading)
│
└── Run-Time Polymorphism
       (Method Overriding)
```

---

# 1. Compile-Time Polymorphism

Compile-time polymorphism is achieved through **Method Overloading**.

The compiler determines which method to call based on the method signature.

---

## Method Overloading

Methods have:

- Same name
- Different parameter lists

Example

```java
class Calculator {

    int add(int a, int b) {

        return a + b;

    }

    double add(double a, double b) {

        return a + b;

    }

}

public class Main {

    public static void main(String[] args) {

        Calculator c = new Calculator();

        System.out.println(c.add(10, 20));
        System.out.println(c.add(5.5, 4.5));

    }

}
```

Output

```text
30
10.0
```

---

# How Compile-Time Polymorphism Works

```text
Method Call
      │
      ▼
Compiler Checks Parameters
      │
      ▼
Correct Method Selected
      │
      ▼
Method Executes
```

The compiler decides the method **before the program runs**.

---

# 2. Run-Time Polymorphism

Run-time polymorphism is achieved through **Method Overriding**.

The JVM decides which method to execute **while the program is running**.

---

## Method Overriding

A child class provides its own implementation of a method already present in the parent class.

Example

```java
class Animal {

    void sound() {

        System.out.println("Animal makes a sound");

    }

}

class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Dog barks");

    }

}
```

---

# Example

```java
class Animal {

    void sound() {

        System.out.println("Animal makes a sound");

    }

}

class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Dog barks");

    }

}

public class Main {

    public static void main(String[] args) {

        Animal obj = new Dog();

        obj.sound();

    }

}
```

Output

```text
Dog barks
```

Although the reference type is `Animal`, the actual object is `Dog`, so the overridden method is executed.

---

# Behind the Scenes

```java
Animal obj = new Dog();

obj.sound();
```

Execution Flow

```text
Dog Object Created
       │
       ▼
Reference Type = Animal
       │
       ▼
JVM Checks Actual Object
       │
       ▼
Dog.sound() Found
       │
       ▼
Dog.sound() Executes
```

This process is called **Dynamic Method Dispatch**.

---

# Method Overloading vs Method Overriding

| Method Overloading | Method Overriding |
|--------------------|-------------------|
| Same class | Parent and child classes |
| Same method name | Same method name |
| Different parameters | Same parameters |
| Compile-time | Run-time |
| Compiler decides | JVM decides |

---

# Rules for Method Overriding

- Method name must be the same.
- Parameters must be the same.
- Return type must be the same or compatible.
- Access modifier cannot be more restrictive.
- Static methods cannot be overridden.
- Constructors cannot be overridden.

---

# Dynamic Method Dispatch

Dynamic Method Dispatch is the mechanism by which Java determines which overridden method to execute at runtime.

Example

```java
Animal obj = new Dog();

obj.sound();
```

The JVM looks at the **actual object (`Dog`)**, not the reference type (`Animal`).

---

# Advantages of Polymorphism

- Code Reusability
- Flexibility
- Extensibility
- Loose Coupling
- Easy Maintenance
- Cleaner Code

---

# Common Mistakes

## Confusing Overloading with Overriding

Incorrect Thinking

```text
Overloading = Overriding
```

Correct

```text
Overloading
→ Different parameters

Overriding
→ Same method signature in parent and child classes
```

---

## Expecting Static Methods to Override

Incorrect

```java
class Parent {

    static void show() {

    }

}

class Child extends Parent {

    static void show() {

    }

}
```

This is **method hiding**, not overriding.

---

## Forgetting `@Override`

Although optional, it is recommended.

Correct

```java
@Override
void sound() {

}
```

The compiler checks whether the method is actually overriding another method.

---

# Best Practices

- Use method overloading when similar operations require different parameters.
- Use method overriding to customize inherited behavior.
- Always use the `@Override` annotation when overriding methods.
- Program to parent references whenever appropriate.

Example

```java
Animal obj = new Dog();
```

instead of

```java
Dog obj = new Dog();
```

---

# Interview Questions

## 1. What is polymorphism?

Polymorphism is the ability of one interface or method to have multiple forms or behaviors.

---

## 2. What are the types of polymorphism in Java?

- Compile-Time Polymorphism (Method Overloading)
- Run-Time Polymorphism (Method Overriding)

---

## 3. What is method overloading?

Method overloading is defining multiple methods with the same name but different parameter lists.

---

## 4. What is method overriding?

Method overriding is providing a new implementation of an inherited method in the child class.

---

## 5. What is Dynamic Method Dispatch?

It is the runtime mechanism where the JVM calls the overridden method based on the actual object.

---

## 6. Can constructors be overridden?

No.

Constructors are not inherited, so they cannot be overridden.

---

# Summary

- Polymorphism means **one interface, many forms**.
- Java supports compile-time and run-time polymorphism.
- Compile-time polymorphism is achieved using method overloading.
- Run-time polymorphism is achieved using method overriding.
- The JVM uses Dynamic Method Dispatch to execute overridden methods.
- Polymorphism improves flexibility, reusability, and maintainability.
