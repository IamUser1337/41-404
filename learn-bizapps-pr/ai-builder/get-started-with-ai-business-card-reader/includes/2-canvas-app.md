Your goal for this exercise is to take a picture or upload an existing photo from the file system and extract contact information that is present in the image. You will then build a canvas app in Power Apps and use the Business card reader component. 

For more information, see the [What are canvas apps in Power Apps?](/power-apps/maker/canvas-apps/getting-started/?azure-portal=true) and the [Use the Business card reader component in a canvas app](/ai-builder/business-card-reader-component-in-powerapps/?azure-portal=true) documentation.

### Create an application in Power Apps

To create an application in Power Apps, follow these steps:

1. Select **Create** in the Power Apps left menu and then select **Canvas app from blank**.
2. Name the canvas app **Contoso Business card reader**.
3. Select **Phone**.
4. Select **Create**.

### Enable automatic retrieval of contact information from business cards

Follow these steps to give users the ability to automatically retrieve contact information from business cards:

1. From the **Insert** menu and **AI Builder** bar, select **Business card reader**. This control will allow you to take or upload a picture and automatically recognize contact information from business cards.
2. Resize the control to fit the screen.

    ![The A I Builder menu is expanded to reveal Business card reader, Form processor, Object detector, and Text recognizer options.](../media/image-2.png)

### Bind the contact information to an existing table from Microsoft Dataverse

To bind the contact information to an existing table from Dataverse, follow these steps:

1. Select **Insert a new Form in edit mode**.
2. Change the **Default mode** property to **New** and the **Data source** property to the **Contacts** table.
3. After the **Data Source** property has been set, three fields are automatically added to the form. Select the **Fields** property and add other contact fields to the form. Business card reader can extract 18 different fields from business cards. For this example, you will add the **Website** field.

### Bind the extracted contact information to the form

To bind the extracted contact information to the form, follow these steps:

1. Go to each of the form's data cards and, in the **Advanced** tab, select **Unlock to change properties**.

    ![Screenshot of the Advanced tab, with Unlock to change properties circled.](../media/image-3.png)

2. You can now change the default value of each data card to map the Business card reader extracted properties. Set the following default values:

   - **Full Name_DataCard1** - BusinessCardReader1.FullName

   - **Email_DataCard1** - BusinessCardReader1.Email

   - **Business Phone_ DataCard1** - BusinessCardReader1.BusinessPhone

   - **Website_ DataCard1** - BusinessCardReader1.Website

You can always add more fields to be mapped. For this example, you can extract the following list of fields from your business cards.

| Property          | Definition                                                                                              |
|-------------------|---------------------------------------------------------------------------------------------------------|
| AddressCity       | The city address                                                                                        |
| AddressCountry    | The country address                                                                                     |
| AddressPostalCode | The postal code address                                                                                 |
| AddressStreet     | The street address                                                                                      |
| BusinessPhone     | The first phone or fax number                                                                           |
| CleanedImage      | The image after processing where the business card appears cropped and enhanced from the original image |
| CompanyName       | The company name                                                                                        |
| Department        | The organization department found                                                                       |
| Email             | The contact email found in the business card, if any                                                    |
| Fax               | The third phone or fax number                                                                           |
| FirstName         | The contact first name                                                                                  |
| FullAddress       | The contact full address                                                                                |
| FullName          | The contact full name                                                                                   |
| JobTitle          | The contact job title                                                                                   |
| LastName          | The contact last name                                                                                   |
| MobilePhone       | The second phone or fax number                                                                          |
| OriginalImage     | The original image before processing                                                                    |
| Website           | The website                                                                                             |

### Add a button to trigger the creation of a new contact

To add a button to trigger the creation of a new contact, follow these steps:

1. Select **Insert a new Button** and place the button below the form.
2. Change the **OnSelect** property to **SubmitForm(Form1)** and the **Text** property to **Create contact**.

    The following image shows an example of the screen that should appear.

    ![A screenshot of the Scan business card form with Full Name, Email, Business Phone, and Website fields and a Create contact button.](../media/image-4.png)

    Test that the application is working properly before moving on to the next step.

3. Select the **run** button on right side of the screen.

    ![A screenshot of the tool bar with the Run button circled.](../media/image-5.png)

4. To analyze a business card, select **Scan business card** and then select an image that you have saved. You can also use your mobile device to take a picture.

AI Builder Business card reader will process the business card and display extracted contact information.

The extracted contact information is now displayed in the form's data cards. You can review it and create a new contact by selecting **Create contact**.

![A screenshot of a scanned business card with the information populating the fields.](../media/image-6.png)

You can add new fields to the form; AI Builder Business card reader will recognize various contact information from business cards. You can also use the extracted information to create records in other tables from Dataverse and to use it in external data sources.

You have now learned how to build a Power Apps canvas app with the AI Builder Business card reader component, and have discovered how to use the extracted contact information to create a new record in the **Contact** table from Dataverse.
