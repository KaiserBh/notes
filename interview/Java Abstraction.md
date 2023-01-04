Abstraction is a feature of object-oriented programming that allows us to focus on the essential features of an object, and ignore the non-essential details. This can be achieved through the use of abstract classes and methods, which are defined by a set of essential characteristics, but do not provide a complete implementation.

Here is an example of abstraction in Java:

```java
abstract class Animal {
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

    public abstract void makeSound();
}

class Dog extends Animal {
    public Dog(String name) {
        super(name, 4);
    }

    @Override
    public void makeSound() {
        System.out.println("Bark!");
    }
}

class Cat extends Animal {
    public Cat(String name) {
        super(name, 4);
    }

    @Override
    public void makeSound() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog("Fido");
        dog.makeSound();

        Animal cat = new Cat("Fluffy");
        cat.makeSound();
    }
}

```

In this example, the `Animal` class is an abstract class that defines the essential characteristics of an animal: a `name` and a `numLegs`. It also has two concrete methods: `getName` and `getNumLegs`, which return the values of these variables.

The `Animal` class also has an abstract method `makeSound`, which is defined but does not have an implementation. This means that the `Animal` class cannot be instantiated, as it is not a complete implementation.

The `Dog` and `Cat` classes are concrete subclasses of `Animal` that provide an implementation for the `makeSound` method. This allows them to be instantiated and the `makeSound` method to be called on them.

By using abstraction, we are able to focus on the essential features of the `Animal` class (the `name` and `numLegs` variables, and the `makeSound` method) and ignore the non-essential details of the implementation. This allows us to create a common interface for different types of animals, without having to worry about the specific implementation details of each type.