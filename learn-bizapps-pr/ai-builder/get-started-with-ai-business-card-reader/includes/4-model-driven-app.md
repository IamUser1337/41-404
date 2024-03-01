Your goal for this exercise is to accelerate the process of creating an appointment by using information from business cards. Users will extract contact information from a business card and prefill the **Quick Create: Appointment** form with the contact information.

You will build a model-driven Power App and use the Business card reader component for this exercise. For more information, see the [What are model-driven apps in Power Apps?](/power-apps/maker/model-driven-apps/model-driven-app-overview/?azure-portal=true) and the [Use the business card reader in model-driven apps](/ai-builder/business-card-reader-component-model-driven/?azure-portal=true) documentation.

## Create a model-driven app in Power Apps

To create a model-driven app in Power Apps, follow these steps:

1. Select **Create** in the Power Apps left menu.
1. Select **Model Driven Apps from blank**.
1. Name the model-driven app **Contoso Business card reader**.
1. In the App Designer, edit the **Site map** and then edit the sub area.
1. Select a Microsoft Dataverse table related to the form that you will create that will use the Business card reader component. For this lesson, use the **Appointment** table.
1. Select **Save and close**.

    ![Screenshot of Power Apps App Designer > Sitemap Designer with the Contoso Business Card in design view.](../media/image-9.png)

    Update the appointment's **Quick Create** form so it can use the Business card reader component.
1. Select **Forms**.
1. Edit the **Quick Create: Appointment** form.

## Update an existing form

You have entered the edition mode of the form. You can now create a new field that will host the Business card component.

1. Select **+ Add field**.
1. Name the field **Business Card** and drag it to your form to add it.
1. Add the AI Builder Business card by selecting **+ Add component**.
1. Select the **AI Builder Business card** control. Set the following properties:

   - Business Card Reader field: Business Card (Text)
   - Full Name Field: Subject (Text)
   - Address Street Field: Location (Text)

    After the component has been added, you should see a page similar to the following image.

    ![Screenshot of Quick Create Appointment form with the Scan business card component highlighted.](../media/image-10.png)

1. Save and publish your updated form.

## Publish your model-driven app

Publish your app and create an appointment by using the Business card reader. You can now use the **Quick Create: Appointment** form.

1. Return to the App Designer. Publish your application and select the **run** button.
1. Test your updated form with the Business card component by selecting the plus sign (**+**), and then in **Activities**, and then in **Appointment**.
1. You can scan a business card and the extracted contact fields will appear in the form. Fill out the remaining fields and save your appointment by selecting **Save and Close**.

    ![Screenshot of the completed Quick Create Appointment form with the Save and Close button at the bottom.](../media/image-11.png)
