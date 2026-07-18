# Multithreading in Java
## Overview

Multithreading is the ability of a program to execute **multiple threads simultaneously**.

A **Thread** is the smallest unit of execution inside a process.

Instead of executing one task at a time, multiple tasks can run concurrently, making programs faster and more responsive.

---

# Why Do We Need Multithreading?

Suppose you are downloading a file while listening to music.

```text
Without Multithreading

Download File
      │
      ▼
Music Starts
```

The second task waits for the first one to finish.

With Multithreading

```text
Download File
      │
      ├──────────────►
      │
Music Playing
```

Both tasks execute at the same time.

---

# Process vs Thread

| Process | Thread |
|----------|---------|
| Independent program | Smallest unit of execution |
| Has its own memory | Shares memory with other threads |
| Heavyweight | Lightweight |
| Slower creation | Faster creation |

---

# Life Cycle of a Thread

```text
New
 │
 ▼
Runnable
 │
 ▼
Running
 │
 ▼
Waiting / Blocked
 │
 ▼
Terminated
```

---

# Creating a Thread

There are two ways to create a thread.

1. Extending the `Thread` class
2. Implementing the `Runnable` interface

---
# Method 1: Extending Thread Class

Example

```java
class MyThread extends Thread {

    @Override
    public void run() {

        System.out.println("Thread is Running");

    }

}

public class Main {

    public static void main(String[] args) {

        MyThread thread = new MyThread();

        thread.start();

    }

}
```

Output

```text
Thread is Running
```

---

# Method 2: Implementing Runnable

Example

```java
class MyTask implements Runnable {

    @Override
    public void run() {

        System.out.println("Runnable Thread");

    }

}

public class Main {

    public static void main(String[] args) {

        Thread thread = new Thread(new MyTask());

        thread.start();

    }

}
```

Output

```text
Runnable Thread
```

---

# start() vs run()

Incorrect

```java
thread.run();
```

This executes like a normal method.

Correct

```java
thread.start();
```

The JVM creates a new thread and then calls the `run()` method automatically.

---

# How start() Works

```text
main()
   │
   ▼
thread.start()
   │
   ▼
JVM Creates New Thread
   │
   ▼
run() Executes
```

---

# Sleeping a Thread

The `sleep()` method pauses the current thread for a specified time.

Example

```java
try {

    Thread.sleep(2000);

} catch (InterruptedException e) {

    e.printStackTrace();

}
```

The thread pauses for **2 seconds**.

---

# Joining Threads

The `join()` method makes one thread wait until another thread finishes.

Example

```java
Thread t = new Thread();

t.start();

t.join();
```

The current thread waits until `t` completes.

---

# Thread Priority

Java allows setting thread priority.

Range

```text
1  -> MIN_PRIORITY
5  -> NORM_PRIORITY
10 -> MAX_PRIORITY
```

Example

```java
thread.setPriority(Thread.MAX_PRIORITY);
```

Priority does not guarantee execution order.

---

# Thread Methods

| Method | Description |
|----------|-------------|
| start() | Starts a new thread |
| run() | Contains thread logic |
| sleep() | Pauses a thread |
| join() | Waits for another thread |
| getName() | Returns thread name |
| setName() | Changes thread name |
| getPriority() | Returns priority |
| setPriority() | Sets priority |
| isAlive() | Checks if thread is running |

---

# Synchronization

When multiple threads access shared data simultaneously, inconsistent results may occur.

Synchronization allows only one thread to access the shared resource at a time.

Example

```java
class Counter {

    private int count = 0;

    public synchronized void increment() {

        count++;

    }

}
```

The `synchronized` keyword prevents multiple threads from executing the method simultaneously.

---

# Race Condition

A Race Condition occurs when multiple threads modify shared data at the same time.

Example

```text
Thread A
     │
     ├──► count++
     │
Thread B
     ├──► count++
```

The final value may become incorrect.

Synchronization prevents this problem.

---

# Daemon Thread

A daemon thread runs in the background.

Examples

- Garbage Collector
- Background Services

Example

```java
thread.setDaemon(true);
```

---

# Multithreading Example

```java
class MyThread extends Thread {

    public void run() {

        for(int i = 1; i <= 5; i++) {

            System.out.println(i);

        }

    }

}

public class Main {

    public static void main(String[] args) {

        MyThread thread = new MyThread();

        thread.start();

        System.out.println("Main Thread");

    }

}
```

Possible Output

```text
Main Thread
1
2
3
4
5
```

The execution order may vary.

---

# Common Mistakes

## Calling run() Instead of start()

Incorrect

```java
thread.run();
```

Correct

```java
thread.start();
```

---

## Ignoring InterruptedException

Methods like `sleep()` and `join()` throw `InterruptedException`.

Always handle or declare it.

---

## Unsynchronized Shared Data

Multiple threads updating shared data without synchronization can cause race conditions.

Use `synchronized` when necessary.

---

# Best Practices

- Prefer implementing `Runnable` over extending `Thread`.
- Keep shared data synchronized.
- Avoid unnecessary thread creation.
- Handle thread interruptions properly.
- Use thread pools (`ExecutorService`) for large applications instead of creating many threads manually.

---

# Interview Questions

## 1. What is a Thread?

A thread is the smallest unit of execution within a process.

---

## 2. What are the two ways to create a thread?

- Extending the `Thread` class
- Implementing the `Runnable` interface

---

## 3. What is the difference between `start()` and `run()`?

| start() | run() |
|----------|--------|
| Creates a new thread | Executes like a normal method |
| Calls `run()` internally | Does not create a new thread |

---

## 4. What is Synchronization?

Synchronization ensures that only one thread accesses shared resources at a time.

---

## 5. What is a Race Condition?

A race condition occurs when multiple threads modify shared data simultaneously, leading to incorrect results.

---

## 6. What is a Daemon Thread?

A daemon thread is a background thread that supports other threads, such as the Garbage Collector.



# Summary

- Multithreading allows multiple tasks to execute concurrently.
- A thread is the smallest unit of execution.
- Threads can be created by extending `Thread` or implementing `Runnable`.
- Use `start()` to begin a new thread.
- `sleep()` pauses execution, while `join()` waits for another thread.
- Synchronization prevents race conditions.
- Multithreading improves performance and responsiveness in Java applications.
