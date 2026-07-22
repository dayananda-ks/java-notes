# Java Networking

## Overview
Java Networking allows Java applications running on different computers to communicate over a network.

Using Java Networking, applications can:

- Send data
- Receive data
- Build client-server applications
- Transfer files
- Create chat applications
- Communicate over the Internet

Java provides networking support through the `java.net` package.

---

# Why Do We Need Networking?

Suppose two computers want to exchange messages.

Without Networking

```text
Computer A

×

Computer B
```

No communication is possible.

With Java Networking

```text
Computer A

↓

Network (Internet/LAN)

↓

Computer B
```

Both computers can exchange data.

---

# Important Networking Terms

| Term | Description |
|--------|-------------|
| IP Address | Unique address of a device |
| Port | Communication endpoint of an application |
| Socket | Connection between two computers |
| Protocol | Rules for communication |
| Client | Requests a service |
| Server | Provides a service |

---

# Client-Server Architecture

```text
Client
   │
   │ Request
   ▼
Server
   │
   │ Response
   ▼
Client
```

Examples

- Browser → Web Server
- Mobile App → Backend Server
- ATM → Bank Server

---

# IP Address

An IP Address uniquely identifies a device on a network.

Example

```text
192.168.1.10
```

Types

- IPv4
- IPv6

---

# Port Number

A Port identifies a specific application running on a device.

Examples

| Service | Port |
|----------|------|
| HTTP | 80 |
| HTTPS | 443 |
| MySQL | 3306 |
| SSH | 22 |

---

# Protocols

A Protocol defines the rules for communication.

Common protocols

- HTTP
- HTTPS
- FTP
- SMTP
- TCP
- UDP

---

# Socket

A Socket is one endpoint of a communication between two machines.

```text
Client Socket
       │
       ▼
Network
       ▲
       │
Server Socket
```

Java uses sockets for communication.

---

# TCP vs UDP

| TCP | UDP |
|------|-----|
| Connection-oriented | Connectionless |
| Reliable | Faster |
| Error Checking | No Error Checking |
| Ordered Data | Unordered Data |

Use TCP when data accuracy is important.

Use UDP when speed is important.

---

# Java Networking Classes

Common classes in `java.net`

| Class | Purpose |
|---------|----------|
| InetAddress | IP address information |
| URL | Represents a web address |
| Socket | Client connection |
| ServerSocket | Server connection |
| DatagramSocket | UDP communication |
| DatagramPacket | UDP data packet |

---

# InetAddress

Used to obtain IP address information.

Example

```java
import java.net.*;

public class Main {

    public static void main(String[] args)
    throws Exception {

        InetAddress ip =
        InetAddress.getByName("google.com");

        System.out.println(ip);

    }

}
```

---

# URL Class

Represents a web address.

Example

```java
URL url =
new URL("https://www.google.com");

System.out.println(url.getHost());
```

Output

```text
www.google.com
```

---

# Socket (Client)

A client uses `Socket` to connect to a server.

Example

```java
Socket socket =
new Socket("localhost", 5000);
```

---

# ServerSocket

A server waits for client requests.

Example

```java
ServerSocket server =
new ServerSocket(5000);

Socket socket =
server.accept();
```

The `accept()` method waits until a client connects.

---

# Simple Client Example

```java
import java.net.*;

public class Client {

    public static void main(String[] args)
    throws Exception {

        Socket socket =
        new Socket("localhost", 5000);

        System.out.println("Connected");

        socket.close();

    }

}
```

---

# Simple Server Example

```java
import java.net.*;

public class Server {

    public static void main(String[] args)
    throws Exception {

        ServerSocket server =
        new ServerSocket(5000);

        System.out.println("Waiting...");

        Socket socket =
        server.accept();

        System.out.println("Client Connected");

        socket.close();

        server.close();

    }

}
```

---

# Sending Data

Example

```java
OutputStream output =
socket.getOutputStream();

output.write("Hello".getBytes());
```

---

# Receiving Data

Example

```java
InputStream input =
socket.getInputStream();

byte[] data = new byte[100];

input.read(data);

System.out.println(new String(data));
```

---

# UDP Communication

UDP uses:

- DatagramSocket
- DatagramPacket

Example

```java
DatagramSocket socket =
new DatagramSocket();
```

---

# Exception Handling

Networking operations may throw exceptions.

Example

```java
try{

    Socket socket =
    new Socket("localhost", 5000);

}catch(IOException e){

    System.out.println(e.getMessage());

}
```

---

# How Java Networking Works

```text
Client
   │
   ▼
Socket
   │
   ▼
Internet / LAN
   │
   ▼
ServerSocket
   │
   ▼
Server
```

---

# Common Mistakes

## Using the Wrong Port

```java
new Socket("localhost", 6000);
```

If the server is listening on port `5000`, the connection fails.

---

## Forgetting to Close the Socket

Incorrect

```java
Socket socket =
new Socket(...);
```

Correct

```java
socket.close();
```

---

## Starting the Client Before the Server

The server must start first.

Otherwise, the client receives:

```text
Connection Refused
```

---

# Best Practices

- Always close sockets after use.
- Handle `IOException` properly.
- Use TCP for reliable communication.
- Use UDP only when speed is more important than reliability.
- Validate all received data.
- Use buffered streams for better performance.

---

# Interview Questions

## 1. What is Java Networking?

Java Networking is the process of communication between Java applications over a network using the `java.net` package.

---

## 2. What is a Socket?

A Socket is one endpoint of a communication between two computers.

---

## 3. What is a ServerSocket?

`ServerSocket` waits for incoming client connections.

---

## 4. What is the difference between TCP and UDP?

| TCP | UDP |
|------|-----|
| Reliable | Faster |
| Connection-oriented | Connectionless |
| Ordered | Unordered |
| Error Checking | Minimal Error Checking |

---

## 5. What is an IP Address?

An IP Address uniquely identifies a device on a network.

---

## 6. What is a Port?

A Port is a logical communication endpoint used by applications running on a device.

---

# Summary

- Java Networking enables communication between applications over a network.
- The `java.net` package provides classes for networking.
- `Socket` is used by clients, while `ServerSocket` is used by servers.
- TCP provides reliable communication, whereas UDP provides faster communication.
- Networking applications commonly use IP addresses, ports, sockets, and protocols.
- Proper exception handling and resource management are essential for building reliable network applications.
