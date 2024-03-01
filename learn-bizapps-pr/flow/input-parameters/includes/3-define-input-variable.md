Variables allow information to change, or be variable, for every run of your flow. If you're using a flow for any type of data entry, you'll need variables to define the fields that you need to enter. Input variables include information that you enter into the flow before or during the run. Output variables are outcomes that the flow returns to you after the run. Power Automate for desktop provides you with the ability to receive input values from cloud flows and return values by using output variables. As a result, your automations can be seamlessly integrated. To define input variables, begin in your Power Automate for desktop app and then open the designer by editing a desktop flow.

Watch the following demo video of the steps that you'll complete in this unit.

 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5cV2F]

> [!NOTE]
> The flow in the demo video was built in the [Build your first Power Automate desktop flow](/training/modules/build-first-desktop-flow/?azure-portal=true) module.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Flows section in Power Automate for desktop with the Edit icon highlighted.](../media/7-edit-flow.png)](../media/7-edit-flow.png#lightbox)

When you're in the designer, select the plus (**+**) icon under the **Input/output variables** section, and then select **Input**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Actions in Power Automate for desktop, with Variables selected and the plus sign icon selected to reveal the Input and Output options.](../media/8-add-input-variable.png)](../media/8-add-input-variable.png#lightbox)

The **Variable type** can be **Input** or **Output**. This example uses input; output variables will be covered later. The **Variable name** will be used and referenced inside the desktop flow. The **External name** will be used outside the desktop flow, and the **Description** field will give you more information on the variable, which can be especially helpful if you have many different input and output variables in the same desktop flow. The **Default value** allows you to define a value if no input is provided. The **Data type** field helps to further define your variable and how Power Automate will handle it. For example, using the data type of **Sensitive text** will encrypt the values, which helps offer security on sensitive data. You can use this data type for passwords to open secure programs or for other personal or private information. You can set your own values for your variable, or you can use the values that are displayed in the following screenshot. Select **Create** to finish your variable.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Add a new input variable dialog.](../media/9-input-variable-info.png)](../media/9-input-variable-info.png#lightbox)

Continue to select the plus (**+**) icon and then create more input variables for your flow. If you're using the desktop flow that's built on the Contoso Invoicing app, define two more variables based on the following values.

**Variable 2**

- **Variable type** - Input

- **Variable name** - Contact

- **Data type** - Text

- **Default value** - `b.Friday@wingtiptoys.com`

- **External name** - Contact email

- **Description** - Contact email

**Variable 3**

- **Variable type** - Input

- **Variable name** - Account

- **Data type** - Text

- **Default value** - WingTip Toys

- **External name** - Account Name

- **Description** - Name of the account that's being invoiced

After you've finished defining your input variables, select **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate for desktop Actions page with the Save button highlighted.](../media/10-save.png)](../media/10-save.png#lightbox)

Now that you've defined the input variables, you can set their use in the desktop flow.
