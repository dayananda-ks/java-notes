# Constructors in Java

## Overview

A **Constructor** is a special member of a class that is automatically called when an object is created.

Its primary purpose is to **initialize the object's data**.

Unlike a method, a constructor **does not have a return type** and **has the same name as the class**.

---

# Why Do We Need Constructors?

Without constructors, we would have to initialize object values manually every time.

Without Constructor

```java
Student s1 = new Student();

s1.name = "Rahul";
s1.age = 20;
```

With Constructor

```java
Student s1 = new Student("Rahul", 20);
```

Constructors make object creation easier, cleaner, and less error-prone.

---

# Characteristics of a Constructor

- Has the same name as the class.
- Has no return type (not even `void`).
- Executes automatically when an object is created.
- Used to initialize object data.
- Can be overloaded.

---

# Syntax

```java
class ClassName {

    ClassName() {

        // Constructor Body

    }

}
```

---

# How Constructor Works

```text
Create Object
      │
      ▼
new Keyword
      │
      ▼
Memory Allocated
      │
      ▼
Constructor Executes Automatically
      │
      ▼
Object Ready to Use
```

---

# Default Constructor

A constructor with **no parameters** is called a **Default (No-Argument) Constructor**.

Example

```java
class Student {

    Student() {

        System.out.println("Constructor Called");

    }

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();

    }

}
```

Output

```text
Constructor Called
```

---

# Parameterized Constructor

A constructor that accepts parameters is called a **Parameterized Constructor**.

Example

```java
class Student {

    String name;
    int age;

    Student(String n, int a) {

        name = n;
        age = a;

    }

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student("Rahul", 20);

        System.out.println(s1.name);
        System.out.println(s1.age);

    }

}
```

Output

```text
Rahul
20
```

---

# Constructor Overloading

A class can have multiple constructors with different parameter lists.

Example

```java
class Student {

    Student() {

        System.out.println("Default Constructor");

    }

    Student(String name) {

        System.out.println(name);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();

        Student s2 = new Student("Rahul");

    }

}
```

Output

```text
Default Constructor
Rahul
```

---

# Default Constructor vs Parameterized Constructor

| Default Constructor | Parameterized Constructor |
|----------------------|---------------------------|
| No parameters | Has parameters |
| Initializes default values | Initializes custom values |
| Easy object creation | Flexible object creation |

---

# Constructor vs Method

| Constructor | Method |
|-------------|--------|
| Same name as class | Can have any valid name |
| No return type | Must have a return type or `void` |
| Called automatically | Called explicitly |
| Used to initialize objects | Used to perform operations |

---

# Example Program

```java
class Employee {

    String name;
    double salary;

    Employee(String name, double salary) {

        this.name = name;
        this.salary = salary;

    }

    void display() {

        System.out.println("Name: " + name);
        System.out.println("Salary: " + salary);

    }

}

public class Main {

    public static void main(String[] args) {

        Employee emp = new Employee("Alice", 50000);

        emp.display();

    }

}
```

Output

```text
Name: Alice
Salary: 50000.0
```

---

# Constructor Execution Flow

```text
Program Starts
      │
      ▼
Object Creation
      │
      ▼
new Keyword
      │
      ▼
Memory Allocated
      │
      ▼
Constructor Executes
      │
      ▼
Variables Initialized
      │
      ▼
Object Ready
```

---

# Important Rules

- Constructor name must match the class name.
- Constructors cannot have a return type.
- Constructors are called automatically.
- A constructor can be overloaded.
- Constructors cannot be inherited.

---

# Common Mistakes

## Giving a Return Type

Incorrect

```java
void Student() {

}
```

This is a method, **not** a constructor.

Correct

```java
Student() {

}
```

---

## Constructor Name Doesn't Match Class Name

Incorrect

```java
class Student {

    Person() {

    }

}
```

Correct

```java
class Student {

    Student() {

    }

}
```

---

## Expecting Constructor to Return a Value

Incorrect

```java
int Student() {

    return 10;

}
```

A constructor never returns a value.

---

# Best Practices

- Use constructors to initialize object data.
- Use parameterized constructors when objects require different values.
- Avoid putting complex business logic inside constructors.
- Use constructor overloading when multiple ways of object creation are needed.

---

# Interview Questions

## 1. What is a constructor?

A constructor is a special member of a class that initializes an object when it is created.

---

## 2. When is a constructor called?

A constructor is called automatically when an object is created using the `new` keyword.

---

## 3. Can a constructor have a return type?

No. A constructor cannot have any return type, not even `void`.

---

## 4. What is constructor overloading?

Constructor overloading is defining multiple constructors with different parameter lists in the same class.

---

## 5. What is the difference between a constructor and a method?

A constructor initializes an object and is called automatically, whereas a method performs operations and must be called explicitly.

---

# Summary

- A constructor is a special member of a class used to initialize objects.
- It has the same name as the class and no return type.
- Constructors are executed automatically when an object is created.
- Java supports default and parameterized constructors.
- Constructors can be overloaded.
- Constructors simplify object initialization and improve code readability.
