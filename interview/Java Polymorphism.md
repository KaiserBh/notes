Polymorphism is a feature of object-oriented programming that allows a single interface to be used for multiple implementations. This can be achieved through inheritance, where a subclass can override the methods of its superclass, or through the use of interfaces, where an implementing class can implement multiple interfaces.

Here is an example of polymorphism in Java through inheritance:

```java
class Animal {
    public void makeSound() {
        System.out.println("Some animal sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Bark!");
    }
}

class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal();
        animal.makeSound();

        Animal dog = new Dog();
        dog.makeSound();

        Animal cat = new Cat();
        cat.makeSound();
    }
}

```

This code defines a superclass `Animal` with a `makeSound` method, and two subclasses `Dog` and `Cat` that override the `makeSound` method. When the `makeSound` method is called on an instance of `Animal`, the superclass implementation is called. However, when it is called on an instance of `Dog` or `Cat`, the overridden implementation in the subclass is called instead.

This allows for a single interface (in this case, the `makeSound` method) to be used with multiple implementations, depending on the type of object it is called on.