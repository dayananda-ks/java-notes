# Java Input and Output (I/O)

## Overview

Java Input and Output (I/O) is used to read data from various sources and write data to different destinations.

Examples:

- Keyboard
- Files
- Network
- Memory
- Database

Java provides the **java.io** package for performing input and output operations.

---

# Why Do We Need I/O?

A program often needs to communicate with the outside world.

For example:

- Read user input
- Save data into a file
- Read data from a file
- Send data over a network

Without I/O, programs cannot interact with users or external resources.

---

# Input vs Output

| Input | Output |
|--------|---------|
| Reads data | Writes data |
| Keyboard | Monitor |
| File Reading | File Writing |
| Network Receiving | Network Sending |

---

# Java I/O Architecture

```text
          Input

Keyboard / File / Network
          │
          ▼
     Input Stream
          │
          ▼
     Java Program
          │
          ▼
    Output Stream
          │
          ▼
Monitor / File / Network
```

---

# Stream

A **Stream** is a sequence of data flowing between a source and a destination.

There are two types:

- Input Stream
- Output Stream

---

# Byte Stream

Byte Streams process data **one byte (8 bits)** at a time.

Used for:

- Images
- Audio
- Video
- Binary files

Main Classes

- InputStream
- OutputStream

---

# Character Stream

Character Streams process data **one character (16 bits)** at a time.

Used for:

- Text files
- Documents

Main Classes

- Reader
- Writer

---

# Byte Stream Hierarchy

```text
InputStream
      │
      ├── FileInputStream
      ├── BufferedInputStream
      └── ByteArrayInputStream

OutputStream
      │
      ├── FileOutputStream
      ├── BufferedOutputStream
      └── ByteArrayOutputStream
```

---

# Character Stream Hierarchy

```text
Reader
   │
   ├── FileReader
   ├── BufferedReader
   └── InputStreamReader

Writer
   │
   ├── FileWriter
   ├── BufferedWriter
   └── PrintWriter
```

---

# InputStream

Used to read binary data.

Example

```java
FileInputStream input =
new FileInputStream("data.txt");
```

---

# OutputStream

Used to write binary data.

Example

```java
FileOutputStream output =
new FileOutputStream("data.txt");
```

---

# Reader

Used to read characters.

Example

```java
FileReader reader =
new FileReader("notes.txt");
```

---

# Writer

Used to write characters.

Example

```java
FileWriter writer =
new FileWriter("notes.txt");
```

---

# Buffered Streams

Buffered streams improve performance by reducing direct disk access.

Example

```java
BufferedReader br =
new BufferedReader(
new FileReader("notes.txt")
);
```

Example

```java
BufferedWriter bw =
new BufferedWriter(
new FileWriter("notes.txt")
);
```

---

# PrintWriter

`PrintWriter` provides convenient methods for writing formatted text.

Example

```java
PrintWriter writer =
new PrintWriter("output.txt");

writer.println("Hello");

writer.close();
```

---

# Reading User Input

Java commonly uses the `Scanner` class.

Example

```java
Scanner sc =
new Scanner(System.in);

String name =
sc.nextLine();

System.out.println(name);
```

---

# Console Class

The `Console` class reads input securely.

Example

```java
Console console =
System.console();
```

It is mainly used for reading passwords.

---

# Standard Streams

Java provides three standard streams.

| Stream | Purpose |
|----------|----------|
| System.in | Standard Input |
| System.out | Standard Output |
| System.err | Standard Error |

Example

```java
System.out.println("Hello");
```

---

# How Java I/O Works

```text
Keyboard / File
       │
       ▼
Input Stream
       │
       ▼
Java Program
       │
       ▼
Output Stream
       │
       ▼
Monitor / File
```

---

# Byte Stream vs Character Stream

| Byte Stream | Character Stream |
|--------------|-----------------|
| Processes bytes | Processes characters |
| Binary files | Text files |
| InputStream | Reader |
| OutputStream | Writer |

---

# Common Mistakes

## Forgetting to Close Streams

Incorrect

```java
FileReader reader =
new FileReader("data.txt");
```

Always close the stream.

```java
reader.close();
```

---

## Using Byte Streams for Text

Incorrect

```java
FileInputStream input =
new FileInputStream("notes.txt");
```

For text files, prefer:

```java
FileReader reader =
new FileReader("notes.txt");
```

---

## Ignoring Exceptions

Most I/O operations throw `IOException`.

Always handle or declare the exception.

---

# Best Practices

- Use Character Streams for text files.
- Use Byte Streams for binary files.
- Use Buffered Streams for better performance.
- Always close streams after use.
- Handle `IOException` properly.
- Use try-with-resources to automatically close streams.

Example

```java
try(FileReader reader =
new FileReader("notes.txt")){

    // Read file

}
```

The stream closes automatically.

---

# Interview Questions

## 1. What is Java I/O?

Java I/O is the mechanism used to read and write data between a Java program and external resources.

---

## 2. What is a Stream?

A Stream is a sequence of data flowing between a source and a destination.

---

## 3. What is the difference between Byte Stream and Character Stream?

| Byte Stream | Character Stream |
|--------------|-----------------|
| Reads bytes | Reads characters |
| Binary files | Text files |
| InputStream | Reader |

---

## 4. Why are Buffered Streams used?

Buffered Streams improve performance by reducing the number of direct read and write operations.

---

## 5. What are the three standard streams in Java?

- System.in
- System.out
- System.err

---

## 6. What is try-with-resources?

It is a feature introduced in Java 7 that automatically closes resources after use.

---

# Summary

- Java I/O enables communication between programs and external resources.
- Streams are used to transfer data.
- Byte Streams handle binary data, while Character Streams handle text.
- Buffered Streams improve performance.
- `Scanner` and `Console` are commonly used for user input.
- Always close streams or use try-with-resources to prevent resource leaks.
- Proper use of Java I/O is essential for file handling, networking, and many real-world applications.
