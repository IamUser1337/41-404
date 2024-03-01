
The basic Power Apps creator journey to build a canvas app looks something like this:

- Identify a business need that Power Apps can address.

- Connect to any necessary data in your Power Apps.

- Design the app using controls, buttons, and an easy-to-use interface. Then your end user can interact with the data to accomplish the business need.

- Save and publish the app and test functionality.

- Once satisfied, share the app with end users to give them a better business process.

To help app creators during their journey, Power Apps has many different components to build solutions including screens, inputs, galleries, forms, and more. 

Let's review some of the most common elements you need to get started.

## Power Apps components

### Power Apps Studio

Power Apps Studio is the web interface used to build Power Apps. With Power Apps, there's no client to download or install for building apps. Everything is done from the browser by logging into [https://make.PowerApps.com](https://make.powerapps.com/). Once in Power Apps studio, you can create an app from scratch, or use one of the many different templates available to speed up development of your app. 

:::image type="content" source="../media/03-describe-building-power-apps-06.png" alt-text="Screenshot of Power Apps Studio showing how to request a template to fit the project objective.":::

### App format

The first step in creating your app is to choose the format of your app: Mobile or Tablet. While both formats can be used interchangeably on a mobile device, a tablet, or a computer, each has different defaults around sizing of the screens and controls. Once you choose the format for an app, you can't change it.

:::image type="content" source="../media/describe-building-apps-with-power-apps-07.png" alt-text="Screenshot of option to choose app format of Tablet or Phone.":::

### Connectors

Once you identified the app format you want to use, you need to connect your app to your data. In Power Apps, this step is done using connectors. There are over 1,000 prebuilt connectors available. 

:::image type="content" source="../media/03-describe-building-power-apps-08.png" alt-text="Screenshot of option to select a data source.":::

### Galleries

As you build your app, you may encounter scenarios where you need to display a list of records on a screen. In Power Apps, these displays are done with the Gallery control. A gallery displays rows from a table of data. A template defines the display of a row, which you can customize to meet your needs. This process allows you to control which columns are shown and how they're formatted. Power Apps then applies this template automatically to every row in your data.

:::image type="content" source="../media/03-describe-building-power-apps-1-09.png" alt-text="Screenshot of sample data display.":::

### Forms

Unlike Galleries, Forms are focused on working with a specific record, often based on a selection from a gallery. In this experience, a user browses a gallery to find and select the desired row to view the details on the form. Forms enable a user to view detailed information, save new records, and edit existing ones. Form modes control the various actions performed with forms, allowing the form to serve many purposes.

 
### Input Controls

To allow you maximum flexibility in customizing your apps, Power Apps has a large selection of Input controls. Text inputs, buttons, dropdowns, toggles, date pickers, and sliders are a few examples. You can add these controls to galleries, forms, and screens to build a functional and aesthetic experience for your app. All inputs have a multitude of settings for default data, formatting, and actions, which allow you to build an app that has the right user experience for your business process.

 
### Intelligent Controls

In addition to common inputs as covered, Power Apps also provides a rich set of controls for more advanced operations. There are hardware-backed controls, which allow access to the camera, bar code scanner, GPS, and more hardware features. There are also service backed controls like the business card reader or object detector, which allow you to add artificial intelligence to your app without writing code.


### Functions

Functions are the glue that binds all these controls, inputs, and data sources together. You can use one or more functions to create formulas in your apps. These formulas are like the language you use in Excel and can be used for actions such as sending data to a data source, formatting information, creating animations, and more. No complicated code is necessary. You just use powerful functions with straightforward inputs to enhance your app.

### Responsive containers

When you create a canvas app in Power Apps, you specify whether to tailor the app for a phone or a tablet. This determines the size and shape of the canvas provided to build your app. This can create challenges when an app designed for one from factor runs on another form factor. For example, when an app, which is designed for a phone runs in a large browser window, the app scales to compensate and typically looks oversized for its space. The app can't take advantage of the extra pixels by showing more controls or more content.

To assist with this, Power Apps includes an option for responsive layout containers. When you use a responsive layout, controls can respond to different devices or window sizes, making various experiences feel more natural. Additionally, when you're working with responsive containers, you can also easily add and reorder controls within and between responsive layout containers. These controls can be easily positioned using Drag and Drop functionality. 

:::image type="content" source="../media/03-describe-building-power-apps-10.png" alt-text="Screenshot that displays inserting responsive containers.":::

### Copilot in Power Apps

As with most Microsoft applications, Copilot is changing the way that work is being done. This is no different with Power Apps. Copilot is helping to make the processing, building, and using Power Apps easier. 

In Canvas apps, Copilot can be used in two ways: 

- **App creation:** Copilot can assist app makers while designing their Canvas applications in Power Apps. Makers just need to provide a description of the app they want to build, and AI designs it for you. You can even use AI to help you modify various aspects of the application and help with expression writing. 

- **Assist users:** App makers and add a special Copilot control to the individual Power Apps they create that can aid users while they work in the application. 

:::image type="content" source="../media/03-describe-building-power-apps-11.png" alt-text="Screenshot that shows connecting your Copilot control to a data source.":::


### App Creation

The easiest way to use Copilot is through app creation. On the Power Apps home screen, tell Copilot what kind of information you want to collect, track, or show. The assistant then generates a Dataverse table and use it to build your canvas app.

:::image type="content" source="../media/03-describe-building-power-apps-12.png" alt-text="Screenshot that shows the describe to design capabilities of using Copilot to create a canvas app.":::


For example, if you were to enter **hotel housekeeping,** Copilot goes into your Dataverse environment and creates a new Dataverse table with data that includes typical hotel housekeeping tasks. 
 

This process is the initial stepping stone for your completed app. At any point, you can make changes to the app such as modifying the details of the table. You can even use Copilot to continue to edit your app. By providing instructions, such as "remove the room type column," Copilot helps you to modify your app. 

### Click-through demo: Build a canvas app

In this click-through demonstration, you're guided through the process of creating a marketing segment that can be used with other features such as email marketing. 

[**Build a canvas app**](https://edxinteractivepage.blob.core.windows.net/edxpages/PL-900/m3_canvasapp_sim/index.html)  
