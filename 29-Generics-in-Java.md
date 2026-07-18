# Generics in Java

## Overview

Generics is a feature in Java that allows us to write classes, interfaces, and methods that work with different data types while maintaining type safety.

Generics were introduced in **Java 5**.

Instead of creating separate code for different data types, we can write one generic implementation.

---

# Why Do We Need Generics?

Without Generics

```java
ArrayList list = new ArrayList();

list.add("Java");
list.add(100);

String name = (String) list.get(1);
```

Output

```text
Runtime Error
(ClassCastException)
```

Since the list accepts every type, wrong data can be added.

---

With Generics

```java
ArrayList<String> list = new ArrayList<>();

list.add("Java");
list.add("Python");
```

Now only `String` values can be stored.

Trying to add

```java
list.add(100);
```

produces a **Compilation Error**.

Generics catch errors during compilation instead of runtime.

---

# Advantages of Generics

- Type Safety
- Code Reusability
- No Explicit Type Casting
- Better Readability
- Compile-Time Error Checking

---

# Generic Class

A generic class uses a type parameter.

Syntax

```java
class ClassName<T> {

}
```

Example

```java
class Box<T> {

    T value;

    void setValue(T value) {

        this.value = value;

    }

    T getValue() {

        return value;

    }

}
```

---

# Using a Generic Class

```java
public class Main {

    public static void main(String[] args) {

        Box<String> box = new Box<>();

        box.setValue("Java");

        System.out.println(box.getValue());

    }

}
```

Output

```text
Java
```

---

# Multiple Type Parameters

Generics can use more than one type.

Example

```java
class Pair<K, V> {

    K key;
    V value;

    Pair(K key, V value) {

        this.key = key;
        this.value = value;

    }

}
```

Usage

```java
Pair<Integer, String> student =
new Pair<>(101, "Ashu");
```

---

# Generic Methods

Methods can also be generic.

Syntax

```java
<T> ReturnType methodName(T value)
```

Example

```java
public class Demo {

    public static <T> void print(T value) {

        System.out.println(value);

    }

}
```

Usage

```java
Demo.print("Java");
Demo.print(100);
Demo.print(10.5);
```

Output

```text
Java
100
10.5
```

---

# Generic Interface

Interfaces can also use generics.

Example

```java
interface Printer<T> {

    void print(T value);

}
```

Implementation

```java
class StringPrinter implements Printer<String> {

    public void print(String value) {

        System.out.println(value);

    }

}
```

---

# Type Parameters

Common generic type names.

| Type | Meaning |
|------|---------|
| T | Type |
| E | Element |
| K | Key |
| V | Value |
| N | Number |

These are conventions, not keywords.

---

# Bounded Generics

Sometimes we want to restrict the allowed data types.

Example

```java
class Calculator<T extends Number> {

    T value;

}
```

Allowed

```java
Calculator<Integer>
Calculator<Double>
Calculator<Float>
```

Not Allowed

```java
Calculator<String>
```

---

# Wildcards

The wildcard symbol is:

```java
?
```

Example

```java
ArrayList<?> list;
```

This means the list can hold any type.

---

# Upper Bounded Wildcard

```java
<? extends Number>
```

Example

```java
List<? extends Number> numbers;
```

Accepts

- Integer
- Double
- Float
- Long

---

# Lower Bounded Wildcard

```java
<? super Integer>
```

Accepts

- Integer
- Number
- Object

---

# Generic Collections

Example

```java
ArrayList<String> languages =
new ArrayList<>();

languages.add("Java");
languages.add("Python");
```

Example

```java
HashMap<Integer, String> students =
new HashMap<>();
```

---

# How Generics Work

```text
Program Starts
       │
       ▼
Generic Class Defined
       │
       ▼
Type Specified
(Box<String>)
       │
       ▼
Compiler Checks Type
       │
       ▼
Object Created
       │
       ▼
Only Valid Data Accepted
```

---

# Generics vs Object

Using Object

```java
class Box {

    Object value;

}
```

Problems

- No type safety
- Explicit casting required
- Runtime errors possible

Using Generics

```java
class Box<T> {

    T value;

}
```

Advantages

- Type safety
- No casting
- Compile-time checking

---

# Common Mistakes

## Using Raw Types

Incorrect

```java
ArrayList list =
new ArrayList();
```

Correct

```java
ArrayList<String> list =
new ArrayList<>();
```

---

## Mixing Data Types

Incorrect

```java
ArrayList<String> list =
new ArrayList<>();

list.add(100);
```

Compilation Error

---

## Forgetting Type Parameters

Incorrect

```java
Box box =
new Box();
```

Correct

```java
Box<String> box =
new Box<>();
```

---

# Best Practices

- Always use generics with collections.
- Avoid raw types.
- Use meaningful type parameters.
- Prefer compile-time type checking over runtime casting.
- Use bounded generics when restricting data types.

---

# Interview Questions

## 1. What are Generics?

Generics allow classes, interfaces, and methods to work with different data types while maintaining type safety.

---

## 2. Why were Generics introduced?

To provide:

- Type Safety
- Code Reusability
- Compile-Time Error Checking

---

## 3. What is a Generic Class?

A class that uses a type parameter.

Example

```java
class Box<T> {

}
```

---

## 4. What is the difference between Generics and Object?

| Generics | Object |
|----------|---------|
| Type Safe | Not Type Safe |
| Compile-Time Checking | Runtime Checking |
| No Casting | Requires Casting |

---

## 5. What does `<T>` mean?

`T` represents a type parameter.

It can represent any data type.

---

## 6. What is a Bounded Generic?

A generic restricted to certain types.

Example

```java
<T extends Number>
```

---

## 7. What is a Wildcard?

The wildcard `?` represents an unknown type.

Example

```java
List<?>
```

---

# Summary

- Generics allow Java code to work with different data types safely.
- They improve type safety and eliminate unnecessary type casting.
- Generic classes, methods, and interfaces make code reusable.
- Bounded generics restrict allowed data types.
- Wildcards (`?`) provide flexibility when working with unknown types.
- Generics are widely used in the Java Collections Framework.
