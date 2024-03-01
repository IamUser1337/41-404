AI Builder is a Microsoft Power Platform capability that provides AI models that are designed to optimize your business processes. AI Builder enables your business to use intelligence to automate processes and glean insights from your data in Power Apps and Power Automate. With AI Builder, you don't need coding or data science skills to access the power of AI. You can build custom models tailored to your needs or choose a prebuilt model that is ready to use for common business scenarios.

:::image type="content" source="../media/07-describe-ai-authoring-experience-pp-09.png" alt-text="Screenshot of the AI Builder home page that also shows template solutions.":::

### Add intelligence to your business

In AI Builder, you can choose from multiple model types that are suited to different business scenarios. Here are several examples:

- If you want to use intelligence to detect your products in images, you can refine a custom AI Builder object detection model. With a customizable model, you build, train, and publish it for your intended use.

- If you want to use intelligence to automate your expense reports by scanning and processing business receipts, you can use a prebuilt AI Builder receipt scanning model. All prebuilt models allow you to go straight to productivity.

- If you want to design a marketing campaign based on patterns in your historical data, you can use a custom prediction model tailored to your business, using your own historical data.

There are two primary types of AI Builder models:

- **Prebuilt**: These are models that help you to add intelligence to apps and flows without having to gather data and then build, train, and publish the model.

- **Custom**: These are models that help you create more complex or targeted AI solutions. You build these models from the ground up.

The following prebuild models are available:

- **Business card reader**: Extracts information from business card images. If it detects a business card in the image, the AI model extracts information such as the person's name, job title, address, email, company, and phone numbers.

- **Category classification**: The prebuilt category classification model is a ready to use AI model that is configured to classify your text into categories that are useful for a specific business scenario. The first prebuilt category classification AI model is built around customer feedback uses. Check back for more category classification prebuilt models or check release plans to see what might be coming.

- **Entity extraction**: The prebuilt entity extraction model recognizes specific data from text that's of interest to your business. The model identifies key elements from text, and then classifies them into predefined categories. This can help to transform unstructured data into structured data that's machine-readable. You can then apply processing to retrieve information, extract facts, and answer questions.

- **ID reader**: You can use the identity document (ID) reader prebuilt model to extract information from passports and US driver licenses, social security, and green cards. The model extracts information such as the person’s first name, date of birth, or gender.

- **Invoice processing**: The invoice processing prebuilt AI model extracts key invoice data to help automate the processing of invoices. The invoice processing model is optimized to recognize common invoice elements like invoice ID, invoice date, amount due, and more.

- **Key phrase extraction**: The key phrase extraction prebuilt model identifies the main points in a text document. For example, given input text "The food was delicious and there was great service!", the model returns the main talking points: "food" and "great service." This model can extract a list of key phrases from unstructured text documents.

- **Language detection**: The language detection prebuilt model identifies the predominant language of a text document. The model analyzes the text and returns the detected language and a numeric score from 0 through 1. Scores close to one indicate higher confidence in the result. The detected language is returned as the "script" of the language. For instance, for the phrase "I have a dog," it returns "en" instead of "en-US." The response for languages that can't be detected is **unknown**.

- **Receipt processing**: Receipt processing is a prebuilt model that uses state-of-the-art optical character recognition (OCR) to detect printed and handwritten text and extract key information from receipts.

- **Sentiment analysis**: The sentiment analysis prebuilt model detects positive or negative sentiment in text data. You can use it to analyze social media, customer reviews, or any text data you're interested in. Sentiment analysis evaluates text input and gives scores and labels at a sentence and document level. The scores and labels can be positive, negative, or neutral. At the document level, there can also be a "mixed" sentiment label, which has no score. Aggregating the sentence scores determines the sentiment of the document.

- **Text recognition**: The text recognition prebuilt model extracts words from documents and images into machine-readable character streams. It uses state-of-the-art optical character recognition (OCR) to detect printed and handwritten text in images.

- **Text translation**: The text translation prebuilt model translates your text data in real time across more than 60 languages. This prebuilt model could help remove language barriers within your company. The text translation model can also detect the language of the text data you want to translate.