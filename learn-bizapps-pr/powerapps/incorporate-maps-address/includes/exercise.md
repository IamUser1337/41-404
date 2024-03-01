In this exercise, you'll enable geospatial features in your Microsoft Power Platform environment. Additionally, you'll determine the value that the **Address input** field can add for users who are looking for an address in a field.

## Enable geospatial features

To enable geospatial features, follow these steps:

1. Sign in to [Microsoft Power Platform admin center](https://admin.powerplatform.microsoft.com/?azure-portal=true). You must be an admin to complete these steps. If you don't have access, you need to ask someone with access to complete the following steps for you, and then you can complete the subsequent sections of this exercise.

1. On the left side menu of the Power Platform admin center, select **Environments** and then select the environment where you want to create the address input field for this exercise.

1. Select **Settings** for the selected environment.

1. Expand the **Product** section and then select **Features**.

1. Under **Map and address services**, turn on the Full toggle.

1. You need to select the checkbox for the terms of service, and then you can select **Enable**.

1. Scroll to the bottom of the **Features** screen and select **Save**.

You're finished with the Power Platform admin center and are ready to use the map and address features.

## Add an address input field to an app

To add an address input field to an app, follow these steps:

1. Sign in to [Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Make sure that you're in the environment where you previously enabled geospatial services.

1. Select **+ Create** and then select **Blank app**.

1. Under **Blank canvas app**, select **Create**.

1. Name the app **Address Input Test** with the format of **Tablet**.

1. Select **Create**.

1. Once your app canvas appears, select **Insert > Input > Address input**.

## Test the Address input field

To test the **Address input** field, follow these steps:

1. Put the app in Preview mode.

1. In the **Address** field, enter an address.

1. Using fuzzy matching logic, the control can auto-suggest several locations that match the address that you entered. Select a matching address.

This address becomes a verified address that you can now use within your canvas app.
