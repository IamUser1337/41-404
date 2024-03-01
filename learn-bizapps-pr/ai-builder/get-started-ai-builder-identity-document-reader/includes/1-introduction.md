Before you begin this course, we recommend that you first complete the [Get started with AI Builder](/training/modules/get-started-with-ai-builder/?azure-portal=true) module and read the [What is AI Builder?](/ai-builder/overview/?azure-portal=true) documentation page.

The identity document reader (ID reader) in AI Builder is a prebuilt AI model that extracts data from passports from any country/region and US driver licenses.

Like any other prebuilt experience in AI Builder, you can add this feature of AI in any existing flows or apps in Microsoft Power Apps because it's designed to work with the whole business and productivity tools from Microsoft. You can read to and write from SharePoint, export in Microsoft Excel, and then feed the output into Dynamics 365.

You might want to use this functionality if your business requires you to check for proof of residency, for instance. You can use the ID reader to determine if the extracted data from a given passport matches any record that you might have in an Excel spreadsheet or database.

Custom AI models require that you provide data samples to train with before you can use them. Prebuilt models are pretrained with data from Microsoft, so they're ready to use immediately. The ID reader is a prebuilt model. It has been trained to implement this specific data extraction, and it uses the latest technology in Microsoft AI Form Recognizer. Additionally, it's able to extract with imperfect photos or scans (glossy or tilted images, for instance).

No picture or face detection happens when the image is processed, and scans of the IDs are deleted after they've been processed by the model.
