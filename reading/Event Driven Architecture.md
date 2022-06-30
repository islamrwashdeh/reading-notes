

# Event Driven Architecture

‘events’ are actions that can be user-generated – such as mouse clicks and keystrokes – or system-generated, such as a program loading. The events themselves can be anything from accepting or rejecting a loan application (referred to as a high-level event), to ‘a user pressed a key’ (a low-level event). An event-driven application is designed to detect events as they occur, and then deal with them using some event-handling procedure.      

![pic](https://hazelcast.com/wp-content/uploads/2021/12/20_EventDrivenArchitecture.png)   

## How does event-driven architecture work?   

Event-driven architecture is made up of event producers and event consumers. An event producer detects or senses an event and represents the event as a message. It does not know the consumer of the event, or the outcome of an event.      

After an event has been detected, it is transmitted from the event producer to the event consumers through event channels, where an event processing platform processes the event asynchronously.    
 Event consumers need to be informed when an event has occurred. They might process the event or may only be impacted by it.     

The event processing platform will execute the correct response to an event and send the activity downstream to the right consumers. This downstream activity is where the outcome of an event is seen.     

Apache Kafka is a distributed data streaming platform that is a popular event processing choice. It can handle publishing, subscribing to, storing, and processing event streams in real time. Apache Kafka supports a range of use cases where high throughput and scalability are vital, and by minimizing the need for point-to-point integrations for data sharing in certain applications, it can reduce latency to milliseconds.     

There are other middleware event managers available that can serve as an event processing platform.        

![pic](https://d1.awsstatic.com/product-marketing/EventBridge/1-SEO-Diagram_Event-Driven-Architecture_Diagram.b3fbc18f8cd65e3af3ccb4845dce735b0b9e2c54.png) 

## Advantages of using the event-driven architecture pattern
 

**Scale and fail independently** 
By decoupling your services, they are only aware of the event router, not each other. This means that your services are interoperable, but if one service has a failure, the rest will keep running. The event router acts as an elastic buffer that will accommodate surges in workloads.      

**Develop with agility**    

You no longer     need to write custom code to poll, filter, and route events; the event router will automatically filter and push events to consumers. The router also removes the need for heavy coordination between producer and consumer services, speeding up your development process.       

**Audit with ease**    

An event router acts as a centralized location to audit your application and define policies. These policies can restrict who can publish and subscribe to a router and control which users and resources have permission to access your data. You can also encrypt your events both in transit and at rest.     

**Cut costs** 
Event-driven architectures are push-based, so everything happens on-demand as the event presents itself in the router. This way, you’re not paying for continuous polling to check for an event. This means less network bandwidth consumption, less CPU utilization, less idle fleet capacity, and less SSL/TLS handshakes.   




