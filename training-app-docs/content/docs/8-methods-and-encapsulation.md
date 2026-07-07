---
weight: 8
title: "8. Methods and Encapsulation"
description: ""
draft: false
toc: true
---

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

{{< details title="Is this related to the periods in the print statement?" closed="true" >}}

  Yes, these periods in our print command do actually mean we're calling a method of the system class! We'll talk about why we use "System" (the class) directly later, instead of creating a System object.

  The reason we use a second period in the "System.out.println" statement is because "out" is similar to a class *inside* of System. Thus, the println method is a method of *out* (for output), which is a class inside "System".
{{< /details >}}

  1. In the main function, call the `add` and `subtract` methods on your `Computer`.
  - Remember these functions return values, so you should store them in variables or print them!


{{< details title="Click for Solution" closed="true" >}}
  The variable X represents your *Computer* variable. The numbers, variable names, actions, etc. are arbritrary.
  <br><br>
  ```java
  int mySum = X.add(5,7);
  int mySub = X.sub(mySum, 2);
  System.out.println(mySub);
  ```
{{< /details >}}

  ### Creating methods

  Inside our `Computer` class, we see the definitions of the two methods `add` and `subtract`. These definitions are incredibly similar to regular function definitions. The only thing they're missing is the `static` part, which differentiates between functions (with `static`) and methods (without `static`).

  Access modifiers (`public`, `private`, `protected`) can also be used on methods, alike fields. We have been using always `public` so that we are able to call the methods from outside the class, but you could also have internal utility functions that are `private`.

  1. Following how `add` and `subtract` were defined in `Computer`, create `multiply` and `divide`.
  2. Call these methods in the main function of `Computer.java` using an instance of the class.

{{< details title="Solution #1" closed="true" >}}
  ```java
  public int multiply(int x, int y) {
    return x * y;
  }

  public double divide (int x, int y) {
    return x / y;
  }
  ```
{{< /details >}}

{{< details title="Solution #2" closed="true" >}}
```java
  Computer x = new Computer();
  <br>
  ...
  <br>
  System.out.println(x.multiply(5,2));
  System.out.println(x.divide(6,7));
```

 {{< /details >}}

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