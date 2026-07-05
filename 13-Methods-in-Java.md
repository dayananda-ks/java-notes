# Methods in Java
## Overview

A method is a block of code that performs a specific task. Instead of writing the same code multiple times, we can write it once inside a method and call it whenever needed.

Methods improve code reusability, readability, and maintainability.
---
# Why Do We Need Methods?

Methods are used to:

- Avoid code duplication.
- Improve code readability.
- Organize programs into smaller parts.
- Reuse code multiple times.

Without Method

```java
System.out.println("Welcome");
System.out.println("Welcome");
System.out.println("Welcome");
```

With Method

```java
printMessage();
printMessage();
printMessage();
```

---

# Syntax

```java
accessModifier static returnType methodName(parameters) {

    // Method Body

}
```

Example

```java
public static void greet() {

    System.out.println("Welcome");

}
```

---

# Parts of a Method

```java
public static int add(int a, int b) {

    return a + b;

}
```

| Part | Description |
|------|-------------|
| public | Access Modifier |
| static | Method belongs to the class |
| int | Return Type |
| add | Method Name |
| int a, int b | Parameters |
| return | Returns a value |

---

# Calling a Method

A method does not execute until it is called.

Example

```java
public class Main {

    public static void greet() {

        System.out.println("Welcome");

    }

    public static void main(String[] args) {

        greet();

    }

}
```

Output

```text
Welcome
```

---

# Method with Parameters

Parameters allow data to be passed into a method.

Example

```java
public class Main {

    public static void greet(String name) {

        System.out.println("Welcome " + name);

    }

    public static void main(String[] args) {

        greet("Alice");

    }

}
```

Output

```text
Welcome Alice
```

---

# Method with Multiple Parameters

Example

```java
public class Main {

    public static void add(int a, int b) {

        System.out.println(a + b);

    }

    public static void main(String[] args) {

        add(10, 20);

    }

}
```

Output

```text
30
```

---

# Return Type

A method can return a value using the `return` keyword.

Example

```java
public class Main {

    public static int add(int a, int b) {

        return a + b;

    }

    public static void main(String[] args) {

        int sum = add(10, 20);

        System.out.println(sum);

    }

}
```

Output

```text
30
```

---

# void Method

A method with the `void` return type does not return any value.

Example

```java
public static void message() {

    System.out.println("Hello");

}
```

---

# Method Arguments

Arguments are the actual values passed when calling a method.

Example

```java
display("Java");
```

Here,

```text
"Java"
```

is the argument.

---

# Parameters vs Arguments

| Parameters | Arguments |
|------------|-----------|
| Declared in the method | Passed during method call |
| Variables | Actual values |

Example

```java
public static void greet(String name) {

}
```

`name` is a parameter.

```java
greet("Alice");
```

`"Alice"` is an argument.

---

# Method Overloading

Method overloading means creating multiple methods with the same name but different parameters.

Example

```java
public class Main {

    static int add(int a, int b) {

        return a + b;

    }

    static double add(double a, double b) {

        return a + b;

    }

    public static void main(String[] args) {

        System.out.println(add(10, 20));
        System.out.println(add(5.5, 4.5));

    }

}
```

Output

```text
30
10.0
```

---

# Types of Methods

## 1. Built-in Methods

Methods provided by Java.

Example

```java
Math.max(10, 20);
```

---

## 2. User-defined Methods

Methods created by the programmer.

Example

```java
public static void greet() {

    System.out.println("Hello");

}
```

---

# Method Execution Flow

```text
main()
   │
   ▼
Method Call
   │
   ▼
Execute Method
   │
   ▼
Return Value (if any)
   │
   ▼
Continue Execution
```

---

# Example Program

```java
public class Main {

    public static int square(int number) {

        return number * number;

    }

    public static void main(String[] args) {

        int result = square(5);

        System.out.println(result);

    }

}
```

Output

```text
25
```

---

# Common Mistakes

## Forgetting to Call the Method

Incorrect

```java
public static void greet() {

    System.out.println("Hello");

}
```

No output is produced because the method is never called.

Correct

```java
greet();
```

---

## Missing Return Statement

Incorrect

```java
public static int add(int a, int b) {

}
```

Correct

```java
public static int add(int a, int b) {

    return a + b;

}
```

---

## Wrong Return Type

Incorrect

```java
public static int message() {

    return "Hello";

}
```

Correct

```java
public static String message() {

    return "Hello";

}
```

---

# Best Practices

- Use meaningful method names.
- Keep methods short and focused.
- Avoid duplicate code.
- Use parameters instead of hardcoding values.
- Return values when needed.

---

# Interview Questions

## 1. What is a method?

A method is a block of code that performs a specific task.

---

## 2. Why are methods used?

Methods are used to improve code reusability, readability, and maintainability.

---

## 3. What is the difference between parameters and arguments?

- Parameters are variables declared in the method.
- Arguments are the actual values passed to the method.

---

## 4. What is method overloading?

Method overloading is defining multiple methods with the same name but different parameter lists.

---

## 5. What is the difference between `void` and a return type?

- `void` methods do not return a value.
- Methods with a return type return a value using the `return` keyword.

---

# Summary

- A method is a reusable block of code.
- Methods help avoid code duplication.
- A method can have parameters and a return value.
- `void` methods do not return a value.
- Arguments are passed to methods during method calls.
- Method overloading allows multiple methods with the same name but different parameters.
- Methods make programs modular, readable, and maintainable.
