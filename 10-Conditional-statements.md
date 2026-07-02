# Conditional Statements in Java

## Overview

Conditional statements allow a program to make decisions based on conditions.

They execute different blocks of code depending on whether a condition is `true` or `false`.

---

# Why Do We Need Conditional Statements?

Conditional statements are used to:

- Make decisions.
- Execute code based on conditions.
- Control the program flow.

Examples:

- Check whether a person is eligible to vote.
- Find the largest number.
- Check whether a number is positive or negative.
- Determine grades based on marks.

---

# Types of Conditional Statements

Java provides the following conditional statements:

1. if Statement
2. if-else Statement
3. if-else-if Ladder
4. Nested if
5. switch Statement

---

# 1. if Statement

The `if` statement executes a block of code only if the condition is `true`.

## Syntax

```java
if (condition) {

    // Code

}
```

## Example

```java
public class Main {

    public static void main(String[] args) {

        int age = 20;

        if (age >= 18) {
            System.out.println("Eligible to Vote");
        }

    }

}
```

Output

```text
Eligible to Vote
```

---

# 2. if-else Statement

The `if-else` statement executes one block if the condition is `true` and another block if it is `false`.

## Syntax

```java
if (condition) {

    // Code if true

} else {

    // Code if false

}
```

## Example

```java
public class Main {

    public static void main(String[] args) {

        int age = 16;

        if (age >= 18) {
            System.out.println("Eligible to Vote");
        } else {
            System.out.println("Not Eligible");
        }

    }

}
```

Output

```text
Not Eligible
```

---

# 3. if-else-if Ladder

Used when multiple conditions need to be checked.

## Syntax

```java
if (condition1) {

} else if (condition2) {

} else if (condition3) {

} else {

}
```

## Example

```java
public class Main {

    public static void main(String[] args) {

        int marks = 82;

        if (marks >= 90) {
            System.out.println("Grade A");
        } else if (marks >= 75) {
            System.out.println("Grade B");
        } else if (marks >= 50) {
            System.out.println("Grade C");
        } else {
            System.out.println("Fail");
        }

    }

}
```

Output

```text
Grade B
```

---

# 4. Nested if

A Nested `if` is an `if` statement inside another `if` statement.

## Example

```java
public class Main {

    public static void main(String[] args) {

        int age = 22;
        boolean hasLicense = true;

        if (age >= 18) {

            if (hasLicense) {
                System.out.println("Can Drive");
            } else {
                System.out.println("License Required");
            }

        } else {
            System.out.println("Not Eligible");
        }

    }

}
```

Output

```text
Can Drive
```

---

# 5. switch Statement

The `switch` statement is used when one variable has multiple possible values.

## Syntax

```java
switch (expression) {

    case value1:
        // Code
        break;

    case value2:
        // Code
        break;

    default:
        // Code

}
```

---

## Example

```java
public class Main {

    public static void main(String[] args) {

        int day = 3;

        switch (day) {

            case 1:
                System.out.println("Monday");
                break;

            case 2:
                System.out.println("Tuesday");
                break;

            case 3:
                System.out.println("Wednesday");
                break;

            default:
                System.out.println("Invalid Day");

        }

    }

}
```

Output

```text
Wednesday
```

---

# break Statement

The `break` statement terminates the current case.

Without `break`, execution continues into the next case.

Example

```java
int number = 2;

switch (number) {

    case 1:
        System.out.println("One");

    case 2:
        System.out.println("Two");

    case 3:
        System.out.println("Three");

}
```

Output

```text
Two
Three
```

With `break`

```java
case 2:
    System.out.println("Two");
    break;
```

Output

```text
Two
```

---

# default Case

The `default` block executes when none of the cases match.

Example

```java
int day = 8;

switch (day) {

    default:
        System.out.println("Invalid Day");

}
```

Output

```text
Invalid Day
```

---

# if vs switch

| if | switch |
|----|---------|
| Checks conditions | Checks a single expression |
| Supports logical operators | Does not use logical operators in case labels |
| Suitable for ranges | Suitable for fixed values |
| More flexible | Easier to read for many fixed options |

---

# Common Mistakes

## Missing Parentheses

Incorrect

```java
if age >= 18
```

Correct

```java
if (age >= 18)
```

---

## Using Assignment Instead of Comparison

Incorrect

```java
if (age = 18)
```

Correct

```java
if (age == 18)
```

---

## Forgetting break in switch

Incorrect

```java
case 1:
    System.out.println("One");
```

Execution continues to the next case.

Correct

```java
case 1:
    System.out.println("One");
    break;
```

---

# Best Practices

- Use `if` for complex conditions.
- Use `switch` for fixed values.
- Always use `break` unless fall-through is intended.
- Keep conditions simple and readable.
- Indent code properly.

---

# Interview Questions

## 1. What is a conditional statement?

A conditional statement is used to execute different blocks of code based on a condition.

---

## 2. What are the different conditional statements in Java?

- if
- if-else
- if-else-if
- Nested if
- switch

---

## 3. When should you use `switch` instead of `if`?

Use `switch` when checking one variable against multiple fixed values.

---

## 4. What is the purpose of the `break` statement?

The `break` statement exits the current `switch` case and prevents execution from continuing to the next case.

---

## 5. What is the `default` case?

The `default` case executes when no `case` matches the expression.

---

# Summary

- Conditional statements help programs make decisions.
- Java provides `if`, `if-else`, `if-else-if`, `Nested if`, and `switch`.
- Use `if` for complex conditions.
- Use `switch` for multiple fixed values.
- Always use `break` in `switch` unless fall-through is required.
- The `default` case handles unmatched values.
