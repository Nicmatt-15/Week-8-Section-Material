# Class vs Object

## What is a Class?

When we are talking about _implementer code_, a class is like a blueprint that the client can use .

_Example:_

```java
public class HumanNicolas {
    private String name;

    public HumanNicolas(String middleName) {
        name = "Nicolas " + middleName;
    }

    public String toString() {
        return name;
    }
}
```

> The class above is a blueprint that a client code can use to create the real _HumanNicolas_ object.

---

## What is an Object?

An object is an item in java that is created when you call the blueprint (_from a client code or another implementer code_). By creating the object, you can now utilize the object's functionality in your code.

Example of creating an object:

- Creation of a Scanner object
  ```java
  Scanner console = new Scanner(System.in);
  ```
- Creation of a PrintStream object
  ```java
  PrintStream fileOutput = new PrintStream("output.txt");
  ```
- Creation of a HumanNicolas object

  ```java
  HumanNicolas humanOne = new HumanNicolas("Matthew");
  ```

> **_Analogy:_** Imagine you have a blueprint of a car! You can't use the blueprint itself to get you from one place to another. You have to create the car itself using the blueprint and use the car to get you fromm one place to another.
