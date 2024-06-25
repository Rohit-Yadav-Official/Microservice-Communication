# Microservice-Communication
One of the biggest challenge when moving to microservices-based application is changing the communication mechanism. Because microservices are distributed and microservices communicate with each other by inter-service communication on network level. Each microservice has its own instance and process. Therefore, services must interact using an inter-service communication protocols like HTTP, gRPC or message brokers AMQP protocol.

Since microservices are complex structure into independently developed and deployed services, we should be careful when considering communication types and manage them into design phases.

Before we design our microservices communications, we should understand about communication styles, it is possible to classify them in two axes. The first step is to define communication protocol is synchronous or asynchronous.
