In a digitally driven era, the volume of documents, emails, and other types of messages that an organization must process can be overwhelming.

Category classification provides you with opportunities to automatically determine the priority level of messages and even help detect potential spam messages. By classifying the messages in different categories, you'll make it possible to implement such automations.

AI Builder category classification provides the potential for you to learn from previously labeled text and be trained to recognize your own categories for new messages.

In this unit, you'll learn how AI Builder category classification can process unstructured text data that's stored in Microsoft Dataverse into business-specific categories.

## AI Builder category classification

Category classification extraction is an AI Builder custom model. It requires training on existing data before you can publish and consume it in your processes.

To train a new model, make sure that you identify or create a Dataverse table for the data source and then consider the following recommendations:

- Include reference text and related tags for both columns in the same table.

- Specify a Tags column, such as no tag, single tag, or multiple tags that are delimited by a supported separator (commas, semicolons, and tab characters).

- You need at least 10 examples (rows) where a tag is referenced and 10 examples (rows) where it isn't referenced for each category.

- Use a table that has between two and 200 distinct tags.

- Ensure that reference text has fewer than 5,000 characters.

- Ensure that text is in one of the [supported languages](/ai-builder/before-you-build-text-classification-model?azure-portal=true#supported-languages).

As you add more data to the reference tables, you can retrain a model as needed to provide a current and more accurate performance level.

Now that you've learned about the fundamentals of AI Builder category classification, you'll learn how to solve business problems with this custom model.
