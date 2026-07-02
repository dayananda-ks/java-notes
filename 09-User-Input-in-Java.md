# User Input in Java
## Overview
User input allows a program to receive data from the user while it is running.

In Java, user input is commonly taken using the **Scanner** class, which is part of the `java.util` package.

---

# Why Do We Need User Input?

User input makes programs interactive.

Examples:

- Entering a name
- Entering age
- Entering marks
- Entering salary
- Entering two numbers for calculation
---
# Scanner Class

The `Scanner` class is used to read input from the keyboard.

Before using it, import the Scanner class.

```java
import java.util.Scanner;
```

---

# Creating a Scanner Object

Syntax

```java
Scanner sc = new Scanner(System.in);
```

Explanation

| Part | Description |
|------|-------------|
| Scanner | Class Name |
| sc | Object Name |
| new | Creates a new object |
| System.in | Reads input from the keyboard |

---

# Reading an Integer

Example

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your age: ");

        int age = sc.nextInt();

        System.out.println("Age: " + age);

    }

}
```

Output

```text
Enter your age: 21
Age: 21
```

---

# Reading a String (Single Word)

Example

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");

        String name = sc.next();

        System.out.println("Name: " + name);

    }

}
```

Output

```text
Enter your name: John
Name: John
```

> **Note:** `next()` reads only one word.

---

# Reading a Full Line

Use `nextLine()` to read an entire line including spaces.

Example

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your full name: ");

        String name = sc.nextLine();

        System.out.println("Name: " + name);

    }

}
```

Output

```text
Enter your full name: John Smith
Name: John Smith
```

---

# Reading Different Data Types

## Integer

```java
int age = sc.nextInt();
```

---

## Double

```java
double salary = sc.nextDouble();
```

---

## Float

```java
float price = sc.nextFloat();
```

---

## Long

```java
long population = sc.nextLong();
```

---

## Boolean

```java
boolean isPassed = sc.nextBoolean();
```

---

## Character

Scanner does not have a `nextChar()` method.

Read a character using:

```java
char grade = sc.next().charAt(0);
```

---

# Example Program

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = sc.nextLine();

        System.out.print("Enter your age: ");
        int age = sc.nextInt();

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);

    }

}
```

Output

```text
Enter your name: Alice
Enter your age: 22

Name: Alice
Age: 22
```

---

# Scanner Methods

| Method | Reads |
|---------|-------|
| `next()` | Single word |
| `nextLine()` | Entire line |
| `nextInt()` | Integer |
| `nextDouble()` | Double |
| `nextFloat()` | Float |
| `nextLong()` | Long |
| `nextBoolean()` | Boolean |

---

# Closing Scanner

After using the Scanner object, close it to release system resources.

```java
sc.close();
```

Example

```java
Scanner sc = new Scanner(System.in);

// Read input

sc.close();
```

---

# Common Mistakes

## Forgetting to Import Scanner

Incorrect

```java
Scanner sc = new Scanner(System.in);
```

Compilation Error

Correct

```java
import java.util.Scanner;
```

---

## Forgetting to Create a Scanner Object

Incorrect

```java
int age = sc.nextInt();
```

Correct

```java
Scanner sc = new Scanner(System.in);

int age = sc.nextInt();
```

---

## Using `next()` Instead of `nextLine()`

Input

```text
John Smith
```

Using

```java
String name = sc.next();
```

Output

```text
John
```

Correct

```java
String name = sc.nextLine();
```

Output

```text
John Smith
```

---

## Mixing `nextInt()` and `nextLine()`

Incorrect

```java
int age = sc.nextInt();

String name = sc.nextLine();
```

The `nextLine()` may read the leftover newline character.

Correct

```java
int age = sc.nextInt();
sc.nextLine();

String name = sc.nextLine();
```

---

# Best Practices

- Import the `Scanner` class before using it.
- Create only one Scanner object for `System.in`.
- Close the Scanner after use.
- Use `nextLine()` when reading full sentences.
- Validate user input in larger applications.

---

# Interview Questions

## 1. What is the Scanner class?

The `Scanner` class is used to read user input from the keyboard.

---

## 2. Which package contains the Scanner class?

```java
java.util
```

---

## 3. How do you create a Scanner object?

```java
Scanner sc = new Scanner(System.in);
```

---

## 4. What is the difference between `next()` and `nextLine()`?

- `next()` reads a single word.
- `nextLine()` reads an entire line.

---

## 5. How do you read an integer?

```java
int age = sc.nextInt();
```

---

## Summary

- The `Scanner` class is used to take input from the user.
- Import `java.util.Scanner` before using it.
- Create a Scanner object using `new Scanner(System.in)`.
- Different Scanner methods read different data types.
- Use `nextLine()` to read an entire line.
- Close the Scanner after use to release resources.
