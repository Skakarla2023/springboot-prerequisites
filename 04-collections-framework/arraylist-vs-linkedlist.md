## ArrayList

- An ArrayList in Java is a resizable array implementation that allows dynamic modification of its size, unlike traditional fixed-size arrays.
- It is a resizable-array implementation.

**Features**:

- Internally it uses a dynamic array.
- It allows duplicate elements.
- It maintains insertion order.
- It allows index-based access.

**When to Use ArrayList?**

Use ArrayList when:

- You need fast random access.
- You mostly add elements at the end.
- You rarely insert/delete in the middle.



Simple ArrayList Example :

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {

        ArrayList<String> list = new ArrayList<>();

        list.add("Apple");
        list.add("Banana");
        list.add("Mango");

        System.out.println("Element at index 1: " + list.get(1));

        list.remove("Banana");

        System.out.println(list);
    }
}
```



| Feature                    | ArrayList                                      | LinkedList                                         |
| -------------------------- | ---------------------------------------------- | -------------------------------------------------- |
| **Data Structure**         | Resizable array                                | Doubly linked list                                 |
| **Memory Layout**          | Elements stored in contiguous memory           | Each element stored in separate node with pointers |
| **Access by Index**        | Fast O(1)                                      | Slow O(n)                                          |
| **Insertion at End**       | Fast amortized O(1)                            | Fast O(1)                                          |
| **Insertion at Beginning** | Slow O(n)                                      | Fast O(1)                                          |
| **Insertion in Middle**    | Slow O(n)                                      | Slow O(n)                                          |
| **Deletion by Index**      | Slow O(n)                                      | Slow O(n)                                          |
| **Deletion at Beginning**  | Slow O(n)                                      | Fast O(1)                                          |
| **Searching Element**      | Fast with index O(1), slow if value-based O(n) | Always O(n)                                        |
| **Memory Usage**           | Less (only stores elements)                    | More (stores element + 2 pointers per node)        |
| **Resizing**               | Needs array copy when capacity exceeded        | No resizing needed                                 |
| **Iterator Efficiency**    | Faster for sequential access                   | Slightly slower due to node traversal              |
| **Use Case**               | Random access and frequent read                | Frequent insert/delete operations                  |
| **Maintains Order**        | Yes                                            | Yes                                                |
| **Implements**             | List interface                                 | List and Deque interfaces                          |

