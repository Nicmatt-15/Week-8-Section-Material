# Tips for Take-Home Assessment 8

## Table of Content

1. [Document & Readability Checklist](#document--readability-checklist)
2. [Other Style Checklist](#other-style-checklist)
3. [Field Count](#field-count)
4. [Other Tips](#other-tips)

---

## Document & Readability Checklist

1. Header comment <ins>**in all three classes (Bear, Lion, Giant)**</ins>
2. Class comment <ins>**in all three classes (Bear, Lion, Giant)**</ins>
3. Method comment <ins>**in all three classes (Bear, Lion, Giant)**</ins>
4. Parameter comment <ins>**in all three classes (Bear, Lion, Giant)**</ins>
5. Return comment <ins>**in all three classes (Bear, Lion, Giant)**</ins>
6. Constructor comment (and parameter comment for it) <ins>**in all three classes (Bear, Lion, Giant)**</ins>
7. Proper indentation
8. Long lines (lines over 100 characters) should be broken into multiple lines
9. Blank lines between the closing curly bracket of one method and the next method comment
10. <ins>**Descriptive**</ins> and <ins>**camelCased**</ins> variable name

> No comment is needed for fields
> Method comment must describe the **specific** behavior of the Critter you are commenting on.
>
> For example, if you are describing the `getMove()` method in the Lion class, you should describe the pattern of the Lion's move instead of what `getMove()` does in general. Take a look at the example [here](https://edstem.org/us/courses/16200/lessons/27355/slides/154514/solution).

---

## Other Style Checklist

1. Add the `private` keyword to all your fields <ins>**in all three classes (Bear, Lion, Giant)**</ins>
2. Use a Random object if you need to simulate randomness.
3. Random object must be declared as a field so that it's not constantly being remade each time a method is called.
4. You don't need to use array in this Take-Home Assignment.
5. You should not have more fields than the amount specified below.

---

## Field Count

1. Bear class -> 2 fields
2. Lion class -> 3 fields
3. Giant class -> 1 field

---

## Other Tips

1. In all three classes, you may find keeping track of how many times the Critter has moved (how many times `getMove()` has been called) to be very useful.
2. For the Bear class, remember to save the `boolean polar` passed in the constructor to your field so you can use it in your methods.
3. For the Giant `toString()` method, the pattern resets after every 24 moves. You may find using `% 24` to be useful in your if/else-if/else conditionals.
4. For the Lion class, because of the random nature of the `getColor()` method and the high dependency with how many times the `getMove()` class has been called, it is best to determine the random number associated to the color of the Lion in the `getMove()` method and save it to a field.

   > The Lion `getColor()` will only have the conditional that maps the random number saved in your field with Color.RED, Color.GREEN, Color.BLUE.

   > Make sure to initialize the random number field in your constructor with a random number!

5. Remember, you cannot move multiple times at once. Your Critter can only move once when the client calls the `getMove()` method once.
6. Remember that the Bear `toString()` should start with forward slash `"/"` before the first move.
7. It is best to keep track how many times a Critter has moved starting from 0.
