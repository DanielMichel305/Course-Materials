# Design patterns

### Reasons to use design patterns
- Improve code reusability and code quality
- Encourage best practices to standard problems (Example: Database Connection)

##### Design patterns usually consist of the following
- Intent
- Structure 
- Code example
- Motivation

### Types of Design patterns:
| Type | purpose |
| --- |---|
|- Creational| Object Creation and code reusablity|
|- Behavioural | assignment of responsibilities between objects | 
|- Structural | using multiple classes and object to create more complex ones


#### Creational Design patterns
- ##### Factory :
   - Replace Direct object creation (using ```new```) with a factory method that returns the created Object.
    - Objects created by Factory methods are called <mark>products</mark>. 
- ##### Builder
    - Simplify the creation of complex objects.
    - Seperates object creation from representation.
    - Reduces the number of constructors needed to created different classes derived from the same base class at the cost of the single constructor having many optional parameters often set to null when not used.
- ##### Singleton
    - Singleton ensures that the class only has a <mark>single instance in the entire codebase</mark> while providing a <mark>single global access point</mark>.
- ##### Abstract Factory
    - ###### Not Discussed
- ##### Prototype
    - ###### Not Discussed

#### Structural Design patterns
- ##### Adapter
    - As the name implies it allowes 2 or more objects with 2 or more incompatible classes to collaborate.
    - Example: Intermediate class to convert XML to JSON or Formdata to JSON.    
- ##### Decorator
    - Allows an object to have a new behaviour/functionality than the base class by wrapping the object in a wapper object with the added functionality.
    - Example: Car and a TunedCar where the TunedCar is a Car but with the added functionality that it is tuned.

<details >
<summary>Patterns not discussed in the course</summary>

- Bridge 
- Composite 
- Facade 
- Flyweight 
</details>

#### Behavioural Design Patterns

- ##### Observer
    - Allows a <mark>subscriber</mark> to get notified when a <mark>publisher</mark> pushes an update about a topic/<mark>subject</mark>.
    - Think RabbitMQ or other message queues whith a publisher-subscriber architecture.
- ##### Strategy
    - Has many concrete strategies that change depending on a set context.
    - ###### Example:
        If in a match the opposing team is stronger(context) then the strategy is set to defensiveStrategy(concrete strategy) otherwise set strategy to offenseStrategy(another concrete Strategy)  
     
<details >
<summary>Patterns not discussed in the course</summary>

- Chain of Responsibility 
- Command 
- Iterator
- Mediator 
- Momento 
- State 
- Template (discussed previously) 
</details>


---
author: [@DanielMichel305](https://github.com/DanielMichel305)
---