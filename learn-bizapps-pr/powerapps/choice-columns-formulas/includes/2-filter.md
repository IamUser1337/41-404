When you have a Dataverse table with choice column, you'll often want to filter the data by using a choice column. The most common filtering scenarios are:

- Filter the table rows for display in a gallery.

- Have a dropdown menu or combo box control with the list of choice values, and then let the user select one or more. Then, you can use the selected values to filter the table rows that you show in the gallery.

For example, if you had a **Category** choice field on the Accounts table, you could use the following logic to filter only the preferred customers:

```powerappsfl
Filter(
  Accounts,
  Category = 'Category (Accounts)'.'Preferred Customer'
)
```

Make sure that you don't only use the string 'Preferred Customer' (like the image below) because it's an invalid comparison. It will give you the error 'Incompatible types for comparison'. Since the 'Category' is a table (or option set) itself, you can't compare the table value with a text value. Therefore, you need to use the fully qualified reference: `'Category (Accounts)'.'Preferred Customer'` (also displayed as `[@Category].'Preferred Customer')`.

> [!div class="mx-imgBorder"]
> [![Screenshot of the invalid Power Fx formula of: Filter ( Accounts, Category = "Preferred Customer" ).](../media/invalid.png)](../media/invalid.png#lightbox)

Frequently, you'll want to use a dropdown menu or combo box so that users can determine the filtered values for the gallery. In the following example, a combo box is used to allow multiple selections of categories of accounts to show.

> [!div class="mx-imgBorder"]
> [![Screenshot of a partial account information form, showing a dropdown list with multiple categories selected: Standard and Preferred Customer.](../media/categories.png)](../media/categories.png#lightbox)

First, you add a combo box to the screen and then set the **Items** property by using the [Choices function](/power-apps/maker/canvas-apps/functions/function-choices/?azure-portal=true).

> [!div class="mx-imgBorder"]
> [![Screenshot of the following expression as a formula for the Items property: Choices(Accounts.Category).](../media/choices.png)](../media/choices.png#lightbox)

The Choices() function prepares a list of values for your user to select from by using the metadata for the choice column **Accounts.Category**.

Next, you'll modify the **Items** formula for the gallery to include using the combo box **SelectedItems** property.

`Filter(Accounts, Category in ComboBoxCategory.SelectedItems)`

Using the **in** operator allows the formula to filter on any of the selected categories.

This formula will only show rows in the gallery when at least one category is selected. If you want to show all rows when no categories are selected, you could add an **IsEmpty** check to your formula.

```powerappsfl
Filter(
  Accounts, Category in ComboBoxCategory.SelectedItems
  || IsEmpty(ComboBoxCategory.SelectedItems)
)
```

## Filter choices columns

Filtering table rows on a choices column is complicated by how the data is stored in Dataverse as a comma-separated list. As a result, any filter that you compose that involves a choices column will receive a [delegation](/power-apps/maker/canvas-apps/delegation-overview/?azure-portal=true) warning, as illustrated in the following example.

> [!div class="mx-imgBorder"]
> [![Screenshot of the formula Filter(Accounts,Text(Dropdown1.Selected.Value in 'Preferred Delivery').](../media/filter.png)](../media/filter.png#lightbox)

One approach that you could take is to create a Dataverse table view that filters the choices values and then uses it in your Filter() function criteria. This approach would help you avoid the delegation challenge, but it won't allow the app user to provide the filter criteria values. The following screenshot shows an example of a Dataverse view filter for the **Preferred Delivery** choices column.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Dataverse view edit filter criteria that shows filtering on the Preferred Delivery choices column.](../media/edit.png)](../media/edit.png#lightbox)

You could use this Dataverse view named **Monday Delivery** by using the following Filter() function:

```powerappsfl
Filter(
  Accounts,
  'Accounts (Views)'.'Monday Delivery'
)
```

Additionally, you can still include user-entered criteria for other columns than the view. For example, the following Filter() function shows the addition of the **Category** choice column, which is filtered on the value that the user selected from the dropdown list.

```powerappsfl
Filter(
  Accounts,
  'Accounts (Views)'.'Monday Delivery',
  Category = Dropdown1.Selected.Value
)
```

Because of their standardized list of values, choice and choices columns are useful in providing consistent ways to filter table rows.
