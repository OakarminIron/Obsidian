A software architectural style that describes the architecture of the Web. It was derived from the following constraints:

- client-server communication
- stateless communication
- caching
- uniform interface
- layered system
- code on demand (Client Side JavaScript)

In computing, a **stateless protocol** is a communications protocol in which **no session information is retained by the receiver**, usually a server. 
Relevant session data is sent to the receiver by the client in such a way that every packet of information transferred can be understood in isolation, without context information from previous packets in the session.

Cache can be stored in a Content Delivery Network ([[🐿CDN]]).

A client cannot ordinarily tell whether it is connected directly to the end server or to an intermediary along the way. If a proxy or `load-balancer` is placed between the client and server, it won't affect their communications, and there won't be a need to update the client or server code. Intermediary servers can improve system scalability by enabling load balancing and by providing shared caches. Also, security can be added as a layer on top of the web services, separating business logic from security logic. (Layered)

https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm
![[REST.pdf]]