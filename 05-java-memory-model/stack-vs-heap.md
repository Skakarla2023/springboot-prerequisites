# Memory Allocation in Java

- Memory Allocation in Java is divided into two parts:
  1. Stack Memory
  2. Heap Memory


## Stack Memory

 - It stores local variables, method call information and references during program execution.
 - Static memory allocation.

## Heap Memory 

- It stores actual objects and dynamic data allocated at runtime.
- Dynamic memory Allocation.
- Objects created with **new** are placed here, and this memory is managed by the **garbage collector**.



<img width="1395" height="495" alt="image" src="https://github.com/user-attachments/assets/4bfbb1d3-e5a8-4e63-9e9f-c753fa49bb3d" />


- Observe the following code for a simpler understanding of stack and heap memory:


```java
public class MemoryDemo {

    // instance variable -> stored inside the obj in heap
    int num = 10;

    public static void main(String[] args) {

        // primitive variables -> stored in stack
        int a = 5;
        int b = 10;

        // primitive result variable -> stored in stack
        int sum = a+b;

        // sctual stribg obj -> stored inside heap
        String message = new String("Hello Java");

        // reference variable -> stored in stack
        // actual object -> stored in heap
        MemoryDemo obj = new MemoryDemo();

        int[] nums = {1, 2, 3, 4};

        System.out.println("Sum= "+sum);
        System.out.println("Message= "+message);
        System.out.println("Object number= "+obj.number);


        for(int i=0;i<nums.length;i++) {
            System.out.println("Array value = "+nums[i]);
        }
    }
}
```
