# Operators in Java

## Overview

Operators are special symbols used to perform operations on variables and values.

They are used for arithmetic calculations, comparisons, logical operations, assignments, and more.

---

# Why Do We Need Operators?

Operators are used to:

- Perform mathematical calculations.
- Compare values.
- Assign values to variables.
- Combine multiple conditions.
- Manipulate data.

Example:

```java
int sum = 10 + 20;
```

Here, `+` is an operator.

---

# Types of Operators

Java provides the following types of operators:

1. Arithmetic Operators
2. Assignment Operators
3. Comparison (Relational) Operators
4. Logical Operators
5. Unary Operators
6. Increment and Decrement Operators
7. Ternary Operator
8. Bitwise Operators

---

# 1. Arithmetic Operators

Used to perform mathematical operations.

| Operator | Description | Example |
|----------|-------------|---------|
| + | Addition | `a + b` |
| - | Subtraction | `a - b` |
| * | Multiplication | `a * b` |
| / | Division | `a / b` |
| % | Modulus (Remainder) | `a % b` |

---

## Example

```java
public class Main {

    public static void main(String[] args) {

        int a = 20;
        int b = 10;

        System.out.println(a + b);
        System.out.println(a - b);
        System.out.println(a * b);
        System.out.println(a / b);
        System.out.println(a % b);

    }

}
```

Output

```text
30
10
200
2
0
```

---

# 2. Assignment Operators

Used to assign values to variables.

| Operator | Example | Meaning |
|----------|---------|---------|
| = | `a = 10` | Assign value |
| += | `a += 5` | `a = a + 5` |
| -= | `a -= 5` | `a = a - 5` |
| *= | `a *= 5` | `a = a * 5` |
| /= | `a /= 5` | `a = a / 5` |
| %= | `a %= 5` | `a = a % 5` |

---

## Example

```java
int a = 10;

a += 5;

System.out.println(a);
```

Output

```text
15
```

---

# 3. Comparison (Relational) Operators

Used to compare two values.

The result is always a boolean value (`true` or `false`).

| Operator | Description |
|----------|-------------|
| == | Equal to |
| != | Not Equal to |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than or Equal To |
| <= | Less Than or Equal To |

---

## Example

```java
int a = 20;
int b = 10;

System.out.println(a == b);
System.out.println(a != b);
System.out.println(a > b);
System.out.println(a < b);
System.out.println(a >= b);
System.out.println(a <= b);
```

Output

```text
false
true
true
false
true
false
```

---

# 4. Logical Operators

Used to combine multiple conditions.

| Operator | Description |
|----------|-------------|
| && | Logical AND |
| \|\| | Logical OR |
| ! | Logical NOT |

---

## Example

```java
int age = 20;

System.out.println(age >= 18 && age <= 60);
System.out.println(age < 18 || age > 60);
System.out.println(!(age == 20));
```

Output

```text
true
false
false
```

---

# 5. Unary Operators

Operate on a single operand.

| Operator | Description |
|----------|-------------|
| + | Unary Plus |
| - | Unary Minus |
| ! | Logical NOT |

---

## Example

```java
int number = 10;

System.out.println(-number);
System.out.println(+number);
```

Output

```text
-10
10
```

---

# 6. Increment and Decrement Operators

Increase or decrease a variable by one.

| Operator | Description |
|----------|-------------|
| ++ | Increment |
| -- | Decrement |

---

## Pre-Increment

```java
int a = 10;

System.out.println(++a);
```

Output

```text
11
```

---

## Post-Increment

```java
int a = 10;

System.out.println(a++);
System.out.println(a);
```

Output

```text
10
11
```

---

## Pre-Decrement

```java
int a = 10;

System.out.println(--a);
```

Output

```text
9
```

---

## Post-Decrement

```java
int a = 10;

System.out.println(a--);
System.out.println(a);
```

Output

```text
10
9
```

---

# 7. Ternary Operator

A shorthand for the `if-else` statement.

Syntax

```java
condition ? value1 : value2;
```

Example

```java
int age = 20;

String result = (age >= 18) ? "Adult" : "Minor";

System.out.println(result);
```

Output

```text
Adult
```

---

# 8. Bitwise Operators

Used to perform operations on binary values.

| Operator | Description |
|----------|-------------|
| & | Bitwise AND |
| \| | Bitwise OR |
| ^ | Bitwise XOR |
| ~ | Bitwise NOT |
| << | Left Shift |
| >> | Right Shift |

These operators are commonly used in low-level programming and are less frequently used in everyday Java applications.

---

# Operator Precedence

Java evaluates operators based on precedence.

Example

```java
int result = 10 + 5 * 2;

System.out.println(result);
```

Output

```text
20
```

Explanation

```text
5 × 2 = 10

10 + 10 = 20
```

Multiplication has higher precedence than addition.

---

# Common Mistakes

## Using Assignment Instead of Comparison

Incorrect

```java
if (a = 10)
```

Correct

```java
if (a == 10)
```

---

## Division by Zero

Incorrect

```java
int result = 10 / 0;
```

Result

```text
ArithmeticException
```

---

## Forgetting Operator Precedence

Incorrect Expectation

```java
10 + 5 * 2
```

Actual Result

```text
20
```

---

# Best Practices

- Use parentheses to improve readability.
- Use meaningful variable names.
- Use comparison operators carefully.
- Avoid unnecessary complex expressions.

---

# Interview Questions

## 1. What is an operator?

An operator is a special symbol used to perform operations on variables and values.

---

## 2. What are the different types of operators in Java?

- Arithmetic
- Assignment
- Comparison (Relational)
- Logical
- Unary
- Increment and Decrement
- Ternary
- Bitwise

---

## 3. What is the difference between `=` and `==`?

- `=` assigns a value.
- `==` compares two values.

---

## 4. What is the difference between `&&` and `||`?

- `&&` returns `true` only if both conditions are true.
- `||` returns `true` if at least one condition is true.

---

## 5. What is the ternary operator?

The ternary operator is a shorthand form of the `if-else` statement.

Syntax

```java
condition ? value1 : value2;
```

---

# Summary

- Operators perform operations on variables and values.
- Java provides Arithmetic, Assignment, Comparison, Logical, Unary, Increment/Decrement, Ternary, and Bitwise operators.
- Comparison operators return boolean values.
- Logical operators combine conditions.
- The ternary operator is a compact alternative to `if-else`.
- Understanding operator precedence helps avoid unexpected results.
