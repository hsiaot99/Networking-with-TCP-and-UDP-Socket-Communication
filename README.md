# Networking-with-TCP-and-UDP-Socket-Communication

## TCP Server with Multithreading

This repository contains Java code for a simple TCP server that handles multiple client connections concurrently using multithreading.

### 1. `Client.java`
   - Connects to the server at `127.0.0.1` (localhost) on port `2020`.
   - Uses `BufferedReader` and `PrintWriter` for reading from and writing to the socket.
   - Sends a message to the server and receives a response.
   - Closes the socket after communication.

### 2. `ServerMain.java` 
   - Starts a server on port `2020` using `ServerSocket`.
   - Accepts incoming client connections indefinitely in a loop.
   - For each client connection, creates a new `ServerThread` instance (which implements `Runnable`) and starts a new thread to handle client communication.
   - Tracks the number of clients connected.

### 3. `ServerThread.java`
   - Implements `Runnable` to handle communication with a single client.
   - Receives client messages, processes them (e.g., greeting the client with a welcome message and asking for their name), and sends responses.
   - Closes the connection after communication with the client is complete.

#### Notes:
- This implementation demonstrates a basic TCP server using multithreading to handle multiple clients concurrently.
- Error handling is minimal for demonstration purposes; in a production environment, robust error handling and logging would be essential.
- Ensure proper resource management and closing of sockets to avoid resource leaks.

## UDP Communication

This repository contains a simple Java implementation demonstrating communication between a sender and a receiver using UDP (User Datagram Protocol).
UDP is a connectionless protocol that allows for fast transmission of data but does not guarantee delivery or order of packets.

### 1. `Receiver.java`

This class sets up a UDP receiver that listens on port 2020. It receives messages from any sender and responds with an acknowledgment message.

### 2. `Sender.java`

This class sets up a UDP sender that sends messages to the receiver's IP address (`127.0.0.1` for localhost) on port 2020. It then waits to receive an acknowledgment message from the receiver.

### Usage

1. **Receiver**
   - The `Receiver` class listens on UDP port 2020 for incoming messages.
   - When it receives a message from any sender, it prints the message, sends back an acknowledgment ("Ok."), and prints the acknowledgment.

2. **Sender**
   - The `Sender` class allows you to input messages from the keyboard.
   - It sends each message as a UDP packet to the `Receiver` listening on `127.0.0.1:2020`.
   - After sending a message, it waits to receive an acknowledgment from the receiver and prints the acknowledgment message.

## UDP Chat Application

This repository contains a simple UDP-based chat application implemented in Java, consisting of a server (`ChatServer`) and a client (`ChatClient`).
The communication between clients and the server is facilitated using datagrams over UDP (User Datagram Protocol).

### 1. `ChatServer.java`

The server component manages client connections and facilitates message broadcasting to all connected clients. It operates on a specific UDP port (`2020` by default).

#### Features:
- Accepts incoming messages from clients.
- Broadcasts received messages to all connected clients.
- Tracks unique client addresses and ports.

### 2. `ChatClient.java`

The client component provides a graphical user interface (GUI) for users to interact with the chat server. Multiple clients can connect to the server simultaneously.

#### Features:
- GUI built using Swing (`ClientWindow.java`) for message display and input.
- Sends messages typed by the user to the server.
- Receives and displays messages from other clients via the server.

### 3. `ClientWindow.java`

This class handles the GUI components for the client-side application. It includes text panes for displaying chat messages and taking user input.

#### Features:
- Allows users to enter the server address before connecting.
- Provides a chat room display for incoming messages.
- Sends typed messages to the server for distribution.

Ref. https://www.udemy.com/course/programming-network-applications-in-java/?couponCode=KEEPLEARNING
