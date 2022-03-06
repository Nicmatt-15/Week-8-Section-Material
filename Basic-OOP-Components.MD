# Basic Components in OOP

## Table of Content

1. [Method](#method)
2. [Fields](#fields)
3. [Constructor](#constructor)
4. [Combining Client and Implementer](#combining-client-and-impelementer)

---

## Method

A method in the context of _implementer code_ represents one functionality or **behavior** that your class have.

For example, if we are trying to create a human blueprint, here is the list of methods that we could add:

```java
public class Human {
    // method 1
    public void eat() {
        //...
    }

    // method 2
    public void greet(String otherPersonName) {
        System.out.println("Hi there " + otherPersonName);
    }

    // method 3
    public String annoyed() {
        return "Stop annoying me!";
    }
}
```

> Note that these methods represents the "behavior" of our class. In this case, these methods tries to represent the behavior of a human in real life.

_Key Observations:_

1. Notice the lack of **_static_** keyword when you are declaring your method. You should not use static for reasons that are beyond the scope of this class.
2. You can still use any type of return that you want (or void) and include as much parameter as you need!

---

## Fields

Fields represents an identity or trait that your class have.

_Example:_

```java
public class Human {
    String name; // field 1
    int age; // field 2
    boolean wearGlasses; // field 3
    String catchPhrase; // field 4
}
```

> Note that these fields represents the "trait" of our class. In this case, these fields tries to represent the trait that a human in real life may have.

In a more general context, fields are used to:

1. Remember information that is needed in different methods since you do not have a main method to "store" and "remember" these values.
2. Remember information between multiple method calls of the same method.

---

## Constructor

The constructor is a special method that will get called **only once**. The constructor is <ins>ALWAYS</ins> the first method to be called every time an object is created. The purpose of a constructor is as follow:

1. <ins>**From the client perspective:**</ins> Allows the creation of the object itself. The constructor is a part of the blueprint the client calls to create an object.
2. <ins>**From the implementer persepctive:**</ins> Initializes the default or initial value for all fields.

Implementer Perspective:

```java
public class Human {
    String name; // field 1
    int age; // field 2
    boolean wearGlasses; // field 3
    String catchPhrase; // field 4

    // constructor
    public Human(String desiredName, int desiredAge) {
        name = desiredName;
        age = desiredAge;
        wearGlasses = false;
        catchPhrase = "I love turtles";
    }
}
```

Client Perspective:

```java
public class Demo {
    public static void main(String[] args) {
        Human humanOne = new Human("Eric Cartman", 10);
    }
}
```

Key Observation:

1. The syntax `new Human(...)` from the client side is actually calling the constructor of the Human class blueprint. This means that you need to include the appropriate value to send to the constructor's parenthesis.
2. Notice that the constructor takes in 2 parameters (a `String` for the human's name, and an `int` for the human's age). I have to provide this information when I am creating my object or calling `new Human(...)`.

   _In the example above, I provided `"Eric Cartman"` as the human's name and `10` as the human's age._

---

## Combining Client and Impelementer

Our complete Human class will look like the following:

```java
public class Human {
    String name; // field 1
    int age; // field 2
    boolean wearGlasses; // field 3
    String catchPhrase; // field 4

    // constructor
    public Human(String desiredName, int desiredAge) {
        name = desiredName;
        age = desiredAge;
        wearGlasses = false;
        catchPhrase = "I love turtles";
    }

    // method 2
    public void greet(String otherPersonName) {
        System.out.println("Hi there " + otherPersonName);
    }

    // method 3
    public String annoyed() {
        return "Stop annoying me!";
    }
}
```

Our client side:

```java
public class Demo {
    public static void main(String[] args) {
        // Creating a Human object
        Human prototypeOne = new Human("Eric Cartman", 10);

        // Asking the Human object to greet by calling
        // the greet method
        prototypeOne.greet("Nicolas");

        // Accessing the field of the Human object
        String humanCatchPhrase = prototypeOne.catchPhrase;
        System.out.println(humanCatchPhrase);

        // Getting the phrase if the Human object is annoyed
        String annoyedPhrase = prototpyeOne.annoyed();
        System.out.println(annoyedPhrase);
    }
}
```

Running the client code, we will have the following output:

```
Hi there Nicolas
I love turtles
Stop annoying me!
```
