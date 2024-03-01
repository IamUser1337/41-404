In this exercise, you'll use the paconn CLI to download a connector, validate the definition, and resolve issues. This exercise simulates what you would do to prepare for creating and certifying an open-source custom connector.

This exercise requires you to install Python and access the command prompt on the machine that you're using for the exercise.

> [!Important]
> Use a test environment with Microsoft Dataverse provisioned. If you don't have one, you can sign up for the **[community plan](https://powerapps.microsoft.com/communityplan/?azure-portal=true)**.

> [!NOTE]
> Download the following file to your local computer to complete this exercise: [Contoso Invoicing Triggers](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-automate-connectors/certify/ContosoInvoicingOpenSource_1_0_0_0.zip). Select the download button in the middle-right portion of the screen.

## Import the solution

In this task, you'll import an unmanaged solution that contains a Contoso Invoicing custom connector. You use this connector to complete the tasks in this exercise.

1. Go to [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true) and make sure that you're in the correct environment.

1. Select **Solutions > Import solution**.

1. Select **Browse**.

1. Select the **ContosoInvoicingOpenSource_1_0_0_0.zip** solution and then select **Open**.

1. Select **Next**.

1. Select **Import** and then wait for the import to complete. You should get a success message after the import completes.

1. Open the **Contoso Invoicing - Open Source** solution that you imported.

  The **Contoso Invoicing - Open Source** custom connector component should display.

## Install Microsoft Power Platform Connectors CLI

Microsoft Power Platform Connectors CLI includes the paconn command-line tool that's designed to aid Microsoft Power Platform custom connector development. The paconn tool uses Python runtime, which you're installing as well.

1. Go to [Download Python](https://www.python.org/downloads/?azure-portal=true) and select the **Download Python** button. You can use any version greater than 3.5.

1. Select the downloaded .exe file to start installation.

1. Select the **Add Python xx to Path** checkbox, select **Install Now**, and then wait for the installation to complete.

1. Close the installation wizard after the installation completes.

1. Start the command prompt and then run the following command to install paconn.

   `pip install paconn`

1. Wait for the installation to complete.

## Download the connector locally

In this task, you download the connector definition files locally so that you can add the Host URL property.

1. Run the `paconn login` command.

1. Copy the provided **Code**.

1. In a browser, sign in with the same credentials as your environment. Go to [Microsoft Device Login](https://microsoft.com/devicelogin/?azure-portal=true), paste the **Code** that you copied, and then select **Next**.

1. Provide your credentials.

1. Select **Continue**.

   You should get a successful sign-in message.

1. Return to the command prompt, where a login successful message displays.

1. Run the download command.

   `paconn download`

1. When prompted to select an environment, enter a number for the environment where you installed the solution. Press the **Enter** key on your keyboard.

1. Provide the number of the **Contoso Invoicing - Open Source** connector and then press the **Enter** key on your keyboard.

1. The download should complete successfully. Note the location where the connector was downloaded.

## Validate the connector, fix errors, and add metadata

In this task, you'll validate the connector, fix some common errors, and add the required connector metadata.

1. Copy the path where the connector was downloaded.

1. Run the validate command by using the path that you copied plus the API definition Swagger file name **\apiDefinition.swagger.json**.

   `paconn validate --api-def [Path to apiDefinition.swagger.json]`

   You should get an error for a missing summary for the fourth parameter of the ListInvoices action and a missing contact property.

1. Fix the missing summary. Go to [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true) and make sure that you're in the correct environment.

1. Select **Solutions** and then open the **Contoso Invoicing - Open Source** solution.

1. Select the **Contoso Invoicing - Open Source** connector and then select **Edit**.

1. Select the **Definition** tab and then select the **ListInvoices** action.

1. Scroll down to the **Request** section, select the ellipsis (**Chevron**) button of the **toAmount** parameter, and then select **Edit**.

1. Enter **To amount** in the **Summary** field and then select **Update connector**.

1. Wait for the connector update to complete.

1. Delete the connector that you previously downloaded (you'll add it again in a moment). Delete the connector that you downloaded from your machine.

1. Download the connector again. Return to the command prompt and run the download command again.

   `paconn download`

1. When prompted to select an environment, enter the number for the environment where you installed the solution. Press the **Enter** key on your keyboard.

1. Provide the number of the **Contoso Invoicing - Open Source** connector and then press the **Enter** key on your keyboard.

1. The download should complete successfully. Note the location where the connector was downloaded.

1. Run the validate command by using the path that you copied plus the API definition Swagger file name **\apiDefinition.swagger.json**.

   `paconn validate --api-def [Path to apiDefinition.swagger.json]`

   You should now receive only one error for the missing contact parameter.

1. Go to the connector folder that you downloaded and open the **apiDefinition.swagger.json** file by using the text editor of your choice, such as Notepad.

1. Add a contact property to the information after the description property.

   ```json
   "contact": {
     "name": "Contoso Support",
     "url": "https://contosoinvoicingtest.azurewebsites.net",
     "email": "info@Contoso.com"
   }
   ```

1. Add connector metadata after the information.

   ```json
   "x-ms-connector-metadata": [
     {
      "propertyName": "Website",
      "propertyValue": "https://contosoinvoicingtest.azurewebsites.net"
     },
     {
      "propertyName": "Privacy policy",
      "propertyValue": "https://contosoinvoicingtest.azurewebsites.net"
     },
     {
      "propertyName": "Categories",
      "propertyValue": "Productivity"
     }
   ],
   ```

1. Select **File** and then **Save** your changes.

1. Run the validate command one more time.

   `paconn validate --api-def [Path to apiDefinition.swagger.json]`

Now, the connector should be validated successfully.

You've successfully prepared the connector to be created as open source and then certified. When building a real connector, you would go on to publish the connector to GitHub.
