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

## E-Commerce Service Communications

In an e-commerce architecture, synchronous communication lines are often represented by HTTP-based RESTful APIs returning JSON objects. For internal microservices communication, gRPC is preferred due to its faster response times, despite the trade-off of not seeing payloads explicitly.

### Summary

Microservice-based applications often use a combination of synchronous and asynchronous communication styles. In our e-commerce architecture, both types are utilized to optimize performance and efficiency.

When preferring synchronous communication, the options are:

- **HTTP protocols and REST approaches**
- **gRPC binary format communications**

Further elaboration on these approaches will be provided in upcoming sections.
