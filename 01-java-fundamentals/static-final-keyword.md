<h2 align="center"><b>static and final keywords</b></h2>

- static means it belongs to the class, not the object.
- Usually when Java creates an object, it has its own copy of variables and methods, but when something is `static`,only one copy of it exists and it is shared by **everyone**.

### Why do we need static?

We need static because, some things:

- Do not need object data.
- Should be shared across the class.
- Are needed even before the object is created.

### Where do we use static?

1. Variables
2. Methods
3. Blocks
4. Classes

#### static with variables

- static variables are also called as **class** variables.
- The variable belongs to the class itself rather than any other object.
- Which means all instances of the class share a single copy of the variable.
- Changes made by one instance are visible to all others.

```java
class Main{
    static int count = 0;
    public static void main(String[] args){
        Main obj1 = new Main();
        Main obj2 = new Main();
        obj1.count++;
        System.out.println(obj2.count);
    }
}
```

Output:
```
1
```

#### static with methods

- static method is a method that belongs to the class itself, rather than to any instance of the class.
- This means you can call a static method directly using the class name, without needing to create an object.
- static methods cannot access another methods and variables that are non-static as they need objects for their initialization.

```java
class Calculator{
    static int add(int a, int b){
        return a+b;
    }

    public int multiply(int a, int b){
        return a*b;
    }

    public static void main(String[] args){

        int sum = Calculator.add(5,3);
        System.out.println("Sum:"+sum);

        Calculator c = new Calculator();
        int product = c.multiply(12,5);
        System.out.println("Product:"+product);
        
    }
}
```

Output:
```
Sum:8
Product:60
```


#### static with blocks

- static block is a block of code associated with the `static` keyword that is executed only once after the code is loaded into memory by JVM.
- It runs automatically during class loading, even before `main` method or any constructors are called.

<img width="944" height="440" alt="image" src="https://github.com/user-attachments/assets/459c699d-a663-46da-9b67-0d3b8081d2fb" />

```java
class Sample {
    static int num=0;
    
    static{
        System.out.println("First static block executed");
        num += 10;
    }

    static{
        System.out.println("Second static block executed");
        num *= 2;
    }

    public static void main(String[] args){
        System.out.println("Main method executed");
        System.out.println("Number value:"+num);
    }
}
```

Output:

```
First static block executed
Second static block executed
Main method executed
Number value:20
```

#### static with classes

- static keyword allows to delcare classes inside classes i.e., nested class.
- A nested class can be initialized inside an outer class without creating an instance of the outer class.
- It can only access static members of the class even of they are declared **private**.
- It cannot access non-static members of the class, because it has no implicit reference to an outer class object.


```java
public class OuterClass {
    // static member of the outer class
    static int staticOuterField = 10;
    // non-static member of the outside class
    int instanceOuterField = 20;

    static class StaticNestedClass {
        void display(){
            // can access outer static members directly.
            System.out.println("Static outer field:"+staticOuterField);
        }
    }
    public static void main(String[] args){
        OuterClass.StaticNestedClass obj = new OuterClass.StaticNestedClass();
        obj.display();
    }
}
```

Output:
```
Static outer field:10
```
