## Single/Multi(updated)-Client Server Project

This project demonstrates a multi-client server model in Java. It includes implementations for handling multiple client connections using both basic threading and a thread pool for optimized performance.

### Features
- Supports multiple concurrent client connections.
- Implements both a basic multi-threaded server and a thread pool-based server.
- Implements a single-threaded server for basic use cases.
- Uses sockets for client-server communication.
- Clients send a message to the server and receive a response.

### Project Structure
## multi/
- Client.java // Basic client implementation
- Server.java // Multi-threaded server handling each client in a separate thread threadpool/
## threadpool/
- Server.java // Optimized server using a thread pool for handling multiple clients efficiently single/
## single/
- Client.java // Basic single-threaded client
- Server.java // Basic single-threaded server


### How It Works

#### Multi-Threaded Server (`multi/server.java`)
- Listens on port `8010`.
- Accepts client connections and spawns a new thread for each client.
- Sends a greeting message to the connected client.

#### Thread Pool Server (`threadpool/server.java`)
- Uses a fixed-size thread pool (default: 10 threads) to handle client requests efficiently.
- Reduces thread creation overhead by reusing existing threads.

#### Single-Threaded Server (`single/Server.java`)
- Listens on port `8090`.
- Accepts one client connection at a time.
- Sends a greeting message to the connected client.

#### Client (`multi/client.java`)
- Connects to the server at `localhost:8010`.
- Sends a message to the server.
- Receives and prints the server's response.
- Spawns up to 100 concurrent client threads.

#### Single-Threaded Client (`single/Client.java`)
- Connects to the single-threaded server at `localhost:8090`.
- Sends a message to the server.
- Receives and prints the server's response.
- Closes the connection after communication.

### Running the Project
#### 1. Start the Server
- Start from the root directory 

##### For the multi-threaded server:
```sh
javac multi/Server.java
cd multi
java Server
```
##### For the threadpool server:
```sh
javac threadpool/Server.java
cd threadpool
java Server
```
##### For the single-threaded server:
```sh
javac single/Server.java
cd single
java Server
```
#### 2. Run the Client
##### For the multi-threaded client:
```sh
javac multi/Client.java
cd multi
java Client
```
##### For the single-threaded client:
```sh
javac single/Client.java
cd single
java Client
```
### Notes

- Ensure that the server is running before starting the client.
- Modify port values in the code if needed.
- Adjust the thread pool size in threadpool/server.java based on expected load.
- The single-threaded server processes one client at a time, making it suitable for simple use cases.

### License
- This project is open-source. Feel free to modify and use it for learning purposes.
