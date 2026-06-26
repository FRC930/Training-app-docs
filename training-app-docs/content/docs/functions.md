---
weight: 5
title: "5. Functions"
description: ""
icon: "article"
date: "2026-06-25T18:24:05-05:00"
lastmod: "2026-06-25T18:24:05-05:00"
draft: false
toc: true
---

 1. Open and run Functions.java.
 - What do you notice about the code?
 - What do you notice about the result?
 2. Break down what you see.
 ```
   This tells Java that we want a *function* in our class
   |     This tells Java we won't return anything
   |     |    This is what we name our function
   |     |    |     These parentheses include paramaters. (none)   
   v     v    v     v
 static void printHi(){
    // This is the code we are running
    System.out.println("Hello!");
 }
 ```
 - This breakdown uses unknown language like class, and paramaters, which we will learn later.
 3. Edit the code in the function.
 - Add some other println to the function. Remember, the code should be put in after the first println, but before the ending curly bracet (`}`).
 - Run the code, and see what happens.
 4. Functions make code easier to write and read.
 - Think back on the MathProblems.java you wrote. How could you improve this with functions?
 - You will need to learn one more thing about functions before you can rewrite MathProblems with functions.

### Parameters <!-- TODO: Continue Machines explanation -->
 1. Open Parameters.java, and run it.
 - What is different about the calls (the function name with parentheses) in main?
 - Change some of the numbers in the parentheses of the calls.
 - Look through the `square(int num)` function. What do you think it does?
 2. Change the square function into a multiply function.
 - While this may seem redundant (Why not just use `*`?), it is easy for practice.
 - Add another parameter into the square function, by adding a comma, and then another variable declaration.

<details>
<summary>Click for solution.</summary>
static void square(int num, int num2)
</details>

 - Rename the function by right-clicking on "square" and in the menu, clicking on "Rename Symbol".
 - Update all of the function calls to use this new paramater with a comma.

<details>
<summary>Click for solution.</summary>
<!--67!!!!!!!!-->
multiply(3, 6);
multiply(2, 9);
</details>

 3. Pass in some variables to `multiply()`.
 - Create some `int` variables in main.
 - Pass in the variables to the `multiply()` function, by just saying their name instead of a number. Example: `multiply(myNum,myNum2);`
 4. Try to pass in a decimal number (double or float) to multiply.
 - `multiply(2.3,6.1);`
 - The red squigglies on `multiply` read: `The method multiply(int, int) in the type ParametersSolution is not applicable for the arguments (double, double).` This is basically telling you that multiply *MUST* take in 2 ints, and cannot take in 2 doubles.
 5. Duplicate (copy & paste) multiply, and modify it to take in 2 doubles, and name it `multiplyDecimals`.
 - Try to change the `multiply(2.3,6.1);` into a `multiplyDecimals(2.3,6.1);`.
 4. Problem with functions currently:
 - What if you didn't want to just print out the result, but pass it into another function, or do something else rather than printing?

### Return Values <!-- TODO: Finish Machines explanation -->
 1. Open Return.java, and look through the code.
 - Run the code. What is it doing?
 - The `return` keyword is put at the end of the function running. It is when the function is done running, and it gives a result.
 - You can use the return value like a variable. This means, you can call the function wherever you would use a variable, even storing the return in a variable!
 2. Remove the variables, replacing them with function calls in the code.
 - Call `square(5)` and `square(2)` in place of squareFive and squareTwo in the println statement.
 - Try adding more `square()` calls in code, like another print statement.
 3. Assign the result from a `square()` to a float.
 - Before running, what do you think will happen?
 - Try fixing the function.
    - Remember - the paramater used in the template is a float.

<details>
<summary>Click for solution.</summary>
static float square(float num){
    //code
}
<br>
Turns into...
<br>
static int square(int num){
    //code
}
</details>