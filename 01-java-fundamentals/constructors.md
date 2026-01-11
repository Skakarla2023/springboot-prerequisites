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

```
