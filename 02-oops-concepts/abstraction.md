<h2 align="center"><b>Java Abstraction</b></h2>

- Abstraction in Java is the process of hiding internal implementation details and showing only essential functionality to the user.
- It focuses on what an object does rather than how it does it.
- Abstraction = Showing only what is needed, hiding how it works inside.

---


<img width="1149" height="766" alt="image" src="https://github.com/user-attachments/assets/f97fe08c-067e-4580-b898-5bbf329e7fc0" />

---

### How to Achieve Abstraction in Java?

Java provides two ways to implement abstraction, which are listed below:
- Abstract Classes (Partial Abstraction)
- Interface (100% Abstraction)


## Abstract Class

- An abstract class is a class that cannot be instantiated and may contain abstract methods (methods without body) as well as concrete methods (with implementation).
- To declare that your class is an abstract class, use the keyword abstract before the class keyword in your class declaration:

```java
 abstract class Number {
 . . .
 }
```

```java

abstract class Shape{
    String color;

    abstract double area();
    public abstract String toString();

    public Shape(String color){
        System.out.println("Shape constructor called");
        this.color = color;
    }

    public String getColor(){
        return color;
    }
}
class Circle extends Shape{
    double radius;
    public Circle(String color,double radius){
        super(color);
        System.out.println("Circle constructor called");
        this.radius = radius;
    }
    @Override double area(){
        return Math.PI * Math.pow(radius,2);
    }
    @Override public String toString(){
        return "Circle color is "+ super.getColor()+" and area is : "+area(); 
    }
}
public class ShapeMain{
    public static void main(String[] args){
        Shape s1 = new Circle("Red",5.5);
        System.out.println(s1.toString());
    }
}
```

**Output**:

```
Shape constructor called
Circle constructor called
Circle color is Red and area is : 95.03317777109125
```

## Interface

#### A real life scenario of how abstraction works:

```java
// Interface (Abstraction)
interface Login {
    void login();
    void signin();
}

// Email Login Implementation
class EmailLogin implements Login {

    public void login() {
        System.out.println("User logged in using Email");
    }

    public void signin(){
        System.out.println("User signed in into his account");
    }
}

// Google Login Implementation
class GoogleLogin implements Login {

    public void login() {
        System.out.println("User logged in using Google");
    }

    public void signin(){
        System.out.println("User signed in using Google");
    }
}

// Main Class
public class AbstractionExample {

    public static void main(String[] args) {

        // Using Email Login
        Login login1 = new EmailLogin();
        login1.login();
        login1.signin();

        // Using Google Login
        Login login2 = new GoogleLogin();
        login2.login();
        login2.signin();
    }
}

```

**Output:**

```txt
User logged in using Email
User signed in into his account
User logged in using Google
User signed in using Google
```

