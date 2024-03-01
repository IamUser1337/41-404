
How do you determine which app to use? If your application isn't going to be connected to a Microsoft Dataverse database, then the choice is easy. You create a canvas application since model-driven apps can only be built on top of Dataverse. Otherwise, it's important to first identify what your application is going to be used for. 

The table provides a high-level comparison between the two. 

|**App consideration**| **Canvas**| **Model-driven** |
| - |- |-|
| **Data source**| Not Dataverse-driven| Dataverse-driven |
| **App purpose**| Task or screen focused| Back office / process focused |
| **User Interface (UI)**| Custom UI| Responsive / consistent UI |
| | Device integration| User personalization |
| | Easily embeddable| Data relationship navigation |
| | | Security trimming of UI |


 

To expand on this explanation a little more, let’s look at an example. Contoso Real Estate sells commercial and residential properties. They have a team of agents in the field that meet with potential sellers and show properties to buyers. They need to quickly identify which properties to show based on the needs of the buyer they're working with. When working with a new seller, they also need to quickly intake the property, snap pictures, schedule open houses, and capture any other relevant information so the property can be listed as quickly as possible. Contoso’s managers need to:
- quickly see which properties are currently listed
- know how many times they were shown
- manage offers as they come in
- help provide support to sellers as they work to sell properties

From a seller standpoint, the best solution would be to create a canvas app to support them in the field. The canvas app can not only connect to Dataverse data, but it can easily connect to other data sources such as Google Calendar to schedule open houses for properties. The ability to create a custom user interface means the application can be designed to provide the best experience for sellers working in the field. Finally, because of the device integration capabilities, sellers can easily take pictures of the property using their mobile device, and those pictures are automatically associated with the property. 

The image shows an example of what the seller’s canvas application might look like. 

:::image type="content" source="../media/03-describe-building-power-apps-04.png" alt-text="Screenshot of sample canvas application.":::

Sellers are provided with a list of properties they can easily search through to identify properties to show perspective buyers. Once a property is identified, they can easily view specifics about the property including pictures. This capability lets the buyer see the property and decide if it's worth visiting. 

Let’s take a closer look at how a canvas app can help listing agents be more productive while working in the field. 

[**Canvas app**](https://www.microsoft.com/videoplayer/embed/RW10Cyz)

As far as the managers for Contoso Real Estate go, they need to have an application that lets them manage the big picture and help support sellers. A model-driven app would best help them support sellers and manage daily operations. As sellers enter properties using the canvas application, they're available in the model-driven app. Additionally, they would have easy access to open houses, showings, and offers that are stored in Microsoft Dataverse. Items like business rules and business process flows can be used to help guide sellers through the various processes: listing a home, staging the home, managing open houses and showings, and negotiating offers. 

The image shows an example of what a model driven application might look like. 


:::image type="content" source="../media/describe-building-apps-with-power-apps-05.png" alt-text="Screenshot of sample canvas application in development.":::

Under the Property Management group, managers can easily access things like the real estate properties that are currently for sale. As they open a specific property, they are presented with basic information such as the property type, asking price, and the year built. In the **Related Details** section, we have access to any open houses, showings, and offers associated with this property. This provides managers with everything associated with this property from a single screen without needing to navigate to different areas of the application. 

Additionally, a canvas application can be used to help compliment the data in the model-driven application. In this case, we have an embedded canvas application on the Real Estate Property form. This app looks at the address, square footage, number of bedrooms, and asking price of the home being looked at. The app also lists similar properties in the surrounding area. This information helps managers do things such as evaluate the asking price of the home vs similar properties in the area. If needed, they can adjust their asking price as needed. 

Let’s see how a model-driven application can help Contoso Real Estate better support their agents in the field to sell properties faster. 

[**Model-driven app**](https://www.microsoft.com/videoplayer/embed/RW10pPY)

As you see, when building solutions with Power Apps it's often about identifying what users are going to need an application to do, and then designing the applications accordingly. Most often, a solution contains a combination of both canvas and model-driven apps. 

Now that we discussed canvas and model-driven apps and explored scenarios for each of them, let’s take a deeper look at how to build each of them. 
