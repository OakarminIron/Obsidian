In class-based, object-oriented programming, a constructor  is a special type of function called to create an object.
It prepares the new object for use, often accepting arguments that the constructor uses to set required member variables.

A constructor resembles an instance method, but it differs from a method in that it has no explicit return type, it is not implicitly inherited and it usually has different rules for scope modifiers. 
Constructors often have the same name as the declaring class. They have the task of initializing the object's data members and of establishing the invariant of the class, failing if the invariant is invalid. 
A properly written constructor leaves the resulting object in a valid state. Immutable objects must be initialized in a constructor.

Most languages allow overloading the constructor in that there can be more than one constructor for a class, with differing parameters. 
Some languages take consideration of some special types of constructors. Constructors, which concretely use a single class to create objects and return a new instance of the class, are abstracted by factories, which also create objects but can do so in various ways, using multiple classes or different allocation schemes such as an object pool.
