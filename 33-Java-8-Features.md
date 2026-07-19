# Java 8 Features

## Overview

Java 8 is one of the most important releases of Java.

Released in **March 2014**, it introduced several powerful features that made Java more modern, concise, and efficient.

Major improvements include:

- Lambda Expressions
- Functional Interfaces
- Stream API
- Method References
- Default Methods
- Static Methods in Interfaces
- Optional Class
- Date and Time API
- CompletableFuture
- Nashorn JavaScript Engine

---

# Why Java 8?

Before Java 8, Java programs required more boilerplate code.

Example (Before Java 8)

```java
Collections.sort(names, new Comparator<String>() {

    @Override
    public int compare(String a, String b) {

        return a.compareTo(b);

    }

});
```

With Java 8

```java
names.sort((a, b) -> a.compareTo(b));
```

The code becomes shorter, cleaner, and easier to read.

---

# Major Java 8 Features

```text
Java 8
│
├── Lambda Expressions
├── Functional Interfaces
├── Method References
├── Stream API
├── Default Methods
├── Static Interface Methods
├── Optional Class
├── New Date & Time API
├── CompletableFuture
└── Nashorn Engine
```

---

# 1. Lambda Expressions

Lambda Expressions provide a concise way to implement functional interfaces.

Example

```java
List<String> names =
Arrays.asList("Java", "Python");

names.forEach(name -> System.out.println(name));
```

Benefits

- Less code
- Better readability
- Functional programming support

---

# 2. Functional Interfaces

A Functional Interface contains exactly one abstract method.

Example

```java
@FunctionalInterface
interface Message {

    void show();

}
```

It is mainly used with Lambda Expressions.

---

# 3. Method References

Method References provide a shorter way to call existing methods.

Instead of

```java
names.forEach(name -> System.out.println(name));
```

Use

```java
names.forEach(System.out::println);
```

Syntax

```text
ClassName::methodName
```

Types

- Static Method Reference
- Instance Method Reference
- Constructor Reference

---

# 4. Stream API

The Stream API processes collections efficiently.

Example

```java
List<Integer> numbers =
Arrays.asList(1,2,3,4,5,6);

numbers.stream()
       .filter(n -> n % 2 == 0)
       .forEach(System.out::println);
```

Output

```text
2
4
6
```

---

# 5. Default Methods

Interfaces can contain methods with implementation.

Example

```java
interface Vehicle {

    default void start() {

        System.out.println("Vehicle Started");

    }

}
```

This allows adding new methods to interfaces without breaking existing classes.

---

# 6. Static Methods in Interfaces

Interfaces can contain static methods.

Example

```java
interface MathUtil {

    static void print() {

        System.out.println("Hello");

    }

}
```

Usage

```java
MathUtil.print();
```

---

# 7. Optional Class

The `Optional` class helps avoid `NullPointerException`.

Without Optional

```java
String name = null;

System.out.println(name.length());
```

Runtime Error

With Optional

```java
Optional<String> name =
Optional.ofNullable(null);

System.out.println(name.orElse("Guest"));
```

Output

```text
Guest
```

---

# 8. New Date and Time API

Java 8 introduced the `java.time` package.

Example

```java
LocalDate today = LocalDate.now();

System.out.println(today);
```

Example

```java
LocalTime time = LocalTime.now();

System.out.println(time);
```

Advantages

- Immutable
- Thread-safe
- Easy to use

---

# 9. CompletableFuture

Used for asynchronous programming.

Example

```java
CompletableFuture.runAsync(() -> {

    System.out.println("Running...");

});
```

It allows tasks to execute without blocking the main thread.

---

# 10. Nashorn JavaScript Engine

Java 8 introduced the Nashorn engine to execute JavaScript inside Java applications.

Example

```java
ScriptEngine engine =
new ScriptEngineManager()
.getEngineByName("nashorn");
```

**Note:** Nashorn was deprecated in Java 11 and removed in later versions.

---

# forEach() Method

Collections now support the `forEach()` method.

Example

```java
List<String> languages =
Arrays.asList("Java","Python","C++");

languages.forEach(System.out::println);
```

---

# Method Reference Types

| Type | Example |
|------|---------|
| Static Method | `Math::abs` |
| Instance Method | `System.out::println` |
| Constructor | `Student::new` |

---

# Old Java vs Java 8

| Before Java 8 | Java 8 |
|---------------|---------|
| Anonymous Classes | Lambda Expressions |
| Manual Loops | Stream API |
| No Optional | Optional Class |
| Old Date API | java.time API |
| More Boilerplate | Cleaner Code |

---

# How Java 8 Features Work

```text
Collection
      │
      ▼
Lambda Expression
      │
      ▼
Stream API
      │
      ▼
Method Reference
      │
      ▼
Processed Result
```

---

# Advantages

- Less boilerplate code
- Improved readability
- Functional programming support
- Better collection processing
- Improved date and time handling
- Reduced NullPointerException using Optional
- Easier asynchronous programming

---

# Common Mistakes

## Using Optional for Everything

Incorrect

```java
Optional<Integer> age;
```

Use `Optional` mainly for return values, not for every variable.

---

## Using Streams for Complex Logic

Streams are best for data processing.

Avoid placing large business logic inside stream operations.

---

## Confusing Method References with Lambda Expressions

Lambda

```java
x -> System.out.println(x)
```

Method Reference

```java
System.out::println
```

---

# Best Practices

- Prefer Lambda Expressions over anonymous classes for simple implementations.
- Use Method References when they improve readability.
- Use Stream API for collection processing.
- Use Optional to avoid null-related errors.
- Use the `java.time` package instead of old date classes.
- Use CompletableFuture for asynchronous tasks.

---

# Interview Questions

## 1. What are the major features introduced in Java 8?

- Lambda Expressions
- Functional Interfaces
- Stream API
- Method References
- Default Methods
- Static Interface Methods
- Optional Class
- Date & Time API
- CompletableFuture

---

## 2. What is a Method Reference?

A Method Reference is a shorthand syntax for referring to an existing method using `::`.

---

## 3. Why was Optional introduced?

To reduce `NullPointerException` by safely handling null values.

---

## 4. Which package contains the new Date and Time API?

```java
java.time
```

---

## 5. What is CompletableFuture?

It is a class used for asynchronous, non-blocking programming.

---

## 6. What is the purpose of Default Methods?

They allow interfaces to include method implementations without breaking existing classes.

---

# Summary

- Java 8 introduced several modern features that improved Java programming.
- Lambda Expressions reduce boilerplate code.
- Functional Interfaces work with Lambda Expressions.
- Stream API simplifies collection processing.
- Method References provide cleaner syntax.
- Optional helps prevent `NullPointerException`.
- The `java.time` package replaces the old Date API.
- CompletableFuture enables asynchronous programming.
- Java 8 made Java more readable, maintainable, and efficient.
