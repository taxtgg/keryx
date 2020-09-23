# Messaging platform design

## Goals
The idea is to create design for modern asynchronous messaging system building on the best qualities of Kafka, RabbitMQ and likes.
The specific goals would be:

**Functional:**
 - Ability to store messages in distributed log
 - Provide assured write consistency (acknowledged messages are guaranteed to be persisted)
 - (Bonus) Ability to configure write consistency guarantee (acknowledged messages are guaranteed to be distributed to quorum vs. persisted)
 - Ability for an arbitrary number of consumers to consume messages
 - Ability to consume messages in order and/or with "only once" guarantee


**Operational:**
 - Clear and definitive state reporting
 - Performant scale-in and scale-out
 - Reliable and predictable recovery
 - Ability of new/returning cluster nodes to discover and join other cluster members

## Motivation
Fix Kafka pain points:
- Large number of components: Zookeeper, schema registry, manager, etc.
- Long bootstrap time after failure.
- Recovery is not consistent. Partitions may become unbalanced.
- Recovery after network partitioning often requires manual intervention
- Must be aware of which node is supervisor while performing rolling maintenance

## References
### Messaging/Streaming platforms comparisons
1. [Kafka vs. RabbitMQ: Architecture, Performance & Use Cases](https://www.upsolver.com/blog/kafka-versus-rabbitmq-architecture-performance-use-case)
1. [RabbitMQ vs. Kafka](https://medium.com/better-programming/rabbitmq-vs-kafka-1ef22a041793)

### General
3. [OpenTracing](https://opentracing.io/)
