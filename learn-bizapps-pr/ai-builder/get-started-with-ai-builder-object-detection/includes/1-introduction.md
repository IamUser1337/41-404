Before following this course, we recommend that you read the [Get Started with AI Builder](/training/modules/get-started-with-ai-builder/?azure-portal=true) module and read the [What is AI Builder?](/ai-builder/overview/?azure-portal=true) documentation.

## Introduction to AI Builder Object detection

AI Builder Object detection is an AI model that you can train to detect objects in pictures. AI models usually require that you provide samples of data to train before you are able to perform predictions. Prebuilt models are pre-trained by using a set of samples that are provided by Microsoft, so they are instantly ready to be used in predictions.

When you are predicting, AI Builder Object detection will recognize the objects that you submitted during the training phase with help from [Azure Custom Vision Object detection](/azure/cognitive-services/custom-vision-service/home/?azure-portal=true) technology. Object detection can detect up to 500 different objects in a single model and support JPG, PNG, BMP image format or photos through the Power Apps control.

## What you can do with Object detection

AI Builder Object detection provides object recognition capabilities to makers. Being fully integrated with the rest of the business platform means that you can accelerate manual workflow and automate a wide range of scenarios that are currently only achieved with human intervention.

### Scenario 1 - Object counting

Front-line audit workers take pictures of products on shelves. Object detection provides a count of each product in the picture. This information can be used to update the inventory management software.

**Example:**

A consumer packaged goods company sends auditors to take pictures of their products on shelves for compliance detection. The auditor takes a picture, which will then be processed by AI Builder to extract the numbers of each product. Those numbers can be transmitted to the company in real time to assess supermarket compliance.

### Scenario 2 - Brand logo recognition

A company wants to monitor the use of its logo and brand on social media.

**Example:**

A company processes images that are flagged with a specific hashtag. Additionally, they can detect the presence of their logo and see how it's being used. That process is run automatically through a flow.

### Scenario 3 - Object recognition in a learning scenario

A field agent takes a picture of a product. The product is recognized, and all manually entered, additional information is automatically retrieved.

**Example:**

A company sends technicians to repair industrial boilers. The technicians are not required to carry manuals and reference guides for all boilers that they might work on. The technicians take a picture of a boiler and gain access to the product manual, which was written by an expert in the company.


Now that you've learned about the basics of AI Builder Object detection, you can create your first Object detection model.
