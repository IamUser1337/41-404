After creating your AI Builder model, you can use it in Power Apps and Power Automate.

## View your model details

After your model has completed training, you can view important details about your newly trained model on a details page for that model. The information might vary depending on the model type.

[![Models > My Document Processing model shows a Training document with Publish and Quick Test buttons, a Selected fields list, and how your model is used.](../media/image-4.jpg)](../media/image-4.jpg#lightbox)

On the model details page, you can see the customizations that you made to train your model. It shows additional insights with the accuracy score so that you can improve your model performance. Some model types  give you the opportunity to quick test your model
to see it live in action.

You can access this page at any time from the left menu by
selecting **AI Builder > Models** and then searching for your model name.

## Publish your model

Your model can't be used until it is published. If you are satisfied
with your model, select **Publish** to make it available.

Three main ways that you can use your model are:

- As a component in an app
- As an action in a flow
- As new data in your database

When your model is published, select **Use model** to see a list of the
available actions that you can take to use your model.

## Use your model in an app

In the **Use your model** pane, select **Create new app**, which appears if your
model type supports it.

This selection redirects you to the canvas app creation experience, with the AI
Builder component already added to your canvas and your model
automatically linked to the component.

![FormProcessor1 is in design view with the Text property set to Analyze.](../media/image-5.jpg)

You can add AI Builder components to your existing apps at any time
by selecting the **Insert** tab and then selecting the component from the **AI Builder** menu.

![A I Builder menu is expanded to reveal Business card reader, Form Processor, Object detector, and Text recognizer options.](../media/image-6.png)

## Use your model in a flow

In the **Use your model** pane, select **Create new flow**, which appears if
your model type supports it.

This selection redirects you to the flow template page in Power Automate. Confirm
the connections and then select **Continue**.

![My Document Processing flow shows Manually trigger a flow, and Predict.](../media/image-7.jpg)

In the flow creation experience, you'll find the AI Builder action
already added to your flow and your model automatically linked to the
action.

You can add the AI Builder action to [solution-aware
flows](/power-automate/create-flow-solution/?azure-portal=true)
by searching for the **Predict** action under **Microsoft Dataverse** and then selecting your model name from the **Model** drop-down menu.

## Use your model in your database

Some model types write the intelligence back to your database, so you
can use it in your data views in Power Apps or Power BI.

After you have published your model, some model types automatically begin scheduling the model to write data back to your database by default. For others, you can customize the scheduling. In the **Use your model** pane, select **Set run schedule** to define the frequency. This option appears when the model supports it.

You have now learned the various ways that you can use your AI Builder models in Power Apps and Power Automate.
