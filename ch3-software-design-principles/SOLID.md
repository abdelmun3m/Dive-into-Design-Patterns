# SOLID Principles 
  A mnemonic for 5 design principles intended to make software design more understandable, flexible and maintainable

## 1-(S) Single Responsibility Princible 
  - Try to make every class responsible for a single part of the functionality provided by the software.
  - Make the responsibility entirely encapsulated by that class
  - The main goal of this principle is reducing the complexity.

## 2-(O) Open/Close Principle
  Classes should be **Open** for **Externsion** but **Closed** for **Modefications** 
  - The main goal is to protect the current code from breaking when changing or implementing new features
  - **Open** means that the class can be extended producing a subclass and do whatever you want with the new subclass
  - **Close** means that it is 100% ready to be used by other classes (developed, tested and reviewed).
  - It doesn't mean that subclass will be responsible to fix the superclass's bug
  
## 3-(L) Liskove Substitution Princible
  When extending a class make sure that the new subclass is compatible with the superclass.
  - You should be able to pass an object of the subclass in place of an object of the superclass
  - When overriding a method, extend the base class behaviour rather than replace it.
  - It is a set of checks that should be validated when creating a subclass 
      1. **Parameter** types in a method of **subclass** should match or be more **abstract** than parameter types in the method of the superclass.
           ```
            Class super:
                def feed(cat : Cat):
                  pass

            Class sub(super):
                # where Cat is an Animal 
                def feed(animal: Animal):
                  pass
           ```
        
     2. **Return** types in a method of the **subclass** should match or be a **subtype** of the return type in the method of the superclass e.g.
          ```
          Class super:
              def feed(cat : Cat) -> Animal:
                pass

          Class sub(super):
              # where Cat is an Animal 
              def feed(animal: Animal) -> Cat:
                pass
          ```
      3. A method in the subclass shouldn't throw types of exceptions which the base method isn't expected to throw.
      4. A subclass shouldn't strengthen pre-conditions: if you expect to have a supermethod that expects in the param **int** don't extend it and change the behavior to only accept positive numbers.
      5. A subclass shouldn't lessen the post-conditions: if your superclass closes db connections after opening it, don't extend the method and keep the connections open for reuse.
      6. Invariants of superclass must be preserved: invariants are conditions in which an object makes sense **_don't break your superclass behaviour_**.
      7. a subclass shouldn't change the values of private fields of the superclass.

## 4-(I) Interface Segregation Princible
  Clients shouldn't be forced to depend on methods they don't need 
  - Try to make your interfaces narrow enough 
  - Break down "fat" interfaces into more granular and specific ones.

    
## 5-(D) Dependency Inversion Principles 
  **High level** classes shoudn't depend on the **low-level** classes.
  - **Low-Level** classes: implement basic operations such as disk management and DB interactions.
  - **High Level** Classes: contains complex business logic that directs low-level classes to do something.
  - Both levels should depend on abstractions
  - Abstractions shouldn't depend on details 
  - Details should depend on Abstractions
  - make the low-level classes depend on (directed by) the high-level classes 
  - it is called inversion because it inverts the dependency from **High level -> Low Level** to **High Level <- Low Level** (-> means depends on)


