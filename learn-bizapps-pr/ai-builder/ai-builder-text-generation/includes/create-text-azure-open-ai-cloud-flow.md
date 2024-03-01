In this exercise, you'll learn how to create text from blank with text generation in a cloud flow.

Your task is to create an automated flow from blank when a new email arrives, summarize the email, send the response to Microsoft Teams by using the AI Builder action **Create text with GPT**.

1. Go to [Power Automate](https://make.powerautomate.com/?azure-portal=true).

1. On the left pane, select **Create > Automated cloud flow**.

1. Name your flow, for instance,  **Summarize emails**.

1. Select **When a new email arrives (V3)** as a trigger.

1. Select **Create**.

1. Select **Next step**.

1. Select **Html to text (Preview)**.

1. Select **Body** from the **Dynamic content** list.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the flow HTML to text with focus on the Body and the Body option selected in the Dynamic content list.](../media/html-text.png)](../media/html-text.png#lightbox)

1. Select **New step > AI Builder > Create text with GPT (preview)**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the new step named AI Builder with focus on the Create text with GPT action.](../media/create-text-action.png)](../media/create-text-action.png#lightbox)

1. Select **Create prompt > Start from blank**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the flow with focus on the Use prompt templates option in the Create text with GPT step and the Start from blank option selected in the Create prompt dialog.](../media/use-prompt-start-blank.png)](../media/use-prompt-start-blank.png#lightbox)

   > [!NOTE]
   > Make sure that AI-generated content is accurate and appropriate before you use it.

1. In the **Create prompt** window, describe the text that the model should create.

1. Add your email content between `###` and `###`.

   `###`

   `<Your Text>`

   `###`

1. Select **Test it out**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Create prompt window filled in.](../media/describe-text-test.png)](../media/describe-text-test.png#lightbox)

   > [!NOTE]
   > No user data has been stored; this exercise has been designed specifically to help you with your queries on text generation.

1. If you're satisfied with the response, select **Use prompt in flow**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Create prompt window with focus on the Response.](../media/test-response.png)](../media/test-response.png#lightbox)

   Before saving and running your flow, make sure that you replace your sample with the dynamic content that your flow is using.

1. In the AI Builder action **Create text with GPT**, select **The plain text content** option from the **Dynamic content** list.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Create text with GPT with the Dynamic content list open and focus on The plain text content option.](../media/select-plain-text-content.png)](../media/select-plain-text-content.png#lightbox)

   > [!IMPORTANT]
   > To ensure safe practices, make sure that you exercise caution when sharing AI-generated content due to the possibility of errors and biases. Using human oversight before posting on platforms like Teams, internally and externally, is highly recommended.

1. Select **Next step > Approvals**.

1. Select **Start and wait for an approval** and then complete the following actions:

   1. In the **Approval type** field, enter **Select Approve/Reject - First to respond**.

   1. In the **Title** field, enter **Review summarized email**.

   1. In the **Details** box, select **Text** from the **Dynamic content** list.

   1. In the **Assigned to** field, enter the email alias of the approver.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Start and wait for an approval step filled in and the Dynamic content window showing.](../media/start-wait-approval.png)](../media/start-wait-approval.png#lightbox)

1. Select **Next step >  Condition**.

1. In the **Condition** box, add **Outcome** from the **Dynamic content** list from the approval step as the condition to check.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Condition step with focus on Outcome from the Dynamic content list.](../media/approvals-set-outcome.png)](../media/approvals-set-outcome.png#lightbox)

1. In the **Condition** box, set **Approve** as the positive response to validate.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Condition step with focus on Approve as the positive response.](../media/approvals-set-approve.png)](../media/approvals-set-approve.png#lightbox)

1. If the condition is true (which is Approve in this case), select **+ New step > Teams** and then select **Post message in a chat or channel**.

1. Use the AI-generated **Text** from the **Dynamic content** list as the content to post on a desired Teams chat or channel.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the If yes side of the condition filled in with focus on the Dynamic content Text field.](../media/post-message-chat.png)](../media/post-message-chat.png#lightbox)

1. Select **Save** in the upper right and then select **Test** to try out your flow.

Congratulations, you've created a flow that uses an AI Builder to create text with GPT capability.

## Observe the approvals in action
To observe the approvals in action, follow these steps:

1. On the left pane, select **Approvals**.

1. Select the **Review summarized email** request.

1. On the right pane, you can review the **details** of the AI Text that has generated.

1. Choose your response as **Approve**, **Reject**, or **Reassign** (depending on your satisfaction with the generated text). For this exercise, select **Approve**.

1. Select **Confirm**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Power Automate Approvals page, showing the Review summarized email request selected and the Respond: Approve pane filled in with details.](../media/approvals.png)](../media/approvals.png#lightbox)

The post message should show as having been sent to Teams.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the message in Teams.](../media/teams.png)](../media/teams.png#lightbox)

> [!IMPORTANT]
> Make sure that AI-generated content is accurate and appropriate before you use it.
