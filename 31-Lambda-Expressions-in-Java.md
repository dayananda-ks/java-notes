# Lambda Expressions in Java

## Overview

A **Lambda Expression** is a concise way to write anonymous functions in Java.

It was introduced in **Java 8** to make code shorter, cleaner, and more readable.

Lambda Expressions are mainly used with:

- Functional Interfaces
- Collections
- Stream API

---

# Why Do We Need Lambda Expressions?

Before Java 8, implementing a simple interface often required creating a separate class or an anonymous class.

Example (Without Lambda)

```java
interface Greeting {

    void sayHello();

}

public class Main {

    public static void main(String[] args) {

        Greeting g = new Greeting() {

            @Override
            public void sayHello() {

                System.out.println("Hello");

            }

        };

        g.sayHello();

    }

}
```

This requires a lot of code.

With Lambda Expression

```java
Greeting g = () -> System.out.println("Hello");

g.sayHello();
```

The same work is done with much less code.

---

# What is a Lambda Expression?

A Lambda Expression is an **anonymous function**.

It has:

- No name
- No return type declaration
- No access modifier

General Syntax

```java
(parameters) -> expression
```

or

```java
(parameters) -> {

    // Statements

}
```

---

# Lambda Expression Syntax

```java
(parameter) -> expression
```

Example

```java
x -> x * x
```

With multiple parameters

```java
(a, b) -> a + b
```

With a block

```java
(a, b) -> {

    return a + b;

}
```

---

# Functional Interface

A Lambda Expression works only with a **Functional Interface**.

A Functional Interface contains **exactly one abstract method**.

Example

```java
interface Message {

    void print();

}
```

---

# Simple Example

```java
interface Message {

    void print();

}

public class Main {

    public static void main(String[] args) {

        Message msg = () -> System.out.println("Hello Java");

        msg.print();

    }

}
```

Output

```text
Hello Java
```

---

# Lambda with Parameters

Example

```java
interface Add {

    int sum(int a, int b);

}

public class Main {

    public static void main(String[] args) {

        Add add = (a, b) -> a + b;

        System.out.println(add.sum(10, 20));

    }

}
```

Output

```text
30
```

---

# Lambda with Multiple Statements

Example

```java
interface Square {

    int calculate(int x);

}

public class Main {

    public static void main(String[] args) {

        Square s = (x) -> {

            int result = x * x;

            return result;

        };

        System.out.println(s.calculate(5));

    }

}
```

Output

```text
25
```

---

# Lambda with No Parameters

Example

```java
interface Welcome {

    void greet();

}

public class Main {

    public static void main(String[] args) {

        Welcome w = () -> System.out.println("Welcome");

        w.greet();

    }

}
```

Output

```text
Welcome
```

---

# How Lambda Works

```text
Functional Interface
        │
        ▼
Lambda Expression
        │
        ▼
Compiler Converts Lambda
        │
        ▼
Method Executes
```

---

# Functional Interface Annotation

Java provides the `@FunctionalInterface` annotation.

Example

```java
@FunctionalInterface
interface Demo {

    void show();

}
```

If another abstract method is added, the compiler reports an error.

---

# Built-in Functional Interfaces

Java provides several built-in functional interfaces in the `java.util.function` package.

| Interface | Method | Purpose |
|-----------|--------|---------|
| Predicate<T> | test() | Returns true or false |
| Function<T,R> | apply() | Converts one type to another |
| Consumer<T> | accept() | Consumes data |
| Supplier<T> | get() | Supplies data |

---

# Predicate Example

```java
import java.util.function.Predicate;

public class Main {

    public static void main(String[] args) {

        Predicate<Integer> even = n -> n % 2 == 0;

        System.out.println(even.test(8));

    }

}
```

Output

```text
true
```

---

# Consumer Example

```java
import java.util.function.Consumer;

public class Main {

    public static void main(String[] args) {

        Consumer<String> c = name -> System.out.println(name);

        c.accept("Java");

    }

}
```

Output

```text
Java
```

---

# Function Example

```java
import java.util.function.Function;

public class Main {

    public static void main(String[] args) {

        Function<Integer, Integer> square = x -> x * x;

        System.out.println(square.apply(5));

    }

}
```

Output

```text
25
```

---

# Supplier Example

```java
import java.util.function.Supplier;

public class Main {

    public static void main(String[] args) {

        Supplier<String> s = () -> "Hello";

        System.out.println(s.get());

    }

}
```

Output

```text
Hello
```

---

# Advantages

- Reduces boilerplate code
- Improves readability
- Makes code concise
- Supports functional programming
- Works well with Stream API

---

# Common Mistakes

## Using Lambda Without a Functional Interface

Incorrect

```java
interface Demo {

    void show();

    void print();

}
```

Compilation Error

A Lambda Expression requires exactly one abstract method.

---

## Forgetting Return Statement

Incorrect

```java
(a, b) -> {

    a + b;

}
```

Correct

```java
(a, b) -> {

    return a + b;

}
```

---

## Adding Parentheses Incorrectly

Correct

```java
x -> x * x
```

or

```java
(x) -> x * x
```

Both are valid for a single parameter.

---

# Best Practices

- Use Lambda Expressions for short and simple logic.
- Use method references when possible.
- Keep lambda expressions readable.
- Prefer built-in functional interfaces over creating new ones.
- Avoid writing large blocks of code inside lambdas.

---

# Interview Questions

## 1. What is a Lambda Expression?

A Lambda Expression is an anonymous function used to implement the single abstract method of a functional interface.

---

## 2. In which version of Java were Lambda Expressions introduced?

Java 8.

---

## 3. What is a Functional Interface?

A Functional Interface is an interface that contains exactly one abstract method.

---

## 4. Can a Functional Interface have default or static methods?

Yes.

It can have multiple default and static methods, but only one abstract method.

---

## 5. What is the purpose of the `@FunctionalInterface` annotation?

It ensures that the interface contains exactly one abstract method.

---

## 6. Name some built-in Functional Interfaces.

- Predicate
- Function
- Consumer
- Supplier

---

# Summary

- Lambda Expressions were introduced in Java 8.
- They provide a concise way to implement functional interfaces.
- A Lambda Expression works only with a functional interface.
- Functional interfaces contain exactly one abstract method.
- Java provides built-in functional interfaces such as `Predicate`, `Function`, `Consumer`, and `Supplier`.
- Lambda Expressions make Java code cleaner, shorter, and easier to read.
