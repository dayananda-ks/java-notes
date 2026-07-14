# Inheritance in Java

## Overview

Inheritance is one of the four pillars of Object-Oriented Programming (OOP).

Inheritance allows one class to **acquire the properties and methods of another class**.

The class that provides the properties is called the **Parent (Super/Base) Class**.

The class that acquires the properties is called the **Child (Sub/Derived) Class**.

Inheritance promotes **code reusability** and establishes an **"is-a" relationship**.

---

# Why Do We Need Inheritance?

Suppose we have two classes.

Without Inheritance

```java
class Animal {

    void eat() {
        System.out.println("Animal is eating");
    }

}

class Dog {

    void eat() {
        System.out.println("Animal is eating");
    }

}
```

The `eat()` method is duplicated.

With Inheritance

```java
class Animal {

    void eat() {
        System.out.println("Animal is eating");
    }

}

class Dog extends Animal {

}
```

Now `Dog` automatically inherits the `eat()` method.

---

# Real-World Example

```text
Animal
│
├── eat()
├── sleep()
└── breathe()

        ▲
        │

      Dog
      Cat
      Lion
```

Every Dog, Cat, and Lion is an **Animal**.

---

# Syntax

```java
class Parent {

}
```

```java
class Child extends Parent {

}
```

The `extends` keyword is used to inherit a class.

---

# How Inheritance Works

```text
Parent Class
      │
      ▼
Child Class extends Parent
      │
      ▼
Child Gets Parent's Members
      │
      ▼
Child Can Add New Members
```

---

# Example

```java
class Animal {

    void eat() {

        System.out.println("Animal is eating");

    }

}

class Dog extends Animal {

    void bark() {

        System.out.println("Dog is barking");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog dog = new Dog();

        dog.eat();

        dog.bark();

    }

}
```

Output

```text
Animal is eating
Dog is barking
```

---

# Behind the Scenes

```java
Dog dog = new Dog();
```

Execution Flow

```text
Dog Object Created
        │
        ▼
Animal Class Members Loaded
        │
        ▼
Dog Class Members Loaded
        │
        ▼
Dog Object Ready
```

The child object contains both the parent's inherited members and its own members.

---

# Types of Inheritance

## 1. Single Inheritance

One child inherits from one parent.

```text
Animal
   │
   ▼
 Dog
```

---

## 2. Multilevel Inheritance

A child becomes the parent of another class.

```text
Animal
   │
   ▼
 Dog
   │
   ▼
 Puppy
```

---

## 3. Hierarchical Inheritance

Multiple child classes inherit from one parent.

```text
        Animal
       /   |   \
     Dog  Cat  Lion
```

---

## Types Not Supported by Classes

### Multiple Inheritance

```text
Parent1
    \
     \
      Child
     /
    /
Parent2
```

Java **does not support** multiple inheritance with classes because it can create ambiguity (Diamond Problem).

Java achieves this using **Interfaces**, which will be covered later.

---

# `super` Keyword

The `super` keyword refers to the immediate parent class.

It is used to:

- Access parent variables.
- Call parent methods.
- Call the parent constructor.

Example

```java
class Animal {

    void eat() {

        System.out.println("Animal is eating");

    }

}

class Dog extends Animal {

    void eat() {

        super.eat();

        System.out.println("Dog is eating");

    }

}
```

Output

```text
Animal is eating
Dog is eating
```

---

# Constructor Execution Order

Example

```java
class Animal {

    Animal() {

        System.out.println("Animal Constructor");

    }

}

class Dog extends Animal {

    Dog() {

        System.out.println("Dog Constructor");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog d = new Dog();

    }

}
```

Output

```text
Animal Constructor
Dog Constructor
```

The parent constructor executes before the child constructor.

---

# What is Inherited?

| Member | Inherited? |
|---------|------------|
| Variables | ✅ |
| Methods | ✅ |
| Constructors | ❌ |
| Private Members | ❌ |

Constructors are **not inherited**, but the parent constructor is called during object creation.

Private members belong only to the parent class and cannot be accessed directly by the child class.

---

# Advantages of Inheritance

- Code Reusability
- Reduced Code Duplication
- Easy Maintenance
- Extensibility
- Supports Method Overriding
- Represents Real-World Relationships

---

# Common Mistakes

## Forgetting `extends`

Incorrect

```java
class Dog {

}
```

The class does not inherit anything.

Correct

```java
class Dog extends Animal {

}
```

---

## Trying to Access Private Members

Incorrect

```java
class Animal {

    private int age = 5;

}

class Dog extends Animal {

    void show() {

        System.out.println(age);

    }

}
```

Compilation Error

Private members are not accessible directly in child classes.

---

## Assuming Constructors are Inherited

Incorrect Thinking

```text
Child inherits Parent Constructor.
```

Correct

```text
Parent Constructor is called,
but constructors are NOT inherited.
```

---

# Best Practices

- Use inheritance only when there is an **"is-a"** relationship.
- Avoid unnecessary inheritance.
- Keep parent classes generic.
- Use `super` when accessing parent members.
- Prefer composition over inheritance when an "is-a" relationship does not exist.

---

# Interview Questions

## 1. What is inheritance?

Inheritance is the process by which one class acquires the properties and methods of another class.

---

## 2. Which keyword is used for inheritance?

```java
extends
```

---

## 3. What are the advantages of inheritance?

- Code reusability
- Reduced duplication
- Easy maintenance
- Better organization

---

## 4. Does Java support multiple inheritance with classes?

No.

Java supports single, multilevel, and hierarchical inheritance for classes.

Multiple inheritance is achieved using interfaces.

---

## 5. Are constructors inherited?

No.

Constructors are not inherited, but the parent constructor executes before the child constructor.

---

## 6. What is the `super` keyword?

The `super` keyword refers to the immediate parent class and is used to access parent variables, methods, and constructors.

---

# Summary

- Inheritance allows one class to inherit the properties and methods of another class.
- The `extends` keyword is used to create inheritance.
- Inheritance promotes code reusability and maintainability.
- Java supports single, multilevel, and hierarchical inheritance.
- Constructors are not inherited, but the parent constructor is executed first.
- The `super` keyword is used to access members of the parent class.
- Inheritance represents an **"is-a" relationship** between classes.
