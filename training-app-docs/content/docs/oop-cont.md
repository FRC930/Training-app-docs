---
weight: 7
title: "7. Object Oriented Programming Continued"
description: ""
icon: "article"
date: "2026-06-25T18:24:05-05:00"
lastmod: "2026-06-25T18:24:05-05:00"
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
  - **Public**: Everthing in your Java program can see / use it.
  - **class**: This new thing is going to be a *class*.
  - **Computer** The name of this class is going to be "*Computer*".
  - After these words, the pair of `{}` brackets (one after `Computer` and one at the end of the document, before `public class ComputerMain`) show that all the code within these blocks is a part of our class.

  This is how we define our class, `Computer`. It is fairly simple syntax.

  <details>
  <!--67!!!!!!!!-->
  <summary>Why do we have "public class ComputerMain" at the end of the file?</summary>
  In Java, all functions (which are what you can put code in) must be a part of a class.

  We will learn more about these functions, formally called "methods", but for now just understand that we need the function running our code to be in a special class that is marked to run the code.

  You can also look at our previous code in other files to see that they all have classes as well, and the specially marked `public static void main(String[] args) function`.
  </details>

  Creating a new `Computer` is easy; all you need to do is create an new variable.

  1. In the `main` function of the `ComputerMain` class (which will be referred to as just "the main function"), create a new variable of type `Computer`.
  2. On the right side of the equal sign, type: `new Computer();`
  <details>
  <summary>Click for solution.</summary>
  Computer myPC = new Computer();
  </details>

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

  ## Access Modifiers

  Access modifiers are things that change what parts of the code can see a class's fields. There are three basic ones:
  - `public`: *All* of your Java code can see this field. This doesn't have much use in fields, but we will see it used nearly all the time in methods. It is also seen before `class` in many places.
  - `protected`: Only classes inheriting your class can see this field. This is scarcely used, but can be good to demonstrate simple encapsulation before using methods.
  - `private`: Only the code & methods inside this class can see the variable. This is similar to the default option (nothing), except in the default option you can modify the field anywhere in the same *file*, where with `private` you can only modify the field in the `class`.

  Access modifiers are placed before a variable's type. For example:
  ```java
  public int coolNum;
  ```
  is a public integer of a *really cool number*.
  ```java
  private int notCoolNum;
  ```
  is a private integer of a not-so-cool number.

  1. Fix the fields in `Computer` to be `protected`. (For now!)
  2. Fix the fields in your parent class to be `protected` as well. 

  ## Methods
  1. Open `Computer.java`.

  In short, methods are just functions that are specific to a class object. Methods can be thought of "actions" an object can do. For example, calculators can add or subtract, and people can talk.

  The only thing different between methods and functions is that functions don't need a class; they just do something independt of objects. They may take in or return them, but they don't belong to objects. Methods, on the other hand, are parts of Objects. They need a specific object to be able to work, as they are a part of it. They may be able to read or change parts of the object.

  Because of how Java is **absolutely** Object-Oriented, literally *everything* in Java is an object. This means that all functions also need to be part of objects / classes. This is why we define our functions still inside the class. We will talk about what `static` methods and functions actually are later.

  ### Calling Methods
  To use methods, we use our normal function-calling syntax with an extra prefix: [*variable name*]`.`[*function*]. For example, calling the `add` method on our computer variable (**if the `Computer` variable were named *myPC***) would be `myPC.add(1,2);`.

  <details>
  <summary>Is this related to the periods in System.out.println("Hello!"); ?</summary>
  Yes, these periods in our print command do actually mean we're calling a method of the system class! We'll talk about why we use "System" (the class) directly later, instead of creating a System object.

  The reason we use a second period in the "System.out.println" statement is because "out" is similar to a class *inside* of System. Thus, the println method is a method of *out* (for output), which is a class inside "System".
  </details>

  1. In the main function, call the `add` and `subtract` methods on your `Computer`.
  - Remember these functions return values, so you should store them in variables or print them!
  <details>
  <summary>Solution</summary>
  The variable X represents your *Computer* variable. The numbers, variable names, actions, etc. are arbritrary.
  <br><br>
  int mySum = X.add(5,7);
  int mySub = X.sub(mySum, 2);
  System.out.println(mySub);
  </details>

  ### Creating methods

  Inside our `Computer` class, we see the definitions of the two methods `add` and `subtract`. These definitions are incredibly similar to regular function definitions. The only thing they're missing is the `static` part, which differentiates between functions (with `static`) and methods (without `static`).

  Access modifiers (`public`, `private`, `protected`) can also be used on methods, alike fields. We have been using always `public` so that we are able to call the methods from outside the class, but you could also have internal utility functions that are `private`.

  1. Following how `add` and `subtract` were defined in `Computer`, create `multiply` and `divide`.
  2. Call these methods in the main function of `Computer.java` using an instance of the class.

  <details>
  <summary>Solution #1</summary>
  public int multiply(int x, int y) {
    return x * y;
  }

  public double divide (int x, int y) {
    return x / y;
  }
  </details>
  <details>
  <summary>Solution #2</summary>
  Computer x = new Computer();
  <br>
  ...
  <br>
  System.out.println(x.multiply(5,2));
  System.out.println(x.divide(6,7));
  </details>

  1. Add and call your own 3 methods in your parent class.
  - Remember to *call* the methods outside the class, inside of the main function.

  ### Methods in methods

  Methods can be called inside of other methods. The way we would need to do that is put the name of the instance, then a period and the function, right? But, since we're in the definition of the class, we have no idea what the class instance is going to be called!

  To counter this, Java provides a default name for the current instance for use in methods. The keyword `this` refers to the current instance a method is running on For example, if we were to add a new method to `Computer` using another method, we could put:
  ```java
  public void printAdd(int x, int y) {
    System.out.println(this.add(x,y));
  }
  ```

  1. In your parent class, add another method that uses one of your previously made methods.

  ## Encapsulation & Modifying Fields in Methods
  Even though we learned about the access modifiers, actually using them seems to be fairly silly. We can make the fields private, but then we can't do anything with them yet. Well, when the fields are private, we can still modify them inside of methods in the class!

  The syntax for modifying a field inside a method is similar to calling another method within a method.

  1. Open and observe `Classes/Counter.java`'s syntax.
  2. Add value decrement & value doubling methods.

  We can see here, the syntax for getting & modifying a field is similar to how you would do it outside, but using Java's helpful `this` keyword to refer to the class itself.

  ### Why use methods to "hide" variables?
  Return to our previous problem before using methods; any code can just modify variables in any way we want. Using methods and access modifiers to hide variables a bit better helps with this problem, as we can define in our methods how exactly we will modify the variables. An example of this was in our `Counter.java`. We could only increment, decrement, and double our counter. This prevented weird actions such as setting the count to a random number or performing unwanted operations.
  <!--TAHRARAHRAHRHARHARHRARHAHRAHRUSDOFIHDSLKKKKJTW:Jthis must be so hard to understand what is going on, where is going on, how is going on, and why is going on-->

  ### Getters and Setters

  Getters and setters are specific names for methods that perform that exact purpose; they get and set a variable.

  ```java
  private int setMyVar(int n) {
    this.myVar = n;
  }
  public int getMyVar() {
    return this.myVar;
  }
  ```

  Using these types of methods allows you to easily fine-tune control to variables, and allows for checks that the value is legal before setting it.

  1. Change all of the `protected` variables to `private`s in `Computer` and your parent class, and use getters / setters where appropriate. 