[[Server Side Event SSE]] vs [[Web-Socket🌐🔌]]
As communication protocols, SSE and Web-Sockets define the rules and conventions for establishing and maintaining a connection between a client and a server, allowing real-time communication and data transfer.

As communication mechanisms, SSE and Web-Sockets provide specific ways for applications to exchange data and events. They offer different communication patterns and capabilities compared to traditional request-response mechanisms like HTTP.

| WebSockets                                                                            | Server-Sent Events                                         |
|---------------------------------------------------------------------------------------|------------------------------------------------------------|
| Two-way message transmission                                                          | One-way message transmission (server to client)            |
| Supports binary and UTF-8 data transmission                                           | Supports UTF-8 data transmission only                      |
| Supports a large number of connections per browser                                    | Supports a limited number of connections per browser (six) |
| Can't be polyfilled using JavaScript; you need to fall back to basic HTTP messages    | Can be polyfilled using JavaScript                         |
| Some enterprise firewalls with packet inspection have trouble dealing with WebSockets | No blocking by enterprise firewalls                        |


