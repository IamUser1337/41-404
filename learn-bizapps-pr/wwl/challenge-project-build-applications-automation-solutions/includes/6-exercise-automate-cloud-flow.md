

Create a cloud flow that is triggered from a button on the canvas application.  This flow should gather information from the player record to send to a stakeholder.
- When the flow is triggered, it should get the player row from Dataverse, and then send an email that includes some information about the player to someone (you may use your own user’s email).
- Add a button to the edit player form in the canvas application that triggers this flow.
- This button shouldn't be visible in the app when creating a new player.

## Considerations
- Is this requirement too vague to implement?
- As this cloud flow is a proof of concept, what can you make to show stakeholders the power of automation?

## Check your work
1. Walk through your flow steps and see what could be missing. Where would you spend your time testing in the future? 
2. Open your canvas app and open the player form to create a new player. Before creating the player, validate that your flow button is not visible. 
3. Finish creating a player in your canvas app. Validate that the flow button is now visible. Ensure that your flow button triggers the flow, or take some time to research how you might do this if given the time. 

> [!TIP]
> If you get stuck here, reviewing [Integrate Power Automate flows and Dataverse](/training/paths/integrate-dataverse-power-automate/) may help.