To retrieve the paths of commonly used directories, which vary among different users and computers, use the **Get special folder** action. Under **Special folder name**, select the directory to retrieve, and its path will be displayed beneath. The action stores the path in a variable to use with other file and folder handling actions.

![Screenshot of the Get Special Folder action properties dialog.](..\media\get-special-folder-action-properties.png)

The following screenshot shows the numerous examples of special folders whose paths can be retrieved.

![Screenshot of the Special folder name parameter drop down.](..\media\get-special-folder-action-properties-continued.png)

Create new folders with the **Create folder** action. Specify the directory where you want to create the folder and the name of the new folder. For example, the **Create folder** action can reference the output of the **Get special folder** action.

The following screenshot shows that the previously retrieved special folder is used as the directory for the new folder, which will be named **Files**.

![Screenshot of the Create Folder action properties dialog.](..\media\create-folder-action-properties.png)

The output of this action is a Folder type variable and contains the attributes that are shown in the following table.

|Property|Variable Type|
|-----|-----|
|.CreationTime|Datetime|
|.Exists|Boolean value|
|.FullName|Text value|
|.IsEmpty|Boolean value|
|.IsHidden|Boolean value|
|.LastModified|Datetime|
|.Name|Text value|
|.RootPath|Folder|
|.FilesCount|Numeric value|
|.FoldersCount|Numeric value|
|.Parent|Folder|

To copy a folder to a different directory, use the **Copy folder** action. This action requires you to fill in the **Folder to copy** and **Destination folder** fields. As shown in the following screenshot, information in these fields can be provided as paths or as folder-type variables.

If a folder already exists with the same name as the one that you want to copy into the **Destination folder** field, use the **If folder exists** drop-down menu to set this option to **Overwrite** to overwrite the folder in the destination, or you can set it to **Do nothing**.

![Screenshot of the Copy Folder action properties dialog.](..\media\copy-folder-action-properties.png)

Similarly, you can copy a folder to a new destination with the **Move folder** action. Note that when you move rather than copy a folder, it is deleted from its original location. The folder to move and the destination folder are required inputs.

![Screenshot of the Move Folder action properties dialog.](..\media\move-folder-action-properties.png)

To rename a folder, use the **Rename folder** action, and then specify a folder to rename and a new name.

![Screenshot of the Rename Folder action properties dialog.](..\media\rename-folder-action-properties.png)

Delete folders by using the **Delete folder** action. Otherwise, if you want to delete only the contents of the folder rather than the actual folder, use the **Empty folder** action. Specify the folder by file path or variable.

To get a list of a folder's contents, use the **Get subfolders in folder** action. This action will retrieve a list of folders inside the specified (parent) folder and will provide as output a list of folders. Additionally, to filter the output by folder name, configure a **Folder filter**. Include additional layers of subfolders by selecting the **Include subfolders** check box.

![Screenshot of the Get Subfolders in Folder action properties dialog.](..\media\get-subfolders-in-folder-action-properties.png)

Set the action to fail if access is denied to any of the subfolders, or you can sort the output sequentially by three fields in the **Advanced** section. Selecting the **Descending** check box will sort the output by the selected field in descending order, as opposed to ascending order if the check box is cleared.

![Screenshot of the Get Subfolders in Folder properties dialog Advanced section.](..\media\get-subfolders-in-folder-properties-advanced-tab.png)
