In this exercise, you will develop a flow that prompts the user for their first and last name. The flow will then generate a username by using the first letter of the user’s first name, appended to their last name in lowercase. Then, the system will randomly generate a temporary password and display the output to the user.

## Tasks

For this exercise, you'll create a flow that will:

- Prompt a user to enter their first and last name.
- Split the two names into separate strings of text.
- Shift the two strings to lowercase.
- Get the first letter of the first name.
- Generate a password randomly.
- Display a message with the username and password.

## Steps

Select the **Display input dialog** action, and then follow these steps:

1. Set the **Title** property to **Name input** and the **Input dialog message** property to **Please enter your first and last name (for example, Norbert Varga)**. This action will display a message that prompts the user for input.

   ![Screenshot of the display input dialog action properties dialog.](..\media\display-input-dialog-exercise.png)

2. Use the **Split text** action to split the first and last name into two separate strings of text. In the **Text to split** field, enter **%UserInput%**.

   ![Screenshot of the split text action properties dialog.](..\media\split-text-exercise.png)

3. Select the **Change text case** action.

4. In the **Text to convert** field, enter **%TextList[0]%**.

5. With the index of a list type variable, provide the first item of the list, which will be the first name. Set the **Convert to** property to **lowercase**.

   ![Screenshot of the change text case action properties dialog.](..\media\change-text-case-exercise.png)

6. Add another **Change text case** action. This time, set the **Text to convert** property to **%TextList[1]%**, thus referencing the last name.

7. Set the **Convert to** property to **lowercase** again.

   The output is stored in a different variable than the previous **Change text case** action.

   ![Screenshot of the change text case action properties filled in.](..\media\change-text-case-exercise-continued.png)

8. Select the **Get subtext** action to get the first character of the first name.

9. In the **Original text** field, enter **%TextWithNewCase%** (the variable where the first name in lowercase is stored).

10. In the **Start index** section, set **Character position** to **0**.

11. In the **Length** section, set **Number of chars** to **1**. This setting will get the first character of the text string.

    ![Screenshot of the get subtext action properties dialog.](..\media\get-subtext-exercise.png)

12. To generate a random password, use the **Create random text** action. The action’s properties can be left at their default values.

    ![Screenshot of the create random text action properties dialog.](..\media\create-random-text-exercise.png)

13. Select the **Display message** action, which will display a message box with the new username and password. In the **Message box title** field, enter **Username & Password**, and in the **Message to display** field, enter the following content:

    ```c
    Hello, %UserInput%, your username is: %SubText%%TextWithNewCase2% Your temporary password is: %RandomText%
    ```

The username (first letter of first name, combined with last name) will be displayed and the result of the **Generate random text** action will show as the user’s password.

![Screenshot of the display message action properties dialog.](..\media\display-message-exercise.png)

The completed flow should look like the following figure.

![Screenshot of the completed flow.](..\media\completed-flow-workspace-exercise.png)
