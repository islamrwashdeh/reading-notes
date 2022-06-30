## Message Queues


[Socket.io Chat Example](https://canvas.instructure.com/courses/4839234/discussion_topics/14886086)    

 this guide talking how to  create a basic chat application. It requires almost no basic prior knowledge of Node.JS or Socket.IO, so it’s ideal for users of all knowledge levels.

 and  its also show the deferent btween Writing a chat application with popular web applications stacks  and Sockets   : 

 1. popular web applications stacks like LAMP (PHP) has normally been very hard. It involves polling the server for changes, keeping track of timestamps, and it’s a lot slower than it should be.    

 2.   Sockets have traditionally been the solution around which most real-time chat systems are architected, providing a bi-directional communication channel between a client and a server.   

 **as summary**  the server can push messages to clients. Whenever you write a chat message, the idea is that the server will get it and push it to all other connected clients.      cc
    
# Rooms

A room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients       



![pic](https://socket.io/images/rooms.png)


**Joining and leaving** 
You can call join to subscribe the socket to a given channel:

```
io.on("connection", (socket) => {
  socket.join("some room");
});
```

And then simply use to or in (they are the same) when broadcasting or emitting:   
```
io.to("some room").emit("some event");
```
You can emit to several rooms at the same time:
```
io.to("room1").to("room2").to("room3").emit("some event");
In that case, a union is performed: every socket that is at least in one of the rooms will get the event once (even if the socket is in two or more rooms).
```
You can also broadcast to a room from a given socket:
```
io.on("connection", (socket) => {
  socket.to("some room").emit("some event");
});
```

# Namespaces
A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing").

![pic](https://socket.io/assets/images/namespaces-088745a8a8882118740f50b6b1232588.png)   

**Each namespace has its own:**
1. event handlers
2. rooms
3. middlewares 

# Socket.io Emit Cheatsheet
Server-side  
```
io.on("connection", (socket) => {

  // basic emit
  socket.emit(/* ... */);

  // to all clients in the current namespace except the sender
  socket.broadcast.emit(/* ... */);

  // to all clients in room1 except the sender
  socket.to("room1").emit(/* ... */);

  // to all clients in room1 and/or room2 except the sender
  socket.to(["room1", "room2"]).emit(/* ... */);

  // to all clients in room1
  io.in("room1").emit(/* ... */);

  // to all clients in room1 and/or room2 except those in room3
  io.to(["room1", "room2"]).except("room3").emit(/* ... */);

  // to all clients in namespace "myNamespace"
  io.of("myNamespace").emit(/* ... */);

  // to all clients in room1 in namespace "myNamespace"
  io.of("myNamespace").to("room1").emit(/* ... */);

  // to individual socketid (private message)
  io.to(socketId).emit(/* ... */);

  // to all clients on this node (when using multiple nodes)
  io.local.emit(/* ... */);

  // to all connected clients
  io.emit(/* ... */);

  // WARNING: `socket.to(socket.id).emit()` will NOT work, as it will send to everyone in the room
  // named `socket.id` but the sender. Please use the classic `socket.emit()` instead.

  // with acknowledgement
  socket.emit("question", (answer) => {
    // ...
  });

  // without compression
  socket.compress(false).emit(/* ... */);

  // a message that might be dropped if the low-level transport is not writable
  socket.volatile.emit(/* ... */);

  // with timeout
  socket.timeout(5000).emit("my-event", (err) => {
    if (err) {
      // the other side did not acknowledge the event in the given delay
    }
  });
});

```
Client-side
```
// basic emit
socket.emit(/* ... */);

// with acknowledgement
socket.emit("question", (answer) => {
  // ...
});

// without compression
socket.compress(false).emit(/* ... */);

// a message that might be dropped if the low-level transport is not writable
socket.volatile.emit(/* ... */);

// with timeout
socket.timeout(5000).emit("my-event", (err) => {
  if (err) {
    // the other side did not acknowledge the event in the given delay
  }
});

```
# recourses

1. [Rooms](https://socket.io/docs/v4/rooms) 
2. [Namespaces](https://canvas.instructure.com/courses/4839234/discussion_topics/14886086)