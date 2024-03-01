As a new Power BI user, you should know that there are two calculation languages: M and DAX. Both languages filter, manage, and visualize your data.

| Comparison | **DAX** | **M** |
|--|--|--|
| Why? | Calculations and analysis | Transformation and connections |
| Where? | Used in Power BI Desktop. | Used in Power Query Editor. |
| What? | Returns a single value, column, or table. Can make calculations using fields from many tables. | Controls shape of data when loaded into Power BI. Transforms one table at a time or combine tables. |
| Tableau comparison | Tableau calculations | Tableau Data Flow or transformation steps before making Tableau Extract. |

**Comparison between the two Power BI calculation languages: DAX and M.**

DAX defines calculations; DAX writes functions that build measures, calculated columns, and calculated tables.

> [!NOTE]
> Use DAX after your data has been imported into your data model.

> [!TIP]
> CORRELATING TO TABLEAU: As a Tableau analyst, the language that you are most familiar with is called MDX. Just like DAX, this language builds the calculated measures and dimensions in Tableau Desktop.

M is a query formula language that prepares data in the Power BI Query Editor before it gets loaded into the Power BI model.

By the end of this module, you'll be able to write functions that build measures, calculated columns, and calculated tables. You'll primarily be focused on DAX in this module and here are some of the DAX functions you'll be exploring:

- Filter functions

- Logical functions

- Mathematical functions
