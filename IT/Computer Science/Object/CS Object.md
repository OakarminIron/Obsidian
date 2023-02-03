In computer science, an object can be a variable, a data structure, a function, or a method. As regions of memory, they contain value and are referenced by identifiers.

An important concept for objects is the design pattern. A design pattern provides a reusable template to address a common problem. The following object descriptions are examples of some of the most common design patterns for objects.

- Function object: an object with a single method (in C++, this method would be the function operator, "operator()") that acts much like a function (like a C/C++ pointer to a function).
- Immutable object: an object set up with a fixed state at creation time and which does not change afterward.
- First-class object: an object that can be used without restriction.
- Container object: an object that can contain other objects.
- Factory object: an object whose purpose is to create other objects.
- Metaobject: an object from which other objects can be created (compare with a class, which is not necessarily an object).
- Prototype object: a specialized metaobject from which other objects can be created by copying
- God object: an object that knows or does too much (it is an example of an anti-pattern).
- Singleton object: an object that is the only instance of its class during the lifetime of the program.
- Filter object: an object that receives a stream of data as its input and transforms it into the object's output. Often the input and output streams are streams of characters, but these also may be streams of arbitrary objects. These are generally used in wrappers since they conceal the existing implementation with the abstraction required at the developer side.


| OOP Objects | Semantic Web Objects |
| ----------- | ----------- |
| Classes are regarded as types for instances. | Classes are regarded as sets of individuals. |
| Instances can not change their type at runtime. | Class membership may change at runtime. |
| The list of classes is fully known at compile-time and cannot change after that. | Classes can be created and changed at runtime. |
| Compilers are used at build-time. Compile-time errors indicate problems. | Reasoners can be used for classification and consistency checking at runtime or build-time. |
| Classes encode much of their meaning and behavior through imperative functions and methods. | Classes make their meaning explicit in terms of OWL statements. No imperative code can be attached. |
| Instances are anonymous insofar that they cannot easily be addressed from outside of an executing program. | All named RDF and OWL resources have a unique URI under which they can be referenced. |
| Closed world: If there is not enough information to prove a statement true, then it is assumed to be false. | Open world: If there is not enough information to prove a statement true, then it may be true or false. |


[[OOP]]
[[ORM]]
