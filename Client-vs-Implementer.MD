# Client vs Implementer

## What is a "Client Code"?

A client code is a code that generally has the following characteristics:

1. It can be run (it has a main method)
2. A code that utilizes other code. For example, in Assessment 1 - Assessment 7, your code may have used other code such as:
   1. Scanner.java
   2. String.java
   3. PrintStream.java
   4. File.java
   5. Random.java
3. The code that is "user-facing". The execution of your code is what the user would see.

> In Assessment 8, an example of client code is `CritterMain.java`

---

## What is an "Implementer Code"?

An implementer code is a code that generally has the following characteristics:

1. It has no main method (there is nothing to run)
2. It is built for the sole purpose of being used in another code
3. The code is "developer facing". Implementer code are usually read and utilized by another developer that is creating another implementer code or client code. (**It is very rare that a user is going to read your code**)

> In Assessment 8, there are a lot of implementer codes! Here are some of them:
>
> 1. Husky.java
> 2. Bear.java
> 3. Lion.java
> 4. Giant.java
> 5. Critter.java
