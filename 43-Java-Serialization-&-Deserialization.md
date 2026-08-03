# Java Serialization & Deserialization

## Overview

**Serialization** is the process of converting a Java object into a byte stream so it can be:

- Saved to a file
- Sent over a network
- Stored in a database
- Cached

**Deserialization** is the reverse process of converting a byte stream back into a Java object.

Java provides support for Serialization through the **java.io** package.

---

# Why Do We Need Serialization?

Suppose a Java program creates a `Student` object.

Normally

```text
Program Ends

↓

Object is Lost
```

With Serialization

```text
Student Object

↓

Byte Stream

↓

File / Network / Database

↓

Later Restored
```

The object can be recovered even after the program exits.

---

# Real-World Uses

Serialization is used in:

- File Storage
- Network Communication
- Distributed Systems
- HTTP Sessions
- Caching
- RMI (Remote Method Invocation)

---

# Serialization Process

```text
Java Object
      │
      ▼
Serialization
      │
      ▼
Byte Stream
      │
      ▼
File / Network
```

---

# Deserialization Process

```text
File / Network
      │
      ▼
Byte Stream
      │
      ▼
Deserialization
      │
      ▼
Java Object
```

---

# Serializable Interface

A class must implement the `Serializable` interface.

Example

```java
import java.io.Serializable;

class Student implements Serializable{

    int id;

    String name;

}
```

`Serializable` is a **marker interface**.

It contains **no methods**.

---

# Marker Interface

A marker interface is an interface without any methods.

Examples

- Serializable
- Cloneable
- Remote

Its purpose is to provide information to the JVM or compiler.

---

# Serializing an Object

Example

```java
import java.io.*;

public class Main{

    public static void main(String[] args)
    throws Exception{

        Student student =
        new Student();

        student.id = 1;
        student.name = "Ashu";

        FileOutputStream file =
        new FileOutputStream("student.ser");

        ObjectOutputStream output =
        new ObjectOutputStream(file);

        output.writeObject(student);

        output.close();

        file.close();

    }

}
```

This creates a file named:

```text
student.ser
```

---

# Deserializing an Object

Example

```java
import java.io.*;

public class Main{

    public static void main(String[] args)
    throws Exception{

        FileInputStream file =
        new FileInputStream("student.ser");

        ObjectInputStream input =
        new ObjectInputStream(file);

        Student student =
        (Student) input.readObject();

        System.out.println(student.name);

        input.close();

        file.close();

    }

}
```

Output

```text
Ashu
```

---

# ObjectOutputStream

Used to write objects.

Example

```java
ObjectOutputStream output =
new ObjectOutputStream(file);

output.writeObject(student);
```

---

# ObjectInputStream

Used to read serialized objects.

Example

```java
ObjectInputStream input =
new ObjectInputStream(file);

Student student =
(Student) input.readObject();
```

---

# serialVersionUID

Each Serializable class should define a version ID.

Example

```java
class Student
implements Serializable{

    private static final long
    serialVersionUID = 1L;

}
```

It ensures compatibility during deserialization.

---

# transient Keyword

The `transient` keyword prevents a field from being serialized.

Example

```java
class Student
implements Serializable{

    String name;

    transient String password;

}
```

After deserialization,

```java
password
```

becomes

```text
null
```

---

# static Fields

Static variables belong to the class, not the object.

They are **not serialized**.

Example

```java
class Student
implements Serializable{

    static String college =
    "KVG";

}
```

---

# Complete Example

```java
import java.io.*;

class Student
implements Serializable{

    private static final long
    serialVersionUID = 1L;

    int id;

    String name;

}

public class Main{

    public static void main(String[] args)
    throws Exception{

        Student student =
        new Student();

        student.id = 1;

        student.name = "Ashu";

        ObjectOutputStream out =
        new ObjectOutputStream(
        new FileOutputStream(
        "student.ser"));

        out.writeObject(student);

        out.close();

        ObjectInputStream in =
        new ObjectInputStream(
        new FileInputStream(
        "student.ser"));

        Student s =
        (Student) in.readObject();

        System.out.println(s.name);

        in.close();

    }

}
```

Output

```text
Ashu
```

---

# How Serialization Works

```text
Java Object
      │
      ▼
Serializable
      │
      ▼
ObjectOutputStream
      │
      ▼
Byte Stream
      │
      ▼
File
```

---

# How Deserialization Works

```text
File
     │
     ▼
ObjectInputStream
     │
     ▼
Byte Stream
     │
     ▼
Java Object
```

---

# Serialization vs Deserialization

| Serialization | Deserialization |
|---------------|-----------------|
| Object → Byte Stream | Byte Stream → Object |
| ObjectOutputStream | ObjectInputStream |
| writeObject() | readObject() |

---

# Common Mistakes

## Forgetting Serializable

Incorrect

```java
class Student{

}
```

Runtime Error

```text
NotSerializableException
```

Correct

```java
class Student
implements Serializable{

}
```

---

## Forgetting serialVersionUID

Without it,

changes in the class may cause

```text
InvalidClassException
```

---

## Expecting transient Fields to be Saved

Example

```java
transient String password;
```

The value is not stored.

---

# Best Practices

- Always implement `Serializable` when serialization is required.
- Define `serialVersionUID`.
- Mark sensitive fields as `transient`.
- Close streams properly.
- Use try-with-resources for automatic resource management.
- Avoid serializing unnecessary data.

---

# Interview Questions

## 1. What is Serialization?

Serialization is the process of converting a Java object into a byte stream.

---

## 2. What is Deserialization?

Deserialization is the process of converting a byte stream back into a Java object.

---

## 3. Which interface enables Serialization?

```java
Serializable
```

---

## 4. What is a Marker Interface?

A Marker Interface is an interface with no methods.

It provides metadata to the JVM.

---

## 5. What is serialVersionUID?

It is a unique version identifier used to verify compatibility during deserialization.

---

## 6. What does the `transient` keyword do?

It prevents a field from being serialized.

---

## 7. Are static variables serialized?

No.

Static variables belong to the class, not to individual objects.

---

# Summary

- Serialization converts Java objects into byte streams.
- Deserialization restores byte streams back into Java objects.
- The `Serializable` interface enables serialization.
- `ObjectOutputStream` writes objects, and `ObjectInputStream` reads them.
- `serialVersionUID` ensures version compatibility.
- `transient` fields and `static` fields are not serialized.
- Serialization is widely used in file storage, networking, caching, and distributed applications.
