When a flow contains a large number of actions, it may be split up into subflows, making it more manageable and easier to maintain. Subflows can be used to organize a flow's actions, but they also allow the reuse of parts of the flow, which helps to avoid cluttering by copy-pasted actions.

Finished flows usually contain tens, hundreds, or even thousands of actions:

![Screenshot of the workspace with a number of actions and nested loops.](..\media\busy-workspace.png)

Let’s improve this flow's readability without changing its functionality, using subflows to break it up into self-contained parts. This can be done through the subflows list on the top-left:

![Screenshot of the Subflows pane expanded to reveal the search box.](..\media\subflows-list.png)

The **Main** subflow is always present, since it signifies the start of the flow; we will add more subflows by pressing the **New subflow** button:

![Screenshot of the Subflows pane with the New subflow button highlighted.](..\media\subflows-pane.png)

An empty subflow is created and named. We will proceed to add a few subflows which correspond to discrete parts of the flow:

![Screenshot of the Subflows pane with the empty subflow added.](..\media\subflows-pane-continued.png)

New subflows are visible as tabs at the top of the workspace:

![Screenshot of the new subflow tabs along the top.](..\media\subflows-tabs.png)

Now, we can proceed to move actions from the Main subflow into these new ones:

![Screenshot of the generate master file subflow workspace.](..\media\generate-master-file-subflow-workspace.png)

Finally, to run the subflows, we must make use of the **Run subflow** action:

![Screenshot of the main subflow workspace.](..\media\main-subflow-workspace.png)
