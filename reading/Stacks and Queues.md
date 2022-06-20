# Stacks and Queues

**1. stacks**

A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.


![pic](https://res.cloudinary.com/practicaldev/image/fetch/s--GS1k4iwx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/l8r4ic2gedi0j9obd7ix.jpg)



**_There are 3 basic operations on a stack:_**
1. **Push**: Insert a data item on the stack.
2. **Pop**: Remove an item from the top of the stack.
3. **Peek**: Read the value of an item from the top of the stack WITHOUT removing it.

**Stacks concepts:**
1. **FILO**  >>
First In Last Out  

2. **LIFO** >>
Last In First Out


## how to code 

**Constructor**


```
this.stack = [];
constructor() {
  this.stack = [];
}  
```
**Get**


```
get length() {
  return this.stack.length;
}   
```
**Push**

```
push(item) {
  return this.stack.push(item);
}    
```
**Pop**


```
pop() {
  return this.stack.pop();
}    

```
**Peek**

```
peek() {
  return this.stack[this.length - 1];
}   
```
***isEmpty**

```

isEmpty() {
  return this.length === 0;
}

```


# Queue
A queue is an abstract data structure that follows "first-in-first-out" or FIFO model.


![pic](https://res.cloudinary.com/practicaldev/image/fetch/s--40bG1tSg--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/fcxri84smzo9m1pxbxj9.png) 


**_Basic operations on a queue:_**
1. **Enque/Add/Put**: Insert a data item on the back or rear of the queue.
2. **Deque/Delete/Get**: Remove an item from the front of the queue.
3. **Peek**: Read the value of an item from the front of the queue without removing it.   

**Queues  concepts:**  

**FIFO** >>
First In First Out



**LILO** >>
Last In Last Out     


## how to code    


**Constructor**

```
this.queue = [];
constructor() {
  this.queue = [];
}  
```
**Get**  

```
get length() {
  return this.queue.length;
}  

```
**Enqueue**

```
enqueue(item) {
  return queue.unshift(item);
}   

```
**Dequeue**
```

dequeue() {
  return queue.pop();
}  

```
**Peek**

```
peek() {
  return queue[this.length - 1];
}

```
**isEmpty**


```
isEmpty() {
  return this.length === 0;
}
```


# recourses
[staks and queue](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html) 