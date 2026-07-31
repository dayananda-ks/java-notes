# Java Collections Framework (Advanced)

## Overview

The **Java Collections Framework (JCF)** is a unified architecture for storing, managing, and manipulating groups of objects.

Basic collections include:

- List
- Set
- Queue
- Map

This chapter covers **advanced collection classes, utilities, and best practices** commonly used in real-world applications.

---

# Why Advanced Collections?

As applications grow, we need:

- Faster searching
- Efficient sorting
- Thread-safe collections
- Special-purpose collections
- Utility methods

The Java Collections Framework provides solutions for these needs.

---

# Collections Utility Class

The `Collections` class contains static utility methods for working with collections.

Common methods:

- sort()
- reverse()
- shuffle()
- binarySearch()
- min()
- max()
- frequency()
- copy()

---

# sort()

Sorts elements in ascending order.

Example

```java
List<Integer> numbers =
Arrays.asList(5, 2, 8, 1);

Collections.sort(numbers);

System.out.println(numbers);
```

Output

```text
[1, 2, 5, 8]
```

---

# reverse()

Reverses the order of elements.

Example

```java
Collections.reverse(numbers);
```

Output

```text
[8, 5, 2, 1]
```

---

# shuffle()

Randomly rearranges elements.

Example

```java
Collections.shuffle(numbers);
```

Possible Output

```text
[2, 8, 1, 5]
```

---

# binarySearch()

Searches an element in a sorted list.

Example

```java
Collections.sort(numbers);

int index =
Collections.binarySearch(numbers, 5);

System.out.println(index);
```

---

# min() and max()

Finds the minimum and maximum element.

Example

```java
int min =
Collections.min(numbers);

int max =
Collections.max(numbers);
```

---

# frequency()

Counts occurrences of an element.

Example

```java
List<String> names =
Arrays.asList("Java","Python","Java");

System.out.println(
Collections.frequency(names, "Java")
);
```

Output

```text
2
```

---

# Comparable Interface

Used for **natural sorting**.

Example

```java
class Student
implements Comparable<Student>{

    int age;

    public int compareTo(Student s){

        return this.age - s.age;

    }

}
```

Now objects can be sorted using:

```java
Collections.sort(studentList);
```

---

# Comparator Interface

Used for **custom sorting**.

Example

```java
Comparator<Student> comparator =
(a, b) -> a.age - b.age;

Collections.sort(studentList, comparator);
```

---

# Comparable vs Comparator

| Comparable | Comparator |
|------------|------------|
| Inside class | Outside class |
| One sorting logic | Multiple sorting logics |
| compareTo() | compare() |

---

# PriorityQueue

Stores elements according to priority.

Example

```java
PriorityQueue<Integer> queue =
new PriorityQueue<>();

queue.add(30);
queue.add(10);
queue.add(20);

System.out.println(queue.poll());
```

Output

```text
10
```

---

# Deque

A Deque supports insertion and deletion from both ends.

Example

```java
Deque<Integer> deque =
new ArrayDeque<>();

deque.addFirst(10);

deque.addLast(20);
```

---

# ArrayDeque

Faster than `Stack` for stack operations.

Example

```java
ArrayDeque<Integer> stack =
new ArrayDeque<>();

stack.push(10);

stack.push(20);

System.out.println(stack.pop());
```

Output

```text
20
```

---

# EnumSet

Stores enum values efficiently.

Example

```java
enum Day{

    MONDAY,
    TUESDAY,
    WEDNESDAY

}

EnumSet<Day> days =
EnumSet.allOf(Day.class);

System.out.println(days);
```

---

# EnumMap

Specialized map for enum keys.

Example

```java
EnumMap<Day, String> map =
new EnumMap<>(Day.class);

map.put(Day.MONDAY, "Work");
```

---

# WeakHashMap

Entries are removed automatically when keys are no longer referenced.

Useful for caching.

---

# IdentityHashMap

Compares keys using `==` instead of `equals()`.

Normally,

```java
HashMap
```

uses

```java
equals()
```

---

# LinkedHashMap

Maintains insertion order.

Example

```java
Map<Integer, String> map =
new LinkedHashMap<>();
```

---

# TreeMap

Stores keys in sorted order.

Example

```java
TreeMap<Integer, String> map =
new TreeMap<>();
```

---

# Concurrent Collections

Used in multithreaded applications.

Examples

- ConcurrentHashMap
- CopyOnWriteArrayList
- ConcurrentLinkedQueue

---

# ConcurrentHashMap

Thread-safe alternative to `HashMap`.

Example

```java
ConcurrentHashMap<Integer, String> map =
new ConcurrentHashMap<>();
```

---

# CopyOnWriteArrayList

Safe for concurrent read operations.

Example

```java
CopyOnWriteArrayList<String> list =
new CopyOnWriteArrayList<>();
```

---

# Unmodifiable Collections

Create read-only collections.

Example

```java
List<String> list =
Collections.unmodifiableList(names);
```

---

# Synchronized Collections

Convert normal collections into thread-safe collections.

Example

```java
List<String> list =
Collections.synchronizedList(
new ArrayList<>()
);
```

---

# How Advanced Collections Work

```text
Collection
      │
      ▼
Collections Utility
      │
      ▼
Sorting / Searching
      │
      ▼
Processed Data
```

---

# Common Mistakes

## Using HashMap When Order Matters

Incorrect

```java
HashMap<Integer, String> map =
new HashMap<>();
```

Use

```java
LinkedHashMap
```

or

```java
TreeMap
```

---

## Using Comparable for Multiple Sorting Rules

Use `Comparator` when different sorting orders are required.

---

## Using HashMap in Multithreading

Incorrect

```java
HashMap
```

Use

```java
ConcurrentHashMap
```

---

# Best Practices

- Use `ArrayList` for frequent reading.
- Use `LinkedList` for frequent insertion and deletion.
- Use `HashSet` for unique elements.
- Use `HashMap` for fast key-value lookup.
- Use `TreeMap` when sorted keys are required.
- Use `LinkedHashMap` when insertion order is important.
- Use `Comparator` for custom sorting.
- Use concurrent collections in multithreaded applications.

---

# Interview Questions

## 1. What is the Collections class?

The `Collections` class provides utility methods for sorting, searching, reversing, and manipulating collections.

---

## 2. What is the difference between Comparable and Comparator?

| Comparable | Comparator |
|------------|------------|
| compareTo() | compare() |
| Natural sorting | Custom sorting |
| Inside class | Outside class |

---

## 3. What is PriorityQueue?

A queue that stores elements according to priority instead of insertion order.

---

## 4. What is ConcurrentHashMap?

A thread-safe implementation of the `Map` interface designed for concurrent access.

---

## 5. What is the difference between HashMap and TreeMap?

| HashMap | TreeMap |
|----------|----------|
| Unordered | Sorted |
| Faster | Slightly slower |
| Uses Hashing | Uses Red-Black Tree |

---

## 6. What is LinkedHashMap?

A `LinkedHashMap` maintains the insertion order of elements.

---

## 7. When should Comparator be used?

When multiple or custom sorting strategies are required.

---

# Summary

- The Java Collections Framework provides advanced utilities for efficient data management.
- The `Collections` class offers methods for sorting, searching, reversing, and other common operations.
- `Comparable` defines natural ordering, while `Comparator` supports custom ordering.
- Specialized collections such as `PriorityQueue`, `ArrayDeque`, `EnumSet`, and `ConcurrentHashMap` solve specific use cases.
- Choosing the appropriate collection improves performance, scalability, and maintainability in Java applications.
