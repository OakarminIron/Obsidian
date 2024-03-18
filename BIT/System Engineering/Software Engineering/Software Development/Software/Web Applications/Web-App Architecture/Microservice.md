In software engineering, a microservice architecture is a variant of the service-oriented architecture structural style. 
It is an architectural pattern that arranges an application as a collection of loosely coupled, fine-grained services, communicating through lightweight protocols.
One of its goals is that teams can develop and deploy their services independently of others.
This is achieved by the reduction of several dependencies in the code base, allowing for developers to evolve their services with limited restrictions from users, and for additional complexity to be hidden from users.
As a consequence, organizations are able to develop software with fast growth and size, as well as use off-the-shelf services more easily.
Communication requirements are reduced.
These benefits come at a cost to maintaining the decoupling. 
Interfaces need to be designed carefully and treated as a public API. 
One technique that is used is having multiple interfaces on the same service, or multiple versions of the same service, so as to not disrupt existing users of the code.


