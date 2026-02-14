<h2 align="center"><b> Polymorphism in Java</b></h2>

- Polymorphism in Java is the ability of an object to take on many forms, allowing a single action or method name to behave differently based on the specific object or context.
- This core concept of object-oriented programming (OOP) promotes code reusability, flexibility, and scalability.
- Java supports two main types of polymorphism: 
  1. Compile-time Polymorphism (Static Polymorphism)
  2. Runtime Polymorphism (Dynamic Polymorphism) 

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/70f2a2a5-4172-4fb4-b33b-2e3bd1ae3d24" />

## Compile-Time Polymorphism

- Compile-Time Polymorphism in Java is also known as static polymorphism and also known as method overloading.
- This happens when multiple methods in the same class have the same name but different parameters.
- Method overloading means defining multiple methods with the same name but different parameter lists.
- The method call is resolved at compile time based on the arguments passed.

**Example**: Method overloading by changing the number of arguments.

```java
class ShoppingCart{
    double calculateBill(double price){
        return price;
    }

    double calculateBill(double price, int quantity){
        return price*quantity;
    }

    double calculateBill(double price, int quantity, double discount){
        double total = price*quantity;
        return total-discount;
    }

    public static void main(String[] main){
        ShoppingCart cart = new ShoppingCart();

        System.out.println("Bill: " + cart.calculateBill(500));

        System.out.println("Bill: " + cart.calculateBill(200, 3));

        System.out.println("Bill: " + cart.calculateBill(300, 2, 100));
    }
}
```

**Output:**

```
Bill: 500.0
Bill: 600.0
Bill: 500.0
```
