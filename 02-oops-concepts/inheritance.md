<h2 align="center"><b>Inheritance in Java</b></h2>

- Inheritance in Java is a core OOP concept that allows a class to acquire properties and behaviors from another class.
- The class that gets the properties and methods is called subclass or child class, and the class from which it gets the properties is called **super class** or parent class.
- A subclass can reuse the fields and methods of the parent class without rewriting the code.
- A subclass can add its own fields and methods or modify existing ones to extend functionality.
- We use **extends** keyword to extend(inherit) a class from another.


#### Syntax:

```java
class Parent {

    // fields and methods

}
class Child extends Parent {

    // additional fields and methods

}
```

Observe the following code for more understanding:

```java
class Animal {
    void sound(){
        System.out.println("Animal makes a sound");
    }
}

class Cow extends Animal{
    void sound(){
        System.out.println("Cow moos");
    }
}

class Cat extends Animal {
    void sound(){
        System.out.println("Cat meows");
    }
}

class Dog extends Animal {
    void sound(){
        System.out.println("Dog barks");
    }
}

class InheritanceExample {
    public static void main(String[] args){
        Animal a = new Animal();
        a.sound();

        Cow cow = new Cow();
        cow.sound();

        Cat cat = new Cat();
        cat.sound();

        Dog dog = new Dog();
        dog.sound();
    }
}
```

**Output**:

```
Animal makes a sound
Cow moos
Cat meows
Dog barks
```

In the above code ,Animal is the parent class and the subclasses Cow,Cat and Dog are its subclasses, these classes get the sound method which is defined in the parent class and provide their own implementation of it.



### Types of Inheritance:


<img width="1100" height="733" alt="image" src="https://github.com/user-attachments/assets/68ff0a2d-17f6-424b-b212-bdbf440836c7" />


### 1. Single Inheritance

In single inheritance, a sub-class is derived from only one super class. It inherits the properties and behavior of a single-parent class. Sometimes, it is also known as simple inheritance.


<img width="682" height="400" alt="image" src="https://github.com/user-attachments/assets/ab48b2c5-2374-4623-ab2c-ac430f8d0a4e" />

### 2. Multilevel Inheritance

In Multilevel Inheritance, a derived class will be inheriting a base class and as well as the derived class also acts as the base class for other classes.

<img width="682" height="400" alt="image" src="https://github.com/user-attachments/assets/c49345ca-dc95-4e3a-baf3-ca8e58260860" />

```java
class GrandFather{
    public void property(){
        System.out.println("This is our family property");
    }
}

class Father extends GrandFather{
    public void property(){
        System.out.println("I will give this property to my son");
    }
}
class Son extends Father{
    public void property(){
        System.out.println("I got this property from my dad, who got it from his dad");
    }
}

class MultiLevelInheritance{
    public static void main(String[] args){

        GrandFather g = new GrandFather();
        g.property();

        Father f = new Father();
        f.property();

        Son s = new Son();
        s.property();
    }
}

```

**Output**:
```
This is our family property
I will give this property to my son
I got this property from my dad, who got it from his dad
```

### 3. Hierarchical Inheritance

In hierarchical inheritance, more than one subclass is inherited from a single base class. i.e. more than one derived class is created from a single base class. For example, cars and buses both are vehicle

<img width="682" height="400" alt="image" src="https://github.com/user-attachments/assets/4d5535d1-937f-4732-b846-6dd42dd2aed1" />


```java
class Vehicle {
    Vehicle() {
        System.out.println("This is a Vehicle");
    }
}

class Car extends Vehicle {
    Car() {
        System.out.println("This Vehicle is Car");
    }
}

class Bus extends Vehicle {
    Bus() {
        System.out.println("This Vehicle is Bus");
    }
}

public class Test {
    public static void main(String[] args) {
        Car obj1 = new Car(); 
        Bus obj2 = new Bus(); 
    }
}
```

**Output**:
```
This is a Vehicle
This Vehicle is Car
This is a Vehicle
This Vehicle is Bus
```

### 4. Multiple Inheritance (Through Interfaces)

In Multiple inheritances, one class can have more than one superclass and inherit features from all parent classes.

<img width="682" height="400" alt="image" src="https://github.com/user-attachments/assets/3d9a26d0-0925-4b7c-a6a4-f54f44ed2859" />


```java
interface LandVehicle {
    default void landInfo() {
        System.out.println("This is a LandVehicle");
    }
}
interface WaterVehicle {
    default void waterInfo() {
        System.out.println("This is a WaterVehicle");
    }
}
// Subclass implementing both interfaces
class AmphibiousVehicle implements LandVehicle, WaterVehicle {
    AmphibiousVehicle() {
        System.out.println("This is an AmphibiousVehicle");
    }
}
public class Test {
    public static void main(String[] args) {
        AmphibiousVehicle obj = new AmphibiousVehicle();
        obj.waterInfo();
        obj.landInfo();
    }
}
```

**Output**:
```
This is an AmphibiousVehicle
This is a WaterVehicle
This is a LandVehicle
```

### 5. Hybrid Inheritance

It is a mix of two or more of the above types of inheritance. In Java, we can achieve hybrid inheritance only through Interfaces if we want to involve multiple inheritance to implement Hybrid inheritance.

<img width="682" height="400" alt="image" src="https://github.com/user-attachments/assets/a8ab247e-7e13-4e1d-903f-b2936fcaa26d" />


```java
class SolarSystem {
}
class Earth extends SolarSystem {
}
class Mars extends SolarSystem {
}
public class Moon extends Earth {
    public static void main(String args[])
    {
        SolarSystem s = new SolarSystem();
        Earth e = new Earth();
        Mars m = new Mars();

        System.out.println(s instanceof SolarSystem);
        System.out.println(e instanceof Earth);
        System.out.println(m instanceof SolarSystem);
    }
}
```

**Output**:
```
true
true
true
```


## Advantages of Inheritance in Java

- **Code Reusability:** Subclasses reuse properties and methods of the superclass, reducing code duplication.
- **Abstraction:** Supports abstract classes that define common interfaces, making code easier to maintain and extend.
- **Class Hierarchy:** Helps create a structured class hierarchy to represent real-world relationships.
- **Polymorphism:** Allows objects to take multiple forms by overriding superclass methods.

## Disadvantages of Inheritance in Java

- **Complexity:** Deep or large inheritance hierarchies can make code harder to understand.
- **Tight Coupling:** Changes in the superclass may affect subclasses, reducing flexibility.

