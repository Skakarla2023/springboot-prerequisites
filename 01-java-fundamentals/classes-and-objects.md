<h2 align="center"><b>Class and Object in Java</b></h2>

## Object

- An Objects is a real world entity used in programming.
- It has 2 characteristics:
  - data
  - behavior
- **Data** is represented using variables.
- **Behavior** is shown using methods.
- It is an instance of a class that holds state and behavior.
- It is created using the **new** keyword.
- Objects are stored in **heap** memory and object reference(memory address of the object in heap mem) is stored in **stack**.
- Objects are created from a class and are used to interact with data in an organised way.


## Class

- A class is a blueprint or template that defines state and behavior.
- It is a template used to create objects.
- It **groups related data** in a single unit using objects, methods and data(variables).
- A class is created using the **class** keyword in Java.
- A class name should always start with an uppercase letter.


##### Observe the following codes to understand the concepts of class and object better:


### 1. Student class with student data and methods

```java
class Student {
    
    int rollno;
    String sname;
    double attendance;
    String address;
    
    public static void main(String[] args){
        
        Student s = new Student();
        
        // -----------------------
        // Student data
        // -----------------------
        s.rollno = 83;
        s.sname = "Simran";
        s.attendance = 90.2;
        s.address = "Hyderabad";
        
        // ------------------
        // Methods 
        // ------------------
        
        printdetails(s);
        getaddress(s);
        
    }
    static void printdetails(Student s){
        System.out.println("Student name: "+s.sname);
        System.out.println("Roll number: "+s.rollno);
        System.out.println("Attendance: "+s.attendance+"%");
        System.out.println("Address: "+s.address);
    }
    static void getaddress(Student s){
        System.out.println("Student resides at:"+s.address);
    }   
}
```
