# Microservice-Communication
One of the biggest challenge when moving to microservices-based application is changing the communication mechanism. Because microservices are distributed and microservices communicate with each other by inter-service communication on network level. Each microservice has its own instance and process. Therefore, services must interact using an inter-service communication protocols like HTTP, gRPC or message brokers AMQP protocol.

Since microservices are complex structure into independently developed and deployed services, we should be careful when considering communication types and manage them into design phases.

Before we design our microservices communications, we should understand about communication styles, it is possible to classify them in two axes. The first step is to define communication protocol is synchronous or asynchronous.



# Microservices Communication Types — Synchronous and Asynchronous Communication

This document aims to provide an overview of the communication types in microservices, focusing on Synchronous and Asynchronous communication.

## Table of Contents

1. [Introduction](#introduction)
2. [Synchronous Communication](#synchronous-communication)
    - [Definition](#definition)
    - [Protocols](#protocols)
    - [Pros and Cons](#pros-and-cons)
3. [Asynchronous Communication](#asynchronous-communication)
    - [Definition](#definition-1)
    - [Protocols](#protocols-1)
    - [Implementation Types](#implementation-types)
4. [Microservices Synchronous Communication Practices](#microservices-synchronous-communication-practices)
    - [Designing HTTP-based RESTful APIs for Microservices](#designing-http-based-restful-apis-for-microservices)
5. [E-Commerce Service Communications](#e-commerce-service-communications)

## Introduction

In microservices architecture, client and services communicate with each other using various communication methods. These methods are mainly classified into two categories:

- Synchronous Communication
- Asynchronous Communication

## Synchronous Communication

### Definition

Synchronous communication involves the client sending a request and waiting for a response from the service. This means the client's code blocks its thread until the server responds.

### Protocols

- **HTTP**
- **HTTPS**
- **gRPC** (for internal microservices communication)

### Pros and Cons

Using synchronous communication has its advantages and disadvantages. It is simple to implement and understand but can lead to blocking operations, potentially reducing performance.

## Asynchronous Communication

### Definition

In asynchronous communication, the client sends a request but does not wait for a response. This means the client's thread is not blocked while waiting for the server's response.

### Protocols

- **AMQP (Advanced Message Queuing Protocol)**

### Implementation Types

Asynchronous systems can be implemented in two modes:

1. **One-to-One (Queue) Mode**: A single producer sends messages to a single receiver.
2. **One-to-Many (Topic) Mode**: Multiple receivers can process each request, with messages published to a topic and consumed by multiple subscribers.

Asynchronous communication is often used with the publish/subscribe mechanism, which is common in event-driven microservices architecture. Tools like Kafka and RabbitMQ are widely used for these operations.

## Microservices Synchronous Communication Practices

When designing and exposing APIs for microservices using HTTP protocols, there are key points to consider:

- **RESTful APIs**: Commonly used for client-facing APIs, allowing explicit visibility of payloads.
- **gRPC**: Used for internal communication within the microservices cluster due to its speed and efficiency.

### Designing HTTP-based RESTful APIs for Microservices

In synchronous communication, when making request/response communication, we should use REST when designing our APIs. It's also called RESTful APIs. REST approach follows the HTTP protocol and implements HTTP verbs like GET, POST, and PUT.

REST is the most commonly used architectural communication approach when creating APIs for our microservices. For implementing REST services, we have several options, such as using Java with the Spring Boot framework or using C# with ASP.NET Core Web API services.

We should focus on how to design our APIs for microservices.

Good API design is very important in a microservices architecture because communication with data transfers happens through messages or API calls.

Designed APIs should be efficient and not involve chatty communications. In microservices architecture, services are designed to work independently, so APIs must be well-defined, documented, and versioned to ensure updates don’t break other services.

There are two types of APIs when designing sync communication in microservices architecture:

1. **Public APIs**: APIs called from the client applications.
2. **Backend APIs**: Used for inter-service communication between backend microservices.

For Public APIs, they should align with client requests. Clients can be web browsers or mobile application requests. This means the public API should use RESTful APIs over the HTTP protocol, using JSON payloads for request-response. This makes it easy to check payloads and establish agreements with clients.

For backend APIs, network performance needs to be considered over easily readable JSON payloads. Inter-service communication can result in a lot of network traffic. Therefore, serialization speed and payload size become more important. For backend APIs, protocols supporting binary serialization should be implemented. Alternatives like gRPC or other binary protocols are mandatory.

Let’s compare the REST and gRPC protocols:

- **REST**: Uses the HTTP protocol, and request-response is structured using JSON objects. API interfaces are designed based on HTTP verbs like GET, PUT, POST, and DELETE.
- **gRPC**: Essentially a Remote Procedure Call, which invokes external system methods over binary network protocols. Payloads are not readable but are faster than REST APIs.

### RESTful API Design over HTTP using JSON

### gRPC Binary Protocol API Design

## E-Commerce Service Communications

In an e-commerce architecture, synchronous communication lines are often represented by HTTP-based RESTful APIs returning JSON objects. For internal microservices communication, gRPC is preferred due to its faster response times, despite the trade-off of not seeing payloads explicitly.

### Summary

Microservice-based applications often use a combination of synchronous and asynchronous communication styles. In our e-commerce architecture, both types are utilized to optimize performance and efficiency.

When preferring synchronous communication, the options are:

- **HTTP protocols and REST approaches**
- **gRPC binary format communications**

Further elaboration on these approaches will be provided in upcoming sections.
