Analysts use conditional formatting to adjust several options in the Format pane, including the color.

> [!TIP]
> The option to edit the title text is built into Power BI.

Colors in conditional formatting work similarly to the Color Marks card in Tableau. It can be broken out into three different types: color scale, rules, and field values.

## Use a color scale

Color scale determines whether the color is a continuous color or a diverging color. This scale is based upon a numeric value.

:::image type="content" source="../media/color-scale-vs-color-scale.png" alt-text="Diagram shows the color scale options are the same for Tableau and Power BI." lightbox="../media/color-scale-vs-color-scale.png":::

## Use rules

Rules are a new concept for Tableau analysts. Normally, you would have to create separate calculations with IF/THEN logic applied where you're associating a range of values to strings or numbers. Then, you drop the calculations onto the Marks card to change the color depending on those strings or numbers.

:::image type="content" source="../media/tableau-rules.png" alt-text="Screenshot shows an example of color formatting with rules in Tableau.":::

In Power BI, this functionality is built straight into the product. You can create a series of IF/THEN statements and associate them to a specific color. Also, you can change the order of the rules so that the rules are evaluated in a specific order.

:::image type="content" source="../media/power-bi-rules.png" alt-text="Screenshot shows rules as defined in Power BI." lightbox="../media/power-bi-rules.png":::

## Use field values

Field values are also a differentiator that allows you to use a color denoted in your data. For example, if you have a column that declares the color, it can interpret these values and convert them into color. You can use either natural language, like green, or code, like #00ff00.

> [!TIP]
> You can load companion files that declare certain colors within your data.
