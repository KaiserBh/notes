Encapsulation is a feature of object-oriented programming that allows you to hide the implementation details of a class from other objects. This can be achieved by making the instance variables of the class private, and providing public methods to access and modify them.

Here is an example of encapsulation in Java:

```java
class BankAccount {
    private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        balance -= amount;
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount(1000.00);
        account.withdraw(250.00);
        account.deposit(100.00);
        System.out.println("Balance: " + account.getBalance());
    }
}

```

In this example, the `BankAccount` class has a private instance variable `balance` that stores the current balance of the account. It has three public methods: `getBalance`, which returns the value of the `balance` variable; `deposit`, which adds a specified amount to the `balance`; and `withdraw`, which subtracts a specified amount from the `balance`.

By making the `balance` variable private and providing public methods to access and modify it, the implementation details of the `BankAccount` class are encapsulated, and other objects cannot directly access or modify the `balance` variable. This helps to ensure the integrity and consistency of the data, as changes to the balance can only be made through the provided methods.