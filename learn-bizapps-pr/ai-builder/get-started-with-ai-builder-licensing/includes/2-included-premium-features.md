After you have a license for the base product that includes AI Builder features, you can access those features without restriction.

AI Builder preview features are included features. You can create models based on preview features and train and publish them without restriction. You can use them (in other words, perform predict actions) without restrictions.

Other AI Builder experiences might be considered as included features, for example, some of the *try out* experiences in prebuilt template cards. You don't need to buy capacity or a license to use these experiences.

Eventually, preview scenarios are released for general availability (GA); then, they become premium features. Every model that is linked to a premium feature is then considered premium, even if it was complete and had been used as a preview model before. In these cases, you must have the correct license and capacity to continue using them.

All GA scenarios are premium features. As such, they consume AI Builder capacity when they are used. To understand what it means to use a premium feature, you should first learn about the different ways that an AI model can be used today:

- For a model that needs training, as soon as it is configured and trained, you can use it in quick test.

- After a model has been published, or if it is a prebuilt model, you can use it in Power Automate.

- You can use your AI models in Power Apps by using a formula or by inserting a specific AI Builder component.

- You can use a model by scheduling it to run on new and updated records or run it periodically.

- You can use certain model types in an integrated way in Dynamics 365 or SharePoint.

For all these experiences, AI models are used and an output is created. These outputs are the actions that use the AI Builder add-on capacity. Depending on the configuration and data that are used, your models use different amounts of AI Builder capacity.

In addition to these prediction actions, which are common to all scenarios, some features use AI Builder capacity to train the model. Indeed, when you are training a model, a large volume of data can be used, so more CPU computing is required. For that reason, some model types such as object detection use AI Builder capacity during training. In this case, the amount of AI Builder capacity depends on the number of images but also on the chosen domain.

For each of these actions where AI Builder capacity is required are two ways to provide it:

- Assign AI Builder capacity to environment

- Activate an AI Builder trial at user level

These concepts will be discussed in a later lesson. For now, remember that AI Builder premium features require AI Builder capacity to run a model (performing prediction), and in some cases, to train models. Therefore, creating a model cannot be done without AI Builder capacity.

You can now differentiate between included and premium features. To review, included features can be used without capacity, with no time or volume limitation, for all actions. Premium features require capacity, which is required at creation for custom models and is required and consumed when a model is used or, in some cases like object detection, when a model is trained. The amount of consumed capacity depends mainly on individual factors.
