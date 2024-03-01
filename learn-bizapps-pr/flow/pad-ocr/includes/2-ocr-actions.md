Power Automate for desktop provides a wide variety of optical character recognition (OCR) actions that you can use to locate or extract text from any application or file.

## Create an OCR engine

To perform any OCR operation, you have to initialize an OCR engine. OCR engines are software tools used to convert typed or handwritten content into a machine-readable and editable format.

Power Automate for desktop supports the Windows and Google Tesseract engine and enables users to initialize it through any OCR action. To initialize the engine, you need to specify its language and set the image's width and height multipliers.

Image multipliers increase the size of the image to make text extraction or searching more effective. Although multipliers are a valuable mechanism, avoid setting values greater than three because high values might lead to failed results.

![Screenshot of the Tesseract options in the Extract text with O C R action.](..\media\extract-text-with-ocr-action-windows-engine-options.png)

Additionally, you can enable the **Use other language** option while using the Tesseract engine to use languages outside the provided list. To use another language, populate the language's abbreviation and the respective data file's path.

## Extract text from screen or images

To extract data from a screen or an image, you can use the **Extract text with OCR** action. This action provides options to extract text from the whole screen, the foreground window, or an image file.

The ability to extract text from the screen is a powerful concept and enables you to apply OCR across the Windows platform. The extraction is not limited to a list of files, but you can extract any text displayed on your screen.

In the action's properties, you can also specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![Screenshot of the Extract text with O C R action.](..\media\extract-text-with-ocr-action.png)

## Verify if a text appears on the screen or a window

Except for text extraction, OCR actions enable you to verify whether a given text appears on the screen or the foreground window.

Using this tool, you can apply different execution paths based on an existing text. For example, you can review the client name in a scanned invoice and execute particular actions based on the result.

To implement this condition, deploy the **If text on screen (OCR)** action. In the action's properties, you have to specify the text to search for and its source. The text can be a literal value or a regular expression.

You can also specify whether the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![Screenshot of the If text on screen action.](..\media\if-text-on-screen-action.png)

## Wait for a text to appear on the screen

While creating flows to automate business procedures, you may need to wait for an application or webpage to load before executing other actions. Performing actions without ensuring that the proper information has been loaded can cause the flow to fail.

To ensure that the required information is loaded, you can use the **Wait for text on screen (OCR)** action.

In the action's properties, you can select whether to wait for a defined text to appear or disappear. The text can be a literal value or a regular expression, while the source can be the whole screen or the foreground window.

![Screenshot of the Wait for text on screen action.](..\media\wait-for-text-on-screen.png)

You can also specify whether the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

As an output, the action produces two variables that describe the exact position of the found text.

![Screenshot of the produced variables of the Wait for text on screen action.](..\media\wait-for-text-on-screen-produced-variables.png)

## Move the cursor to a defined text on the screen

Power Automate for desktop provides the mouse and keyboard actions to automate applications that aren't compatible with the UI actions. These actions can be helpful to automate legacy applications or applications that apply strict security restrictions.

In these circumstances, you can use the **Move mouse to text on screen** action to move the cursor on the screen.

In the action's properties, you have to populate the text to search for and its source. The text can be a literal value or a regular expression, while the source can be the whole screen or the foreground window.

You can also specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion that is relative to an image.

![Screenshot of the Move mouse to text on screen action.](..\media\move-mouse-to-text-on-screen.png)

If several occurrences of the same text exist in the defined source, you can specify which one to select in the **Occurrences** field. Additionally, you can choose whether to move the cursor instantly or with animation.

As an output, the action produces four variables that describe the found text's exact position and size.

![Screenshot of the produced variables of the Move mouse to text on screen action.](..\media\move-mouse-to-text-on-screen-produced-variables.png)
