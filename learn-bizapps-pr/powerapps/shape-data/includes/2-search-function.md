The Filter function excels at precise and typically fixed queries. However, if you're seeking a more adaptable approach, especially against string columns, the Search function becomes your go-to.

Imagine you have a search input box in your app where users can type a string. Using the Search function within your gallery allows for a dynamic query. It retrieves rows that contain the specified string anywhere within the column, offering a more flexible and versatile search functionality for your users.

An example would be if you wanted to do a partial string match on an
address column. If the column was a text column called Address and you
had a Text Input control in your app named SearchInput, then you could
use the following formula in the Items property of a gallery.

```powerappsfl
Search(YourDataSource, SearchInput.Text, "Address")
```

This would return all the rows where the Address column contained the
value entered in the **Text Input** control SearchInput. Another useful
behavior is if SearchInput is blank, meaning the user hasn't entered
any data, then all the rows from YourDataSource would be returned.
This makes the Search function powerful and easy to use.

The Search function can also be used to search across more than one
column. To have the previous example also search in the text column
City, you would update the formulas as follows.

```powerappsfl
Search(YourDataSource, SearchInput.Text, "Address", "City")
```

By adding a comma, and then an extra text column, you're now
searching a second column. You can add as many extra text columns
as needed.
