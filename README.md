# JavaSE-Interfaces

In Java, an interface is a way to achieve abstraction. 

It allows you to define a contract for a class without specifying the actual implementation. 

Here's a simple example to illustrate the concept:

```java
// Define an interface
interface Animal {
    void makeSound();
}

// Implement the interface in a class
class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof!");
    }
}

class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow!");
    }
}

// Main class to test the interface
public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();

        // Polymorphism: calling makeSound without knowing the actual class
        dog.makeSound();  // Output: Woof!
        cat.makeSound();  // Output: Meow!
    }
}
```

In this example:

Animal is an interface that declares a method makeSound.

Dog and Cat are classes that implement the Animal interface. They provide their own specific implementation of the makeSound method.

By using interfaces, you can achieve polymorphism. In the main method, you create instances of Dog and Cat but store them in variables of type Animal.

This allows you to call the makeSound method on each of them without knowing the specific type.

Interfaces also support multiple inheritance in Java, meaning a class can implement multiple interfaces. 

This flexibility allows you to design your classes in a modular and extensible way.


