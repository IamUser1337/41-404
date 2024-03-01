The concept of true and false is important to become familiar with when
using Microsoft Power Apps. When designing your app, the ability to effectively use
and apply true and false concepts will allow you to build a better
overall app. When you want to evaluate conditions in your app with the
**If** function, the results are either **true** or **false**. If you
want to filter the amount of data and or information returned based
on whether a condition is **true** or **false**, this is also
possible. Another place true and false is used is for setting some of
the control\'s properties within Power Apps. Every control, except a
screen, has a **Visible** property, the **Visible** property by default
is set to **true**. If you wanted to hide a control on the screen
you could simply set the **Visible** property to **false**. The
control will still be on the screen, but because the **Visible** property is
**false** no one will see it.

Note that when referencing **true** or **false** in Power Apps it is
always lower case. True and False are incorrect and will not work.

A common use of **true** and **false** is setting the **Visible**
property of a control based on a user's input. The following example
shows how to hide an **Icon** control based on the value of a
**Slider** control.

1.  Insert a **Slider** control onto the canvas. A **Slider** control
    lets users move a slider to define a number value. This is a great way to
    make an easier to use input, especially on mobile apps.

2.  Insert an **Emoji-Smile Icon** control.

3.  Set the **Visible** property of the **Icon** control to:
    **Slider1.Value >= 50**

4.  Preview the app and move the slider value up and down. When
    the value is greater than or equal to 50, the Emoji-Smile Icon will
    be visible.

This example introduces you to the concept of setting a **true** or
**false** property. Notice you did not have to use an **If** function to
control the value. The reason is the formula **Slider1.Value \>= 50**
evaluates to true or false. The **Visible** property accepts **true** or
**false,** so there is no need to check if the formula was true or
false.

As you use true and false another handy function to incorporate can be
the **Not** function. The **Not** function returns the opposite of the
true or false. Use the following example to better understand the
concept:

- 2 + 2 = 4 evaluates to true
- Not(2+2 = 4) evaluates to false

2 + 2 = 4 evaluates to **true**. The same way that 2 + 2 = 5 evaluates
to **false**. The **Not** function takes the outcome of the provided
logic and provides the opposite value. It is an awkward concept at first
but allows for the building of complex logic without complex code as you
become more comfortable with it.

Use the following example to build on the previous **Emoji-Smile**
icon example to complete your understanding of how to apply true and
false.

1.  On the same canvas insert an **Emoji-Frown Icon** control.

2.  Set the **Visible** property to: **Not(Icon1.Visible)**

3.  Preview the app and move the slider value up and down. When
    the value is greater than or equal to 50, the Emoji-Smile Icon will
    be visible and the Emoji-Frown icon is hidden. If the value is less
    than 50, the Emoji-Frown will be shown and Emoji-Smile is hidden.

Now you have a solution where the value is 50 or greater you
display a Smile and when it is less than 50 you see a Frown. This gives
your user a great visual clue and thanks to the true or false concept,
the **Not** function, and the ability to reference the value
of another control value, it makes it easy for you to create a solution. 
