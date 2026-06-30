# Installing Java and IntelliJ IDEA

## Overview

Before writing and running Java programs, you need to install the Java Development Kit (JDK) and an Integrated Development Environment (IDE) such as IntelliJ IDEA.

---

# Step 1: Install Java (JDK)

The Java Development Kit (JDK) contains everything required to develop Java applications.

It includes:

- Java Compiler (`javac`)
- Java Launcher (`java`)
- JVM (Java Virtual Machine)
- Runtime Libraries
- Development Tools

Download the latest JDK from the official Oracle website or OpenJDK distribution.

---

# Step 2: Verify Java Installation

Open a terminal and check the installed Java version.

```bash
java --version
```

Example Output:

```text
openjdk 24.0.2
```

Check the compiler version.

```bash
javac --version
```

Example Output:

```text
javac 24.0.2
```

If both commands return a version number, Java has been installed successfully.

---

# Step 3: Install IntelliJ IDEA

IntelliJ IDEA is one of the most popular IDEs for Java development.

You can install:

- IntelliJ IDEA Community Edition (Free)
- IntelliJ IDEA Ultimate Edition (Paid)

---

# Step 4: Launch IntelliJ IDEA

Open IntelliJ IDEA from:

- Application Menu
- Desktop Shortcut
- Terminal

If IntelliJ asks for a JDK, select the installed JDK.

Example:

```text
JDK 24
```

---

# Step 5: Create Your First Project

1. Open IntelliJ IDEA.
2. Click **New Project**.
3. Select **Java**.
4. Choose the installed JDK.
5. Enter the project name.
6. Click **Create**.

Your project is now ready.

---

# Step 6: Create a Java Class

Inside the `src` folder:

- Right-click `src`
- Select **New**
- Select **Java Class**
- Enter the class name

Example:

```text
Main
```

---

# Step 7: Write Your First Program

```java
public class Main {

    public static void main(String[] args) {

        System.out.println("Hello, World!");

    }

}
```

---

# Step 8: Run the Program

Click the **Run** button or use:

```text
Shift + F10
```

Output:

```text
Hello, World!
```

---

# How IntelliJ Runs Your Program

When you click **Run**, IntelliJ performs the following steps:

```text
Source Code (.java)
        │
        ▼
JDK
        │
        ▼
Compiler (javac)
        │
        ▼
Bytecode (.class)
        │
        ▼
JRE
        │
        ├── JVM
        └── Runtime Libraries
                │
                ▼
Machine Code
                │
                ▼
CPU
                │
                ▼
Output
```

---

# Common Commands

Check Java Version

```bash
java --version
```

Check Compiler Version

```bash
javac --version
```

Compile a Java Program

```bash
javac Main.java
```

Run a Java Program

```bash
java Main
```

---

# Common Errors

## Java Command Not Found

Reason:

- Java is not installed.
- Java is not added to the system PATH.

Solution:

- Install the JDK.
- Configure the PATH environment variable.

---

## javac Command Not Found

Reason:

- JDK is not installed.
- Only the Java Runtime is available.

Solution:

- Install the JDK.
- Verify using:

```bash
javac --version
```

---

## No JDK Specified in IntelliJ

Reason:

IntelliJ cannot find the installed JDK.

Solution:

- Open **Project Structure**.
- Select **Project SDK**.
- Choose the installed JDK.

---

## Main Method Not Found

Reason:

The program does not contain the correct `main()` method.

Correct syntax:

```java
public static void main(String[] args)
```

---

# Summary

- Install the JDK before developing Java applications.
- Verify the installation using `java --version` and `javac --version`.
- Install IntelliJ IDEA.
- Configure the JDK in IntelliJ.
- Create a Java project.
- Write Java code.
- Compile and run the program.

---

# Key Points

- JDK is required to develop Java applications.
- IntelliJ IDEA is an IDE used to write, compile, run, and debug Java programs.
- `java --version` checks the Java runtime version.
- `javac --version` checks the Java compiler version.
- IntelliJ uses the installed JDK to compile and execute Java programs.
