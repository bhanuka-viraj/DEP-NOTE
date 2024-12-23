
|                                                                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the design <br>principles SE                                             | -> KISS - Keep it simple & short<br>-> DRY - Don't repeat your self<br>-> WET - X<br>-> SRP - Single Responsibility Principle  <br>-> OCP - Open-closed Principle<br>-> LSP - Liskow substitution principle<br>-> ISP - Interface Segregation principle<br>-> DIP - Dependency Inversion principle<br>-> YAGNI - You ain't  Gonna Need it<br>-> Strategy Design Pattern<br>-> Factory Design Pattern                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| What is SOLID                                                                     | > SRP - Single Responsibility Principle  <br>-> OCP - Open-closed Principle<br>-> LSP - Liskow substitution principle<br>-> ISP - Interface Segregation principle<br>-> DIP - Dependency Inversion principle                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| What is the <br>Single Responsibility principle<br>(SRP)                          | Give a single responsible for the component as much as possible                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| What is the ISP                                                                   | Only show the necessary things to the client. <br>a interface layer is used to hide things from the <br>client<br><br>from wiki -><br>In the field of [software engineering](https://en.wikipedia.org/wiki/Software_engineering "Software engineering"), the **interface segregation principle** (**ISP**) states that no code should be forced to depend on [methods](https://en.wikipedia.org/wiki/Method_(computer_programming) "Method (computer programming)") it does not use<br><br>wiki -> https://en.wikipedia.org/wiki/Interface_segregation_principle                                                                                                                                                                                                                                                                                                                                                           |
| What is the DIP                                                                   | In [object-oriented design](https://en.wikipedia.org/wiki/Object-oriented_design "Object-oriented design"), the **dependency inversion principle** is a specific methodology for [loosely coupled](https://en.wikipedia.org/wiki/Coupling_(computer_programming) "Coupling (computer programming)") software [modules](https://en.wikipedia.org/wiki/Modular_programming "Modular programming").<br><br>1. High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces). (modules means layers in here)<br><br>2. Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions. (the implementation should be done according to the abstraction not abstraction should not be changed according to the implementation )<br><br>wiki link -> <br>https://en.wikipedia.org/wiki/Dependency_inversion_principle |
| What is the strategy design pattern                                               | Selecting the necessary strategy<br><br>Example -> In Girl Boy example boy have chance to select the <br>girl<br><br>form wiki -> <br>In [computer programming](https://en.wikipedia.org/wiki/Computer_programming "Computer programming"), the **strategy pattern** (also known as the **policy pattern**) is a [behavioral](https://en.wikipedia.org/wiki/Behavioral_design_pattern "Behavioral design pattern") [software design pattern](https://en.wikipedia.org/wiki/Design_pattern_(computer_science) "Design pattern (computer science)") that enables selecting an [algorithm](https://en.wikipedia.org/wiki/Algorithm "Algorithm") at runtime. Instead of implementing a single algorithm directly, code receives runtime instructions as to which in a family of algorithms to use                                                                                                                              |
| What is the factory design<br>principle                                           | In factory design pattern the instance creation is encpasulated.<br><br>ex -> Boy does not have to select the girl                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| What is the reason to use <br>factory design<br>principle in layered architecture | To encapsulate the instance  creation to the upper layers. This is allowed to change the implementation of the lower layers later without knowing the upper layers                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| What does mean IOC                                                                | Inversion of control                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

### Strategy Design Pattern

**The Strategy Pattern** is a behavioral design pattern that allows you to define a family of algorithms, encapsulate each one, and make them interchangeable. This pattern lets you vary the algorithm's behavior without changing the client that uses it.

### Key components:

- **Strategy Interface:** Defines a common interface for all algorithms.
- **Concrete Strategies:** Implement the strategy interface, each representing a specific algorithm.
- **Context:** Holds a reference to a strategy object and delegates work to it.

![[Pasted image 20240815223626.png]]


Good girl interface

```java
package lk.ijse.dep12.cdi;

public interface GoodGirl {
    void kiss();
}
```

Boy

```java
package lk.ijse.dep12.cdi;

public class Boy {
//    Girl gf = new Girl();
    /* strategy design pattern */
//    GoodGirl gf =new Piumi();
    GoodGirl gf =new Kaushi();

    public void kissHer() {
        gf.kiss();
    }
}

```

Kaushi

```java
package lk.ijse.dep12.cdi;

public class Kaushi implements GoodGirl {
    @Override
    public void kiss() {
        System.out.println("Ummmmmaaaa....!");
        System.out.println("Ummmmmaaaa....!");
        System.out.println("Ummmmmaaaa....!");
        System.out.println("Ummmmmaaaa....!");
    }
}

```

Piumi

```java
package lk.ijse.dep12.cdi;

public class Piumi implements GoodGirl {
    @Override
    public void kiss() {
        System.out.println("Ummmmmaaaa....!");

    }
}
```

Boy can decide which good girl to connect, and switch independently.

## Factory Design Pattern

**The Factory Pattern** is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

Factory must be **singleton**.

### Key components:

- **Factory interface or abstract class:** Defines a method for creating objects.
- **Concrete factories:** Implement the factory interface to create specific object types.
- **Product interface or abstract class:** Defines the interface for the objects created by the factory.
- **Concrete products:** Implement the product interface to represent specific product types.

### When to use the Factory Pattern:

- When you need to create objects without exposing the creation logic.
- When the class hierarchy of products is complex.
- When you want to provide a unified interface for creating different types of objects.

By using the Factory pattern, you can create more flexible, maintainable, and testable code.

```java
package lk.ijse.dep12.cdi;

/* this factory is singleton */
public class GoodGirlFactory {
    private static final GoodGirlFactory INSTANCE = new GoodGirlFactory();

    private GoodGirlFactory() {
    }

    public static GoodGirlFactory getInstance() {
        return INSTANCE;
    }

    /* Factory decides which good girl to give */
    public GoodGirl getGoodGirl() {
        return new Kaushi();
    }
}

```

```java
package lk.ijse.dep12.cdi;

public class Boy {
//    Girl gf = new Girl();
    /* strategy design pattern */
//    GoodGirl gf =new Piumi();
//    GoodGirl gf =new Kaushi();

    /* Get a good girl from factory
    * like parents finding a girl for the boy
    * factory can decide which girl to give */
    GoodGirl gf = GoodGirlFactory.getInstance().getGoodGirl();

    public void kissHer() {
        gf.kiss();
    }
}

```
