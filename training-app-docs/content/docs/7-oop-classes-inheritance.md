---
weight: 7
title: "7. Classes and Inheritance"
description: ""
draft: false
toc: true
---


 ## Creating & Instantiating Classes
  1. Open the file `Computer.java` under the directory (folder) `Classes`.

  At the top of this code (line 3), it has the following statement:
  ```java
  public class Computer {
  ```
  Breaking it down word for word, we get:
  - **Public**: Everything in your Java program can see / use it.
  - **class**: This new thing is going to be a *class*.
  - **Computer** The name of this class is going to be "*Computer*".
  - After these words, the pair of `{}` brackets (one after `Computer` and one at the end of the document, before `public class ComputerMain`) show that all the code within these blocks is a part of our class.

  This is how we define our class, `Computer`. It is fairly simple syntax.

{{< details title="Why do we have public class ComputerMain at the end of the file?" closed="true" >}}
In Java, all functions (which are what you can put code in) must be a part of a class.

  We will learn more about these functions, formally called "methods", but for now just understand that we need the function running our code to be in a special class that is marked to run the code.

  You can also look at our previous code in other files to see that they all have classes as well, and the specially marked `public static void main(String[] args) function`.
{{< /details >}}


  Creating a new `Computer` is easy; all you need to do is create an new variable.

  1. In the `main` function of the `ComputerMain` class (which will be referred to as just "the main function"), create a new variable of type `Computer`.
  2. On the right side of the equal sign, type: `new Computer();`

{{< details title="Click for Solution" closed="true" >}}
```java
  Computer myPC = new Computer();
```
{{< /details >}}

  The variables of a class are called "instances" of the class, and the process of creating an instance is formally called "instantiation".

  Now you can create your own class!

  1.  Create a new file in `Classes`. Name it with a captial letter at the start of each word, with no spaces. (CamelCase)
  - This is to be sure that you can properly create the class, as all Java files have to have at least one class in them with the same name as the file.
  2. Create a new class. Name it whatever you want. (This will be *your* class to make any object you want! Try to keep it something more generic, so we can add more specific examples of the class "extending" it.)
  3. Create a second new class. Name it "`[whatever your first class is named]Main`".
  - *Inside the second class*, copy & paste this exact function in.
  ```java
  public static void main(String[] args) {

    }
  ```
  4. Instantiate (create a variable of your class) in the main function you pasted.

  ## Inheritance
  During the explanation of Object Oriented Programming, we included a "tree" of computer and alike things. The idea of "subclasses", which were objects with similar traits to the classes above them, is the soul of inheritance in Java. Inheritance is the idea that classes can be extended to have newer traits, while reusing functions & variables from their parent class.

  There are a few specific terms in OOP related to inheritance:
  - **Inherit** or **Extend**: The action of a class taking some traits from another class, while adding its own traits.
  - **Parent**: The class something inherits from.
  - **Children**: All the classes inheriting from a class.
  - **Class Hierarchy**: The entire representation of classes inheriting eachother. (Also known as a class tree)
  - **Substitutability**: The idea that a child class can effectively replace its parent where it is used. (For example, a `Calculator` can still be used as a `Computer` in code, but a `Calculator` has more / different functionality.)

  Inheriting classes is very easy in Java. First, create a new class. Then, after the class name & *before* the `{`, add `extends `[*parent class name*]` `. This should be done in a different / new file than the parent, because you are creating a new class. For example, open `Mobile.java`. On the third line, it shows how extending works syntactically.

  1. Create a new class, inheriting from your already-existing class.
  - The inheritance should make sense, as we will work with it for the remainder of the OOP course.

  ## Fields
  Fields are a fancy name for properties of a class. For example, for a "people" class, a field could be `String name` or `Color eyeColor`. For `Computer`, a field could be `int computationsRun`.

  Open `Computer.java`. At the beginning of the class, there is the line `int manufacturedYear;`. This is similar to how we would create variables in code before, except we don't have an equals-sign and the part afterwards. We are just stating what the variable's name and type, without any value in it. This is a field declaration.

  Fields can also be stated like a regular variable, with an equals sign and default value. This is nice to give default values, but later on we'll talk about constructors, which are more useful for setting starting values in objects.

  Fields are different from variables in the way that fields are tied to a specific object. For example, we can have a `Robot` class with a field `int teamNumber`. If we make two robots, `Robot robot1 = new Robot();` and `Robot robot2 = new Robot();`, and set their team numbers, `robot1`'s team number will be different than `robot2`'s team number, even if they're named the same thing.

  1. Add a "computations run" field to `Computer`.
  2. Add at least 2 fields to your custom parent class.

  The way we read & modify the class's fields is through using the class instance's name, followed by a period and then the desired field. For example, to print a `Computer`'s `prevAction` (the `Computer` is named `com`), you would put:
  ```java
  System.out.println(com.prevAction);
  ```
  To manually change `com`'s previous action, you could do:
  ```java
  com.prevAction = "cool thing";
  ```
  There is a major problem with the code block shown above; what if we're using it to change prevAction, even if we haven't done a new action? This problem of being able to access objects' fields and modify them wrongly is fixed with the idea of Encapsulation.

  1. Play around with changing the `Computer` and your parent class's fields externally. Try printing them, modifying them, etc.

  Fields in `Computer` will be existent on `Mobile` objects as well, and same with your two classes. You just won't be able to access these fields in the child classes yet, because we haven't specified that the child classes can access it yet. They still do exist, we just can't use them.

  