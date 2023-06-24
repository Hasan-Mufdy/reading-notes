# OOP (object oriented programming)

### Inheritance

Inheritance allows us to create classes that are built upon existing classes, to specify a new implementation while maintaining the same behaviors (realizing an interface), to reuse code and to independently extend original software via public classes and interfaces.

### Abstract and virtual methods

When a base class declares a method as virtual, a derived class can override the method with its own implementation. If a base class declares a member as abstract, that method must be overridden in any non-abstract class that directly inherits from that class. If a derived class is itself abstract, it inherits abstract members without implementing them. Abstract and virtual members are the basis for polymorphism, which is the second primary characteristic of object-oriented programming.

### Interfaces

An interface is a reference type that defines a set of members. All classes and structs that implement that interface must implement that set of members. An interface may define a default implementation for any or all of these members. A class can implement multiple interfaces even though it can derive from only a single direct base class.

### Polymorphism

Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance. Polymorphism is a Greek word that means "many-shaped".
it basically means that it uses the same methods to perform different tasks.

### Summary
C# is an object-oriented programming language. The four basic principles of object-oriented programming are:

- Abstraction Modeling the relevant attributes and interactions of entities as classes to define an abstract representation of a system.
- Encapsulation Hiding the internal state and functionality of an object and only allowing access through a public set of functions.
- Inheritance Ability to create new abstractions based on existing abstractions.
Polymorphism Ability to implement inherited properties or methods in different ways across multiple abstractions.