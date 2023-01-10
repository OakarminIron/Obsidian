The distributed nature of cloud applications requires a messaging infrastructure that connects the components and services, ideally loosely coupled to maximize scalability. Asynchronous messaging is widely used and provides many benefits, but it also brings challenges such as ordering messages, poison message management, idempotency, and more.


[Asynchronous Request-Reply](https://learn.microsoft.com/en-us/azure/architecture/patterns/async-request-reply)

Decouple backend processing from a frontend host, where backend processing needs to be asynchronous, but the frontend still needs a clear response.

[Claim Check](https://learn.microsoft.com/en-us/azure/architecture/patterns/claim-check)

Split a large message into a claim check and a payload to avoid overwhelming a message bus.

[Choreography](https://learn.microsoft.com/en-us/azure/architecture/patterns/choreography)

Have each component of the system participate in the decision-making process about the workflow of a business transaction, instead of relying on a central point of control.

[Competing Consumers](https://learn.microsoft.com/en-us/azure/architecture/patterns/competing-consumers)

Enable multiple concurrent consumers to process messages received on the same messaging channel.

[Pipes and Filters](https://learn.microsoft.com/en-us/azure/architecture/patterns/pipes-and-filters)

Break down a task that performs complex processing into a series of separate elements that can be reused.

[Priority Queue](https://learn.microsoft.com/en-us/azure/architecture/patterns/priority-queue)

Prioritize requests sent to services so that requests with a higher priority are received and processed more quickly than those with a lower priority.

[Publisher-Subscriber](https://learn.microsoft.com/en-us/azure/architecture/patterns/publisher-subscriber)

Enable an application to announce events to multiple interested consumers asynchronously, without coupling the senders to the receivers.

[Queue-Based Load Leveling](https://learn.microsoft.com/en-us/azure/architecture/patterns/queue-based-load-leveling)

Use a queue that acts as a buffer between a task and a service that it invokes in order to smooth intermittent heavy loads.

[Scheduler Agent Supervisor](https://learn.microsoft.com/en-us/azure/architecture/patterns/scheduler-agent-supervisor)

Coordinate a set of actions across a distributed set of services and other remote resources.

[Sequential Convoy](https://learn.microsoft.com/en-us/azure/architecture/patterns/sequential-convoy)

Process a set of related messages in a defined order, without blocking processing of other groups of messages.
