# Event-Driven Programming in Node.js

Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision    

**EventEmitter**  
EventEmitter is an object provided by the events module. It binds a function with an event. This bound function is then used to handle the event and perform actions accordingly.   

 to access the EventEmitter class use  events module. 

 ```
 const EventEmitter = require('events').EventEmitter;
const myEventEmitter = new EventEmitter;
```

 then event listener : 

 ```
 const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

function userJoined(username){
  // Assuming we already have a function to alert all users.
  alertAllUsers('User ' + username + ' has joined the chat.');
}

// Run the userJoined function when a 'userJoined' event is triggered.
chatRoomEvents.on('userJoined', userJoined);

```

emit method that we we use to trigger the event. 

```

function login(username){
  chatRoomEvents.emit('userJoined', username);
}

```



**Asynchronous vs. synchronous**

The EventEmitter calls all listeners synchronously in the order in which they were registered. This ensures the proper sequencing of events and helps avoid race conditions and logic errors. When appropriate, listener functions can switch to an asynchronous mode of operation using the setImmediate() or process.nextTick() methods:   

```
const myEmitter = new MyEmitter();
myEmitter.on('event', (a, b) => {
  setImmediate(() => {
    console.log('this happens asynchronously');
  });
});
myEmitter.emit('event', 'a', 'b');
```


# resources
1. [Event-Driven Programming in Node.js](https://www.digitalocean.com/community/tutorials/nodejs-event-driven-programming)


2. [Event - Node.js](https://nodejs.org/api/events.html#passing-arguments-and-this-to-listeners
)