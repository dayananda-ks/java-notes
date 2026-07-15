# Abstraction in Java

## Overview

Abstraction is one of the four pillars of Object-Oriented Programming (OOP).

Abstraction is the process of **hiding implementation details and showing only the essential functionality** to the user.

It focuses on **what an object does**, not **how it does it**.

In Java, abstraction is achieved using:

- Abstract Classes
- Interfaces (covered in the next chapter)

---

# Why Do We Need Abstraction?

Suppose you drive a car.

You know how to:

- Start the car
- Accelerate
- Brake

But you don't need to know:

- How the engine works
- How fuel is injected
- How the gearbox operates

The internal implementation is hidden.

This is abstraction.

Similarly, Java hides implementation details and exposes only the required functionality.

---

# Real-World Example

```text
ATM Machine
│
├── Insert Card
├── Enter PIN
├── Withdraw Money
└── Check Balance
```

The user doesn't know how the ATM processes transactions internally.

Only the required operations are visible.

---

# Abstract Class

An **abstract class** is a class that **cannot be instantiated (objects cannot be created directly).**

It is declared using the `abstract` keyword.

An abstract class may contain:

- Abstract methods
- Normal (concrete) methods
- Variables
- Constructors

---

# Syntax

```java
abstract class ClassName {

}
```

Example

```java
abstract class Animal {

}
```

---

# Abstract Method

An abstract method has **no implementation**.

Only the method declaration is provided.

The child class must implement it.

Syntax

```java
abstract void methodName();
```

Example

```java
abstract class Animal {

    abstract void sound();

}
```

---

# Complete Example

```java
abstract class Animal {

    abstract void sound();

    void eat() {

        System.out.println("Animal is eating");

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

        Dog dog = new Dog();

        dog.sound();
        dog.eat();

    }

}
```

Output

```text
Dog barks
Animal is eating
```

---

# Behind the Scenes

```java
Dog dog = new Dog();
```

Execution Flow

```text
Abstract Class Defined
        │
        ▼
Child Class Extends It
        │
        ▼
Child Implements Abstract Methods
        │
        ▼
Object Created Using Child Class
        │
        ▼
Methods Execute
```

---

# Important Rules

- An abstract class cannot be instantiated.
- An abstract class can have constructors.
- An abstract class can contain both abstract and concrete methods.
- If a class contains an abstract method, the class must also be declared `abstract`.
- A child class must implement all inherited abstract methods unless it is also abstract.

---

# Abstract Class vs Concrete Class

| Abstract Class | Concrete Class |
|----------------|----------------|
| Cannot create objects | Objects can be created |
| May contain abstract methods | Contains only implemented methods |
| Used as a blueprint | Used to create objects |

---

# Abstract Method vs Normal Method

| Abstract Method | Normal Method |
|-----------------|---------------|
| No method body | Has method body |
| Ends with `;` | Uses `{}` |
| Must be implemented by child class | Already implemented |

Example

Abstract Method

```java
abstract void sound();
```

Normal Method

```java
void eat() {

    System.out.println("Eating");

}
```

---

# Can an Abstract Class Have a Constructor?

Yes.

Example

```java
abstract class Animal {

    Animal() {

        System.out.println("Animal Constructor");

    }

}
```

The constructor executes when a child object is created.

---

# Can an Abstract Class Have Variables?

Yes.

Example

```java
abstract class Animal {

    String type = "Mammal";

}
```

---

# Can We Create an Object of an Abstract Class?

Incorrect

```java
Animal a = new Animal();
```

Compilation Error

Correct

```java
Animal a = new Dog();
```

The reference type is `Animal`, but the object is `Dog`.

---

# Advantages of Abstraction

- Hides implementation details.
- Reduces code complexity.
- Improves security.
- Encourages code reuse.
- Makes programs easier to maintain.

---

# Common Mistakes

## Creating an Object of an Abstract Class

Incorrect

```java
Animal a = new Animal();
```

Compilation Error

Correct

```java
Animal a = new Dog();
```

---

## Forgetting to Implement Abstract Methods

Incorrect

```java
class Dog extends Animal {

}
```

Compilation Error

Correct

```java
class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Dog barks");

    }

}
```

---

## Forgetting the `abstract` Keyword

Incorrect

```java
class Animal {

    abstract void sound();

}
```

Compilation Error

Correct

```java
abstract class Animal {

    abstract void sound();

}
```

---

# Best Practices

- Use abstract classes when multiple related classes share common behavior.
- Keep only the necessary methods abstract.
- Use concrete methods for shared functionality.
- Do not create objects of abstract classes directly.

---

# Interview Questions

## 1. What is abstraction?

Abstraction is the process of hiding implementation details and exposing only the essential functionality.

---

## 2. How is abstraction achieved in Java?

Using:

- Abstract Classes
- Interfaces

---

## 3. Can we create an object of an abstract class?

No.

An abstract class cannot be instantiated.

---

## 4. Can an abstract class have constructors?

Yes.

Its constructor is called when a child class object is created.

---

## 5. Can an abstract class contain normal methods?

Yes.

It can contain both abstract methods and concrete methods.

---

## 6. What is the difference between abstraction and encapsulation?

| Abstraction | Encapsulation |
|-------------|---------------|
| Hides implementation details | Hides data |
| Focuses on "what" | Focuses on "how data is protected" |
| Achieved using abstract classes and interfaces | Achieved using private variables and getters/setters |

---

# Summary

- Abstraction hides implementation details and exposes only essential functionality.
- Java achieves abstraction using abstract classes and interfaces.
- Abstract classes cannot be instantiated.
- Abstract methods do not have a method body and must be implemented by child classes.
- Abstract classes can contain constructors, variables, abstract methods, and concrete methods.
- Abstraction simplifies programs, improves maintainability, and promotes code reuse.
