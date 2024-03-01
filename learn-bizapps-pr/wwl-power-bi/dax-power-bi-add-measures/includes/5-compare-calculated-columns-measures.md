DAX beginners often experience a degree of confusion about calculated columns and measures. The following section reviews the similarities and differences between both.

Regarding similarities between calculated columns and measures, both are:

- Calculations that you can add to your semantic model.
- Defined by using a DAX formula.
- Referenced in DAX formulas by enclosing their names within square brackets.

The areas where calculated columns and measures differ include:

- **Purpose** - Calculated columns extend a table with a new column, while measures define how to summarize model data.
- **Evaluation** - Calculated columns are evaluated by using *row context* at data refresh time, while measures are evaluated by using *filter context* at query time. Filter context is introduced in a later module; it's an important topic to understand and master so that you can achieve complex summarizations.
- **Storage** - Calculated columns (in Import storage mode tables) store a value for each row in the table, but a measure never stores values in the model.
- **Visual use** - Calculated columns (like any column) can be used to filter, group, or summarize (as an implicit measure), whereas measures are designed to summarize.
