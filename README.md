# Programming Guide

- [Programming Guide](#programming-guide)
  - [Templates](#templates)
  - [Code Design](#code-design)
    - [SOLID](#solid)
    - [KISS](#kiss)
    - [UML class diagrams](#uml-class-diagrams)
    - [Design pattern](#design-pattern)
      - [Creational pattern](#creational-pattern)
        - [Singleton pattern](#singleton-pattern)
  - [C<span>#</span>](#c)
  - [Mathematics](#mathematics)
  - [Unity](#unity)

## Templates

 - [.editorconfig](templates/.editorconfig)

## Code Design

### SOLID

### KISS
**k**eep* **i**t **s**imple, **s**tupid  
The KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore, simplicity should be a key goal in design, and unnecessary complexity should be avoided. 

### UML class diagrams
[plantUML](https://plantuml.com/class-diagram)  
Example:  
![Class Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Projektanker/programming-guide/master/uml/example.puml)

### Design pattern

#### Creational pattern

##### Singleton pattern

![Class Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Projektanker/programming-guide/master/uml/singleton.puml)


Thread safe:
```cs
// Lazy singleton C#
class Singleton
{
  private static readonly Lazy<Singleton> _instance = new Lazy<Singleton>(() => new Singleton());

  private Singleton()
  {
    // constructor code
  }

  public static Singleton Instance => _instance.Value;  
}
```


## C<span>#</span>

## Mathematics

## Unity