# Loops in Java

## Overview

Loops are used to execute a block of code repeatedly until a specified condition becomes false.

Instead of writing the same code multiple times, loops allow us to write it once and execute it many times.

---

# Why Do We Need Loops?

Loops are used to:

- Reduce code repetition.
- Execute code multiple times.
- Iterate through collections and arrays.
- Improve code readability.

Example:

Without Loop

```java
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
```

With Loop

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Hello");
}
```

---

# Types of Loops

Java provides four types of loops:

1. for Loop
2. while Loop
3. do-while Loop
4. Enhanced for Loop (For-Each)

---

# 1. for Loop

The `for` loop is used when the number of iterations is known.

## Syntax

```java
for (initialization; condition; update) {

    // Code

}
```

### Components

| Component | Description |
|-----------|-------------|
| Initialization | Executes once before the loop starts |
| Condition | Checked before every iteration |
| Update | Executes after each iteration |

---

## Example

```java
public class Main {

    public static void main(String[] args) {

        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }

    }

}
```

Output

```text
1
2
3
4
5
```

---

# Flow of for Loop

```text
Initialization
      │
      ▼
Condition
      │
      ├── False ──► Exit Loop
      │
      ▼
Execute Code
      │
      ▼
Update
      │
      └────────────► Condition
```

---

# 2. while Loop

The `while` loop is used when the number of iterations is not known.

## Syntax

```java
while (condition) {

    // Code

}
```

---

## Example

```java
public class Main {

    public static void main(String[] args) {

        int i = 1;

        while (i <= 5) {

            System.out.println(i);

            i++;

        }

    }

}
```

Output

```text
1
2
3
4
5
```

---

# Flow of while Loop

```text
Condition
     │
     ├── False ──► Exit Loop
     │
     ▼
Execute Code
     │
     ▼
Update
     │
     └──────────► Condition
```

---

# 3. do-while Loop

The `do-while` loop executes the code at least once, even if the condition is false.

## Syntax

```java
do {

    // Code

} while (condition);
```

---

## Example

```java
public class Main {

    public static void main(String[] args) {

        int i = 1;

        do {

            System.out.println(i);

            i++;

        } while (i <= 5);

    }

}
```

Output

```text
1
2
3
4
5
```

---

## Example (Condition is False)

```java
int i = 10;

do {

    System.out.println(i);

} while (i < 5);
```

Output

```text
10
```

The loop executes once before checking the condition.

---

# 4. Enhanced for Loop (For-Each)

The enhanced `for` loop is used to iterate through arrays and collections.

## Syntax

```java
for (dataType variable : collection) {

    // Code

}
```

---

## Example

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

# Loop Control Statements

Java provides three loop control statements:

- break
- continue
- return

---

# break Statement

The `break` statement immediately terminates the loop.

Example

```java
for (int i = 1; i <= 5; i++) {

    if (i == 3) {
        break;
    }

    System.out.println(i);

}
```

Output

```text
1
2
```

---

# continue Statement

The `continue` statement skips the current iteration and moves to the next iteration.

Example

```java
for (int i = 1; i <= 5; i++) {

    if (i == 3) {
        continue;
    }

    System.out.println(i);

}
```

Output

```text
1
2
4
5
```

---

# Infinite Loop

A loop that never ends is called an infinite loop.

Example

```java
while (true) {

    System.out.println("Hello");

}
```

---

# for vs while vs do-while

| for | while | do-while |
|------|--------|-----------|
| Known number of iterations | Unknown number of iterations | Executes at least once |
| Initialization inside loop | Initialization outside loop | Condition checked after execution |
| Condition checked first | Condition checked first | Condition checked last |

---

# Common Mistakes

## Forgetting Update

Incorrect

```java
int i = 1;

while (i <= 5) {

    System.out.println(i);

}
```

Result

```text
Infinite Loop
```

Correct

```java
i++;
```

---

## Using Wrong Condition

Incorrect

```java
for (int i = 1; i >= 5; i++)
```

The loop never executes.

---

## Missing Semicolon in do-while

Incorrect

```java
} while (i <= 5)
```

Correct

```java
} while (i <= 5);
```

---

# Best Practices

- Use `for` when the number of iterations is known.
- Use `while` when the number of iterations is unknown.
- Use `do-while` when the loop must execute at least once.
- Avoid infinite loops unless intentionally required.
- Use `break` and `continue` carefully.

---

# Interview Questions

## 1. What is a loop?

A loop is a control structure used to execute a block of code repeatedly until a condition becomes false.

---

## 2. What are the types of loops in Java?

- for
- while
- do-while
- Enhanced for (For-Each)

---

## 3. What is the difference between `while` and `do-while`?

- `while` checks the condition before executing the loop.
- `do-while` executes the loop first and then checks the condition.

---

## 4. What is an infinite loop?

An infinite loop is a loop whose condition never becomes false.

Example

```java
while (true) {

}
```

---

## 5. What is the difference between `break` and `continue`?

- `break` exits the loop immediately.
- `continue` skips the current iteration and continues with the next iteration.

---

# Summary

- Loops execute a block of code repeatedly.
- Java provides `for`, `while`, `do-while`, and Enhanced `for` loops.
- `for` is used when the number of iterations is known.
- `while` is used when the number of iterations is unknown.
- `do-while` always executes at least once.
- `break` terminates the loop.
- `continue` skips the current iteration.
- Enhanced `for` is used to iterate through arrays and collections.
