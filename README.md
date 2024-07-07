# Networking-with-TCP-and-UDP-Socket-Communication

## TCP Server with Multithreading

This repository contains Java code for a simple TCP server that handles multiple client connections concurrently using multithreading.

### 1. **Client.java**: 
   - Connects to the server at `127.0.0.1` (localhost) on port `2020`.
   - Uses `BufferedReader` and `PrintWriter` for reading from and writing to the socket.
   - Sends a message to the server and receives a response.
   - Closes the socket after communication.

### 2. **ServerMain.java**: 
   - Starts a server on port `2020` using `ServerSocket`.
   - Accepts incoming client connections indefinitely in a loop.
   - For each client connection, creates a new `ServerThread` instance (which implements `Runnable`) and starts a new thread to handle client communication.
   - Tracks the number of clients connected.

### 3. **ServerThread.java**: 
   - Implements `Runnable` to handle communication with a single client.
   - Receives client messages, processes them (e.g., greeting the client with a welcome message and asking for their name), and sends responses.
   - Closes the connection after communication with the client is complete.

#### Notes:
- This implementation demonstrates a basic TCP server using multithreading to handle multiple clients concurrently.
- Error handling is minimal for demonstration purposes; in a production environment, robust error handling and logging would be essential.
- Ensure proper resource management and closing of sockets to avoid resource leaks.
