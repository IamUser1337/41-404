As stated above, loops enable users to repeat blocks of actions until specific conditions are met and perform certain tasks on large amounts of data.

In this exercise, you'll apply loop actions to perform certain actions over multiple iterations and access the elements of a list.

Before starting, you should create two empty folders, named **PDF** and **DOCX**, inside the **My Documents** folder.

1. Deploy two **Get special folder** actions to retrieve the **Desktop** and **Documents** folder paths, respectively:

    ![Screenshot of the get special folder action properties dialog for Desktop.](..\media\get-special-folder-action-properties.png)

    ![Screenshot of the get special folder action properties dialog for Documents.](..\media\get-special-folder-action-properties-continued.png)

1. Use the **Get files in folder** action to retrieve all .pdf and .docx files from the desktop folder:

    ![Screenshot of the get files in folder action properties dialog for Desktop.](..\media\get-files-in-folder-action-properties.png)

1. Add a **For each** loop in order to loop through the list of retrieved files. The loop will iterate through each one of the retrieved files, storing it in the **%CurrentItem%** variable:

    ![Screenshot of the for each action properties dialog.](..\media\for-each-action-properties.png)

1. Within the loop, use the **If** and **Else** actions to determine whether the current file is a .pdf or a .docx file, and move it to the appropriate subfolder inside the **Documents** folder:

    ![Screenshot of the for each if workspace example.](..\media\for-each-if-workspace-example.png)

    1. Configure the two **Move file(s)** actions as presented in the following screenshots:

        > [!NOTE]
        > Το populate the **Destination path** field of the **Move file(s)** actions, you have to use a combination of variables and literal values. To find more information regarding variable concatenation and manipulation, see the [Handle variables in Power Automate for desktop](../../pad-variables/index.yml) module.

        ![Screenshot of the Move file(s) action that moves the pdf files.](..\media\move-files-action-pdf.png)

        ![Screenshot of the Move file(s) action that moves the docx files.](..\media\move-files-action-docx.png)

1. As before, retrieve all the .txt files from the desktop folder. To achieve this functionality, add a **Get files in folder** action outside the previously created loop.

    ![Screenshot of the get files in folder action properties dialog.](..\media\get-files-in-folder-action-properties-continued.png)

1. This time, instead of using a **For each** loop to cycle through each of the retrieved files, add a **loop** action to make use of the loop index. The loop will start at 0 and end after the number of iterations is equal to the number of files retrieved. To achieve this, use the list variable’s **count** property:

    ![Screenshot of the loop action properties select variable pop-out.](..\media\loop-action-properties-select-variable-popout.png)

    ![Screenshot of the loop action properties dialog.](..\media\loop-action-properties-continued-2.png)

1. Within the loop, add a **Write text to file** action to add the file index number to the contents of the .txt file. Since the **Loop** action only increases the loop index, the file in question will have to be retrieved using the **%Files%** variable and the loop index. To start counting the files from one and not zero, add one to the index number.

    ![Screenshot of the write text to file action properties dialog.](..\media\write-text-to-file-action-properties.png)

    
