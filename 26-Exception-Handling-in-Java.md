# Exception Handling in Java

## Overview

Exception Handling is a mechanism in Java that allows a program to handle runtime errors gracefully without terminating unexpectedly.

Instead of crashing, the program can catch the exception, execute alternative code, and continue execution.

---

# Why Do We Need Exception Handling?

Consider the following program.

```java
public class Main {

    public static void main(String[] args) {

        int a = 10;
        int b = 0;

        System.out.println(a / b);

        System.out.println("Program End");
    }

}
```

Output

```text
Exception in thread "main" java.lang.ArithmeticException: / by zero
```

The program stops immediately.

Using Exception Handling

```java
public class Main {

    public static void main(String[] args) {

        try {

            int a = 10;
            int b = 0;

            System.out.println(a / b);

        } catch (ArithmeticException e) {

            System.out.println("Cannot divide by zero.");

        }

        System.out.println("Program End");

    }

}
```

Output

```text
Cannot divide by zero.
Program End
```

---

# What is an Exception?

An Exception is an event that occurs during program execution that interrupts the normal flow of the program.

Examples

- Dividing by zero
- Accessing an invalid array index
- Opening a file that doesn't exist
- Invalid user input

---

# Exception Hierarchy

```text
Object
   │
Throwable
   │
 ┌───────────────┐
 │               │
Error        Exception
                  │
        RuntimeException
```

- **Error** → Serious problems that applications usually do not handle.
- **Exception** → Problems that programs can catch and handle.

---

# Types of Exceptions

## 1. Checked Exceptions

Checked at compile time.

Examples

- IOException
- SQLException
- FileNotFoundException

These must be handled or declared using `throws`.

---

## 2. Unchecked Exceptions

Occur during runtime.

Examples

- ArithmeticException
- NullPointerException
- ArrayIndexOutOfBoundsException
- NumberFormatException

Handling them is optional but recommended.

---

# Exception Handling Keywords

Java provides five keywords.

- try
- catch
- finally
- throw
- throws

---

# try Block

The code that may produce an exception is written inside the `try` block.

Example

```java
try {

    int result = 10 / 0;

}
```

---

# catch Block

The `catch` block handles the exception.

Example

```java
try {

    int result = 10 / 0;

} catch (ArithmeticException e) {

    System.out.println("Cannot divide by zero.");

}
```

---

# How Exception Handling Works

```text
Program Starts
       │
       ▼
Execute try Block
       │
       ▼
Exception Occurred?
    ┌───────┴────────┐
    │                │
   Yes              No
    │                │
    ▼                ▼
Execute catch     Skip catch
        │
        ▼
Continue Program
```

---

# Complete Example

```java
public class Main {

    public static void main(String[] args) {

        try {

            int[] numbers = {10, 20, 30};

            System.out.println(numbers[5]);

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("Invalid Array Index.");

        }

        System.out.println("Program Continues.");

    }

}
```

Output

```text
Invalid Array Index.
Program Continues.
```

---

# Multiple catch Blocks

Different exceptions can be handled separately.

```java
try {

    int[] arr = new int[3];

    System.out.println(arr[5]);

} catch (ArithmeticException e) {

    System.out.println("Arithmetic Error");

} catch (ArrayIndexOutOfBoundsException e) {

    System.out.println("Invalid Index");

}
```

Output

```text
Invalid Index
```

---

# finally Block

The `finally` block always executes, whether an exception occurs or not.

Example

```java
try {

    System.out.println("Inside Try");

} finally {

    System.out.println("Finally Block Executed");

}
```

Output

```text
Inside Try
Finally Block Executed
```

---

# throw Keyword

The `throw` keyword is used to create and throw an exception manually.

Example

```java
public class Main {

    public static void main(String[] args) {

        throw new ArithmeticException("Custom Exception");

    }

}
```

Output

```text
Exception in thread "main"
java.lang.ArithmeticException: Custom Exception
```

---

# throws Keyword

The `throws` keyword declares that a method may throw an exception.

Example

```java
import java.io.IOException;

class Demo {

    void readFile() throws IOException {

        System.out.println("Reading File");

    }

}
```

The caller must handle the exception or declare it again.

---

# throw vs throws

| throw | throws |
|--------|---------|
| Throws an exception object | Declares possible exceptions |
| Used inside a method | Used in method declaration |
| Throws one exception at a time | Can declare multiple exceptions |

---

# Common Runtime Exceptions

| Exception | Cause |
|-----------|-------|
| ArithmeticException | Division by zero |
| NullPointerException | Using a null reference |
| ArrayIndexOutOfBoundsException | Invalid array index |
| NumberFormatException | Invalid number conversion |
| ClassCastException | Invalid object casting |

---

# Custom Exception

You can create your own exception by extending the `Exception` class.

Example

```java
class InvalidAgeException extends Exception {

    InvalidAgeException(String message) {

        super(message);

    }

}
```

Usage

```java
throw new InvalidAgeException("Age must be at least 18.");
```

---

# Common Mistakes

## Catching the Wrong Exception

Incorrect

```java
catch (NullPointerException e)
```

when the exception is actually

```java
ArithmeticException
```

---

## Empty catch Block

Incorrect

```java
catch (Exception e) {

}
```

Always handle or log the exception.

---

## Writing Important Logic in finally

Avoid placing return statements or important business logic inside the `finally` block.

---

# Best Practices

- Catch only the exceptions you can handle.
- Use specific exception types instead of `Exception` whenever possible.
- Never leave a catch block empty.
- Write meaningful exception messages.
- Use `finally` or try-with-resources to release resources.
- Create custom exceptions for business-specific errors.

---

# Interview Questions

## 1. What is Exception Handling?

Exception Handling is a mechanism that allows Java programs to handle runtime errors without terminating unexpectedly.

---

## 2. What is the difference between Checked and Unchecked Exceptions?

Checked exceptions are verified during compilation and must be handled.

Unchecked exceptions occur during runtime and handling them is optional.

---

## 3. What is the purpose of the finally block?

The `finally` block executes whether an exception occurs or not and is mainly used for cleanup operations.

---

## 4. What is the difference between throw and throws?

`throw` explicitly throws an exception object.

`throws` declares that a method may throw one or more exceptions.

---

## 5. Can we have a try block without a catch block?

Yes.

A `try` block can exist without a `catch` block if it has a `finally` block.

Example

```java
try {

    System.out.println("Hello");

} finally {

    System.out.println("Done");

}
```

---

## 6. Can we have multiple catch blocks?

Yes.

A single `try` block can have multiple `catch` blocks to handle different exceptions.

---

# Summary

- Exception Handling prevents abnormal program termination.
- Exceptions are objects that represent runtime errors.
- Java provides `try`, `catch`, `finally`, `throw`, and `throws` for handling exceptions.
- Checked exceptions are handled during compilation.
- Unchecked exceptions occur during runtime.
- The `finally` block always executes.
- `throw` creates an exception object, while `throws` declares possible exceptions.
- Proper exception handling improves the reliability and maintainability of Java applications.
