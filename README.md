# Broadcast Chat Tutorial Module 10 Adpro - Tutorial 2

Tristan Agra Yudhistira (2306245112)

# 2.1. Original code of broadcast chat.

![alt text](public/2-1.png)

## How to Run the Broadcast Chat

### Prerequisites

- Make sure you have Rust and Cargo installed
- Ensure port 2000 is not being used by another process

### Running the Server

1. Open a terminal and run:

```bash
cargo run --bin server
```

The server will start listening on port 2000.

### Running the Clients

1. Open three separate terminal windows
2. In each terminal, run:

```bash
cargo run --bin client
```

### How it Works

1. When you start the server, it will print "listening on port 2000"
2. When each client connects, the server will print "New connection from {address}"
3. Each client will receive a "Hello, world!" message upon connection
4. When you type a message in any client:
   - The message will be sent to the server
   - The server will print the message along with the client's address
   - The server will broadcast the message to all connected clients
   - All clients will receive and display the message.

# 2.2 Modifying the websocket port
The broadcast chat system uses WebSocket protocol for real-time communication between the server and clients. The connection details are defined in both the server and client code. The WebSocket protocol is defined in both files using the `tokio_websockets` crate, which provides the WebSocket implementation. The protocol is specified as ws:// in the client's URI, and the server uses the same protocol through the ServerBuilder and ClientBuilder from the same crate.