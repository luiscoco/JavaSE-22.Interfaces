# JavaSE-Interfaces

See the Udemy course: https://www.udemy.com/course/curso-certificacion-profesional-desarrollador-java-se-11

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

## More Advanced topics related to interfaces in Java.

### Default Methods
Starting from Java 8, interfaces can have default methods, providing a default implementation for a method. 

This allows you to add new methods to an interface without breaking the existing implementations.

```java
interface Vehicle {
    void start();

    void stop();

    default void honk() {
        System.out.println("Honking!");
    }
}

class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("Car starting...");
    }

    @Override
    public void stop() {
        System.out.println("Car stopping...");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start();
        car.stop();
        car.honk(); // Default method from the interface
    }
}
```

In this example, the Vehicle interface has a default method honk(). The Car class implements the Vehicle interface and inherits the default implementation of the honk method.

### Functional Interfaces

Functional interfaces have a single abstract method and can be used as the basis for lambda expressions. 

The @FunctionalInterface annotation is often used to ensure that the interface has only one abstract method.

```java
@FunctionalInterface
interface Calculator {
    int calculate(int a, int b);

    // Uncommenting the line below would result in a compilation error
    // int subtract(int a, int b);
}

public class Main {
    public static void main(String[] args) {
        // Using a lambda expression to implement the calculate method
        Calculator addition = (a, b) -> a + b;

        System.out.println("Result: " + addition.calculate(5, 3));
    }
}
```

### Static Methods:

Interfaces can also have static methods, which are associated with the interface itself, not with any instance of it.

```java
interface Helper {
    static void displayHelp() {
        System.out.println("Help is available!");
    }
}

public class Main {
    public static void main(String[] args) {
        Helper.displayHelp(); // Calling static method from the interface
    }
}
```

Here, the Helper interface has a static method displayHelp(), which can be called without creating an instance of the interface.

These advanced features enhance the flexibility and expressiveness of Java interfaces, allowing for more sophisticated designs and better support for evolving codebases.
