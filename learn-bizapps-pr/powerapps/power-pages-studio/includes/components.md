After a page has been created, you can add components to create the layout and add static and dynamic content. This simple design approach will add corresponding HTML, CSS, or code to the page without the need to know the structure or syntax of these languages. 

To add a section, select any existing section on the page, select the plus sign (**+**) or **Add a section**, and then select from one of the available section layouts.

> [!TIP]
> Section layout can be changed later, after the section has already been created.

![Screenshot of Power Pages content editing.](../media/3-power-pages-editing.png)

To add a component, select either an empty section or an existing element where you'd like to place the component. Use the plus sign (**+**) or the overflow button (**...**) to display all available components, and then select a component to insert.

![Screenshot of Insert a component interface.](../media/3-power-pages-insert-component.png)

There are two types of the components.

* **Standard** components are used to create page layout and static content.
* **Connected to data** components are used to display dynamic and interactive content based on Dataverse data.    

All sections and components allow for in-context editing and you can edit any section or component directly from the canvas. When a section or a component is selected, context menu appears where you can adjust properties of the selected element such as alignment, style, color, size, etc. For more information, see [Customize webpages](/power-pages/getting-started/customize-pages#see-also) for more details about available components and their properties.

## Source code

Often there are requirements for other elements that aren't available as the design studio components. A page may need more complex layout and formatting, or call for more CSS or JavaScript. These requirements can be created in the Visual Studio Code for the Web editor that allows makers and pro developers to view and modify the source code of the page and associated CSS and JavaScript.  

To view the source code of the page, select **Edit code** button in the command bar.

![Screenshot of the Visual Studio Code for the Web editor access available in the design studio.](../media/3-power-pages-source-code.png)

After selecting **Edit code**, you'll be redirected to Visual Studio Code for the Web to make your edits to the page HTML, CSS, or JavaScript. After the source code is saved, the changes are synchronized to appear on the canvas.

![Screenshot of a prompt to synchronize page content after editing is complete in Visual Studio Code for the Web](../media/3-sync-after-code-edit.png)

> [!WARNING]
> You can potentially damage the layout of your page by entering incorrect syntax in the source code. Create a copy of the original code before making any significant changes.
