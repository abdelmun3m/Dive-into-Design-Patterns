# SOLID Principles 
  A mnemonic for 5 design principles intend to make software design more undestandable , flexable and maintable

## 1-(S) Single Responsibility Princible 
  - Try to make every class responsible for a single part of the funcionality provided by the software.
  - Make the esponsibility entirely encapsulated by that class
  - The main goal of this princible is reducing the complexity.

## 2-(O) Open/Close Principle
  Classes should be **Open** for **Externsion** but **Closed** for **Modefications** 
  - The main goal is to protect the current code from breaking when changing or implmenting a new features
  - **Open** means that the calss can be extended producing a subclass and do whatever yu want with the new subclass
  - **Close** means that the if it is 100% ready for be used by other classes (developed, tested and reviewed).
  - It dosn't mean that subclass will be responsible to fix superclass's bug
  
## 3-(L) Liskove Substitution Princible
  When extending a class make sure that the new subclass is compatible with the super class.
  - You shoud be able to pass an object of the subclass in place of an object of the super class
  - When overriding a method, extend the base class behavior rather thatn replacing it totally.
  - It is a set of checkes that should be validated when creating a sub class 
      1. **Parameter** types in a method of **subclass** should match or be more **abstract** than parameters types in the metod of the superclass.
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

          Class sub(super) -> Cat:
              # where Cat is an Animal 
              def feed(animal: Animal):
                pass
          ```
      3. A method in the subclass shoudn't throw types of exceptions which the base metod isn't expected to throw.
      4. A subclass shoudn't strengthen pre-condetions: if you expect have a supermethod that expects in the param **int** don't extend it and change the behavior to only accept positive number only.
      5. A subclass shoudn't weeken the post-condetions: if your super class close db connections after opening it, don't extend the method and keep the connections open for reuse.
      6. Invariants of superclass must be preserved: invariantes are condetions in which an object makes sense **_don't break you superclass behavior_**.
      7. a subclass shoudn't change te values of private fields of th superclass.

## 4-(I) Interface Segregation Princible
  Clients shoudn't be forced to depend on methods they don't need 
  - Try to make your interfaces narrowenugh 
  - Break down "fat" interfaces into more geanuall and specific ones.

    
## 5-(D) Dependency Inversion Principles 
  **High level** classes shoudn't depend on the **low-level** classes.
  - **Low Level** classes: implment basic operations such as disk managent an DB interactions.
  - **High Level** Classes: contains complex busniess logic that direct low-level classes to do something.
  - Both levels should depend on abstractions
  - Abstractions shudn't depend on details 
  - Details sould depend on Abstractions
  - make the low-level classes depend on (directed by) the high level classes 
  - it is called inversion because it invert the dependency from **High level -> Low Level** to **High Level <- Low Level** (-> menns depends on)


