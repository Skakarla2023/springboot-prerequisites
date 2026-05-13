# Garbage Collection

- Garbage Collection is an automatic memory management process, which reclaims the heap memory by removing or deleting objects that are no longer in use.
- Unlike C and C++ where we(developers) have to manually deallocate the memory, the JVM automatically does it in Java using Garbage Collector.
- Garbage Collecction happens in 3 steps:
  1. Marking
  2. Sweeping
  3. Compacting
 
## How Garbage Collecting works?

<img width="874" height="326" alt="image" src="https://github.com/user-attachments/assets/309377d8-0098-450c-943d-58ac146d8058" />

<img width="860" height="301" alt="image" src="https://github.com/user-attachments/assets/decea54b-17fc-48ca-a9fe-4f3184d84aa6" />

<img width="860" height="311" alt="image" src="https://github.com/user-attachments/assets/3ea6eeeb-82f4-43d1-b627-17f12a971ca9" />


## Java Heap

- Java heap is divided into generations:
  - **Young Generation**: In this new objects are allocated.
  - **Old Generation**: In this long-lived objects are stored.
