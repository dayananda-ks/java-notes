# Java Reflection API

## Overview

The **Java Reflection API** allows a Java program to inspect and manipulate classes, methods, constructors, fields, and objects at runtime.

Normally, Java code knows everything at compile time.

Reflection allows a program to discover information dynamically while it is running.

The Reflection API is available in the **java.lang.reflect** package.

---

# Why Do We Need Reflection?

Normally

```java
Student student = new Student();

student.display();
```

The compiler already knows:

- Class
- Methods
- Fields

Sometimes we don't know these details until runtime.

Example

- Spring Boot
- Hibernate
- JUnit
- Dependency Injection
- Serialization Libraries

These frameworks use Reflection to inspect classes dynamically.

---

# What Reflection Can Do

Reflection can:

- Get class information
- Get constructors
- Get methods
- Get fields
- Create objects
- Invoke methods
- Access private members

---

# Reflection Architecture

```text
Java Class
     │
     ▼
Reflection API
     │
     ▼
Class Information
     │
     ▼
Fields
Methods
Constructors
Annotations
```

---

# Class Class

Reflection starts with the `Class` class.

Every Java class has one `Class` object.

Example

```java
Class<?> cls = String.class;
```

---

# Getting a Class Object

Method 1

```java
Class<?> cls = Student.class;
```

Method 2

```java
Student s = new Student();

Class<?> cls = s.getClass();
```

Method 3

```java
Class<?> cls =
Class.forName("Student");
```

---

# Getting Class Name

Example

```java
Class<?> cls = Student.class;

System.out.println(cls.getName());
```

Output

```text
Student
```

---

# Getting Constructors

Example

```java
Constructor<?>[] constructors =
cls.getConstructors();

for(Constructor<?> c : constructors){

    System.out.println(c);

}
```

---

# Getting Methods

Example

```java
Method[] methods =
cls.getDeclaredMethods();

for(Method m : methods){

    System.out.println(m.getName());

}
```

---

# Getting Fields

Example

```java
Field[] fields =
cls.getDeclaredFields();

for(Field f : fields){

    System.out.println(f.getName());

}
```

---

# Creating an Object

Example

```java
Class<?> cls =
Class.forName("Student");

Object obj =
cls.getDeclaredConstructor()
.newInstance();
```

Reflection creates the object at runtime.

---

# Invoking a Method

Example

```java
Method method =
cls.getMethod("display");

method.invoke(obj);
```

This calls the `display()` method dynamically.

---

# Accessing Private Fields

Example

```java
Field field =
cls.getDeclaredField("name");

field.setAccessible(true);

field.set(obj, "Ashu");
```

Even private fields can be accessed.

---

# Reading Private Field

Example

```java
Object value =
field.get(obj);

System.out.println(value);
```

---

# Reflection with Constructors

Example

```java
Constructor<?> constructor =
cls.getConstructor();

Object object =
constructor.newInstance();
```

---

# Reflection Example

```java
class Student{

    public void display(){

        System.out.println("Hello");

    }

}

public class Main{

    public static void main(String[] args)
    throws Exception{

        Class<?> cls = Student.class;

        Object obj =
        cls.getDeclaredConstructor()
           .newInstance();

        Method method =
        cls.getMethod("display");

        method.invoke(obj);

    }

}
```

Output

```text
Hello
```

---

# Reflection and Annotations

Reflection can read annotations.

Example

```java
Annotation[] annotations =
cls.getAnnotations();
```

Spring and Hibernate use this feature extensively.

---

# Reflection and Frameworks

| Framework | Reflection Usage |
|------------|------------------|
| Spring | Dependency Injection |
| Spring Boot | Bean Creation |
| Hibernate | Entity Mapping |
| JUnit | Test Discovery |
| Mockito | Mock Object Creation |

---

# Advantages

- Dynamic object creation
- Runtime inspection
- Supports frameworks
- Enables dependency injection
- Useful for testing libraries

---

# Disadvantages

- Slower than normal code
- Can access private members
- Reduces compile-time safety
- More difficult to understand
- May introduce security concerns

---

# How Reflection Works

```text
Class
   │
   ▼
Reflection API
   │
   ├── Fields
   ├── Methods
   ├── Constructors
   └── Annotations
         │
         ▼
Runtime Operations
```

---

# Common Mistakes

## Forgetting Exception Handling

Reflection methods throw checked exceptions.

Example

```java
Class.forName("Student");
```

Handle or declare the exception.

---

## Accessing Private Members Unnecessarily

Avoid

```java
field.setAccessible(true);
```

unless absolutely necessary.

---

## Overusing Reflection

Reflection is powerful but slower than direct method calls.

Use it only when runtime flexibility is required.

---

# Best Practices

- Prefer normal Java code over Reflection when possible.
- Use Reflection only for dynamic behavior.
- Avoid modifying private members unless required.
- Cache Reflection objects if used repeatedly.
- Understand security implications before using `setAccessible(true)`.

---

# Interview Questions

## 1. What is the Reflection API?

The Reflection API allows Java programs to inspect and manipulate classes, methods, constructors, and fields at runtime.

---

## 2. Which package contains the Reflection API?

```java
java.lang.reflect
```

---

## 3. What is the purpose of the `Class` class?

It represents metadata about a Java class and is the entry point for Reflection.

---

## 4. Name three ways to obtain a `Class` object.

- `Student.class`
- `object.getClass()`
- `Class.forName()`

---

## 5. Which frameworks use Reflection?

- Spring
- Spring Boot
- Hibernate
- JUnit
- Mockito

---

## 6. Why is Reflection slower than normal Java code?

Because class information is inspected and accessed dynamically at runtime instead of being resolved during compilation.

---

# Summary

- The Reflection API enables runtime inspection and manipulation of Java classes.
- It is provided by the `java.lang.reflect` package.
- Reflection can access constructors, methods, fields, and annotations.
- It supports dynamic object creation and method invocation.
- Frameworks like Spring, Hibernate, and JUnit rely heavily on Reflection.
- Reflection is powerful but should be used carefully because it has performance and security implications.
