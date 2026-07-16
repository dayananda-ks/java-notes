# Collections Framework in Java

## Overview

The **Java Collections Framework (JCF)** is a set of classes and interfaces used to store and manipulate groups of objects efficiently.

Instead of creating your own data structures, Java provides ready-made collections such as Lists, Sets, Queues, and Maps.

The Collections Framework provides:

- Dynamic storage
- Searching
- Sorting
- Insertion
- Deletion
- Traversal

---

# Why Do We Need Collections?

Suppose you want to store the names of 1000 students.

Without Collections

```java
String[] students = new String[1000];
```

Problems:

- Fixed size
- Difficult insertion and deletion
- Manual searching

With Collections

```java
ArrayList<String> students = new ArrayList<>();
```

Advantages:

- Dynamic size
- Easy insertion
- Easy deletion
- Built-in methods

---

# Collections Framework Hierarchy

```text
                  Iterable
                      │
                  Collection
        ┌──────────┼──────────┐
        │          │          │
      List        Set       Queue
        │          │          │
 ArrayList     HashSet    PriorityQueue
 LinkedList    LinkedHashSet
 Vector        TreeSet

Map (Separate Interface)
        │
  HashMap
  LinkedHashMap
  TreeMap
```

---

# Main Interfaces

The Collections Framework contains four major interfaces.

- List
- Set
- Queue
- Map

---

# 1. List

A List stores elements in insertion order.

Characteristics

- Allows duplicates
- Ordered
- Index-based

Example

```java
import java.util.*;

public class Main {

    public static void main(String[] args) {

        List<String> list = new ArrayList<>();

        list.add("Java");
        list.add("Python");
        list.add("Java");

        System.out.println(list);

    }

}
```

Output

```text
[Java, Python, Java]
```

---

# ArrayList

ArrayList is the most commonly used implementation of List.

Features

- Dynamic array
- Fast random access
- Slow insertion in the middle

Example

```java
ArrayList<Integer> numbers = new ArrayList<>();

numbers.add(10);
numbers.add(20);
numbers.add(30);
```

---

# LinkedList

LinkedList stores elements as nodes.

Features

- Fast insertion and deletion
- Slower random access

Example

```java
LinkedList<String> names = new LinkedList<>();

names.add("Ashu");
names.add("Rahul");
```

---

# Vector

Vector is similar to ArrayList but is synchronized.

Example

```java
Vector<Integer> list = new Vector<>();
```

---

# 2. Set

A Set stores only unique elements.

Characteristics

- No duplicates
- Not index-based

Example

```java
Set<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(10);

System.out.println(set);
```

Output

```text
[10, 20]
```

---

# HashSet

Features

- No duplicates
- No insertion order
- Fast operations

Example

```java
HashSet<String> set = new HashSet<>();

set.add("Java");
set.add("Python");
```

---

# LinkedHashSet

Features

- Maintains insertion order
- No duplicates

Example

```java
LinkedHashSet<Integer> set = new LinkedHashSet<>();
```

---

# TreeSet

Features

- Sorted order
- No duplicates

Example

```java
TreeSet<Integer> set = new TreeSet<>();

set.add(30);
set.add(10);
set.add(20);

System.out.println(set);
```

Output

```text
[10, 20, 30]
```

---

# 3. Queue

Queue follows the FIFO (First In First Out) principle.

Example

```java
Queue<Integer> queue = new LinkedList<>();

queue.offer(10);
queue.offer(20);
queue.offer(30);

System.out.println(queue.poll());
```

Output

```text
10
```

---

# PriorityQueue

Elements are arranged according to priority.

Example

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();

pq.add(50);
pq.add(10);
pq.add(30);

System.out.println(pq.poll());
```

Output

```text
10
```

---

# 4. Map

Map stores data as **Key-Value pairs**.

Characteristics

- Unique keys
- Duplicate values allowed

Example

```java
Map<Integer, String> map = new HashMap<>();

map.put(1, "Ashu");
map.put(2, "Rahul");

System.out.println(map);
```

---

# HashMap

Features

- Fast lookup
- No ordering

Example

```java
HashMap<Integer, String> map = new HashMap<>();
```

---

# LinkedHashMap

Features

- Maintains insertion order

Example

```java
LinkedHashMap<Integer, String> map = new LinkedHashMap<>();
```

---

# TreeMap

Features

- Keys are automatically sorted

Example

```java
TreeMap<Integer, String> map = new TreeMap<>();
```

---

# Common Collection Methods

| Method | Description |
|---------|-------------|
| add() | Adds an element |
| remove() | Removes an element |
| get() | Returns an element |
| contains() | Checks existence |
| size() | Returns number of elements |
| clear() | Removes all elements |
| isEmpty() | Checks if empty |

---

# Iterating Through Collections

Using Enhanced for Loop

```java
ArrayList<String> list = new ArrayList<>();

list.add("Java");
list.add("Python");

for(String language : list){

    System.out.println(language);

}
```

---

# List vs Set vs Queue vs Map

| Feature | List | Set | Queue | Map |
|----------|------|-----|-------|-----|
| Duplicates | Yes | No | Yes | Keys No |
| Ordered | Yes | Usually No | Yes | Depends |
| Index Based | Yes | No | No | No |
| Stores | Elements | Elements | Elements | Key-Value |

---

# Common Mistakes

## Using ArrayList When Fast Insertions Are Needed

For frequent insertions in the middle, use LinkedList.

---

## Expecting HashSet to Maintain Order

Incorrect

```java
HashSet<String> set = new HashSet<>();
```

HashSet does not preserve insertion order.

Use LinkedHashSet if order matters.

---

## Using Duplicate Keys in HashMap

```java
map.put(1, "Java");
map.put(1, "Python");
```

Output

```text
{1=Python}
```

The second value replaces the first.

---

# Best Practices

- Use ArrayList for frequent reads.
- Use LinkedList for frequent insertions and deletions.
- Use HashSet for unique values.
- Use HashMap for key-value storage.
- Use TreeSet or TreeMap when sorting is required.
- Program using interfaces.

Example

```java
List<String> list = new ArrayList<>();
```

instead of

```java
ArrayList<String> list = new ArrayList<>();
```

---

# Interview Questions

## 1. What is the Collections Framework?

The Collections Framework is a set of interfaces and classes used to store and manipulate groups of objects.

---

## 2. What is the difference between ArrayList and LinkedList?

ArrayList uses a dynamic array and provides faster random access.

LinkedList uses nodes and provides faster insertion and deletion.

---

## 3. What is the difference between HashSet and TreeSet?

HashSet stores unique elements without order.

TreeSet stores unique elements in sorted order.

---

## 4. What is the difference between HashMap and TreeMap?

HashMap stores key-value pairs without ordering.

TreeMap stores keys in sorted order.

---

## 5. Which collection allows duplicate elements?

List and Queue allow duplicates.

Set does not.

---

## 6. Which collection stores key-value pairs?

Map stores data as key-value pairs.

---

# Summary

- The Collections Framework provides ready-made data structures.
- The four main interfaces are List, Set, Queue, and Map.
- ArrayList is best for fast access.
- LinkedList is best for frequent insertion and deletion.
- Set stores unique elements.
- Queue follows FIFO.
- Map stores key-value pairs.
- Choosing the correct collection improves performance and code quality.
