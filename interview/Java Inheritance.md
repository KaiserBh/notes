Inheritance is a feature of object-oriented programming that allows a subclass to inherit the properties and methods of its superclass. This allows for code reuse, as the subclass can reuse the implementation of the superclass and can also override or extend it if necessary.

Here is an example of inheritance in Java:

```java
class Animal {
    protected String name;
    protected int numLegs;

    public Animal(String name, int numLegs) {
        this.name = name;
        this.numLegs = numLegs;
    }

    public String getName() {
        return name;
    }

    public int getNumLegs() {
        return numLegs;
    }
}

class Dog extends Animal {
    public Dog(String name) {
        super(name, 4);
    }
}

class Cat extends Animal {
    public Cat(String name) {
        super(name, 4);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("Fido");
        System.out.println("Dog name: " + dog.getName());
        System.out.println("Num legs: " + dog.getNumLegs());

        Cat cat = new Cat("Fluffy");
        System.out.println("Cat name: " + cat.getName());
        System.out.println("Num legs: " + cat.getNumLegs());
    }
}

```

In this example, the `Animal` class is the superclass, and the `Dog` and `Cat` classes are subclasses that inherit from it. The `Animal` class has two instance variables: `name` and `numLegs`. It also has two methods, `getName` and `getNumLegs`, that return the values of these variables.

The `Dog` and `Cat` classes are subclasses of `Animal` and inherit its properties and methods. They each have a single constructor that calls the constructor of the `Animal` class using the `super` keyword, and passes it the necessary arguments to initialize the `name` and `numLegs` variables.

In the `main` method, we create instances of the `Dog` and `Cat` classes, and call the inherited `getName` and `getNumLegs` methods on them. This demonstrates how the subclasses are able to reuse the implementation of the superclass and access its properties and methods.