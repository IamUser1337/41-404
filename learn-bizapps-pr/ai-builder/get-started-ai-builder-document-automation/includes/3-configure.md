In this unit, you will

- Learn which are the predefined personas supported and which features are available.

- Discover how to configure the roles.

- Understand how to create a forms processing model to extract data from your documents.

- Assess how to prepare the pipeline to process your documents.

The targeted person for configuring roles and permissions should:

- Understand which users must have access to which features.

- Have good knowledge of Microsoft Power Platform's role-based access control.

Makers are usually a good fit for this task.

The **Document automation base kit** provides a basic implementation of role-based access control allowing you to control features available to each persona described in the previous unit, the manual reviewer, and the process owner.

The features available in the validation application by each persona are summarized in the table.

| Feature | Manual Reviewer | Process Owner |
|---|---|---|
|     Controlling Dataverse role                              |     Document Automation Reviewer                                            | System Customizer    |
|     Access the   **Configuration** tab                        |                                                                             |     X                |
|     Configure   the model to use                            |                                                                             |     X                |
|     Access the   **Documents** tab                            |     X                                                                       |     X                |
|     View documents                                          |     Only in **Manual Review** state if not yet opened by another reviewer*    |     X                |
|     Filter   documents list by state                        |                                                                             |     X                |
|     Open the side-by-side   viewer (file/extracted data)    |     X                                                                       |     X                |
|     Edit fields                                             |     X                                                                       |     X                |
|     Validate a   document                                   |     X                                                                       |     X                |
|     Delete a   document                                     |                                                                             |     X                |

*When someone opens a processed document, he automatically assigns it to himself. Other validators will no longer see this document in the list and would get an error if they tried to update it.

> [!NOTE]
> If your company does not need to have role-based access control, you can just assign the **System customizer** role to everybody.

## Configuring roles

1. Open the [Microsoft Power Platform Admin center](https://tip.admin.powerplatform.microsoft.com/) and select your environment, then select **Settings** on the top.

    > [!div class="mx-imgBorder"]
    > [![List of saved environments.](../media/3-environment.png)](../media/3-environment.png#lightbox)

1. Expand **Users + permissions** and select **Users**.

    > [!div class="mx-imgBorder"]
    > [![Environment settings with Users + permissions.](../media/3-users-permissions.png)](../media/3-users-permissions.png#lightbox)

1. Then select **Manage users in Dynamics 365** on the top banner.

    > [!div class="mx-imgBorder"]
    > [![Users list with Manage users in Dynamics 365 command.](../media/3-manage-users.png)](../media/3-manage-users.png#lightbox)

1. Search for a user name, select the user, and select **Manage Roles**.

    > [!div class="mx-imgBorder"]
    > [![User search with Manage roles command.](../media/3-manage-roles.png)](../media/3-manage-roles.png#lightbox)

1. Add the **System Customizer** role to **Process Owners** or the **Document Automation Reviewer** role to **Manual Reviewers**.

    > [!div class="mx-imgBorder"]
    > [![Manage User Roles dialog with list of selectable roles.](../media/3-manage-user-roles.png)](../media/3-manage-user-roles.png#lightbox)

1. Select the **3 ... dots on the top banner** and Select **System Views**.
    > [!div class="mx-imgBorder"]
    > [![Select 3 dots on the top banner.](../media/select-system-views.png)](../media/select-system-views.png#lightbox)

1. On the **left pane** > Select **Security Roles** > Select **System Customizer**.
    > [!div class="mx-imgBorder"]
    > [![Select Security Roles entity from the left pane.](../media/select-security-roles.png)](../media/select-security-roles.png#lightbox)

1. Select **Business Management** Tab > **Security Role** >  Enable the privilege **Business Unit** for **Create** and **Write** > **Save and Close**.
    > [!div class="mx-imgBorder"]
    > [![Select Business Unit prvilege to Create and Write for the security role.](../media/select-business-unit.png)](../media/select-business-unit.png#lightbox)

## Create a form processing model

The next step is to create a Form Processing model that will extract the data from your document with AI Builder.

Follow the module [Get started with Form processing in AI Builder](/training/modules/get-started-with-form-processing/?azure-portal=true) to learn how to make it.

> [!TIP]
> To create an AI Builder model, you need at least 5 samples of documents. If your suppliers send documents with various layouts, you should consider creating one collection per document type in the model.

## Optionally configure rules on received emails

You can customize the way emails are processed by selecting **View Solution**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate Document automation page with the View solution button in the Custom documents section.](../media/3-select.jpg)](../media/3-select.jpg#lightbox)

1. Select "Document automation base kit."

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power Automate Solutions page with the Document automation base kit selected.](../media/3-solutions.jpg)](../media/3-solutions.jpg#lightbox)

1. Then select “Document Automation Email Importer” and **Edit** in the top banner.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power Automate My flows page with the Document Automation Email Importer open.](../media/3-importer.jpg)](../media/3-importer.jpg#lightbox)

1. You are in the authoring experience of the email importer flow. Here you can configure the email rules to filter on the specific emails that you want to process. You must keep the “include attachments” property set to “Yes” as this flow takes the document on attachment as the document to be processed. But you can configure filters on the topic, senders, and so on, based on your needs.  

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the settings in the "When a new email arrives" step that flows into the "For each attachment" step.](../media/3-email.jpg)](../media/3-email.jpg#lightbox)

## Configuring the model to use

### Role

The targeted person for configuring providers should:

- Have an overview of the suppliers of the company and get samples of these documents.

- Have good knowledge of AI Builder including building a Form Processing model.

Makers are usually a good fit for this task.

Once the model is created, you can use it in the pipeline.

1. Launch the **Document Automation Application** from [Power Automate Document Automation](https://flow.microsoft.com/aibuilder/document-automation) by selecting **Open application**. You will land on the documents list page where you will see all processed documents.

    > [!div class="mx-imgBorder"]
    > [![Document Automation Application's Document List tab.](../media/3-document-automation-application.png)](../media/3-document-automation-application.png#lightbox)

1. Select the **Configuration** tab, then **Add configuration** to configure the AI model to be used.

    > [!div class="mx-imgBorder"]
    > [![Document Automation Application's Configuration tab.](../media/3-configuration.png)](../media/3-configuration.png#lightbox)

1. You now need to select an AI Builder model to extract labels from documents.

    See [Get started with form processing](/training/modules/get-started-with-form-processing/?azure-portal=true) to learn how to create an AI Builder form processing model.

    Once your model is created and **published**, you can refresh this page with **Reload models**, select the appropriate model, and select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Model selection tab with models list.](../media/3-model-selection.png)](../media/3-model-selection.png#lightbox)

1. The next screen will show how the labels of the model will be stored in the **Document Automation Data** table of Dataverse. Select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Fields mapping tab with values extracted from model.](../media/3-fields-mapping.png)](../media/3-fields-mapping.png#lightbox)

    > [!NOTE]
    > If you update your model changing the label of model, you must get back to this page and use the **Refresh** button to have changes applied to the starter kit and select **Save** again.

1. The kit is ready to perform the document extraction and to automate the processing of your documents.

    > [!div class="mx-imgBorder"]
    > [![Configuration saved for Document Processing.](../media/3-document-process.png)](../media/3-document-process.png#lightbox)

You have successfully understood how the **Document automation base kit** allows you to define different security roles and how it must be configured to process your documents.
