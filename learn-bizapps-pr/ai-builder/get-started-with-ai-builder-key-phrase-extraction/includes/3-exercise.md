For this exercise, you will develop a simple flow with Power Automate that uses AI Builder Key phrase extraction to check for key phrases whenever you receive a new message in a Viva Engage group. The sentiment is then sent as a push notification to your mobile flow app. For more information, see [Create a flow in Power Automate](/power-automate/get-started-logic-flow/?azure-portal=true).

**Create a flow that extracts key phrases**

Power Automate has connectors to many different services, including Viva Engage. Create a flow that automatically stores key phrases to a Microsoft Excel file for each message that arrives in your Viva Engage group.

1.  Sign in to [Power Automate](https://make.powerautomate.com/?azure-portal=true).

2.  Select **My flows**.

3.  Select **New > Automated-from blank**.

4.  Search for Viva Engage in the **Choose your flow's trigger** field and then select **When there is a new message in a group**. If you do not have a Viva Engage account, you could select **When a new email arrives** as your flow's trigger. 

5.  Select **Create**.

6.  Select the Viva Engage group that you want to use for key phrase extraction.

7.  Select **Add an action** and then select **Predict** under **Actions**.

8.  Select the following parameters:

    -   **Model** - KeyphraseExtraction model

    -   **Text** - Message Body Text

    -   **Language** - Two-letter abbreviation for your language

9. Add the **Add a row into a table** action from Excel connector. Select your previously saved Excel file and the table that you want to update with key phrases.

10. In the **Select an output from previous steps** field, enter **Key phrases results**.

11.  Select **Save** to save and test the flow.

12. To change the flow, select **Edit flow**.

Now, when a new message on a Viva Engage channel arrives, the Excel file will automatically update with key phrases from the message.
