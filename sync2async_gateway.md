[http2amqp](https://github.com/aleasoluciones/http2amqp)

Publish each query message to the message bus
One or more services can reply to the query message

The client can use a sync http request, but the bacmikend can be implemented by small services that only receive messages from the messages bus an respond to the same message bus

Advantages:
 * You can access to a lot of async micro services using a uniq base url
 * Decouple between the client and the services
 * The client can use the services using sync calls (easier)
 * There can be more than one microservice for a certain kind of query at the same time (high availability, deploy decoupling)

 We are starting with this aproximation so we have no real production feedback.