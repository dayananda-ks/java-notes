# Static Keyword in Java

## Overview

The `static` keyword belongs to the **class**, not to individual objects.

A static member is shared among all objects of the class. It is created only once when the class is loaded into memory.

The `static` keyword can be used with:

- Variables
- Methods
- Blocks
- Nested Classes

---

# Why Do We Need `static`?

Suppose every student belongs to the same college.

Without `static`

```java
Student s1 = new Student();
Student s2 = new Student();
Student s3 = new Student();
```

Each object stores its own copy of the college name.

This wastes memory.

Using `static`

```java
static String college = "KVG College";
```

Only one copy is created and shared by all objects.

---

# How Static Works

```text
Class Loaded
      │
      ▼
Static Members Created
      │
      ▼
Objects Created
      │
      ▼
All Objects Share Static Members
```

---

# Static Variable

A static variable belongs to the class instead of individual objects.

## Syntax

```java
static dataType variableName;
```

---

## Example

```java
class Student {

    String name;
    static String college = "KVG College";

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();
        Student s2 = new Student();

        s1.name = "Rahul";
        s2.name = "Priya";

        System.out.println(s1.college);
        System.out.println(s2.college);

    }

}
```

Output

```text
KVG College
KVG College
```

Both objects share the same variable.

---

# Memory Representation

```text
             Student Class
        ------------------------
        | college = KVG College |
        ------------------------
               ▲
               │
      ---------------------
      |                   |
      ▼                   ▼

   Object s1          Object s2
  ------------       ------------
  | name=Rahul |     | name=Priya|
  ------------       ------------
```

Only one copy of `college` exists.

---

# Static Method

A static method belongs to the class.

It can be called without creating an object.

## Syntax

```java
static returnType methodName() {

}
```

---

## Example

```java
class Student {

    static void message() {

        System.out.println("Welcome");

    }

}

public class Main {

    public static void main(String[] args) {

        Student.message();

    }

}
```

Output

```text
Welcome
```

---

# Why is `main()` Static?

```java
public static void main(String[] args)
```

The JVM starts program execution by calling `main()`.

If `main()` were not static, the JVM would first need to create an object of the class.

Making it `static` allows the JVM to call it directly.

---

# Static Method Rules

A static method:

- Can access static variables.
- Can call static methods.
- Cannot directly access instance variables.
- Cannot directly call instance methods.
- Cannot use the `this` keyword.

---

## Example

```java
class Student {

    static String college = "KVG";
    String name = "Rahul";

    static void display() {

        System.out.println(college);

    }

}
```

Valid because `college` is static.

---

Incorrect

```java
static void display() {

    System.out.println(name);

}
```

Compilation Error

Reason:

`name` belongs to an object, while `display()` belongs to the class.

---

# Static Block

A static block executes automatically when the class is loaded.

It executes only once.

## Syntax

```java
static {

    // Code

}
```

---

## Example

```java
class Student {

    static {

        System.out.println("Static Block Executed");

    }

    public static void main(String[] args) {

        System.out.println("Main Method");

    }

}
```

Output

```text
Static Block Executed
Main Method
```

---

# Execution Flow

```text
Program Starts
      │
      ▼
Class Loaded
      │
      ▼
Static Block Executes
      │
      ▼
main() Executes
      │
      ▼
Objects Created (if required)
```

---

# Static vs Instance Variable

| Static Variable | Instance Variable |
|-----------------|-------------------|
| Belongs to the class | Belongs to an object |
| One copy exists | Every object has its own copy |
| Shared by all objects | Separate for each object |
| Created when class loads | Created when object is created |

---

# Static vs Instance Method

| Static Method | Instance Method |
|---------------|-----------------|
| Belongs to class | Belongs to object |
| Called using class name | Called using object |
| Cannot use `this` | Can use `this` |
| Can access only static members directly | Can access both static and instance members |

---

# Accessing Static Members

Using Class Name

```java
Student.college;

Student.message();
```

Using Object (Allowed but Not Recommended)

```java
Student s = new Student();

System.out.println(s.college);
```

Best Practice

```java
Student.college;
```

---

# Common Mistakes

## Accessing Instance Variable in Static Method

Incorrect

```java
static void display() {

    System.out.println(name);

}
```

Compilation Error

Correct

```java
System.out.println(college);
```

---

## Using `this` in Static Method

Incorrect

```java
static void show() {

    System.out.println(this);

}
```

Compilation Error

Reason:

`this` refers to an object, but static methods belong to the class.

---

## Creating Objects for Static Members

Incorrect

```java
Student s = new Student();

s.message();
```

Correct

```java
Student.message();
```

---

# Best Practices

- Use `static` for data shared by all objects.
- Call static members using the class name.
- Avoid accessing static members through objects.
- Keep static methods independent of object-specific data.

---

# Interview Questions

## 1. What is the `static` keyword?

The `static` keyword makes a member belong to the class instead of individual objects.

---

## 2. Why is the `main()` method static?

Because the JVM can call it without creating an object.

---

## 3. Can a static method access instance variables?

No.

A static method can directly access only static members.

---

## 4. Can we use `this` inside a static method?

No.

`this` refers to the current object, but a static method belongs to the class.

---

## 5. What is the difference between a static variable and an instance variable?

A static variable is shared by all objects, whereas an instance variable has a separate copy for each object.

---

# Summary

- The `static` keyword belongs to the class, not to objects.
- Static variables are shared among all objects.
- Static methods can be called without creating an object.
- The `main()` method is static so the JVM can execute it directly.
- Static methods cannot use `this` or directly access instance members.
- Static blocks execute once when the class is loaded.
