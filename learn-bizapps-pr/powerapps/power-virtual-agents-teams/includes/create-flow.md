In this exercise, you'll set up the chatbot to interact with the Dataverse for Teams tables that you created in a previous lab in this learning path. Your goal is to make sure that the user can submit a request for swag by using the chatbot. To do so, you'll use the embedded flow experience inside the Power Virtual Agents app in Teams.

## Task: Get the schema name for your Dataverse for Teams table

To get the schema name for your Dataverse for Teams table, follow these steps:

1. When you create your Dataverse for Teams tables and columns, each component is given a technical or schema name behind the scenes. You'll need to find that technical or schema name to use it in your flow. Return to Microsoft Power Apps by using the icon on the Teams left navigation bar. Select the **Build** tab and then select the team that you've been working in. Select the Asset table in the list of created items.

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Build tab and Asset table.](../media/build.png)](../media/build.png#lightbox)

1. Select **Columns**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the Columns option selected.](../media/columns.png)](../media/columns.png#lightbox)

1. A behind-the-scenes view of your table and columns will show. Beneath the **Name** header are schema names, shown in a format like **crao5_AssetId**. Your schema names might differ; you'll have your own unique prefix that isn't similar to this example.

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the schema names in the Columns section.](../media/column-names.png)](../media/column-names.png#lightbox)

1. Note your schema names for the following columns; you'll need them in this task and in subsequent tasks.
    
    **Asset**

    **Asset Name**

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the schema names of Asset and Asset Name for the column.](../media/schema-names.png)](../media/schema-names.png#lightbox)

1. Return to Power Virtual Agents by using the icon on the Teams left navigation bar. Select the **Chatbots** tab and then select the chatbot that you've been working on to open it. 
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Chatbots tab and the Office Helper chatbot selected.](../media/chatbot.png)](../media/chatbot.png#lightbox)

## Task: Create a new topic

To create a new topic, follow these steps:

1. Go to **Topics** and then select **+ New topic**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the New topic button.](../media/new-topic-flow.png)](../media/new-topic-flow.png#lightbox)

1. Add the following trigger phrases and then select the button after each until all appear in the list:

   *Want to order swag*

   *I need to make a request for merch*

   *Can I put in a request?*

   *Place an order for swag*

   *How do I put in an order?*

1. Select **Details** and then enter **Request swag** in the **Name** box. Close the **Details** pane.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Details pane, showing Request swag entered in the Name box.](../media/details-name-box.png)](../media/details-name-box.png#lightbox)

1. In the **Message** box, add the following text:

    *I can help you request Contoso Coffee swag*. 
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing text being entered in the Message box.](../media/trigger-message.png)](../media/trigger-message.png#lightbox)

1. Save your bot before continuing to the next task by selecting the **Save** icon in the upper-right corner.

## Task: Create a flow to get a row from a Dataverse for Teams table

Power Virtual Agents in Teams comes with a built-in experience for Microsoft Power Automate, with templates to help make it easier for you to get your chatbot to call an action. In this task, you'll use Power Automate to look up the first item in your Assets table in Dataverse for Teams and then return that item as a suggestion for the user to request that item. 

1. Add a node and select **Call an action**. Select **Create a flow**, which will launch Power Automate inside Microsoft Teams.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Create a flow option.](../media/create-flow.png)](../media/create-flow.png#lightbox)

1. Select **Power Virtual Agents Flow Template**. This template is designed to pass inputs from the chat to a flow and then provide outputs from the flow back to Power Virtual Agents.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting Power Virtual Agents Flow Template.](../media/virtual-agent-flow.png)](../media/virtual-agent-flow.png#lightbox)

1. A screen might appear to confirm your flow connections. Select **Continue**.

1. The flow template should display, with the Power Virtual Agents input and output steps. You're not bringing inputs from the chat into this flow, so you don’t need to do anything in that first stage. Select **Add an action** between the input and output steps.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Add an action button.](../media/add-action.png)](../media/add-action.png#lightbox)

1. Search for **list rows** and then select the **List rows Microsoft Dataverse** action. 

    *This connector allows your chatbot to connect to your Dataverse for Teams tables, with various actions including creating, updating, deleting, or retrieving records*.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the List rows action.](../media/choose-operations.png)](../media/choose-operations.png#lightbox)

1. Select the **Assets** table name from the dropdown list. You can type the word **Assets** into the box to make it easier to find your table.

1. Select **Show advanced options** to view the rest of this action step.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Show advanced options dropdown menu in the List rows action step.](../media/advance-options.png)](../media/advance-options.png#lightbox)

1. To retrieve the first row from the table, enter the number **1** in the **Row count** box.

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the number one being entered in the Row count box.](../media/row-count.png)](../media/row-count.png#lightbox)

1. Compose a variable to store the information from the item that you retrieved in the previous step so that it's easier to pass it back to the chatbot. Add an action underneath this one, search for **compose**, and then select the **Compose (Data Operation)** action.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Compose Data Operation action.](../media/compose.png)](../media/compose.png#lightbox)

1.	In the action step, select the **Inputs** box, and then select the **Expression** tab in the **Dynamic content** box that appears. Enter the following expression into the function box of the **Expression** area of **Dynamic content** and then select **OK**. This expression gets the value of the item: 

    `first(body('List_rows')?['value'])`

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Inputs box and the Expression tab to add an expression.](../media/expression.png)](../media/expression.png#lightbox)

	A formula will show in the **Inputs** box.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the formula in the Inputs box.](../media/compose-inputs.png)](../media/compose-inputs.png#lightbox)

1.	Return the asset name and ID to the chatbot. Select the **Return value(s) to Power Virtual Agents** step and then select **+ Add an output**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Add an output button.](../media/add-output.png)](../media/add-output.png#lightbox)

1.	Select **Text** and then enter the title as **Name**. In the **Enter a value to respond** box, go to the **Expression** tab on the **Dynamic content** box and then enter the following formula. Substitute the schema name for your own schema name (the word **Name**, as shown in the following screenshot) for the **Asset Name** column in your table that you noted previously. Your schema name will have a different prefix. Select **OK**.

    `outputs('Compose')?['cra05_Name']`
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Enter a value to respond box, showing a formula entered in the Expression tab.](../media/return-value.png)](../media/return-value.png#lightbox)

1.	Repeat the previous step to add the ID to the outputs. Select **+ Add an output > Text**. Enter the title as **ID**. In the **Enter a value to respond** box, go to the **Expression** tab on the **Dynamic content** box and then enter the following formula. Substitute the highlighted schema name for your own schema name for the **Asset** column in your table that you noted previously. Your schema name will have a different prefix. Select **OK**.

    `outputs('Compose')?['cra05_AssetId']`

   Formulas will show in both output boxes.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Return Values to Power Virtual Agents action, showing formulas in both output boxes.](../media/compose-return-value.png)](../media/compose-return-value.png#lightbox)

1.	Change the name of your flow in the upper-left corner of the screen to **Get first asset**. Save by selecting the **Save** button.

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Get first asset flow and the Save button.](../media/save-asset.png)](../media/save-asset.png#lightbox)

1.	After your flow has been saved, select the blue arrow next to the name of your flow to return to Power Virtual Agents. In the next task, you'll connect this flow to your chatbot.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the blue arrow to return to Power Virtual Agents.](../media/return-flow.png)](../media/return-flow.png#lightbox)

## Task: Connect your flow with outputs to your chatbot

Your next task is to connect your flow with outputs to your chatbot. Under your **Message** node, select **Call an action** and then select the flow that you created in the previous task. Make sure that you select the name of the flow, not the blue hyperlink, to show flow details (the link will take you back to editing the flow).

   > [!div class="mx-imgBorder"]
   > [![Screenshot highlighting the Get first asset option under Call an action.](../media/get-first-asset.png)](../media/get-first-asset.png#lightbox)

Your flow is now connected to your chatbot.
 
   > [!div class="mx-imgBorder"]
   > [![Screenshot highlighting the flow details and the Power Automate outputs.](../media/flow-connected.png)](../media/flow-connected.png#lightbox)

## Task: Create a flow to submit a request for an asset

Follow these steps to create a flow to submit a request for an asset:

1. Add a new **Message** node underneath the flow action node and then enter the following text:

    *The first thing we always provide for new employees is*:

1. Select the variable button and then select the **Name** variable. This selection brings in the name of the first item from your Assets table that the flow retrieved in the previous step.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Variable button and selecting the Name variable.](../media/name-variable.png)](../media/name-variable.png#lightbox)

1. Add a node for **Ask a question**. Enter the following text into the **Ask a question** box:

    *Would you like me to request this for you?*

1. In the **Identify** box, open the options and then select **Boolean**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Identify box and showing the Boolean option.](../media/boolean.png)](../media/boolean.png#lightbox)

1. Edit the name of the variable to **FirstRequest**. Close the **Variable properties** pane by selecting the **X** in the upper-right corner.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the name of the variable changed to First Request.](../media/variable-properties.png)](../media/variable-properties.png#lightbox)

1. Add a new node and then select **Add a Condition**. In the left branch of the condition, select the **FirstRequest** variable from the dropdown list and then select **True** from the second dropdown list.
    
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Add a condition action, showing First Request and True selected in the dropdown lists.](../media/node-condition.png)](../media/node-condition.png#lightbox)

1. Add another node underneath and select **Ask a question**. Enter the following text:

    *Please add your comments to submit with this request*

1. From the **Identify** option, select **User’s entire response**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Identify option and the User's entire response option selected.](../media/user-response.png)](../media/user-response.png#lightbox)

1. Change the name of the variable to **Comments** and then close the **Variable properties** pane.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the variable name changed to Comments.](../media/variable-properties-name.png)](../media/variable-properties-name.png#lightbox)

1. Save your bot by selecting the **Save** button in the upper-right corner.
    
1.	Create another flow, this time to request the asset on behalf of the user. Add a new node, select **Call an action**, and then select **Create a flow**. 
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the Call an action and the Create a flow options selected.](../media/action-create-flow.png)](../media/action-create-flow.png#lightbox)

1.	Select **Power Virtual Agents Flow Template**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing Power Virtual Agents Flow Template selected.](../media/power-agent-template.png)](../media/power-agent-template.png#lightbox)

1.	In the previous flow, you got the ID of the asset that the person is now requesting. You need to pass that ID into this flow as an input from the chatbot. Open the first Power Virtual Agents step in the flow by selecting it and then select **+ Add an input**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the Add an input option selected in Power Virtual Agents.](../media/add-input-agent.png)](../media/add-input-agent.png#lightbox)

1.	Select **Text**, and then in the **Input name** box, enter **AssetID**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the selection of Text and Asset ID entered in the Input name box.](../media/input-name.png)](../media/input-name.png#lightbox)

1.	Repeat this step to add another input for the comments that are provided by the user. Select **+ Add an input**, select **Text**, and in the **Input name** box, enter **Comments**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the addition of another input name.](../media/another-input-name.png)](../media/input-name.png#lightbox)

1.	Add an action under this input step.

1.	Search for **add a new row** and then select the **Add a new row Microsoft Dataverse** action.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add a new row Microsoft Dataverse action being selected.](../media/add-new-row.png)](../media/add-new-row.png#lightbox)

1.	This flow will submit a request for the user. Select **Requests** from the **Table name** dropdown list and then select **Show advanced options**.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing Requests selected from the Table name dropdown list and the Show advanced options selection.](../media/row-advance-option.png)](../media/row-advance-option.png#lightbox)

1.	In the **Name** box, enter **New employee swag request**. Select in the **Comment** box and then select **Comments** from the **Dynamic content** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing New employee swag request entered in the Name box.](../media/row-comment.png)](../media/row-comment.png#lightbox)

1.	Select in the **Asset (Assets)** box and then enter the following expression (replace the prefix with the same prefix that you found in your own schema names previously). When you create the request and fill in the asset, you're connecting to the Assets table as well with the lookup column. The flow needs you to define the name of that connected table when you're creating this record.

    `cra05_assets()`

    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Asset Assets row, showing the expression entered in the box.](../media/row-asset.png)](../media/row-asset.png#lightbox)

1.	Select between the brackets in this formula and then select **AssetID** from the **Dynamic content** box. Make sure that **AssetID** dynamic content is between the brackets in your expression.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting Asset ID in the expression.](../media/asset-identification.png)](../media/asset-identification.png#lightbox)

1.	Change the name of your flow to **Create a request**. Save your flow and then use the back arrow next to the flow name to return to Power Virtual Agents.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the name of the flow changed to Create a request and the Save button.](../media/save-request.png)](../media/save-request.png#lightbox)

## Task: Connect your flow with inputs to your chatbot

To connect your flow with inputs to your chatbot, follow these steps:

1. Scroll down to the question where you asked the user to add comments. Add a new node, select **Call an action**, and then select the flow that you created. You may need to select **Overview** from the left navigation to get to this screen.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing Call an action and Create a request selected.](../media/create-request.png)](../media/create-request.png#lightbox)

1. Map the variables that you created in Power Virtual Agents to the inputs from the flow. Select your variables from the dropdown lists as follows:

    AssetID (text) gets value from - **ID**
    
    Comments (text) get value from - **Comments**
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the variables selected from the dropdown lists.](../media/comment-text.png)](../media/comment-text.png#lightbox)

1. Add a confirmation message so that the user will know that their request has been sent. Add a node underneath and then select **Show a message**. Enter the following text in the **Message** box.

    *Thank you, your request for has been submitted*.

1. Select after the word **for** and then select the **Name** variable.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the Name variable.](../media/name-variable-word.png)](../media/name-variable-word.png#lightbox)

1. Add another node underneath to end the conversation with a survey.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the addition of another node and the End the Conversation node.](../media/end-message.png)](../media/end-message.png#lightbox)

1. Scroll up to the **Would you like me to request this for you** question node. Under the condition branch for **All other conditions**, add an **End with survey** node.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the End of Conversation node.](../media/end-flow-survey.png)](../media/end-flow-survey.png#lightbox)

1. Save your bot by selecting the **Save** icon.

## Task: Test your bot

Now it's time to test your bot.

1. Turn on the **Track between topics** toggle at the top of the **Test bot** pane. Type a trigger phrase, such as **I want to order swag**, in the **Test bot** pane. The bot should return a suggested item, which is the first item in your Assets table.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the Track between topics toggle switch turned on in the Test bot pane.](../media/track-topic-toggle.png)](../media/track-topic-toggle.png#lightbox)

1. Continue the conversation with the chatbot by selecting **Yes** and then entering your comments: 

    *Can I get this delivered to me by Monday, please*.

1. A confirmation message will appear, showing the name of the asset and the **End of Conversation** topic.
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the conversation message with the name of the asset.](../media/confirmation-name-asset.png)](../media/confirmation-name-asset.png#lightbox)

1. To check that the request has been submitted, select the Teams icon in the left navigation bar. Go to the team and channel where you created your app in a previous lab in this learning path. The request that you submitted should show in the app. 
 
    > [!div class="mx-imgBorder"]
    > [![Screenshot highlighting the submitted app in Teams and in the channel.](../media/submitted.png)](../media/submitted.png#lightbox)

Congratulations, you've built a bot that can answer questions, retrieve an asset from your Dataverse for Teams database, and submit a request on behalf of the user. 

In the next exercise, we'll publish and share it and use it in Teams chat.
