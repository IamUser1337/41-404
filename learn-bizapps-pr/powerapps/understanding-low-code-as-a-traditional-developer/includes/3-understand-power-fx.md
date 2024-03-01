After that quick background on low code development, both you and Kiana have noticed similarities and differences between the programming languages you've traditionally used to build applications, like C# and JavaScript, and Power FX used in Power Apps.

Microsoft Power Fx is the low code language for expressing logic inside of canvas-based Power Apps. Power Fx is inspired by Microsoft Excel, and follows many of the patterns found in Excel expressions.

## Expressions and formulas

But you don’t just write expressions in Excel, you write formulas or recipes for how to calculate a specific cell’s value. A1 = B2 * 2 is a formula that defines the value of A1 at all times and is recalculated automatically as B2 changes.

Power Fx follows this same formula pattern. Cells are replaced with the properties of controls or objects. Here’s an example where we have taken this Excel formula from Stack Overflow for reverse string search:

![Excel with the formula: =RIGHT(A1,LEN(A1)-FIND("|",SUBSTITUTE(A1," ","|",LEN(A1)-LEN(SUBSTITUTE(A1," ","")))))](../media/excel-last-word.png)

And created a Power Fx formula from it. All that is different is that the references to cells have been replaced with references to control properties:

![Power Fx running inside of Power Apps with the formula: =RIGHT(Input.Text,LEN(Input.Text)-FIND("|",SUBSTITUTE(Input.Text," ","|",LEN(Input.Text)-LEN(SUBSTITUTE(Input.Text," ","")))))](../media/powerfx-last-word.gif)

Not only does this same syntax and same functions work in Power Fx, but notice something else in the animation. As Input.Text changes (the top box), Label.Text (the bottom box) is automatically recalculated. The app is behaving like a spreadsheet, recalculating all the time without requiring the app developer to add code that specifies how to make that happen.

## A declarative app model

Many traditional application development stacks feature an _imperative_ model for development across the stack. In other words, the app developer has to write code for everything that happens in the app: authentication & authorization, business logic, the user interface, server or cloud service configuration, and so on.

Power Fx is a declarative language, just as Excel is. The developer defines what behavior they want, but it's up to the system to decide how and when to accomplish it. To make that practical, most work is done through pure functions without side effects, making Power Fx also a functional language.

Here is another more colorful example that uses a formula for the Fill color of the screen. As the sliders that control Red, Green, and Blue are changed, the background color automatically changes as it's recalculated:

![Power Fx Formula: Fill = RGBA( RedSlider.Value, GreenSlider.Value, BlueSLider.Value, 100% )](../media/powerfx-slider.gif)

There are no OnChange events for the slider controls as would be common in other languages. In fact, there is no way to explicitly set the Fill property value at all. Which has a huge advantage: there is only one source of truth. If the color isn’t working correctly, you only need to look at one formula to understand why. You don’t need to search through your app to find a rogue piece of code that set the property at an unexpected time. In fact, there is no time element; the correct formula values are always maintained.

Note something else in the animation: as the sliders are set to a dark color the labels for Red, Green, and Blue change to white to match. This is done through a simple formula on each label control’s Color property:

```powerappsfl
If(
    BlueSlider.Value + GreenSlider.Value + RedSlider.Value < 150,
    White,
    Black
)
```

The logic for setting the label color is isolated from what is happening for the Fill color, these are two entirely different calculations. Instead of large monolithic procedures, Power Fx logic is typically lots of smaller formulas that are independent. That’s easier to understand and enables enhancements without disturbing existing logic.

Now there is a time and a place for imperative, step-by-step logic, and Power Fx offers a place for that logic too. Apps write back changes to databases and start automations with the press of a button, while spreadsheets do not do these things. Whenever possible, for all the benefits cited above and consistency with Excel, we favor the declarative approach.

> [!NOTE]
> You can find more information on using imperative development techniques in [Use imperative development techniques for canvas apps in Power Apps](/training/modules/use-imperative-dev-techniques-powerapps-canvas-app/?azure-portal=true).
