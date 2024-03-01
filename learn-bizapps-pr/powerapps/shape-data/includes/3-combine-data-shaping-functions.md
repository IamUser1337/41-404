Power Apps offers the flexibility to combine multiple functions within a single formula to meet specific business needs. One powerful example is the fusion of Search and Filter functions to populate items for a gallery control.

In this scenario, the Filter function returns a table of data, which perfectly aligns with the requirements of the Search function's first parameter—a table of data. Using this, you can use the Filter function as the data source for your Search function. Implementing this formula within the Items property of your Gallery control enables users to view the data they need while having the added functionality of searching within that dataset. Here's an example formula:

```powerappsfl
Search(Filter(YourDataSource, State = "Ohio"), SearchInput.Text, "AddressLine1", "AddressLine2")
```

This formula filters the data source "YourDataSource" for rows where the State equals "Ohio." Then, within this filtered dataset, it searches for rows where either AddressLine1 or AddressLine2 contains the string entered in a text control. Moreover, if the text control is blank, it displays all the rows that matched the initial State filter.

When crafting formulas like this, it's a good practice to start small and gradually expand. Following a structured order of operations helps ensure accuracy. Here's the typical sequence to follow when building a formula:

1. **Filter the data source**: Begin with the primary filter condition, confirming that it returns the expected subset of data.
2. **Apply additional conditions or functions**: Gradually add more conditions or functions to further refine the filtered dataset.
3. **Validate each step**: Verify the results at each stage to ensure they align with your expectations.

This systematic approach helps in building complex formulas methodically and verifying that each step functions as intended.

> [!NOTE]
> The following steps are an example of combining formulas and not intended to work unless a datasource is provided.
> The exercise unit of this module provides step-by-step details.

1. Add a **Gallery** control to your canvas.

1. Add YourDataSource to the **items** property and configure the
    gallery to display the columns for your query. Confirm that you see the
    expected rows.

1. Change the **items** property of the **Gallery** control to use the
    **Filter** function and confirm that you see the expected rows.

   - Filter(YourDataSource, State = \"Ohio\")

1. Add a text input control to the screen and rename it to
    **SearchInput**

1. Change the **items** property of the **Gallery** control to use the
    Search function and confirm that you see the expected rows.

   - Search(YourDataSource, SearchInput.Text, "AddressLine1")

1. Add any other columns to the Search function and confirm you
    see the expected rows.

   - Search(YourDataSource, SearchInput.Text, "AddressLine1",
        "AddressLine2")

1. Now that you confirmed the two formulas are correct, combine
    the formulas and confirm that your results are correct.

   - Search(Filter(YourDataSource, State = \"Ohio\"),
        SearchInput.Text, \"AddressLine1\", \"AddressLine2\")

By breaking down the complex formula into smaller, working parts, you'll have a better experience creating an app. Within Power Apps, you can
utilize the concept of using one function to supply information to
another function in many places.
