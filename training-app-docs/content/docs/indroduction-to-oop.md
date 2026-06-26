---
weight: 6
title: "6. Introduction to Object Oriented Programming"
description: ""
draft: false
toc: true
---


### Why do we do OOP?
 1. Open Robots.java.
 - Look through the code. What is it doing?
 2. Drive the robot around some more.
 - Add more actions for the robot through functions, like turn or intake.
 3. Make another robot.
 - Rename the functions for the current robot by adding a label at the end, like 1.
 - Copy the functions, and edit them to specify that a different robot is doing the actions.
 - Rename the new functions so that you can specify which robot is doing what action in the code.
 - Set the speed for this robot, using a **new** integer variable.
 4. Add another action to both of the robots, with its own parameter.
 - An example would be turn, with a "degrees per second" parameter.
 - Create new variables for each of the robots with their turn speed, passed into the new function.
 #### What is the problem with our method currently?
 This code is becoming very hard to maintain! We need to copy and paste quite a lot. This would be incredibly difficult to run multiple robots simultaneously without interference.

 We need some other way to create and control multiple robots. Rather than manually creating all of the robots, we may just be able to make a robot factory of sorts, that makes multiple robots with ease. Object-oriented programming allows us to make these factories.
 ### What is it?
 Object-oriented programming is a style of programming used by many modern programmers and programming languages. It is actually the **main** style of coding in Java!

 Understanding object-oriented programming may be incredibly difficult at first, but once you start, you will quickly start to realize the benefits of this organization.

 The way object-oriented programming works is by organizing concepts in programming (like a robot, or a calculator) in to an object. These objects are also organized into trees like the one below.
 ```
            [    Computer     ]
           /         |         \
   [Mobile]       [Desktop]  [Calculator]
    /  \             /   \        |
 Phone Tablet     Laptop PC     TI-83
   |                |             |
 iPhone         MS Surface    TI-83 Plus
                                  |
                              TI-83 Plus CE
 ```
 As we can see, there is one overarching object, a computer. There are then classifications below it, such as mobile computer, desktop computer, etc. These classifications also have their own sub-classifications!

 These objects, or **class**ifications are called "Classes" in programming. Computers are a `class`, Desktop computers are a sub-`class` of computers.