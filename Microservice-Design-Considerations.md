### Microservice Design Considerations:

A Microservice is a a simple, single-purpose service that is part of a business application.
Communication between Microservices:

#### Types of communication.
There are two types of communcation, in general.
##### Request/Response: 
In this case, the caller makes a request and waits for a response. The caller may choose to block the thread while waitign or makes use of async io and Future Callback serviing many requests together.
##### Events/Logs/Notifications: The caller sends and forgets. It does not wait for a response beyond an acknowledgement of receipt from the caller.

#### Modes of Communication:
There are two modes of communications, in general.
##### Synchronous Communication:  
In this mode of communication, the sender generally sends a request and waits for a response. As described above, the sender may choose to bolck for the response or use async IO and callback method servicing multiple requests at the same time.
In case of a Request/response type of communctation, synchronous communication method is a natural fit. Below are a few widely used methods of synchronous communication.
REST, gRPC, Thrift are some of the very widely used methods for the synchronous communication. TODO - Elaborate on each.
##### Asynchronous Communication:  
In this mode, the sender sends the information/message and does not wait beyond receiving and acknowledgement of recepit. This method is a natural fit Logs, Events communications from the send to the receiver.
ActiveMQ, RabbitMQ and Kafka are some of the widely used software frameworks for implementing asynchronous communication.  

#### Service Discovery:
Each of the microservices generally run in a multi-instance cluster for both high availablity and for scalability.  
So, how does a microservice find teh endpoint of another microservice to communicate?
There are two general methods:
##### Configuration Service: 

##### Logical Binding and Bootstrap servcie:
