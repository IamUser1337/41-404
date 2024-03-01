Most organizations gain efficiency by forecasting events that will impact their operations.

Many targets that they set are around inventory allocations, marketing budgets, and other areas where the quality of forecasting can improve their efficiency.

In this module, you'll learn how the AI Builder prediction model can help you establish the probability of an event to occur based on captured historical behavior.

## AI Builder prediction model

Prediction is an AI Builder custom model. During training, the prediction model will analyze patterns in the historical data that you provide. Based on the detected patterns, it will predict future outcomes for new data.

You can use prediction to process questions in the following ways:

-   Users can choose from one of two options, such as:

    -   Were you satisfied with your stay? Yes/No

    -   At the pool, what was the water temperature? Hot/Cold

    -   Do you have an arrival preference? Day/Night

-   Users can choose one from multiple options, such as:

    When was the parcel delivered?

      -   Early

      -   On Time

      -   Late

      -   Lost

-   You can also require users to answer by entering a number, such as:

    -   How many days for rental: 12

    -   How many rooms required: 2

## Historical behavior 

As with other custom models, prediction requires training before it's published and made available to use in your solutions.

Your first objective is to determine which data can provide the historical behavior that will help determine the potential outcome for new events. You don't need to be biased in your selection. Using a broad set of related information will provide more options for the AI engine to determine the actual trends and what influences the outcome.

Consider the following requirements for the training data:

-   It must be in Microsoft Dataverse.

-   It should require less than 1.5 GB in database storage.

-   For best results, you should use 1,000 or more rows with a realistic distribution between options.

## Performance and use

After each training, AI Builder provides a performance grade to help you evaluate the accuracy of the prediction:

-   **Grade A** –  The best grade; improvement might still be possible.

-   **Grade B** - Prediction is correct for most cases; improvement can be considered.

-   **Grade C** - Better than a random guess, but it’s recommended that you adjust the model to improve the performance.

-   **Grade D** - A situation where the result is similar or worse than a random guess or is close to 100 percent accuracy. In both cases, the model and underlying data must be revised to perform the prediction at an acceptable level.

When the performance grade is at a satisfactory level for your business scenario, you can publish the model and make it available to run against live data.

Different options are available when you’re using the prediction model:

- **Run now** - On-demand request to update the outcome on live data.

-  **Real-time prediction** - Applicable for scenarios where the prediction is required instantly.

Now that you’ve learned the fundamentals of AI Builder prediction model, you'll learn how to solve business problems with those types of models.
