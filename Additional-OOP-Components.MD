# Additional OOP components

## Table of Content

1. [Encapsulation](#encapsulation)
2. [`this.` Keyword](#this-keyword)
3. [`.toString()` Method](#tostring-method)
4. [Inheritance](#inheritance)
5. [Overriding](#overriding)

---

## Encapsulation

Notice that in the example [here](Basic-OOP-Components.MD#combining-client-and-impelementer), you can see that the client can freely acccess and manipulate the value of the fields.

This poses a security threat if someone wants to create a malicious client field to mess up our implementer code. To avoid this, we will add the keyword `private` before we decalre each field.

The keyword private prevents the client code from accessing the client code.

Example:

```java
public class Human {
    private String name; // field 1
    private int age; // field 2
    private boolean wearGlasses; // field 3
    private String catchPhrase; // field 4
}
```

---

## `this.` Keyword

Take a look at the example below:

```java
public class Human {
    private String name; // field 1

    /**
     * Initialize an object / instance of Human with the client disired name
     * @param name - passes a String from the client to be used
     *               as the Human object's name
     */
    public Human(String name) {
        name = name;
    }
}
```

Notice that in the constructor above, we are trying to set the field `String name` to the value `String name` passed by the parameter. However, since both variable has the same name, Java could not differentiate which `name` refers to which varibale in the statement `name = name;`

To avoid this confusing, we will add `this.` keyword before `name` to indicate that we are referring to the field instead of the parameter. Our statement should now look like the following:

```java
public Human(String name) {
    this.name = name;
}
```

> You can avoid using the `this.` keyword by not using the same name between your field and parameter.

---

## `.toString()` Method

Take a look at the following implementer code:

```java
public class Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }
}
```

and the client code:

```java
public class Demo {
    public static void main(String[] args) {
        Human prototypeOne = new Human("Nicolas");
        System.out.println(prototypeOne);
    }
}
```

The output when we run the client code will be:

```
Human@2f0e140b
```

Notice that the output that we recieved from printing our Object is an information that we don't find useful. To avoid this, we have to declare a special method in our implementer side. The method is called a `toString()` method!

The declaration of the `toString()` method has to be exactly the same as the following:

```java
public String toString() {
    // return a String here that you want to display when the object is printed
}
```

---

Take a look at our <ins>**updated**</ins> implementer code:

```java
public class Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }

    // toString method
    public String toString() {
        return "I am a human and my name is " + this.name;
    }
}
```

Client code:

```java
public class Demo {
    public static void main(String[] args) {
        Human prototypeOne = new Human("Nicolas");
        System.out.println(prototypeOne);
    }
}
```

Ouput:

```
I am a human and my name is Nicolas
```

---

## Inheritance

The term inheritance is synchronous with the term <ins>**parent**</ins> and <ins>**child**</ins>.

The way inheritance in Java work is like the following analogy:

> Imagine if there is a mother (a parent) and a child. While they are walking, someone wants to fight the child. However, the child does not know how to fight, so the child calls their mother (their parent) to fight for them.
>
> The same idea works in Java. You'll have at least two different classes where one of them is the parent and one of them is the child class. If the client tries to call a method that does not exist in the child's class, the child class can call it's parent's method that the client wants.

Take a look at the class below:

```java
public class Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }

    public Human() {

    }

    public void greet() {
        System.out.println("Hi!");
    }
}
```

Here is our second class:

```java
public class Nicolas extends Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }
}
```

Client code:

```java
public class Demo {
    public static void main(String[] args) {
        Nicolas someNicolas = new Nicolas("Nicolas Matthew");
        someNicolas.greet();
    }
}
```

Output code:

```
Hi!
```

Key observations:

1. We have 2 blueprint / classes, the `Human` class and the `Nicolas` class.
2. The `Nicolas` class is the child class of the `Human` class. We know this because of the syntax:

   ```java
   public class Nicolas extends Human
   ```

   The above syntax indicates that the `Nicolas` class is an extension of the `Human` class.

3. The `Nicolas` class does not have any method in it. However, the client is trying to call the greet method for a Nicolas object.
4. The `Nicolas` class (child class) calls the `Human` class (parent class) greet method and the `Human` class `greet()` method prints out `"Hi!"` into the console.

---

## Overriding

Take a look at the `Human` class again:

```java
public class Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }

    public Human() {

    }

    public void greet() {
        System.out.println("Hi!");
    }
}
```

and our modified `Nicolas` class:

```java
public class Nicolas extends Human {
    private String name;

    public Human(String name) {
        this.name = name;
    }

    public void greet() {
        System.out.println("Sup, dawg!");
    }
}
```

and our previous client code:

```java
public class Demo {
    public static void main(String[] args) {
        Nicolas someNicolas = new Nicolas("Nicolas Matthew");
        someNicolas.greet();
    }
}
```

Output code:

```
Sup, dawg!
```

Key observations:

1. The `Nicolas` class (child class) declares the <ins>**same exact method**</ins> (_the `greet()` method_) as the parent's class.
2. When the client tries to call the `greet()` method of the child's class, now the child will use its `greet()` method instead of the parent's `greet()` method.

   > This is indicated by the output of the client code chaging from `Hi!` to `Sup, dawg!`, the message that we print in the Nicolas class `greet()` method.

3. In order for overriding to work properly, the method in the child class must follow these criterias:
   1. The same method <ins>**name**</ins> as the one in the parent class.
   2. The same method <ins>**return type**</ins> as the one in the parent class.
   3. The same <ins>**amount, type, and orders of parameters**</ins> as the one in the parent class.
