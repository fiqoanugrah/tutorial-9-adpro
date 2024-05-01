Tutorial 9 Adpro

## **Hi! :wave:, I'm Muhammad Fiqo Anugrah and this is my repo for Tutorial 9 Adpro C**


> REFLECTION

1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?:
In unary RPC, the client sends a single, small data request to the server, receiving a single response.
In server streaming RPC, the server sends multiple pieces of large data continuously over a single stream to the client.
Bidirectional streaming RPC resembles server streaming but includes the client also sending data continuously in a similar manner.
Unary RPC is ideal for scenarios like authentication or submitting forms.
Server streaming RPC is well-suited for continuously transmitting large data sets such as stock prices or live news updates.
Bidirectional streaming RPC excels in use cases like collaborative editing, real-time gaming, or interactive chatbots.

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?:
gRPC necessitates continuous validation for authentication/authorization with each data segment sent, as opposed to REST which requires validation only once per request. Additionally, each data piece in gRPC must be separately encrypted to ensure privacy. This makes gRPC more demanding in terms of repeated authorization/authentication/encryption processes within a single data stream request, while REST requires validation only once since the connection closes after the response.

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?:
Developing chat applications using Rust gRPC might face challenges like improper message synchronization between senders and receivers, potential deadlocks from mutual waiting, buffer overflow risks if messages aren't consumed promptly, the necessity for error recovery mechanisms for unstable connections, and special attention to concurrency and security issues such as message encryption and user authentication.

4. What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?:
Utilizing tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services offers flexibility and easy integration within the Tokio ecosystem but brings added complexity and a slight performance overhead, especially for developers unfamiliar with asynchronous programming and Tokio concepts.

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?:
Proper structuring in Rust gRPC facilitates improved maintainability and extensibility by using protocol .proto files integrated with an interface allowing the implementation of Rust classes, easing feature additions and overall code modifications.

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?:
To manage more complex payment processing logic in MyPaymentService, additional steps might include meticulous validation and error handling, user authentication and authorization, integration with external payment gateways, transaction status management, scalability, business rule enforcement, event notifications, transaction reconciliation, and thorough testing.

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?:
The use of gRPC eliminates concerns about accessing modules via HTTP methods by automatically managing method calls through agreed definitions in the .proto file, simplifying connectivity and operations across different technologies, platforms, and distributed systems.

8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?:
HTTP/2 allows multiple requests and responses over a single connection, offering efficiencies for large data transmissions. Compared to HTTP/1.1, it may introduce higher performance and memory overhead for small data transmissions. However, for REST APIs, HTTP/2 supports features like multiplexing, header compression, server push, and flow prioritization, providing wider infrastructure support, though WebSocket may be better for real-time communications.

9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?:
REST API’s request-response model is primarily one-way, suitable for static data fetching, whereas gRPC’s bidirectional streaming capability allows for direct, real-time communication, making it superior for scenarios requiring prompt interaction and updates.

10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?:
gRPC’s schema-based approach using Protocol Buffers offers advantages in efficiency, reliability, and security in data exchanges between services. This contrasts with the more flexible but less efficient and loosely structured nature of JSON used in REST APIs. While gRPC might be slightly more complex to learn, it provides better performance and ensures data consistency, making it preferable for applications requiring high speed and security.
