# Stream API in Java

## Overview

The **Stream API** was introduced in **Java 8** to process collections of data in a simple, readable, and efficient way.

A Stream allows us to perform operations like:

- Filtering
- Sorting
- Mapping
- Searching
- Counting
- Collecting

without modifying the original collection.

---

# Why Do We Need Stream API?

Suppose we have a list of numbers and want to print only even numbers.

Without Stream API

```java
List<Integer> numbers = Arrays.asList(1,2,3,4,5,6);

for(int n : numbers){

    if(n % 2 == 0){

        System.out.println(n);

    }

}
```

With Stream API

```java
numbers.stream()
       .filter(n -> n % 2 == 0)
       .forEach(System.out::println);
```

The Stream API makes the code shorter and easier to understand.

---

# What is a Stream?

A **Stream** is a sequence of elements that supports functional-style operations.

A Stream:

- Does not store data
- Processes data from a source
- Does not modify the original collection
- Can be used only once

---

# Stream Pipeline

A Stream works in three stages.

```text
Collection
     │
     ▼
Create Stream
     │
     ▼
Intermediate Operations
     │
     ▼
Terminal Operation
     │
     ▼
Result
```

---

# Creating a Stream

From a List

```java
List<String> names = Arrays.asList("Java", "Python", "C++");

Stream<String> stream = names.stream();
```

---

# Intermediate Operations

Intermediate operations return another Stream.

Common operations:

- filter()
- map()
- sorted()
- distinct()
- limit()
- skip()

---

# filter()

Used to select elements based on a condition.

Example

```java
List<Integer> numbers = Arrays.asList(1,2,3,4,5,6);

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

# map()

Transforms each element into another form.

Example

```java
List<String> names = Arrays.asList("java","python");

names.stream()
     .map(String::toUpperCase)
     .forEach(System.out::println);
```

Output

```text
JAVA
PYTHON
```

---

# sorted()

Sorts the elements.

Example

```java
List<Integer> list = Arrays.asList(5,2,8,1);

list.stream()
    .sorted()
    .forEach(System.out::println);
```

Output

```text
1
2
5
8
```

---

# distinct()

Removes duplicate elements.

Example

```java
List<Integer> list = Arrays.asList(1,2,2,3,3,4);

list.stream()
    .distinct()
    .forEach(System.out::println);
```

Output

```text
1
2
3
4
```

---

# limit()

Returns only the first specified number of elements.

Example

```java
List<Integer> list = Arrays.asList(1,2,3,4,5);

list.stream()
    .limit(3)
    .forEach(System.out::println);
```

Output

```text
1
2
3
```

---

# skip()

Skips the first specified number of elements.

Example

```java
List<Integer> list = Arrays.asList(1,2,3,4,5);

list.stream()
    .skip(2)
    .forEach(System.out::println);
```

Output

```text
3
4
5
```

---

# Terminal Operations

Terminal operations produce the final result.

Common terminal operations:

- forEach()
- collect()
- count()
- findFirst()
- anyMatch()
- allMatch()
- reduce()

---

# forEach()

Executes an action for each element.

Example

```java
numbers.stream()
       .forEach(System.out::println);
```

---

# collect()

Collects the result into a collection.

Example

```java
List<Integer> evenNumbers =
numbers.stream()
       .filter(n -> n % 2 == 0)
       .collect(Collectors.toList());
```

---

# count()

Returns the number of elements.

Example

```java
long total =
numbers.stream().count();

System.out.println(total);
```

---

# findFirst()

Returns the first element.

Example

```java
Optional<Integer> first =
numbers.stream()
       .findFirst();
```

---

# anyMatch()

Checks whether at least one element satisfies the condition.

Example

```java
boolean result =
numbers.stream()
       .anyMatch(n -> n > 10);
```

---

# allMatch()

Checks whether all elements satisfy the condition.

Example

```java
boolean result =
numbers.stream()
       .allMatch(n -> n > 0);
```

---

# reduce()

Combines all elements into a single result.

Example

```java
int sum =
numbers.stream()
       .reduce(0, Integer::sum);

System.out.println(sum);
```

Output

```text
21
```

---

# Method Chaining

Multiple operations can be combined.

Example

```java
List<String> names = Arrays.asList(
"java",
"python",
"c",
"javascript"
);

names.stream()
     .filter(name -> name.length() > 3)
     .map(String::toUpperCase)
     .sorted()
     .forEach(System.out::println);
```

Output

```text
JAVA
JAVASCRIPT
PYTHON
```

---

# Stream vs Collection

| Collection | Stream |
|------------|--------|
| Stores data | Processes data |
| Can be reused | Used only once |
| Direct access | Sequential processing |
| Mutable | Does not modify source |

---

# How Stream API Works

```text
Collection
     │
     ▼
stream()
     │
     ▼
filter()
     │
     ▼
map()
     │
     ▼
sorted()
     │
     ▼
collect()
     │
     ▼
Final Result
```

---

# Common Mistakes

## Reusing a Stream

Incorrect

```java
Stream<Integer> stream =
numbers.stream();

stream.forEach(System.out::println);

stream.count();
```

Runtime Error

A Stream can be used only once.

---

## Forgetting Terminal Operation

Incorrect

```java
numbers.stream()
       .filter(n -> n > 5);
```

Nothing happens because no terminal operation is present.

Correct

```java
numbers.stream()
       .filter(n -> n > 5)
       .forEach(System.out::println);
```

---

## Modifying Source Collection Inside Stream

Avoid modifying the original collection while processing it.

---

# Best Practices

- Keep stream pipelines simple.
- Prefer method references when possible.
- Avoid side effects inside stream operations.
- Use streams for data processing, not for complex business logic.
- Remember that streams are consumed after a terminal operation.

---

# Interview Questions

## 1. What is Stream API?

The Stream API is a feature introduced in Java 8 for processing collections using functional-style operations.

---

## 2. Does a Stream store data?

No.

A Stream processes data but does not store it.

---

## 3. What are Intermediate Operations?

Intermediate operations return another Stream.

Examples:

- filter()
- map()
- sorted()

---

## 4. What are Terminal Operations?

Terminal operations produce the final result.

Examples:

- collect()
- forEach()
- count()

---

## 5. Can a Stream be reused?

No.

A Stream can be consumed only once.

---

## 6. Does Stream modify the original collection?

No.

The original collection remains unchanged.

---

# Summary

- Stream API was introduced in Java 8.
- It simplifies collection processing using functional programming.
- Streams process data without modifying the original collection.
- Intermediate operations return another Stream.
- Terminal operations produce the final result.
- A Stream can be used only once.
- Stream API makes Java code cleaner, more readable, and easier to maintain.
