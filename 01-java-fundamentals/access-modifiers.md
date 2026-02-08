<h1 align="center"><b>Access Modifiers</h1></b>

In Java, access modifiers are essential tools that define how the members of a class, like variables, methods, and even the class itself, can be accessed from other parts of our program.

<img width="1000" height="377" alt="image" src="https://github.com/user-attachments/assets/6de11c5a-5a54-4ec9-b171-8153aafa064b" />


### Private Access Modifier

- The private access modifier is specified using the keyword private.
- The methods or data members declared as private are accessible only within the class in which they are declared.

**Code**:

```java
class StaticExample{
    private String name;
    
    public void setName(String name){
        this.name = name;
    }
    public String getName(){
        return name;
    }
}
public class Junior {
    public static void main(String[] args){
        StaticExample se = new StaticExample();
        se.setName("Priya");
        
        System.out.println(se.name);
    }
}
```

**Output**:

```
ERROR!
/tmp/8ESkzQbyJ8/Main.java:16: error: name has private access in StaticExample
        System.out.println(se.name);
                             ^
1 error
ERROR!
error: compilation failed
```

Corrected Java code:

```java
public class Junior {
    public static void main(String[] args){
        StaticExample se = new StaticExample();
        se.setName("Priya");
        
        System.out.println(se.getName());
    }
}

class StaticExample{
    private String name;
    
    public void setName(String name){
        this.name = name;
    }
    public String getName(){
        return name;
    }
}
```

**Output**:

```
Priya
```

### Default Access Modifier

- When no access modifier is specified for a class, method, or data member, it is said to have the default access modifier by default.
- This means only classes within the same package can access it.

**Code**:

 ```java
class Tata{
    public static void main(String[] args){
        Car c = new Car();
        c.model = "Nexon";
        System.out.println("Model :"+c.model);
    }
}
class Car {
    String model;
}
```

**Output**:

```
Model :Nexon
```

### Protected Access Modifier

- The protected access modifier is specified using the keyword protected.
- The methods or data members declared as protected are accessible within the same package or subclasses in different packages.

**Code**:

```java
class Sonet{
    public static void main(String[] args){
        Kia k = new Kia();
        k.setSpeed(100);
        System.out.println("Access via subclass method : "+k.getSpeed());
        
        System.out.println("Speed : "+k.speed);
        
        Vehicle v = new Vehicle();
        System.out.println("Speed: "+v.speed);
    }
}
class Vehicle {
    protected int speed;
}
class Kia extends Vehicle {
    void setSpeed(int s){
        speed = s;
    }
    int getSpeed(){
        return speed;
    }
}
```

**Output**:

```
Access via subclass method : 100
Speed : 100
Speed: 0
```


### Public Access Modifier

- The public access modifier is specified using the keyword public.
- Public members are accessible from everywhere in the program.
- There is no restriction on the scope of public data members.

**Code**:

```java
class Example{ 
    public static int add(int a, int b) {
        return a + b;
    }
}
public class Main {
    public static void main(String[] args) {
        System.out.println(Example.add(5, 10)); // accessible anywhere
    }
}
```


**Output**:

```
15
```

