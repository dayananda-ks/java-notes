# Arrays in Java

## Overview

An array is a collection of elements of the same data type stored in contiguous memory locations.

Instead of creating multiple variables of the same type, an array allows you to store multiple values in a single variable.

---

# Why Do We Need Arrays?

Arrays are used to:

- Store multiple values of the same type.
- Reduce the number of variables.
- Access elements using an index.
- Simplify data processing.

Without Array

```java
int mark1 = 90;
int mark2 = 85;
int mark3 = 95;
int mark4 = 88;
int mark5 = 91;
```

With Array

```java
int[] marks = {90, 85, 95, 88, 91};
```

---

# Array Declaration

Syntax

```java
dataType[] arrayName;
```

Example

```java
int[] numbers;
```

---

# Array Creation

Syntax

```java
arrayName = new dataType[size];
```

Example

```java
int[] numbers = new int[5];
```

This creates an array that can store 5 integers.

---

# Array Initialization

Arrays can be initialized while creating them.

Example

```java
int[] numbers = {10, 20, 30, 40, 50};
```

---

# Complete Example

```java
public class Main {

    public static void main(String[] args) {

        int[] numbers = {10, 20, 30, 40, 50};

        System.out.println(numbers[0]);
        System.out.println(numbers[1]);
        System.out.println(numbers[2]);

    }

}
```

Output

```text
10
20
30
```

---

# Array Index

Each element has an index.

Indexing starts from **0**.

```text
Index:   0   1   2   3   4
Value:  10  20  30  40  50
```

---

# Accessing Array Elements

Syntax

```java
arrayName[index];
```

Example

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[1]);
```

Output

```text
20
```

---

# Updating Array Elements

Example

```java
int[] numbers = {10, 20, 30};

numbers[1] = 100;

System.out.println(numbers[1]);
```

Output

```text
100
```

---

# Array Length

The `length` property returns the number of elements in an array.

Example

```java
int[] numbers = {10, 20, 30, 40};

System.out.println(numbers.length);
```

Output

```text
4
```

---

# Traversing an Array using for Loop

Example

```java
int[] numbers = {10, 20, 30, 40, 50};

for (int i = 0; i < numbers.length; i++) {

    System.out.println(numbers[i]);

}
```

Output

```text
10
20
30
40
50
```

---

# Traversing an Array using Enhanced for Loop

Example

```java
int[] numbers = {10, 20, 30, 40, 50};

for (int number : numbers) {

    System.out.println(number);

}
```

Output

```text
10
20
30
40
50
```

---

# Default Values

When an array is created using `new`, Java initializes its elements with default values.

| Data Type | Default Value |
|-----------|---------------|
| byte | 0 |
| short | 0 |
| int | 0 |
| long | 0 |
| float | 0.0 |
| double | 0.0 |
| char | `\u0000` |
| boolean | false |
| Reference Types | null |

Example

```java
int[] numbers = new int[3];

System.out.println(numbers[0]);
```

Output

```text
0
```

---

# Types of Arrays

## One-Dimensional Array

```java
int[] numbers = {10, 20, 30};
```

---

## Two-Dimensional Array

```java
int[][] matrix = {

    {1, 2, 3},
    {4, 5, 6}

};
```

---

# Common Operations

## Find Sum

```java
int[] numbers = {10, 20, 30};

int sum = 0;

for (int number : numbers) {

    sum += number;

}

System.out.println(sum);
```

Output

```text
60
```

---

## Find Largest Element

```java
int[] numbers = {10, 45, 22, 90};

int max = numbers[0];

for (int number : numbers) {

    if (number > max) {
        max = number;
    }

}

System.out.println(max);
```

Output

```text
90
```

---

# Common Mistakes

## Array Index Out of Bounds

Incorrect

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[3]);
```

Result

```text
ArrayIndexOutOfBoundsException
```

Valid Indexes

```text
0
1
2
```

---

## Negative Index

Incorrect

```java
numbers[-1];
```

Result

```text
ArrayIndexOutOfBoundsException
```

---

## Accessing Before Initialization

Incorrect

```java
int[] numbers;

System.out.println(numbers[0]);
```

Result

```text
Compilation Error
```

---

# Best Practices

- Use meaningful array names.
- Always check array boundaries.
- Use `length` instead of hardcoding the size.
- Use the enhanced `for` loop when the index is not needed.
- Initialize arrays before accessing their elements.

---

# Interview Questions

## 1. What is an array?

An array is a collection of elements of the same data type stored in contiguous memory locations.

---

## 2. What is the index of the first element?

The first element has an index of **0**.

---

## 3. How do you find the size of an array?

Using the `length` property.

Example

```java
array.length
```

---

## 4. What is the difference between a `for` loop and an enhanced `for` loop?

- `for` loop provides access to the index.
- Enhanced `for` loop directly accesses each element.

---

## 5. What happens if you access an invalid index?

Java throws an **ArrayIndexOutOfBoundsException**.

---

# Summary

- An array stores multiple values of the same data type.
- Array indexing starts from **0**.
- Arrays have a fixed size after creation.
- Use the `length` property to determine the size of an array.
- Arrays can be traversed using `for` and enhanced `for` loops.
- Accessing an invalid index throws an `ArrayIndexOutOfBoundsException`.