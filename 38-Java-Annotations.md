# Java Annotations

## Overview

Annotations are special markers in Java that provide additional information about classes, methods, fields, parameters, and other program elements.

Annotations do not directly change the execution of a program. Instead, they provide metadata that is used by:

- Compiler
- JVM
- Development tools
- Frameworks (Spring, Hibernate, JUnit)

Annotations were introduced in **Java 5**.

---

# Why Do We Need Annotations?

Without annotations, developers had to write extra configuration code.

With annotations, configuration becomes simple and readable.

Example

Without Annotation

```java
public class Student {

    public String toString() {

        return "Student";

    }

}
```

With Annotation

```java
@Override
public String toString() {

    return "Student";

}
```

The compiler checks whether the method actually overrides a parent method.

---

# What is Metadata?

Metadata means **data about data**.

Example

```java
@Override
public void display() {

}
```

`@Override` gives information to the compiler.

It does not become part of the program logic.

---

# Annotation Syntax

General Syntax

```java
@AnnotationName
```

Example

```java
@Override
public String toString() {

    return "Java";

}
```

---

# Built-in Annotations

Java provides several built-in annotations.

Common ones are:

- @Override
- @Deprecated
- @SuppressWarnings
- @FunctionalInterface
- @SafeVarargs

---

# @Override

Indicates that a method overrides a superclass method.

Example

```java
class Animal {

    void sound() {

        System.out.println("Animal Sound");

    }

}

class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Dog Bark");

    }

}
```

If the method name is incorrect, the compiler reports an error.

---

# @Deprecated

Marks a method or class as obsolete.

Example

```java
class Demo {

    @Deprecated
    void oldMethod() {

    }

}
```

The compiler shows a warning when the method is used.

---

# @SuppressWarnings

Suppresses compiler warnings.

Example

```java
@SuppressWarnings("unchecked")
ArrayList list = new ArrayList();
```

---

# @FunctionalInterface

Indicates that an interface contains exactly one abstract method.

Example

```java
@FunctionalInterface
interface Message {

    void print();

}
```

Adding another abstract method causes a compilation error.

---

# @SafeVarargs

Suppresses warnings related to variable arguments (varargs).

Example

```java
@SafeVarargs
public final void display(String... names){

}
```

---

# Custom Annotations

You can create your own annotation.

Syntax

```java
@interface MyAnnotation {

}
```

Example

```java
@interface Author {

    String name();

}
```

Usage

```java
@Author(name = "Ashu")
class Student {

}
```

---

# Annotation Elements

Annotations can have elements.

Example

```java
@interface Info {

    String author();

    int version();

}
```

Usage

```java
@Info(author = "Ashu", version = 1)
class Demo {

}
```

---

# Default Values

Elements can have default values.

Example

```java
@interface Info {

    String author() default "Unknown";

}
```

Usage

```java
@Info
class Demo {

}
```

---

# Meta-Annotations

Meta-Annotations are annotations used to define other annotations.

Common meta-annotations:

- @Target
- @Retention
- @Inherited
- @Documented
- @Repeatable

---

# @Target

Specifies where an annotation can be applied.

Example

```java
@Target(ElementType.METHOD)
@interface Test {

}
```

Now the annotation can only be used on methods.

---

# @Retention

Specifies how long an annotation is retained.

Policies

| Policy | Description |
|---------|-------------|
| SOURCE | Available only during compilation |
| CLASS | Stored in class file |
| RUNTIME | Available at runtime |

Example

```java
@Retention(RetentionPolicy.RUNTIME)
@interface Author {

}
```

---

# @Inherited

Allows child classes to inherit annotations from parent classes.

---

# @Documented

Includes the annotation in generated Java documentation.

---

# @Repeatable

Allows the same annotation to be applied multiple times.

---

# Reflection and Annotations

Annotations are commonly accessed using Reflection.

Example

```java
Class<?> cls = Student.class;

Annotation[] annotations =
cls.getAnnotations();
```

Frameworks such as Spring and Hibernate use Reflection to process annotations.

---

# How Annotations Work

```text
Java Source Code
        │
        ▼
Annotations
        │
        ▼
Compiler / JVM / Framework
        │
        ▼
Additional Processing
```

---

# Common Mistakes

## Forgetting @Override

Incorrect

```java
class Dog extends Animal {

    void sounds(){

    }

}
```

The method name is incorrect.

Using `@Override` helps the compiler detect such mistakes.

---

## Using Deprecated Methods

Avoid using methods marked with:

```java
@Deprecated
```

Use the recommended replacement instead.

---

## Ignoring Compiler Warnings

Avoid using:

```java
@SuppressWarnings("all")
```

Suppress only specific warnings when necessary.

---

# Best Practices

- Always use `@Override` when overriding methods.
- Use `@FunctionalInterface` for functional interfaces.
- Avoid using deprecated APIs.
- Suppress warnings only when justified.
- Use custom annotations for reusable metadata in large applications.

---

# Interview Questions

## 1. What is an Annotation?

An Annotation is metadata that provides additional information about Java code without changing its behavior.

---

## 2. What is the purpose of `@Override`?

It tells the compiler that a method is intended to override a superclass method.

---

## 3. What does `@Deprecated` do?

It marks a class or method as obsolete and generates a compiler warning when used.

---

## 4. What is a Custom Annotation?

A Custom Annotation is a user-defined annotation created using the `@interface` keyword.

---

## 5. What is the purpose of `@Retention`?

It specifies how long an annotation is available (SOURCE, CLASS, or RUNTIME).

---

## 6. Which annotation ensures an interface has only one abstract method?

```java
@FunctionalInterface
```

---

# Summary

- Annotations provide metadata for Java programs.
- They are used by the compiler, JVM, tools, and frameworks.
- Common built-in annotations include `@Override`, `@Deprecated`, `@SuppressWarnings`, and `@FunctionalInterface`.
- Custom annotations can be created using the `@interface` keyword.
- Meta-annotations define how annotations behave.
- Annotations improve code readability, safety, and framework integration.
