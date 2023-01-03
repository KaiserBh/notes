A linked list is a linear data structure in which elements are stored in nodes and each node has a reference to the next node in the list. Linked lists are useful for creating data structures that need to be able to change size dynamically or that need to be able to store large amounts of data efficiently. Here is an example of a simple linked list implementation in Java:

```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class LinkedList {
    Node head;

    public void append(int data) {
        if (head == null) {
            head = new Node(data);
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = new Node(data);
    }

    public void prepend(int data) {
        Node newHead = new Node(data);
        newHead.next = head;
        head = newHead;
    }

    public void deleteWithValue(int data) {
        if (head == null) return;
        if (head.data == data) {
            head = head.next;
            return;
        }
        Node current = head;
        while (current.next != null) {
            if (current.next.data == data) {
                current.next = current.next.next;
                return;
            }
            current = current.next;
        }
    }
}

```

This implementation includes three basic operations: `append`, which adds a new node with the given data to the end of the list; `prepend`, which adds a new node with the given data to the beginning of the list; and `deleteWithValue`, which removes the first node with the given data from the list.


Example using object to store the data.

```java
class Node {
    Object data;
    Node next;

    public Node(Object data) {
        this.data = data;
        this.next = null;
    }
}

```

Then, we can create nodes that store any type of object, such as `String`s, `Integer`s, or even more complex objects like `Person` or `Car`.

```java
Node node1 = new Node("Hello");
Node node2 = new Node(123);
Node node3 = new Node(new Person("John", "Doe"));
Node node4 = new Node(new Car("Toyota", "Camry"));

```

Keep in mind that if we want to store objects of different types in the same linked list, you will need to use a wildcard type for the `data` field, like this:

```java
class Node {
    Object data;
    Node next;

    public Node(Object data) {
        this.data = data;
        this.next = null;
    }
}

```


One example where a linked list can be beneficial is when you need to store a large amount of data and you don't know how much space you will need ahead of time. Since a linked list grows dynamically as you add new elements, it can be a more efficient choice than an array, which has a fixed size.

Here is an example of a program that uses a linked list to store a list of integers that are read from the user:

```java
import java.util.Scanner;

class LinkedList {
    Node head;

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    public void append(int data) {
        if (head == null) {
            head = new Node(data);
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = new Node(data);
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        LinkedList list = new LinkedList();
        while (true) {
            System.out.print("Enter an integer (0 to stop): ");
            int n = scanner.nextInt();
            if (n == 0) break;
            list.append(n);
        }
        scanner.close();
        System.out.println("Elements in the list:");
        LinkedList.Node current = list.head;
        while (current != null) {
            System.out.println(current.data);
            current = current.next;
        }
    }
}

```

This program creates a linked list of integers and allows the user to enter as many integers as they want. The program will stop when the user enters `0`. The linked list is implemented using the `LinkedList` and `Node` classes shown earlier. The `append` method is used to add new elements to the end of the list.

When the user is finished entering integers, the program prints out the elements of the list by iterating through the nodes and printing the `data` field of each node.