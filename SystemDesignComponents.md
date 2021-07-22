# SystemDesignComponents

### Message broker
- Its cloud native and serverless way of communication between inter application. Mostly in microservices.
- THey help application decouple and application written in different languages can talk with eachother becuase of messaging protocols used in this.
- Message broker has component called message queue to store and order the incoming data.
- Message queue will store the data in order of it arrives.It ensures the message is delivered only once to receiver.
- Message brokers guarantee message delivery and know which receiver has got the message.
- Prevents loss of data and system can continue working even incase of network loss or latency.
- Communication between applications can also be done using REST APIs but this will be synchronous way and sender will expect response immediately.
  And is receiver is down sender will be on wait. But in Asynchronous sender can just push the message and need not wait for receiver.
- Message broker makes systems resiliant and scalable.
- Message brokers are of two messaging patterns
  - point-to-point messaging :- One sender will send message to one receiver and consumed only one. its 1-1 relation. eg- payroll and finalcial services.
  - publish/subscribe messaging (pub/sub) : - This is broadcast style messaging. producer will publish message for a topic to message broker 
   and multiple consumer subscribed to that topic will receive that message.
 ### Message Queue (component in message middleware)
 - Stores data that one application creates for another application and when message is consumed it will be deleted.
 - These are scalable
 - message queue uses 1-1 messaging pattern if application needs one message to be sent to multiple recivers then multiple message queues can be used.
 - Message queue vs database 
    - Database are used for storage purpose but message is not storage purpose once message is read its deleted.
    - Databases are not readily scalable and interchangable.
### Apache Kafka
- Open source distributed streaming platform for event driven applications.
- this can ingest trillions of data with no lag.
- This has 3 capabilities
  - Enales applications to publish or subscribe to event streams
  - Stores data in order that they arrive with fault tolerant and durable way.
  - Process data in real time
- THis is Distributed platform -its fault tolerant, highly available cluster. it can spun across multiple servers and multiple datacenters.
- Kafka topics are partitioned and replicated for greater perofrmance.
- Kafka can be used through 4 API's
  - Producer API - record produced to topic cant be altered and deleted at configured time
  - Consumer API
  - Streaming API - Build on producer and consumer, Process multiple topics real time and can do some transformation and publish resultin stream to same or other topics
  - this will do more complex processing.
  - Connector API - Reusable producers/consumers for automate integration of data into kafka cluster. There can be source connector (for data into kafka) 
  - and sink connector(for data out of kafka)
