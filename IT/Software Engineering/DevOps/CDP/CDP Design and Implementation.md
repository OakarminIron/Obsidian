Good design encompasses consistency and coherence in component design and deployment, maintainability to simplify administration and development, and reusability to allow components and subsystems to be used in other applications and scenarios. Decisions made during the design and implementation phase significantly impact the quality and total cost of ownership of cloud-hosted applications and services.

[Ambassador](https://learn.microsoft.com/en-us/azure/architecture/patterns/ambassador)

Create helper services that send network requests on behalf of a consumer service or application.

[Anti-Corruption Layer](https://learn.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer)

Implement a façade or adapter layer between a modern application and a legacy system.

[Backends for Frontends](https://learn.microsoft.com/en-us/azure/architecture/patterns/backends-for-frontends)

Create separate backend services to be consumed by specific frontend applications or interfaces.

[CQRS](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs)

Segregate operations that read data from operations that update data by using separate interfaces.

[Compute Resource Consolidation](https://learn.microsoft.com/en-us/azure/architecture/patterns/compute-resource-consolidation)

Consolidate multiple tasks or operations into a single computational unit

[External Configuration Store](https://learn.microsoft.com/en-us/azure/architecture/patterns/external-configuration-store)

Move configuration information out of the application deployment package to a centralized location.

[Gateway Aggregation](https://learn.microsoft.com/en-us/azure/architecture/patterns/gateway-aggregation)

Use a gateway to aggregate multiple individual requests into a single request.

[Gateway Offloading](https://learn.microsoft.com/en-us/azure/architecture/patterns/gateway-offloading)

Offload shared or specialized service functionality to a gateway proxy.

[Gateway Routing](https://learn.microsoft.com/en-us/azure/architecture/patterns/gateway-routing)

Route requests to multiple services using a single endpoint.

[Leader Election](https://learn.microsoft.com/en-us/azure/architecture/patterns/leader-election)

Coordinate the actions performed by a collection of collaborating task instances in a distributed application by electing one instance as the leader that assumes responsibility for managing the other instances.

[Pipes and Filters](https://learn.microsoft.com/en-us/azure/architecture/patterns/pipes-and-filters)

Break down a task that performs complex processing into a series of separate elements that can be reused.

[Sidecar](https://learn.microsoft.com/en-us/azure/architecture/patterns/sidecar)

Deploy components of an application into a separate process or container to provide isolation and encapsulation.

[Static Content Hosting](https://learn.microsoft.com/en-us/azure/architecture/patterns/static-content-hosting)

Deploy static content to a cloud-based storage service that can deliver them directly to the client.

[Strangler Fig](https://learn.microsoft.com/en-us/azure/architecture/patterns/strangler-fig)

Incrementally migrate a legacy system by gradually replacing specific pieces of functionality with new applications and services.