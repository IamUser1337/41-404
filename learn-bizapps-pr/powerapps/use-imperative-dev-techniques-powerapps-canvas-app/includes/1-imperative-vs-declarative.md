After completing the previous recommended learning paths, you should have a solid
foundation with Power Apps. In this learning path, you will learn some of
the more advanced concepts that Power Apps supports.

This module includes some concepts that might appear to be very developer focused but do not worry. The goal is to help you understand and apply some of these concepts to build better apps.

Imperative versus declarative
--------------------------

There are two main ways to do development, imperative and declarative. In imperative development, the focus is on how to achieve the goal. With declarative, the focus is on getting the result. Imperative provides more flexibility because you control every step in the process, but that means more code and more complexity. Declarative is much simpler and straightforward to use but can lack the ability to have the complete control that you might want.

### Imperative

To better understand imperative programming think about the sandwich that you want for lunch. In imperative programming, you focus on creating the sandwich in your "code". You go to the kitchen, get the ingredients, put the sandwich together, and then send it to the user. You spend a lot of time on the steps, but you have all of the specific functions you want to make it exactly the way you want. No tomatoes? No problem. In a completely made up programming language your code might look something like this.

Function Create Sandwich

{
Go to kitchen;

Get ingredients;

Remove tomato;

Assemble sandwich;}

Function Send Sandwich

{
Destination Mouth;}

As you can see, there are lots of steps in the process, but you get a
sandwich exactly the way you want. This is the approach you will see in
languages like C# or other popular coding languages. The focus is on
pushing the data.

### Declarative

For declarative programming, think of the same scenario, your sandwich for lunch. The difference is now you are focused on producing the sandwich, not how to make a sandwich. This is much less complex, but you might also run into the issue with tomatoes. If the function you use to get the sandwich doesn't support the option of no tomato you are out of luck. Your code may be as straight forward as follows.

GetSandwich(Kitchen, Mouth)

That made up function takes two inputs, where to get the sandwich from
and where to send it. There was no option to remove tomatoes. It would
be up to the creator of the GetSandwich function to add an option for no
Tomato, which might look like this.

GetSandwich(Kitchen, Mouth, {Tomato: false})

Low-code tools like Excel use this approach to development. The focus is
on pulling data.

### Power Apps supports both imperative and declarative methodologies 

Power Apps has capabilities for both imperative and declarative logic. Throughout this training there has been a focus on declarative formulas. In the remainder of this module, the focus will be on imperative concepts and methodologies in Power Apps. The key component of imperative logic in Power Apps is variables.

The next unit will cover the different types of variables and how to use them in an imperative mode.
