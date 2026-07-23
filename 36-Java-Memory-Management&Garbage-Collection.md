# Java Memory Management & Garbage Collection

## Overview

Java automatically manages memory using the **Java Memory Management System**.

Unlike languages such as C and C++, programmers do not need to manually allocate or free memory.

The **JVM (Java Virtual Machine)** is responsible for:

- Allocating memory
- Managing memory
- Reclaiming unused memory
- Preventing memory leaks

This automatic cleanup is performed by the **Garbage Collector (GC)**.

---

# Why Do We Need Memory Management?

Suppose a program creates many objects.

Without Memory Management

```text
Create Objects

↓

Objects Remain Forever

↓

Memory Becomes Full

↓

Program Crashes
```

With Java Memory Management

```text
Create Objects

↓

Objects Become Unused

↓

Garbage Collector Removes Them

↓

Memory Becomes Available Again
```

---

# Java Memory Structure

The JVM divides memory into different areas.

```text
             JVM Memory

        ┌─────────────────┐
        │     Heap        │
        └─────────────────┘
                 ▲
                 │
        ┌─────────────────┐
        │     Stack       │
        └─────────────────┘
                 ▲
                 │
        ┌─────────────────┐
        │ Method Area     │
        └─────────────────┘
```

---

# Heap Memory

The **Heap** stores all objects and instance variables.

Example

```java
Student s = new Student();
```

The object is created in the Heap.

Characteristics

- Shared by all threads
- Stores objects
- Managed by Garbage Collector

---

# Stack Memory

Each thread has its own Stack.

The Stack stores:

- Local variables
- Method calls
- References to objects

Example

```java
public static void main(String[] args){

    int x = 10;

}
```

`x` is stored in the Stack.

---

# Method Area

The Method Area stores:

- Class information
- Static variables
- Method bytecode
- Runtime constant pool

Example

```java
class Student{

    static int count = 0;

}
```

The static variable is stored in the Method Area.

---

# Object Creation

Example

```java
Student s = new Student();
```

Memory Allocation

```text
Stack                  Heap

s  ───────────────►  Student Object
```

The reference variable is stored in the Stack.

The object is stored in the Heap.

---

# What is Garbage Collection?

Garbage Collection is the automatic process of removing objects that are no longer used.

The JVM performs this task automatically.

Programmers do not free memory manually.

---

# Garbage Object

A Garbage Object is an object that has no active references.

Example

```java
Student s = new Student();

s = null;
```

The object becomes eligible for Garbage Collection.

---

# Example

```java
class Student{

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

        s1 = null;

    }

}
```

The created object has no references.

It becomes eligible for Garbage Collection.

---

# Garbage Collector

The Garbage Collector:

- Finds unused objects
- Removes them
- Frees Heap memory

The JVM decides when to run the Garbage Collector.

---

# Requesting Garbage Collection

Example

```java
System.gc();
```

or

```java
Runtime.getRuntime().gc();
```

These only **request** garbage collection.

The JVM may ignore the request.

---

# finalize() Method

Older Java versions allowed cleanup using:

```java
protected void finalize(){

}
```

**Note:** `finalize()` is deprecated and should not be used in modern Java.

---

# Types of References

Java provides different reference types.

| Type | Description |
|------|-------------|
| Strong Reference | Normal object reference |
| Weak Reference | Object can be collected anytime |
| Soft Reference | Collected only when memory is low |
| Phantom Reference | Used for advanced memory management |

Most applications use Strong References.

---

# Memory Leak in Java

Java prevents most memory leaks.

However, leaks can still occur if unused objects are still referenced.

Example

```java
List<Student> students =
new ArrayList<>();

students.add(new Student());
```

If the object remains in the list forever, it cannot be collected.

---

# OutOfMemoryError

If Heap memory becomes full and the JVM cannot allocate more memory,

it throws:

```text
java.lang.OutOfMemoryError
```

Common reasons

- Creating too many objects
- Memory leaks
- Very large collections

---

# How Garbage Collection Works

```text
Create Object
      │
      ▼
Heap Memory
      │
      ▼
Object No Longer Used
      │
      ▼
Garbage Collector Finds It
      │
      ▼
Memory Released
```

---

# Stack vs Heap

| Stack | Heap |
|--------|------|
| Stores local variables | Stores objects |
| Thread-specific | Shared by all threads |
| Faster | Slower |
| Automatically removed after method ends | Managed by Garbage Collector |

---

# Common Mistakes

## Assuming System.gc() Always Runs

Incorrect

```java
System.gc();
```

It only requests the JVM to perform Garbage Collection.

---

## Keeping Unnecessary References

Incorrect

```java
List<Object> list =
new ArrayList<>();

list.add(new Object());
```

If the object is never removed,

it cannot be garbage collected.

---

## Confusing Stack and Heap

Remember:

- Variables → Stack
- Objects → Heap

---

# Best Practices

- Remove unused object references.
- Close resources such as files and database connections.
- Avoid creating unnecessary objects.
- Use appropriate collection sizes.
- Do not rely on `System.gc()`.
- Avoid using `finalize()`.

---

# Interview Questions

## 1. What is Garbage Collection?

Garbage Collection is the automatic process of removing unused objects from Heap memory.

---

## 2. Which part of memory stores objects?

Heap Memory.

---

## 3. Which part stores local variables?

Stack Memory.

---

## 4. Can programmers manually free memory in Java?

No.

The JVM automatically manages memory.

---

## 5. What is OutOfMemoryError?

It occurs when the JVM cannot allocate additional memory.

---

## 6. What does System.gc() do?

It requests the JVM to perform Garbage Collection.

The JVM is not required to execute it immediately.

---

# Summary

- Java automatically manages memory through the JVM.
- Objects are stored in the Heap, while local variables and method calls are stored in the Stack.
- The Method Area stores class metadata and static members.
- Garbage Collection removes objects that are no longer referenced.
- The JVM controls when Garbage Collection occurs.
- Good memory management practices improve application performance and reliability.
