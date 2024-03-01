Occasionally, you might be required to display a pop-up window to your application's user. The Power Apps component framework exposes a pop-up API that allows you to achieve this requirement. The following example shows how to build a pop-up window that displays a loader graphic. This method can help you achieve a satisfying user experience in long-running operations where the underlying UI is blocked from performing operations.

> [!NOTE]
> The Popup service from the Power Apps component framework is only supported in Power Apps model-driven apps.

## Initialize your component's project

To initialize your component's project, follow these steps:

1. Start Visual Studio Code.

1. Select **Terminal**, select **New Terminal**.

1. Change the directory to your source folder.

    ```console
    cd source
    ```

1. From your source directory, create a directory named **Popup-Component**.

    ```console
    md Popup-Component
    ```

1. Run the following command to switch to the new directory.

    ```console
    cd Popup-Component
    ```

1. Initialize the project by running the following command.

    ```console
    pac pcf init --namespace SampleNamespace --name PopupComponent --template field
    ```

1. Run npm install to load dependent libraries into your project.

    ```console
    npm install
    ```

1. Open the project in Visual Studio Code by running the following command.

    ```console
    code -a .
    ```

## Implement your code component's logic

To implement your code component's logic, follow these steps:

1. Expand the **PopupComponent** folder and open the **ControlManifest.Input.xml** file.

1. Replace the entire manifest with the following XML.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <manifest>
      <control namespace="SampleNamespace" constructor="PopupComponent" version="0.0.1" display-name-key="PopupComponent_Display_Key" description-key="PopupComponent_Desc_Key" control-type="standard">
        <!-- property node identifies a specific, configurable piece of data that the control expects from CDS -->
        <property name="sampleProperty" display-name-key="Property_Display_Key" description-key="Property_Desc_Key" of-type="SingleLine.Text" usage="bound" required="true" /> 
        <resources>
          <code path="index.ts" order="1"/>
          <css path="css/loader.css" order="1" />
        </resources>
      </control>
    </manifest>
    ```

    You add the supporting files that are found in this manifest later.

1. Open the **Index.ts** file.

1. Above the **export class** method, insert the following interface method so that you can expose other methods provided by the pop-up API (popupStyle and shadowStyle).

    ```typescript
        interface Popup extends ComponentFramework.FactoryApi.Popup.Popup {
        popupStyle: object;
        shadowStyle: object;
    }
    ```

1. Add the following private variable above the **constructor**.

    ```typescript
    private _container: HTMLDivElement;
    private _popUpService: ComponentFramework.FactoryApi.Popup.PopupService;
    ```

1. Add the following logic to your component's **init** method.

    ```typescript
    this._container = document.createElement('div');
    //============ content of our popup =============
    let popUpContent = document.createElement('div');
    popUpContent.setAttribute("class", "loader");

    //============ our Popup object =============
    let popUpOptions: Popup = {
        closeOnOutsideClick: true,
        content: popUpContent,
        name: 'loaderPopup', // unique popup name
        type: 1, // Root popup
        popupStyle: {
            "width": "100%",
            "height": "100%",
            "overflow": "hidden",
            "backgroundColor": "transparent",
            "display": "flex",
            "flexDirection": "column",
            "position": "absolute",
            "margin-top": 28 + "px"
        },
        shadowStyle:{
            position: "absolute",
            width: "100%",
            height: "100%"
        }
    };

    this._popUpService = context.factory.getPopupService();

    this._popUpService.createPopup(popUpOptions);

    container.appendChild(this._container);
    this._popUpService.openPopup('loaderPopup');
    ```

## Add styling to your code component

To add styling to your code component, follow these steps:

1. Create a new **css** subfolder under the PopupComponent folder.

1. Create a new **loader.css** file inside the CSS subfolder.

1. Add the following style content to the loader.css file.

    ```xml
    .loader {
        border: 16px solid #f3f3f3; /* Light grey */
        border-top: 16px solid #3498db; /* Blue */
        border-radius: 50%;
        position: fixed;
        width: 120px;
        height: 120px;
        top:40%;
        left:50%;
        animation: spin 2s linear infinite;
      }

      @keyframes spin {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
      }
    ```

1. Select **File** and **Save All** your changes.

## Build and run your component

To build and run your component, follow these steps:

1. Build your solution by running the following command.

    ```console
    npm run build
    ```

1. Upon a successful build, you can test your new Popup component by running npm start.

    ```console
    npm start
    ```

1. Close the test harness browser window.

1. Go back to the terminal and stop the watcher by pressing **[CONTROL] + C**.

1. Type **Y** and then press **[ENTER]**.

> [!NOTE]
>This loader component is bound to a text field. To use the component in a model-driven app, it might be beneficial for you to mark this field as hidden if you want to use it in a form.

To test the popup functionality, you need to publish and host the component in a Microsoft Power Platform environment. For more information on how to publish code components, see "Create a code component solution package" in the **Build a Power Apps component** module.
