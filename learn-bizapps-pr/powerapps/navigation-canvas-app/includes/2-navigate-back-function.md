Let's look at how you can add arguments to the `Navigate` and `Back` functions to enhance the user interface in a Power Apps app. In the syntax, square brackets indicate optional parameters.

## Navigate function

Here's a breakdown of the `Navigate` syntax:

`Navigate(Screen [, ScreenTransition [, UpdateContextRecord ]])`

- `Screen` (required): The screen to display (or go to).

- `ScreenTransition` (optional): The visual transition to use between the current screen and the next screen. The default value is `None`.

- `UpdateContextRecord` (optional): A record that contains the name of at least one column and a value for each column. This record updates applicable context variables for the new screen.

In other words, you must include the first parameter to let Power Apps know which screen to go to. You can use the second parameter to define how the old screen visually changes to the new screen. You can use the third parameter to pass a context value to the new screen.

## Back function

Here's a breakdown of the `Back` syntax:

`Back([ScreenTransition])`

- `ScreenTransition` (optional): The visual transition to use between the current screen and the next screen. The default value is the inverse screen transition of the `Navigate` function that brought the user to the screen.

When you add `Back` to your app, it must include parentheses: `Back()`.

The `Back` function returns a user to the screen that the app most recently displayed. As the user goes to other screens, the app tracks the path of the screens and the transitions that it used. So, when the `Back` function runs, the inverse screen transition also runs. Your users can use the `Back` function to return all the way to the screen that appeared when they opened the app.

## Screen transitions

Let's look more closely at screen transitions, because they can be a part of both `Navigate` and `Back` formulas. These options are available in Power Apps:

- `ScreenTransition.Cover`: The new screen slides into view from right to left and covers the current screen.

- `ScreenTransition.CoverRight`: The new screen slides into view from left to right and covers the current screen.

- `ScreenTransition.Fade`: The current screen fades away to reveal the new screen.

- `ScreenTransition.None` (default): The new screen quickly replaces the old screen.

- `ScreenTransition.UnCover`: The current screen slides out of view from right to left and uncovers the new screen.

- `ScreenTransition.UnCoverRight`: The current screen slides out of view from left to right and uncovers the new screen.

## Examples

The following table gives a few examples of formulas that use transitions for both `Navigate` and `Back`. The table also includes some of the `UpdateContextRecord` parameters on `Navigate` examples, so you can visualize what they would look like in your app.

|     Formula                                                                       |     Description                                                                                                                                                                       |     Result                                                                                                                                                                                                                                                                                            |
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     `Navigate(Details)`                                                             |     Displays the `Details` screen with no transition or change in value for a context variable.                                                                                     |     The `Details` screen appears quickly.                                                                                                                                                                                                                                                             |
|     `Navigate(Details,   ScreenTransition.Fade)`                                    |     Displays the `Details` screen with a `Fade` transition. No value of a context variable is changed.                                                                                  |     The current   screen fades away to show the `Details` screen.                                                                                                                                                                                                                                       |
|     `Navigate(Details,   ScreenTransition.Fade, {ID: 12})`                          |     Displays the `Details` screen with a `Fade` transition. Updates the value of the `ID` context variable to `12`.                                                                    |     The current screen fades away to show the `Details` screen, and the context variable `ID` on the screen is set to `12`.                                                                                                                                                                             |
|     `Navigate(Details,   ScreenTransition.Fade, {ID: 12 , Shade: Color.Red})`    |     Displays the `Details` screen with a `Fade` transition. Updates the value of the `ID` context variable to `12`. Updates the value of the `Shade` context variable to `Color.Red`.    |     The current screen fades away to show the `Details` screen. The context variable `ID` on the `Details` screen is set to `12`, and the context variable `Shade` is set to `Color.Red`. If you set the `Fill` property of a control on the `Details` screen to `Shade`, that control appears as red.    |
|     `Back()`                                                                        |     Displays the previous screen with the default return transition.                                                                                                                |     The app displays the previous screen through the inverse transition of the transition through which the current screen appeared.                                                                                                                                                                      |
|     `Back(ScreenTransition.Cover)`                                              |     Displays the previous screen with the `Cover` transition.                                                                                                                         |    The app displays the previous screen through the `Cover` transition, regardless of the transition through which the current screen appeared.                                                                                                                                                            |

In summary, you can customize the `Navigate` and `Back` functions by taking advantage of their parameters. You can use the `Navigate` function to enable users to switch to another screen, but it's also possible to add a visual transition and even set context variables in the process. The `Back` function provides the inverse of any transition that got your user to the current screen, or you can define a transition. It's up to you to determine the user experience!

Up to now, you've used only the `OnSelect` function to add navigation to your app. In the next unit, you'll learn other ways to add app navigation.
