# Factory Method 
Creational Design Pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of the object that will be created.

## Philosophy 
Replace the direct object creation using with calls to a special _Factory Method_, which handles the variation of instance types creation.

## Structure 

1. Product Interface: the interface that gathers the definition of the common properties of the variations of types, the _Factory Method_ should return A Product.
1. Concrete Products: the concrete representation of the different variations of types, where each concrete product should inherit and implement the required properties from the _Product Interface_
1. Creator Interface: the interface has the _Factory Method_ definition
1. Concrete Creators: the concrete implementation for the _Factory Method_ where each subclass returns the concrete version of the matching Product.

## Applicability 

1. when you don't know beforehand the exact types and dependancies.
1. When you want to provide users of your code with a way to extend your internal components.
1. when you want to save intensive resources by reusing existing objects instead of creating new objects every time (connection pooling).    

## Pros and Cons 

1. Avoid tight coupling product usages and product definitions.
1. Single Responsibility Principle. where each product has only one type 
1. Open/Close Principle. you can inherit and create new products without changing or breaking the old code 
1. (Cons) The code gets more complicated with more types you are adding 



