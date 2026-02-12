<h2 align = "center"><b>Java Encapsulation</b></h2>

- Encapsulation means combining data and the functions that work on that data into a single unit, like a class and protecting the data from direct access.
- In Object-Oriented Programming, it helps keep things organized and secure.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/1c81d30a-98af-4203-9375-7e9e970818cb" />

### Why do we need Encapsulation?

<img width="1231" height="523" alt="image" src="https://github.com/user-attachments/assets/b043d8fa-c1bf-4bdb-bb0a-ffb6dce41181" />

### Why do we use Encapsulation?

<img width="1329" height="472" alt="image" src="https://github.com/user-attachments/assets/e7e2cf62-e805-4ade-bc8a-0320e2d5bc0b" />

### How is Encapsulation acheived?

Encapsulation in Java is achieved using:
- Private data members
- Public getter and setter methods

#### Key Rules:

- **Declare data as private**: Hide the class data so it cannot be accessed directly from outside the class.
- **Use getters and setters**: Keep variables private and provide public getter and setter methods for controlled access and safe modification, often with validation.
- **Apply proper access modifiers**: Use private for data hiding and public for methods that provide access.



Observe the following code:

```java
class Anila{
    public String name;

    public String getName(){ return name; }

    public void setName(String name){ this.name = name; }
}
class EncapsulationExample {
    public static void main(String[] args){
        Anila a = new Anila();
        a.setName("Anikha");
        System.out.println("Name :"+a.getName());
    }
}
```

Output:

```
Name :Anikha
```

### Advantages of Encapsulation

The advantages of encapsulation are listed below:

- **Data Hiding**: Encapsulation restricts direct access to class variables, protecting sensitive data from unauthorized access.
- **Improved Maintainability**: Changes to internal implementation can be made without affecting external code that uses the class.
- **Enhanced Security**: Encapsulation allows validation and control over data, preventing invalid or harmful values from being set.
- **Code Reusability**: Encapsulated classes can be reused in different programs without exposing internal logic.
- **Better Modularity**: Encapsulation promotes organized, modular code by keeping data and methods together within a class.


### Disadvantages

The disadvantages of encapsulation are listed below:

- **Increased Code Complexity**: Writing getter and setter methods for every variable can make the code longer and slightly more complex.
- **Performance Overhead**: Accessing data through methods instead of directly can introduce a minor performance cost, especially in performance-critical applications.
- **Less Flexibility in Some Cases**: Over-restricting access to class members may limit the ability of other classes to extend or use the class efficiently.

