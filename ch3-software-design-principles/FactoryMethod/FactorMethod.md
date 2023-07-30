# Factory Method 
Creational Design Pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of the object that will be created.

## Philosophy 
Replace the direct object creation using with calls to a special _Factory Method_, which handles the variation of instance types creation.

## Structure 

1. Product Interface: the interface that gathers the definition of the common properties of the variations of types, the _Factory Method_ should return A Product.
1. Concrete Products: the concrete representation of the different variations of types, where each concrete product should inherit and implement the required properties from the _Product Interface_
1. Creator Interface: the interface has the _Factory Method_ definition
1. Concrete Creators: the concrete implementation for the _Factory Method_ where each subclass returns the concrete version of the matching Product







