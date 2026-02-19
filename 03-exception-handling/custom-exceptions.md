# Custom Exceptions

- An exception created by the programmer according to the needs of the program.
- When Java’s built-in exceptions are not enough, we make our own exception.
- For Example, while checking the following conditions:
  - age < 18
  - insufficient balance
  - invalid pin
- In such cases, the user creates application specific exceptions to handle them.

### Creating a Custom Exception

1. Extend the Exception class.
  - Extend `Exception` class for checked Exceptions - must declare using `throws` and handle with `try-catch` statements.
  - Extend `RuntimException` for unchecked Exceptions - no throws needed.
2. Write the class with the method that contains the method that raises an exception.
3. Write the class with main method, that contains code to handle the exception.


```diff
+--------------------+
|   Custom Exception |
|  (Checked / Unchecked)
+--------------------+
           |
           | thrown by
           v
+--------------------+
| Method that throws |
|  the exception     |
+--------------------+
           |
           | propagates if not handled here
           v
+--------------------+
|     Main method    |
|   try { ... }      |
|   catch(...) { ... }|
+--------------------+
           |
           | handles the exception
           v
+--------------------+
| Program continues  |
|  safely or exits   |
+--------------------+
```


#### Custom Checked Exception

```java
class InsufficientBalanceException extends Exception {
    public InsufficientBalanceException (String message){
        super(message);
    }
}
class BankAccount {
    double balance = 5000;
    public void withdraw(double amount) throws InsufficientBalanceException {
        if(amount > balance) {
            throw new InsufficientBalanceException ("Not enough balance!!");
        }
        balance -= amount;
        System.out.println("Withdrawl successful. Remaining balance: "+balance);
    }
}
public class BankMain {
    public static void main(String[] args) {
        BankAccount account = new BankAccount();

        try {
            account.withdraw(7000);
        } catch (InsufficientBalanceException e){
            System.out.println("Exception : "+e.getMessage());
        }
    }
}
```

**Output**:

<img width="1325" height="117" alt="image" src="https://github.com/user-attachments/assets/1671b814-ee96-41e7-801e-3bf4b572fd7d" />


#### Cusstom Unchecked Exception

```java
class InvalidAgeException extends RuntimeException{
    public InvalidAgeException(String message){
        super(message);
    }
}
class VotingSystem {
    public void checkAge(int age){
        if(age < 18){
            throw new InvalidAgeException("Age must be 18 or above!");
        }
        System.out.println("Eligible to vote");
    }
}
class AgeMain {
    public static void main(String[] args){
        VotingSystem vote = new VotingSystem();
        vote.checkAge(16);
    }
}
```

**Output**:

<img width="1617" height="169" alt="image" src="https://github.com/user-attachments/assets/1ae11128-4cff-4fe4-bb5a-71e7c041f426" />

