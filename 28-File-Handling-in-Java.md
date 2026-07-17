# File Handling in Java

## Overview

File Handling is the process of creating, reading, writing, updating, and deleting files stored on a computer.

Java provides the **java.io** and **java.nio** packages to perform file operations.

Using File Handling, applications can:

- Store data permanently
- Read existing files
- Write new data
- Update file contents
- Delete unwanted files

---

# Why Do We Need File Handling?

Normally, variables store data only while the program is running.

Example

```java
String name = "Ashu";
```

After the program ends, the value is lost.

Using files, data is stored permanently.

Example

```text
students.txt

Ashu
Rahul
Kiran
```

The data remains even after the program closes.

---

# Java File Handling Packages

Java mainly provides two packages.

```text
java.io
java.nio.file
```

Commonly used classes:

- File
- FileReader
- FileWriter
- BufferedReader
- BufferedWriter
- Scanner
- PrintWriter

---

# The File Class

The `File` class represents a file or directory.

Import

```java
import java.io.File;
```

Example

```java
File file = new File("sample.txt");
```

This only creates a File object.

It does not create the actual file.

---

# Creating a File

Method

```java
createNewFile()
```

Example

```java
import java.io.*;

public class Main {

    public static void main(String[] args) throws IOException {

        File file = new File("sample.txt");

        if(file.createNewFile()){

            System.out.println("File Created");

        }else{

            System.out.println("File Already Exists");

        }

    }

}
```

---

# Writing to a File

Class Used

```text
FileWriter
```

Example

```java
import java.io.*;

public class Main {

    public static void main(String[] args) throws IOException {

        FileWriter writer = new FileWriter("sample.txt");

        writer.write("Hello Java");

        writer.close();

    }

}
```

Output

```text
sample.txt

Hello Java
```

Always close the writer after writing.

---

# Reading a File

Class Used

```text
FileReader
```

Example

```java
import java.io.*;

public class Main {

    public static void main(String[] args) throws IOException {

        FileReader reader = new FileReader("sample.txt");

        int ch;

        while((ch = reader.read()) != -1){

            System.out.print((char) ch);

        }

        reader.close();

    }

}
```

Output

```text
Hello Java
```

---

# Using BufferedReader

BufferedReader reads files efficiently.

Example

```java
import java.io.*;

public class Main {

    public static void main(String[] args) throws IOException {

        BufferedReader br =
        new BufferedReader(new FileReader("sample.txt"));

        String line;

        while((line = br.readLine()) != null){

            System.out.println(line);

        }

        br.close();

    }

}
```

---

# Writing Using BufferedWriter

Example

```java
import java.io.*;

public class Main {

    public static void main(String[] args) throws IOException {

        BufferedWriter bw =
        new BufferedWriter(new FileWriter("sample.txt"));

        bw.write("Welcome");

        bw.close();

    }

}
```

---

# Reading Using Scanner

Example

```java
import java.io.*;
import java.util.*;

public class Main {

    public static void main(String[] args) throws Exception {

        File file = new File("sample.txt");

        Scanner sc = new Scanner(file);

        while(sc.hasNextLine()){

            System.out.println(sc.nextLine());

        }

        sc.close();

    }

}
```

---

# Appending Data

By default, `FileWriter` overwrites existing data.

To append data:

```java
FileWriter writer =
new FileWriter("sample.txt", true);

writer.write("\nJava");

writer.close();
```

Output

```text
Hello Java
Java
```

---

# Deleting a File

Method

```java
delete()
```

Example

```java
File file = new File("sample.txt");

if(file.delete()){

    System.out.println("File Deleted");

}
```

---

# Useful File Methods

| Method | Description |
|----------|-------------|
| createNewFile() | Creates a file |
| exists() | Checks whether file exists |
| delete() | Deletes the file |
| getName() | Returns file name |
| getPath() | Returns file path |
| length() | Returns file size |
| canRead() | Checks read permission |
| canWrite() | Checks write permission |

---

# Exception Handling in File Operations

Most file operations throw checked exceptions.

Example

```java
try{

    FileReader reader =
    new FileReader("sample.txt");

}catch(IOException e){

    System.out.println(e.getMessage());

}
```

---

# How File Handling Works

```text
Program Starts
      │
      ▼
Create File Object
      │
      ▼
Open File
      │
      ▼
Read / Write Data
      │
      ▼
Close File
      │
      ▼
Program Ends
```

---

# Common Mistakes

## Forgetting to Close the File

Incorrect

```java
FileWriter writer =
new FileWriter("sample.txt");

writer.write("Java");
```

Correct

```java
writer.close();
```

---

## Reading a Non-Existing File

```java
new FileReader("abc.txt");
```

This throws:

```text
FileNotFoundException
```

Always check:

```java
file.exists();
```

---

## Overwriting Data Accidentally

Incorrect

```java
new FileWriter("sample.txt");
```

Correct

```java
new FileWriter("sample.txt", true);
```

Use `true` to append.

---

# Best Practices

- Always close streams after use.
- Handle exceptions properly.
- Use BufferedReader and BufferedWriter for better performance.
- Check whether a file exists before reading.
- Use append mode when adding data.

---

# Interview Questions

## 1. What is File Handling?

File Handling is the process of creating, reading, writing, updating, and deleting files.

---

## 2. Which package is used for File Handling?

```text
java.io
```

and

```text
java.nio.file
```

---

## 3. Which class represents a file?

```java
File
```

---

## 4. What is the difference between FileReader and FileWriter?

- FileReader reads data from a file.
- FileWriter writes data to a file.

---

## 5. Why should we close a file?

Closing a file releases system resources and ensures all data is saved properly.

---

## 6. How do you append data to an existing file?

```java
FileWriter writer =
new FileWriter("sample.txt", true);
```

---

# Summary

- File Handling allows programs to store data permanently.
- Java provides the `java.io` and `java.nio.file` packages for file operations.
- The `File` class represents files and directories.
- `FileReader` and `BufferedReader` are used for reading.
- `FileWriter` and `BufferedWriter` are used for writing.
- Always close files after use.
- Handle exceptions properly to avoid runtime errors.
- Use append mode when you want to add data without overwriting existing content.
