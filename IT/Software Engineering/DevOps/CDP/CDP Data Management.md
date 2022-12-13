Data management is the key element of cloud applications, and it influences most of the quality attributes. Data is typically hosted in different locations and across multiple servers for performance, scalability or availability. This can present various challenges. For example, data consistency must be maintained, and data will typically need to be synchronized across different locations.

[Cache-Aside](https://learn.microsoft.com/en-us/azure/architecture/patterns/cache-aside)

Load data on demand into a cache from a data store

[CQRS](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs)

Segregate operations that read data from operations that update data by using separate interfaces.

[Event Sourcing](https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing)

Use an append-only store to record the full series of events that describe actions taken on data in a domain.

[Index Table](https://learn.microsoft.com/en-us/azure/architecture/patterns/index-table)

Create indexes over the fields in data stores that are frequently referenced by queries.

[Materialized View](https://learn.microsoft.com/en-us/azure/architecture/patterns/materialized-view)

Generate prepopulated views over the data in one or more data stores when the data isn't ideally formatted for required query operations.

[Sharding](https://learn.microsoft.com/en-us/azure/architecture/patterns/sharding)

Divide a data store into a set of horizontal partitions or shards.

[Static Content Hosting](https://learn.microsoft.com/en-us/azure/architecture/patterns/static-content-hosting)

Deploy static content to a cloud-based storage service that can deliver them directly to the client.

[Valet Key](https://learn.microsoft.com/en-us/azure/architecture/patterns/valet-key)

Use a token or key that provides clients with restricted direct access to a specific resource or service.