Power Fx is the low-code language that is used throughout Microsoft Power Platform. It’s a general-purpose, strong-typed, declarative, and functional programming language expressed in human-friendly text. This ease of use enables a typical end-user to learn, understand, and work with Power Fx. 

Power Fx binds objects together like how formulas are created in Microsoft Excel. For example, in Microsoft Excel, you might use a formula to control what is displayed in a cell. Enter the formula **=IF(I45="Text","True","False")** into cell I46 and it displays its value based on the contents of cell I45. If cell I45 has the word Text, the formula displays the word True in I46. If I45 doesn't have the word Text in it, it displays False in I46. You can think of the **Visible** property of a UI control in a Canvas app in a similar way. By using the expression **If(IsBlank(“Property Name”.Text),false,true)** on a control called Asking Price, you're evaluating if a control called Property Name has any text in it. If it doesn't, the Asking Price control isn't displayed in the app. If it does, then the Asking Price Control is displayed in the app. As values in the canvas app change, the formula logic recalculates the value automatically, like how a spreadsheet does, which affects the control's visibility.

:::image type="content" source="../media/01-describe-bv-pp-03.png" alt-text="Screenshot that displays the code for a canvas app.":::

Power Fx is used throughout Microsoft Power Platform. Examples include: 

- **Power Apps:** As mentioned previously, Power Fx is the foundational language used when building Canvas apps in Power Apps. It's used to control almost every aspect of a canvas application, including:
    - defining when a control is visible
    - filtering the contents of a gallery
    - performing advanced calculations
    - and more

- **Microsoft Dataverse:** It can be used to build calculated columns in Dataverse tables. For example, in Dataverse, In Dataverse, you can create a table to store line items for sales orders. To calculate the total price of each line item, you can create a Power Fx formula that multiplies the current list price of the product by the quantity of product defined on the line-item record.

- **Copilot Studio:** Power Fx formulas are used when building out topics in Copilot Studio. They're used to do things like set variables, create advanced conditional logic, and more. For example, a restaurant can use Copilot Studio to build a copilot that can take customer reservations. Customers may only make reservations a maximum of 14 days in advance. Using Power Fx, you can verify that the reservation date requested by a customer is within the next 14 days. If it isn't, you can provide the user with feedback that they're not within our reservation window, and instructions for what to do next. 

The examples mentioned are only a few of the different ways that Power Fx can be used. Power Fx makes it easy for anyone to build powerful solutions on Microsoft Power Platform. 