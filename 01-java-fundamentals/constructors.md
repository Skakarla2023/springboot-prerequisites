<h2 align="center"><b>Contructors in Java</b></h2>

- Constructor is a special method, used to initialize objects in Java.
- It is automatically called when an object is created.
- It is used to initialize objects at the time of their creation.
- Constructor has the following charactertistics:

**1. Same Name as the class name** : A constructor must have the same name as its class name.

**2.No Return Type** : A constructor should not return anything

**3.Automatic Invokation** : It is automatically called when an object is created.

**4.Cannot be inherited** : Constructors cannot be inherited by the super class, though they can call the superclass's constructor using the `super` keyword.


### Constructor vs Method

| Constructor  | Method  |
|--------------|---------|
| It initializes the objects.| It defines the operations of an object.|
| It should have the same name as the class name.| It can have any name.|
| No return type(not even void).| Should return something or `void`.|
| Invoked implicitly when object is created.| Invoked explicitly.|

## Types of Constructors

There are four types of constructors in Java:

<img width="1000" height="304" alt="image" src="https://github.com/user-attachments/assets/a67d7095-a472-478c-b5e7-536abb60d7ed" />

### Default Constructor

A Default Constructor has no parameters. It is used to assign default values to an object. If no constructor is written, Java provides a default constructor.

```java
class Main{
    Main(){
        System.out.println("Welcome to this new life!!!");
    }
    public static void main(String[] args){
        Main obj = new Main();
    }
}
```

Output:

```
Welcome to this new life!!!
```

### Parametrized Constructor

A Parametrized Constructor has parameters in Java. If we want to initialize fields of the class with our own values, we use Parametrized Constructor.

```java
class Main{
    
    String name;
    int no;
    
    Main(String name, int no){
        this.name = name;
        this.no = no;
    }
    public static void main(String[] args){
        Main obj = new Main("Joe",10);
        System.out.println("Name : "+obj.name+"\n"+"Number : "+obj.no+"\n");
    }
}
```

Output:

```
Name : Joe
Number : 10
```

### Copy Constructor

Unlike other constructors copy constructor is used to copy the data from one object(avaible object) to other(newly created object).

```java
class Main{
    
    String name;
    int no;
    
    // Parametrized Constructor
    Main(String name, int no){
        this.name = name;
        this.no = no;
    }
    
    // Copy Constructor
    Main(Main obj2){
        this.name = obj2.name;
        this.no = obj2.no;
    }
    public static void main(String[] args){
        // This would invoke the first Constructor
        Main obj = new Main("Joe",10);
        System.out.println("First Object: ");
        System.out.println("Name : "+obj.name+"\n"+"Number : "+obj.no);
        
        System.out.println();
        
        // This is the copy constructor
        Main obj2 = new Main(obj);
        System.out.println("Second object from copy constructor: ");
        System.out.println("Name : "+obj.name+"\n"+"Number : "+obj.no);
    }
}
```

Output:

```
First Object: 
Name : Joe
Number : 10

Second object from copy constructor: 
Name : Joe
Number : 10
```


### Private Constructor

Private Constructor is not accessible from outside the class, it is commonly used :
  - In SingleTon classes i.e., onyl one instance of a class can be created.
  - Prevent instantiation of classes containing only static methods are used.

```java
class Sample{
    private Sample(){
        System.out.println("private constructor");
    }
    
    public static void displayMessage(){
        System.out.println("Hello to my future me");
    }
}
class Main{
    public static void main(String[] args){
        Sample obj = new Sample();
        Sample.displayMessage();
    }
}
```

Output:

```
ERROR!
/tmp/ldyTYy5t79/Main.java:12: error: Sample() has private access in Sample
        Sample obj = new Sample();
                     ^
1 error
ERROR!
error: compilation failed
```

##### Corrected code:

```java
class Main{
    public static void main(String[] args){
        // Sample obj = new Sample();
        Sample.displayMessage();
    }
}
class Sample{
    private Sample(){
        System.out.println("private constructor");
    }
    
    public static void displayMessage(){
        System.out.println("Hello to my future me");
    }
}
```

Output:

```
Hello to my future me
```

## Constructor Overloading

This is a keyconcept in OOPS, it is used to create multiple constructors of the same class with different parameters.

```java
class Main{
    Main(int no){
        System.out.println("Constructor with one parameter(int): "+no);
    }
    Main(String name, int no){
        System.out.println("Constructor with two parameters(String,int): "+name+" "+no);
    }
    Main(){
        System.out.println("Constructor with no parameters");
    }
    public static void main(String[] args){
        
        System.out.println("Implementation of Parametrized constructors:");
        
        // constructor 1
        Main obj1 = new Main();
      
        // constructor 2  
        Main obj2 = new Main(24);
        
        // constructor 3   
        Main obj3 = new Main("Priya",12);
    }
}
```

## Constructor Chaining

- Constructor chaining refers to calling one constructor inside another constructor.
- Constructor Chaining is a mechanism in Java where one constructor calls another constructor either within the same class using `this` or from the parent class using `super`.
- The primary purpose of constructor chaining is reuse initialization code and reducing redundancy.
- The constructor call must always be the **first** statement inside the constructor.

#### Simple rule to remember:
```
one constructor passes the responsibility to another before finishing its job.
```

### Without constructor chaining:

- Code gets repeated
- Initialization logic becomes messy
- Harder to maintain and debug

### With constructor chaining:

- Common initialization code stays in one place
- Cleaner, readable, and professional code
- Ensures proper order of object creation

It keeps constructors connected instead of isolated.

> Write once, reuse everywhere, initialize correctly

- Observe the following codes for better understanding:

### 1️ Student Profile (Same Class – this() chaining)

```java
class Student {
    String name;
    int no;
    String college;
    
    Student(){
        college = "ABC Engineering College";
        System.out.println("College set");
    }
    
    Student(String name){
        this();
        this.name = name;
        System.out.println("Name set");
    }
    
    Student(String name,int no){
        this(name);
        this.no = no;
        System.out.println("Number set");
    }
    
    public static void main(String[] main){
        Student s = new Student("Rahul",100);
    }
}
```

Output:

```
College set
Name set
Number set
```

### 2️ Bank Account (Mandatory account number first)

An account must have an account number before balance or services.

```java
class BankAccount {
    int AccountNumber;
    double balance;
    
    BankAccount(int AccountNumber){
        this.AccountNumber = AccountNumber;
        System.out.println("Account created");
    }
    
    BankAccount(int AccountNumber,double balance){
        this(AccountNumber);
        this.balance = balance;
        System.out.println("Balance added");
    }
    
    public static void main(String[] args){
        BankAccount b = new BankAccount(314563,3236.7456);
    }
}
```

Output:

```
Account created
Balance added
```

> Mandatory data initialized first using constructor chaining.

**super() chaining**:

```java
class Vehicle {
    String  fuelType;

    Vehicle(){
        fuelType = "Petrol";
        System.out.println("Vehicle fuel type set");
    }
}

class Car extends Vehicle{
    String brand;

    Car(){
        super();
        brand = "Toyota";
        System.out.println("Car brand set");
    }

    public static void main(String[] args){
        Car c = new Car();
    }
}
```

Output:

```
Vehicle fuel type set
Car brand set
```

