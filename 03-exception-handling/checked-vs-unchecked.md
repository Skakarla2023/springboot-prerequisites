| **Basis of Difference**   | **Checked Exceptions**                                                          | **Unchecked Exceptions**                            |
| ------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------- |
| **Definition**            | Exceptions that are **checked by the compiler at compile time**                 | Exceptions that are **NOT checked by the compiler** |
| **Compiler Check**        | ✔️ Compiler **forces you** to handle them                                       | ❌ Compiler **does not force** you to handle them    |
| **Handling Required?**    | Must be handled using `try-catch` **or** `throws`                               | Handling is **optional**                            |
| **When They Occur**       | Mostly due to **external factors** (file missing, network issue, database down) | Mostly due to **programming mistakes (bugs)**       |
| **Package**               | Subclasses of `Exception` (except RuntimeException)                             | Subclasses of `RuntimeException`                    |
| **Inheritance**           | Extend `Exception` class                                                        | Extend `RuntimeException` class                     |
| **Compilation**           | Program will **NOT compile** if not handled                                     | Program **will compile** even if not handled        |
| **Runtime Behavior**      | If not handled → compilation error                                              | If not handled → runtime crash                      |
| **Main Purpose**          | Force developer to write **safe code**                                          | Indicate **logical/programming errors**             |
| **Control by Programmer** | Often **outside programmer’s control**                                          | Mostly **in programmer’s control**                  |
| **Recovery Possible?**    | Usually **recoverable**                                                         | Usually **not recoverable easily**                  |
| **Program Stability**     | Helps make programs more **reliable**                                           | Can make program **crash suddenly**                 |
| **Example Situation**     | File not found, server not responding                                           | Dividing by zero, null access                       |
| **Use of `throws`**       | Commonly used                                                                   | Rarely used                                         |
| **Risk Level**            | Lower risk (handled beforehand)                                                 | Higher risk (happens suddenly)                      |
| **Mandatory Handling**    | Yes                                                                             | No                                                  |
