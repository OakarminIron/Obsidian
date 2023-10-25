The SOLID Design Principles are:

- Single-responsibility principle
- Open-Closed principle
- Liskov substitution principle
- Interface segregation principle
- Dependency inversion principle


### Single Responsibility Principle (SRP)

The [[Single Responsibility Principle ]]states that there should never be more than one reason for a class to change. In other words, every class should have only one responsibility.
If there are two reasons to change a class then it has more than one responsibility and should be split. Having multiple reasons to change means that the module has high coupling.
The more responsibilities your class has, the more often you'll need to change it. Since they won't be independent of each other, change to one responsibility may affect the other.

### Open-Closed Principle (OCP)

The [[Open-Closed Principle]] states that a software entity (class, module, function) should be open for extension but closed for modification. We should write our modules so that they can be extended, without requiring them to be modified.
Open for extension: A class should be extensible, i.e., we should be able to make a class behave in different ways as new requirements come.
Closed for modification: The extension should happen without any modification to the class.
This can be achieved through abstraction, i.e., by creating interfaces. Interfaces should not change based on new requirements. Interfaces are extensible and new requirements can be taken care of by implementing classes

### Liskov Substitution Principle (LSP)

The [[Liskov Substitution Principle]] states that sub classes should be substitute for their base classes. Derived classes should be substitute for their base classes wherever the derived class is used.
A client using a base class should continue to function properly even if a derived class is passed to it. This means that we should be able to pass an object of class B to any function that expects an object of class A given that class B is a subclass of class A.

### Dependency Inversion Principle (DIP)

The [[Dependency Inversion Principle]] states that "Depend upon abstractions, not concretions". This means that classes should depend on abstractions (interfaces) of other classes instead of the concrete implementations.
The dependencies are inverted as the concrete classes depend upon abstractions instead of being dependent upon by other classes

### Interface Segregation Principle (ISP)

The [[Interface Segregation Principle]] states that many client-specific interfaces are better than one general-purpose interface.
Clients should not be forced to depend upon interfaces that they do not use. It is better to have smaller interfaces than fewer, fatter interfaces. An interface should be dependent more on the code that calls it rather than the code that implements it.
Therefore, a class should be implementing different interfaces created based on the different types of clients. Each of these interfaces might have common methods as well.