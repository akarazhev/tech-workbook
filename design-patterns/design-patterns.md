# Design Patterns

## Creational Patterns
 
### Abstract Factory 

Idea
 
> Provide an interface for creating families of related or dependent objects without specifying their concrete classes.

Wikipedia says

> The abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme 
without specifying their concrete classes.

In plain words

> A factory of factories; a factory that groups the individual but related/dependent factories together without 
specifying their concrete classes.

### Builder

Idea 
 
> Separate the construction of a complex object from its representation so that the same construction process can create 
  different representations.

Wikipedia says

> The builder pattern is an object creation software design pattern with the intentions of finding a solution 
to the telescoping constructor anti-pattern.

In plain words

> Allows you to create different flavors of an object while avoiding constructor pollution. Useful when there could be 
several flavors of an object. Or when there are a lot of steps involved in creation of an object.

### Factory Method

Idea
 
> Define an interface for creating an object, but let subclasses decide which class to instantiate. 
  Factory Method lets a class defer instantiation to subclasses.
  
Wikipedia says

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with 
the problem of creating objects without having to specify the exact class of the object that will be created. 
This is done by creating objects by calling a factory method—either specified in an interface and implemented by 
child classes, or implemented in a base class and optionally overridden by derived classes—rather than by calling 
a constructor.

In plain words

> It provides a way to delegate the instantiation logic to child classes.  
  
### Prototype

Idea
 
> Specify the kinds of objects to create using a prototypical instance, and create new objects by copying this prototype.

Wikipedia says

> The prototype pattern is a creational design pattern in software development. It is used when the type of objects 
to create is determined by a prototypical instance, which is cloned to produce new objects.

In plain words

> Create object based on an existing object through cloning.

### Singleton

Idea
 
> Ensure a class only has one instance, and provide a global point of access to it.

Wikipedia says

> In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a 
class to one object. This is useful when exactly one object is needed to coordinate actions across the system.

In plain words

> Ensures that only one object of a particular class is ever created.

## Structural Patterns

### Adapter

Idea 
 
> Convert the interface of a class into another interface the clients expect. Adapter lets classes work together that 
  couldn't otherwise because of incompatible interfaces.
  
Wikipedia says

> In software engineering, the adapter pattern is a software design pattern that allows the interface of an existing 
class to be used as another interface. It is often used to make existing classes work with others without modifying 
their source code.

In plain words

> Adapter pattern lets you wrap an otherwise incompatible object in an adapter to make it compatible with another class. 
  
### Bridge

Idea
 
> Decouple an abstraction from its implementation so that the two can vary independently.

Wikipedia says

> The bridge pattern is a design pattern used in software engineering that is meant to "decouple an abstraction from its 
implementation so that the two can vary independently"

In plain words

> Bridge pattern is about preferring composition over inheritance. Implementation details are pushed from a hierarchy 
to another object with a separate hierarchy.

### Composite

Idea
 
> Compose objects into tree structures to represent part-whole hierarchies. Composite lets clients treat individual objects 
  and compositions of objects uniformly.
  
Wikipedia says

> In software engineering, the composite pattern is a partitioning design pattern. The composite pattern describes that 
a group of objects is to be treated in the same way as a single instance of an object. The intent of a composite is 
to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets 
clients treat individual objects and compositions uniformly.

In plain words

> Composite pattern lets clients treat the individual objects in a uniform manner.  
  
### Decorator

Idea
 
> Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing 
  for extending functionality.
  
Wikipedia says

> In object-oriented programming, the decorator pattern is a design pattern that allows behavior to be added to 
an individual object, either statically or dynamically, without affecting the behavior of other objects from 
the same class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows 
functionality to be divided between classes with unique areas of concern.

In plain words

> Decorator pattern lets you dynamically change the behavior of an object at run time by wrapping them in an object of 
a decorator class.  
  
### Facade

Idea
 
> Provide a unified interface to a set of interfaces in a subsystem. Facade defines a higher-level interface that makes 
  the subsystem easier to use.
  
Wikipedia says

> A facade is an object that provides a simplified interface to a larger body of code, such as a class library.

In plain words

> Facade pattern provides a simplified interface to a complex subsystem.
  
### Flyweight

Idea
 
> Use sharing to support large numbers of fine-grained objects efficiently.

Wikipedia says

> In computer programming, flyweight is a software design pattern. A flyweight is an object that minimizes memory use 
by sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when 
a simple repeated representation would use an unacceptable amount of memory.

In plain words

> It is used to minimize memory usage or computational expenses by sharing as much as possible with similar objects.

### Proxy

Idea
 
> Provide a surrogate or placeholder for another object to control access to it.

Wikipedia says

> A proxy, in its most general form, is a class functioning as an interface to something else. A proxy is a wrapper or 
agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy 
can simply be forwarding to the real object, or can provide additional logic. In the proxy extra functionality can be 
provided, for example caching when operations on the real object are resource intensive, or checking preconditions 
before operations on the real object are invoked.

In plain words

> Using the proxy pattern, a class represents the functionality of another class.

## Behavioral Patterns

### Chain Of Responsibility

Idea
 
> Avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. 
Chain the receiving objects and pass the request along the chain until an object handles it.

Wikipedia says

> In object-oriented design, the chain-of-responsibility pattern is a design pattern consisting of a source of 
command objects and a series of processing objects. Each processing object contains logic that defines the types of 
command objects that it can handle; the rest are passed to the next processing object in the chain.

In plain words

> It helps building a chain of objects. Request enters from one end and keeps going from object to object till it 
finds the suitable handler.

### Command

Idea 

> Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or 
log requests, and support undoable operations.

Wikipedia says

> In object-oriented programming, the command pattern is a behavioral design pattern in which an object is used 
to encapsulate all information needed to perform an action or trigger an event at a later time. This information 
includes the method name, the object that owns the method and values for the method parameters.

In plain words

> Using command objects makes it easier to construct general components that need to delegate, sequence or execute 
method calls at a time of their choosing without the need to know the class of the method or the method parameters.