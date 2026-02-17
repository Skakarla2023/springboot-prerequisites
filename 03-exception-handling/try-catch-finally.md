<h2 align="center"><b>try catch finally in Java</b></h3>

- An **exception** in Java is an event that occurs during the execution of a program that disrupts its normal flow.

### Exception Hierarchy

All exceptions and errors in Java are subclasses of the java.lang.Throwable class. The hierarchy branches into two main types: 

- **Errors** : An Error is a serious problem that happens in the system and cannot be handled easily by the programmer.Represent severe, unrecoverable system-level problems (e.g., StackOverflowError, OutOfMemoryError) that are generally beyond the control of the application and should not be caught by the programmer.
- **Exceptions** : An Exception is a problem that happens during program execution, but can be handled by the programmer. Conditions that a reasonable application might want to catch and handle.They are further divided into two categories:
  - **Checked Exceptions** :  These are checked at compile time, and the compiler forces the programmer to handle or declare them. Examples include `IOException`, `SQLException`, and `ClassNotFoundException`.
  - **Unchecked Exceptions (Runtime Exceptions)** : These occur at runtime, typically due to programming logic errors (e.g., `ArithmeticException`, `NullPointerException`, `ArrayIndexOutOfBoundsException`). he compiler does not enforce handling them, though it is good practice to manage them to prevent program crashes.
 

## Exception Handling

- Exception handling lets you catch and handle errors during runtime - so your program doesn't crash.
- It uses different keywords:
  - The `try` statement allows you to define a block of code to be tested for errors while it is being executed.
  - The `catch` statement allows you to define a block of code to be executed, if an error occurs in the try block.
  - The finally statement lets you execute code, after try...catch, regardless of the result:
  - The try and catch keywords come in pairs:
```java
try {
  //  Block of code to try
}
catch(Exception e) {
  //  Block of code to handle errors
}
finally {
  // some statements
}
```

Observe the following Java Code:

```java
class ExceptionHandling {
    public static void main(String[] args){
        try {
            int[] nums = {1, 2, 3};
            System.out.println(nums[10]);
        }
        catch (Exception e){
            System.out.println("Array index out of bounds");
        }
        finally {
            System.out.println("try catch block executed");
        }       
    }
}
```

**Output**:
```
Array index out of bounds
try catch block executed
```


