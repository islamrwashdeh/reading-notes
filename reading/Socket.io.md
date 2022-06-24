# Socket.io

## what is Web Sockets ?

WebSocket is a computer communications protocol, providing full-duplex communication and low-latency channels "between the server and the browser" over a single TCP connection ,  its distinct from HTTP. Both protocols are located at layer 7 in the OSI model and depend on TCP at layer 4.    



**A simple example**
To open a websocket connection, we need to create new WebSocket using the special protocol ws in the url:

There’s also encrypted wss:// protocol. It’s like HTTPS for websockets.       

Once the socket is created, we should listen to events on it. There are totally 4 events:     

**open** – connection established,    
**message** – data received,     
**error** – websocket error,    
**close** – connection closed.


```
let socket = new WebSocket("ws://javascript.info"); 

```

And if we’d like to send something, then socket.send(data) will do that. 

```
let socket = new WebSocket("wss://javascript.info/article/websocket/demo/hello");

socket.onopen = function(e) {
  alert("[open] Connection established");
  alert("Sending to server");
  socket.send("My name is John");
};

socket.onmessage = function(event) {
  alert(`[message] Data received from server: ${event.data}`);
};

socket.onclose = function(event) {
  if (event.wasClean) {
    alert(`[close] Connection closed cleanly, code=${event.code} reason=${event.reason}`);
  } else {
    // e.g. server process killed or network down
    // event.code is usually 1006 in this case
    alert('[close] Connection died');
  }
};

socket.onerror = function(error) {
  alert(`[error] ${error.message}`);
};
```

## Socket.io Tutorial

**What Socket.IO is**  
Socket.IO is a library that enables low-latency, bidirectional and event-based communication between a client and a server.     


![pic](https://socket.io/images/bidirectional-communication2.png)     


It is built on top of the WebSocket protocol and provides additional guarantees like fallback to HTTP long-polling or automatic reconnection.  


_to install Express and Socket.IO._   


```
npm install --save express socket.io
```

 we should keep restarting the server. When we make changes, we will need a tool called nodemon. To install nodemon, open your terminal and enter the following command :

 ```
 npm install -g nodemon
 ```

 to start the server, instead of using the node app.js use, nodemon app.js.


 **example with Socket.IO:**  

Server   

 ```import { Server } from "socket.io";

const io = new Server(3000);

io.on("connection", (socket) => {
  // send a message to the client
  socket.emit("hello from server", 1, "2", { 3: Buffer.from([4]) });

  // receive a message from the client
  socket.on("hello from client", (...args) => {
    // ...
  });
});
```

Client  
```
import { io } from "socket.io-client";

const socket = io("ws://localhost:3000");

// send a message to the server
socket.emit("hello from client", 5, "6", { 7: Uint8Array.from([8]) });

// receive a message from the server
socket.on("hello from server", (...args) => {
  // ...
});
```

## Socket.io vs Web Sockets   

**Key Differences between WebSocket and socket.io**     

Both WebSocket vs Socket.io are popular choices in the market; 
 WebSocket vs Socket.io:

1. It provides the Connection over TCP, while Socket.io is a library to abstract the WebSocket connections.
2. WebSocket doesn’t have fallback options, while Socket.io supports fallback.
3. WebSocket is the technology, while Socket.io is a library for WebSockets.   



![pic](https://cdn.educba.com/academy/wp-content/uploads/2018/11/WebSockets-vs-Socket-1.jpg.webp)



## OSI Model Explained

The Open Systems Interconnection (OSI) model describes seven layers that computer systems use to communicate over a network.

![pic](https://www.imperva.com/learn/wp-content/uploads/sites/13/2020/02/OSI-7-layers.jpg)     


## TCP Handshakes Explained

Three-Way HandShake or a TCP 3-way handshake is a process which is used in a TCP/IP network to make a connection between the server and client. 

TCP Three-Way Handshake Process:   
TCP traffic begins with a three-way handshake. In this TCP handshake process, a client needs to initiate the conversation by requesting a communication session with the Server:     


![piv](https://www.guru99.com/images/1/092119_0753_TCP3WayHand1.png) 

# recourses
1. [WebSocket](https://en.wikipedia.org/wiki/WebSocket)
2. [Socket.io Tutorial](https://www.tutorialspoint.com/socket.io/)
3. [Socket.io vs Web Sockets](https://www.educba.com/websocket-vs-socket-io/)


