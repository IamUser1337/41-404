After your app is unpacked, you can store extracted formulas in the text files by using a subset of [YAML](https://yaml.org/?azure-portal=true). YAML is a human-friendly data serialization language. The goal is to simplify the process of reading and writing the source and determining the differences between the versions. Additionally, you can edit these files by using any text editor if you follow the Microsoft Power Fx YAML formula conventions that have been adopted.

The following label control is represented as YAML:

```yml
   LblAppName1 As label:
        Fill: =RGBA(58, 58, 58, 0)
        Height: =88
        Size: =27
        Text: ="Companies"
        Width: =Parent.Width - Self.X - IconSortUpDown1.Width - IconNewItem1.Width - IconRefresh1.Width
        Wrap: =false
        X: =20
        ZIndex: =2
```

YAML uses key/value pairs to represent the data, and it supports nesting of the pairs. For example, an item like **lblAppName1** can have indented key/value pairs for **Fill**, **Height**, **Size**, and so on. YAML uses indentation to determine structure. Spaces are used for indentation, but tabs are not allowed.

Three unique aspects of how Power Fx formulas are embedded in YAML:

-   **Controls are typed with the As keyword**. You can define label control, such as in the previous example, by using *lblAppName1 as Label:* expression. Normally, YAML has only a single name to the left of the colon (**:**) when you are providing a property value. However, nothing in the YAML specifications excludes more complex left-side expressions, and the Power Fx YAML syntax takes advantage of this omission to name the property and to provide its type.

-   **All formulas start with a leading equal sign**. Similar to Microsoft Excel, the equal sign (**=**) introduces a formula rather than a static value. You don't need to type the leading equal (**=**) sign in Power Apps Studio, but if you notice, it's always in the formula bar. Also, the leading equal (**=**) sign helps you avoid the normal data type interpretation that YAML does for static value, which is not appropriate for formulas.

-   **Some formulas must be expressed in YAML multi-line syntax**. If you have a formula that contains a string with an embedded **\#**, it's interpreted by YAML as the start of a comment; therefore, the rest of the line will be truncated. To avoid this occurrence, make sure that you express the formula by using YAML's multi-line syntax; most common is the use of the **\|** syntax.

For more information, see [Microsoft Power Fx YAML Formula Grammar](/power-platform/power-fx/yaml-formula-grammar/?azure-portal=true).

## Folder structure

When you unpack a canvas app, a [set of files and folders](/power-apps/developer/data-platform/powerapps-cli?azure-portal=true#folder-structure) will be created. After running the unpack process, you will find the following key files and folders:

- **\src** - The control and component files. This file contains the sources.

- **\*.fx.yaml** - The formulas that are extracted from the control.json file. This place is where you can edit your formulas.

- **CanvasManifest.json** - A manifest file that contains what is normally in the header, properties, and publishInfo.

- **\*.json** - The raw control.json file.

- **\EditorState\*.editorstate.json** - Cached information for Power Apps Studio to use.

- **\DataSources** - All data sources that are used by the app.

- **\Connections** - Connection instances that are saved with this app and used when you are reloading into Power Apps Studio.

- **\Assets** - Media files that are embedded in the app.

- **\pkgs** - A downloaded copy of external references, such as templates, API Definition files, and component libraries. These files are similar to nuget/npm references.

- **\other** - All miscellaneous files that are needed for re-creating the .msapp file.

- **entropy.json** - Volatile elements (like timestamps) are extracted to this file. This file helps reduce noisy diffs in other files while ensuring that you can still round-trip. Holds other files from the .msapp file, such as what is in \references.

## File format

The files that end with **\*.fx.yaml** are where you can edit formulas. As you explore the extracted files, you will find that not all contain YAML; many are in their native format and are not meant to be edited outside of Power Apps Studio.

## Merge source changes

One scenario that is enabled by unpacking is the ability for multiple people to edit an app and merge changes in source control. In this scenario, you will want to minimize conflicts. For example, editing formulas on the same control will likely cause a conflict, but two people who are editing different screens is a scenario that's less likely to happen.

If you create the app in the cloud, download it, and then edit it, know that when you upload the repacked version, it will overwrite any changes that are done to the cloud version because it was downloaded.

In this scenario, to avoid overwriting and losing work that was done online, you should download the app from the cloud again, unpack it, commit the file changes, resolve conflicts, and then repack and upload the new app. Make sure that the source control contains the main copy of your app.

Conflicts will occur because multiple people are editing concurrently. For example, if two people picked the same control name on different screens, it would create a merge conflict. For more information, see [Microsoft Power Platform CLI documentation](/power-apps/developer/data-platform/powerapps-cli?azure-portal=true#merging-changes-with-power-apps-studio).
