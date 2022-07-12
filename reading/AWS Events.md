# AWS Events

## AWS SQS vs SNS

SQS is mainly used to decouple applications. SNS distributes several copies of message to several subscribers.

**SNS (Simple Notification Service)**   

Amazon SNS is a fast, flexible, fully managed push notification service that lets you send individual messages or to bulk messages to large numbers of recipients. Amazon SNS makes it simple and cost effective to send push notifications to mobile device users, email recipients or even send messages to other distributed services.   

![pic](https://miro.medium.com/max/628/1*mdUPKzrfJFuXa4d43KhKUQ.png)



**SQS (Simple Queue Service)**
SQS is distributed queuing system. Messages are not pushed to receivers. Receivers have to poll SQS to receive messages. Messages can be stored in SQS for short duration of time (max 14 days).  
![pic](https://miro.medium.com/max/875/1*7eL3udb6Cto4I9Ly1sN8oA.jpeg)


**What are some use cases for both SNS and SQS?**
Use Cases   
Choose SNS if:    

You would like to be able to publish and consume batches of messages.    
You would like to allow same message to be processed in multiple ways.     
Multiple subscribers are needed.      

Choose SQS if:     

You need a simple queue with no particular additional requirements.    
Decoupling two applications and allowing parallel asynchronous processing.     
Only one subscriber is needed.     

## AWS SNS and SQS
The Amazon Simple Queue Service (SQS) and the Amazon Simple Notification Service (SNS) are important “glue” components for scalable, cloud-based applications (see the Reference Architectures in the AWS Architecture Center to learn more about how to put them to use in your own applications).

One common design pattern is called “fanout.” In this pattern, a message published to an SNS topic is distributed to a number of SQS queues in parallel. By using this pattern, you can build applications that take advantage parallel, asynchronous processing. For example, you could publish a message to a topic every time a new image is uploaded. Independent processes, each reading from a separate SQS queue, could generate thumbnails, perform image recognition, and store metadata about the image:



![p](https://media.amazonwebservices.com/blog/sns_sqs_image_proc_2.png)    



# res
1.[AWS SQS vs SNS](https://medium.com/awesome-cloud/aws-difference-between-sqs-and-sns-61a397bf76c5)   
2. [AWS SNS and SQS](https://www.youtube.com/watch?v=mXk0MNjlO7A)       
3. [AWS SNS and SQS](https://aws.amazon.com/blogs/aws/queues-and-notifications-now-best-friends/)       
4. [SQS and SNS Basics](https://www.youtube.com/watch?v=UesxWuZMZqI)
5. 
