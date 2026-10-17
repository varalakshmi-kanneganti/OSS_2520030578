# Inter-Process Chat Application Using IPC

A Linux-based, terminal chat application built using Python to demonstrate **Inter-Process Communication (IPC)** concepts in Operating Systems.

## 📌 Overview

The **Inter-Process Chat Application Using IPC** enables separate processes running on the same Linux machine to exchange messages in real time using operating-system-provided IPC mechanisms.

The project implements two communication approaches:

- **Named Pipes (FIFO):** Enables communication between two users.
- **Unix Domain Sockets:** Supports multi-user group chat through a central server that broadcasts messages to connected clients.

Multithreading allows users to send and receive messages simultaneously, while locks provide synchronization when accessing shared data.

## 🎯 Objectives

- Implement a two-user chat application using named pipes (FIFO).
- Develop a multi-user group chat using Unix domain sockets.
- Enable simultaneous message sending and receiving using threads.
- Use locks to protect shared data and avoid race conditions.
- Display user join and leave notifications.
- Perform clean shutdown and remove IPC files.
- Demonstrate core Operating Systems concepts through a practical application.

## ✨ Features

- Real-time terminal-based messaging.
- Two-user communication using named pipes.
- Multi-user group chat using a server-client architecture.
- Concurrent sending and receiving with multithreading.
- Automatic message broadcasting to other connected clients.
- User join and leave notifications.
- Synchronization using thread locks.
- Cleanup of named pipes and socket files during shutdown.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python 3 | Application development |
| Linux / Ubuntu | Execution environment |
| `os` | Named pipe creation and file cleanup |
| `socket` | Unix domain socket communication |
| `threading` | Concurrent sending and receiving |
| `Lock` | Synchronization of shared data |
| Git & GitHub | Version control and project hosting |
| VS Code / Nano | Code development |

## 🧠 Operating Systems Concepts

### 1. Inter-Process Communication (IPC)
Allows independent processes to exchange messages through operating-system mechanisms.

### 2. Named Pipes (FIFO)
Used as communication channels for the two-user chat implementation through `os.mkfifo()`.

### 3. Unix Domain Sockets
Used for local client-server communication through socket creation, `bind()`, `listen()`, `accept()`, and `connect()`.

### 4. Multithreading
Allows message sending and receiving to happen concurrently without blocking the entire chat client.

### 5. Synchronization
Thread locks protect shared data, such as the server's connected-client list.

### 6. File Descriptors and Blocking I/O
Demonstrates how processes interact with operating-system resources and perform input/output operations.

## ⚙️ System Architecture

### Version 1: Two-User Chat Using Named Pipes

Two separate user processes communicate through named FIFO pipes.

`User 1 ↔ Named Pipes (FIFO) ↔ User 2`

### Version 2: Multi-User Group Chat Using Unix Domain Sockets

1. The server creates a Unix domain socket and waits for connections.
2. Clients connect to the server and provide their usernames.
3. The server announces when a user joins.
4. Clients send messages to the server.
5. The server broadcasts messages to other connected clients.
6. When a client leaves, the server handles disconnection and cleanup.

`Clients → Unix Domain Socket Server → Other Connected Clients`

## 🚀 Getting Started

### Prerequisites

- Linux or Ubuntu
- Python 3
- Terminal access

### 1. Clone the Repository

```bash
git clone https://github.com/muvvalohitha007-cmyk/TRIDE_OSSP.git
```

### 2. Navigate to the Project Directory

```bash
cd TRIDE_OSSP
```

### 3. Run the Application

The exact commands depend on the filenames in the repository.

For the **named-pipe version**, run the two user programs in separate terminals.

For the **Unix domain socket version**, start the server first, then launch the client program in separate terminals.

> Replace the example commands below with the actual filenames in your repository.

```bash
# Terminal 1: Start the server
python3 server.py

# Terminal 2: Start a client
python3 client.py
```

For the FIFO version, follow the execution instructions for the named-pipe scripts.

## 📂 Project Structure

The following is a suggested structure. Update it to match the actual files in the repository.

```text
TRIDE_OSSP/
├── server.py          # Unix domain socket server
├── client.py          # Chat client
├── fifo_chat.py       # Two-user named-pipe chat
└── README.md         
