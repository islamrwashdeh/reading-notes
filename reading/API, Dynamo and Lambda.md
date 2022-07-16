 # AWS: API, Dynamo and Lambda 

 **What is Amazon API Gateway?**

 Amazon API Gateway is a managed service that allows developers to define the HTTP endpoints of a REST API or a WebSocket API and connect those endpoints with the corresponding backend business logic. It also handles authentication, access control, monitoring, and tracing of API requests.    

 **How does API Gateway integrate with other AWS services?**

Many AWS services support integration with Amazon API Gateway, including:    

AWS Lambda: run Lambda functions to generate HTTP API responses.   
AWS SNS: publish SNS notifications when an HTTP API endpoint is accessed.   
Amazon Cognito: provide authentication and authorization for your HTTP APIs.   
API Gateway supports direct integrations that can be configured in the API Gateway user interface (or via the API Gateway’s own API) for the following actions:    


Invoking an AWS Lambda function.   
Invoking another HTTP endpoint, with or without VPC Link.   
Making an HTTP call against the API of any AWS service that provides an HTTP API.   
Returning a mock response generated within API Gateway without calling out to other services.   

# AWS API Gateway 
**What are the some benefits of using Amazon API Gateway?**

1. Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

2. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. 

3. API Gateway supports containerized and serverless workloads, as well as web applications.

# AWS DynamoDB Guide
How it works   :

Amazon DynamoDB is a fully managed, serverless, key-value NoSQL database designed to run high-performance applications at any scale. DynamoDB offers built-in security, continuous backups, automated multi-Region replication, in-memory caching, and data export tools.

![pic](https://d1.awsstatic.com/product-page-diagram_Amazon-DynamoDBa.1f8742c44147f1aed11719df4a14ccdb0b13d9a3.png)

# Dynamoose
**What is Dynamoose?**
Dynamoose is a modeling tool for Amazon's DynamoDB. Dynamoose is heavily inspired by Mongoose, which means if you are coming from Mongoose the syntax will be very familar.

# res
1. [AWS API Gateway Overview](https://www.serverless.com/guides/amazon-api-gateway)      

2. [AWS API Gateway](https://aws.amazon.com/api-gateway/)   

3. [AWS DynamoDB Guide](https://aws.amazon.com/dynamodb/)

4. [Dynamoose](https://dynamoosejs.com/getting_started/Introduction/)