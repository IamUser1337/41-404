Generally, when you build a cloud flow, each step in the flow is an independent transaction. For example, if the first action step in a flow uses **Add a new row** to create a row in a Dataverse table, and then later a step fails, and the flow terminates, that new row is still in the Dataverse table. You could handle this situation by handling errors in the flow, and in your error handling, compensate for the failure by removing the new row before the flow terminates. This approach would leave things in their state before the flow ran.

The Dataverse connector provides an alternative to this approach when you must ensure two or more Dataverse actions are completed or rolled back. Using the **Perform a changeset request**, you can combine two or more Dataverse actions into a single changeset or transaction. With the **Perform a changeset request** action, you can only include the Dataverse **Add a new row**, **Delete a row**, and **Update a row** actions in the changeset.

The actions you include in the changeset can use dynamic content from prior steps before the **Perform a changeset request** action but can't include dynamic content from other actions within the changeset. For example, if you create an Account table row in the first action inside the changeset, you can't use the row ID to associate it with the second action that creates a Contact row.

Let's look at an example of how you might use this. Our scenario has a Rewards Account where a customer earns points. When they redeem the points earned for an award, we need to create a row in the Reward Redemption table and debit the points from their row in the Reward Account table.

The following is how you can do this without a changeset. One action runs after another. If the second action fails, you already debited the points, and the reward is never delivered.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the reward process.](../media/reward-process.svg)](../media/reward-process.svg#lightbox)

Instead we can use the **Perform a changeset request** action and include both the update and the create inside the changeset.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the perform a change-set request action.](../media/changeset.svg)](../media/changeset.svg#lightbox)

Using this approach either they both complete or they both don't complete.
