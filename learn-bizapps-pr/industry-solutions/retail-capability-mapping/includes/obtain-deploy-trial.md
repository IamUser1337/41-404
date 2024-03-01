Microsoft Cloud for Retail capability relies on various components from Dynamics 365, Azure, and Microsoft 365. To use this capability, you’ll need to obtain the following trial licenses:

- Dynamics 365 Intelligent Order Management trial

- Microsoft 365 E5 trial

- Microsoft Cloud for Retail add-on

- Dynamics 365 Finance and Operations trial

## Task 1: Obtain a Dynamics 365 Intelligent Order Management trial

In this task, you'll add the necessary add-on to deploy and use the Intelligent Order Management app as part of the Intelligent Order Management lab.

1. Go to the [Microsoft 365 admin center](https://admin.microsoft.com/?azure-portal=true).

1. Go to **Billing > Purchase services**. Search for **Intelligent Order Management trial** in the search box and then select **Details**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Purchase services page in the Microsoft 365 admin center, showing search results.](../media/search.png)](../media/search.png#lightbox)

1. Select **Start free trial**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the product details for the Intelligent Order Management trial, showing the Start free trial button.](../media/start-trial-2.png)](../media/start-trial-2.png#lightbox)

1. Select **Try now**.

    > [!div class=”mx-imgBorder”]
    > ![Screenshot of the order confirmation, showing one-month term and the Try now button.](../media/try-now-2.png)

1. Select **Continue** to return to the admin center.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the order receipt, showing the Continue button and confirmation number.](../media/continue-2.png)

1. Assign the newly acquired Dynamics 365 Intelligent Order Management trial license to your user. Go to **Users > Active users**, select your user, and then select **Manage product licenses**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Active users page in the Microsoft 365 admin center, showing the Manage product licenses option highlighted.](../media/manage-licenses.png)

1. Select the **Dynamics 365 Intelligent Order Management vTrial** license checkbox and select **Save changes**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Licenses and apps tab, showing the Intelligent Order Management V Trial checkbox selected.](../media/intelligent-license.png)

    > [!Important]
    > It might take up to 24 hours for Dynamics 365 Intelligent Order Management to become available in your Dynamics 365 apps after you’ve obtained the trial license.

## Task 2: Obtain a Microsoft 365 E5 trial

In this task, you'll add the necessary Microsoft 365 trial to use Outlook and Microsoft Teams in the later labs.

1. Go to the [Microsoft 365 admin center](https://admin.microsoft.com/?azure-portal=true).

1. Go to **Billing > Purchase services** and select Microsoft 365. Scroll down to Microsoft 365 E5 and then select **Details**. You can also use the search box.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Purchase services page in the Microsoft 365 admin center, with the Office 365 category selected and the Office 365 E5 tile's Details button highlighted.](../media/purchase-2.png)](../media/purchase-2.png#lightbox)

1. Select **Start free trial**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the product details page for Office 365 E5, showing the Start free trial option.](../media/start-trial-3.png)

    > [!NOTE]
    > In this exercise Microsoft 365 E5 is chosen as it includes Microsoft Teams. However, in case you do not see an option to choose Microsoft 365 E5 in your region, you can choose alternatively Microsoft 365 business premium standard or alternative versions available that include license to Microsoft Teams.

1. Enter a **valid phone number** to prove that you're not a robot.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Prove you're not a robot screen.](../media/robot.png)

1. Select **Try now** to start your free trial.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the check-out screen for the Office 365 E5 trial.](../media/try-now-3.png)

1. Select **Continue** to return to the admin center.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the order receipt with the confirmation number for the Office 365 E5 trial.](../media/continue-3.png)

1. Assign the newly acquired Microsoft 365 E5 trial license to your user. Go to **Users > Active users**, select your user, and then select **Manage product licenses**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Microsoft 365 admin center Active users page, showing the Manage product licenses option.](../media/manage-licenses-3.png)

1. Select the **Microsoft 365 E5** license and then select **Save changes**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Licenses and apps tab with Office 365 E5 selected.](../media/office-e-5-license.png)

## Task 3: Obtain a Microsoft Cloud for Retail trial license

In this task, you'll request and add the Microsoft Cloud for Retail add-on to deploy and use the capabilities that it provides.

1. To obtain a trial license for Microsoft Cloud for Retail, go to the following Microsoft form and fill out the required information: [Trial Request for Microsoft Cloud for Retail](https://aka.ms/MCRTrial/?azure-portal=true).

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Trial Request for Microsoft Cloud for Retail form.](../media/request.png)

1. You'll receive an email with a URL that contains an offer code that you can use to claim a 30-day trial license for Microsoft Cloud for Retail. When you’ve received that email, copy the URL, open a new tab while signed in to your tenant, and then paste the URL.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the email showing the link to claim the license.](../media/email.png)

1. Enter the email address that’s associated with your tenant and then select **Next**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the account setup page showing the email address field.](../media/email-address.png)

1. Select **Sign in**.

1. Select **Try now**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the check-out page for Microsoft Cloud for Retail Add-on Trial, showing the Try now button.](../media/try-now-4.png)

1. Select **Continue**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the order receipt and confirmation number.](../media/continue-4.png)

## Task 4: Obtain and deploy Dynamics 365 Finance and Operations apps

If you have also requested for a Dynamics 365 Finance and Operations trial license then, in this task, we will obtain a trial license for Dynamics 365 Finance and Operations apps and create a new Dynamics 365 Finance and Operations and a linked Power Platform environment.

1. Copy and paste the URL from your email to add the Dynamics 365 Finance and Operations trial license in your tenant.

1. Sign in using the new Microsoft Entra ID credentials.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of email received for a trial envionment."](../media/trial-email.png)](../media/trial-email.png#lightbox)

1. Select **Yes, add it to my account**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Dynamics 365 for Finance and Operations Preview trial showing "It looks like you already have an account."](../media/trial.png)

1. Confirm the order so that the trial license is applied to your tenant.

1. Sign in to [Lifecycle Services](https://lcs.dynamics.com/?azure-portal=true).

1. Select **+** on the screen to create a new project and then select **Migrate, create solutions, and learn**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New project screen showing Migrate, create solutions, and learn selected as the purpose of the project.](../media/migrate.png)](../media/migrate.png#lightbox)

1. Provide the project details as in the screenshot below:

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Create a project screen filled in.](../media/create-project.png)

1. You should then be able to see your project.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the MCR In a Day training showing environments and project tools.](../media/environments.png)](../media/environments.png#lightbox)

1. Perform the steps mentioned in the link: [Complete the Azure Resource Manager onboarding process](/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding/?azure-portal=true).

1. Open your LCS Project and then select **+** to deploy a new environment.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the MCR In a Day training showing the plus sign below environments.](../media/environments.png)](../media/environments.png#lightbox)

1. Select the latest version of the environment (the version shown in the below screenshot is for illustration only) and then select **Next**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Select application and platform version screen.](../media/version.png)

1. In the next step, select **DEMO** to create a demo environment.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Select environment topology page showing the DEMO topology.](../media/demo.png)](../media/demo.png#lightbox)

1. Provide an environment name, select the **Environment Size** as **E8 V3**, and then select **Advanced Settings**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Deploy environment screen filled in.](../media/deploy.png)](../media/deploy.png#lightbox)

1. To enable dual write and create a connected Power Platform environment, in the Advanced Settings, select the **Power Platform Integration** tab, and provide the values as mentioned below:

    - **Configure Power Platform Environment**: Yes

    - **Power Platform template**: Dynamics 365 standard template

    - **Environment type**: SubscriptionBasedTrial

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Deployment settings screen showing the Power Platform Integration tab top part.](../media/deployment.png)](../media/deployment.png#lightbox)

1. Select the **Agree** checkbox and then select **Done**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Deployment settings screen showing the Power Platform Integration tab bottom part.](../media/deployment-2.png)](../media/deployment-2.png#lightbox)

1. Select **Deploy**. Lifecycle Services will then deploy a Dynamics 365 Finance and Operations Virtual Machine in the selected Azure subscription.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Are you sure you want to deploy dialog.](../media/deploy-2.png)](../media/deploy-2.png#lightbox)

1. You will then notice that the environment deployment has been queued. The deployment might take four to eight hours.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the environment deployment queue.](../media/deploy-environment.png)](../media/deploy-environment.png#lightbox)

1. Turn off the Dynamics 365 Finance and Operations Virtual Machine when not in use to avoid consuming Azure credit. Follow the steps below to turn off the Dynamics 365 Finance and Operations environment:

    1. Select the environment in your Lifecycle Services project.

    1. Select the **Stop** button to turn off the environment.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Lifecycle Services M C R in a day Manage environment screen showing the Stop button in the toolbar.](../media/stop.png)

## Task 5: Deploy Dynamics 365 apps

In this task, you'll install Dynamics 365 Intelligent Order Management on the newly created environment. These apps are required to do the Intelligent Order Management lab.

1. In the [Microsoft Power Platform admin center](https://admin.powerplatform.com/?azure-portal=true), expand **Resources** and go to **Dynamics 365 apps** to search for available apps at the tenant level.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Resources expanded to show the Dynamics 365 apps option.](../media/apps.png)

1. In the search bar in the upper right, search for **Dynamics 365 Intelligent Order Management Trial** and then select **Install**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Dynamics 365 apps page in the Microsoft Power Platform admin center, showing Dynamics 365 Intelligent Order Management Trial selected.](../media/dynamics-365-apps.png)

1. Select your newly created trial environment (the Power Platform connected trial environment) from the dropdown menu, agree to the terms, and select **Install**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Install Dynamics 365 Intelligent Order Management Trial screen showing Customer Service Trial selected for the environment.](../media/install.png)](../media/install.png#lightbox)

1. Return to **Dynamics 365 apps** under **Resources** and then search for **Customer Service**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the search results for Customer Service with Dynamics 365 Customer Service Enterprise Trial selected.](../media/apps-customer-service.png)](../media/apps-customer-service.png#lightbox)

1. Select your newly created trial environment from the dropdown menu, agree to the terms, and then select **Install**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the trial terms, showing the Install button.](../media/install-2.png)

1. Track your installations on your environment's Dynamics 365 apps page. These installations will take several hours to complete.

You successfully added the necessary trial licenses to your training environment. After they’ve finished installing, you can proceed to the next exercise to set up the remaining prerequisite applications and deploy Microsoft Cloud for Retail.
