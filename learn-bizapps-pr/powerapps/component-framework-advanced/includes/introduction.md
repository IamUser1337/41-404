As you build more complex code components, the Power Apps component framework provides built-in features, you can use as part of your logic. Using these capabilities, you can learn about the client hosting your component, the device running the component, and other utility-type services such as formatting. For components that want to interact with Dataverse table data, you can use the WebAPI feature to interact with the data. 

Handcrafting the HTML is common for simple components, but as your needs get more complex, using a UI framework library can be helpful. There are many choices of JavaScript UI frameworks, but React is one of the more common libraries used with Power Apps code components.

In the rest of this module, we'll explore these topics in more detail. We'll be using several hands-on examples where you can follow along and build your components using some of these more advanced capabilities of the framework.

## Use the component context 
The context object contains values set up by the customizer mapped to property names defined in the manifest and utility functions. You can use it in your component logic to access most of the built-in capabilities we'll use later in this module in the components you build.

The context parameter is available to components on the init and updateView methods. It's common that in the init method you populate a class level variable to allow access to the context easily in other methods in your component. The following is an example of saving the context for later use in the init method:

```
export class ChoicesPicker implements ComponentFramework.StandardControl<IInputs, IOutputs> {
    
    private _context: ComponentFramework.Context<IInputs>;

    public init(
        context: ComponentFramework.Context<IInputs>,
        notifyOutputChanged: () => void,
        state: ComponentFramework.Dictionary,
        container: HTMLDivElement,
    ): void {
     
        this._context = context;

        /* other logic goes here */
    }
}
```

The component [context object](/power-apps/developer/component-framework/reference/context/?azure-portal=true) can cover a wealth of information about the environment your component is running in. The following is an overview of the key properties available:

- **client** - This property provides you with information about the client(web,Outlook or mobile), the form factor (desktop,tablet or phone), if you're offline, and if the network is available.

- **mode** - This property provides information about the current state of the code component. For example, is the component visible, is it disabled, and what is the current allocated size.

- **userSettings** - This property provides information about the current user like their LanguageId, User ID and Name. For model-driven apps the securityRoles property can be useful to learn the roles for the current user.

The context object also provides access to several useful built-in services. The following are the most common ones:

- **device** - This property provides access to methods to use native device capabilities. Using these services, you can capture audio, video, and images, get bar code values, identify the device geolocation, and pick files.

- **factory** - This currently only offers methods to work with the Popup service, but could support other services in the future.

- **formatting** - Provides methods to help you format data from currency to time. These methods can help you keep formatting consistent with the hosting application user settings.

- **navigation** - Provides navigation-related methods like open forms, open URLs, dialogs (alert, confirm, error), and more.

- **resources** - Provides access to the methods to get all the information about the resource files defined in the manifest. These methods are essential to help localize all your component's content.

- **utils** - Provides access to table metadata and also allows you to check user access to specific tables. The lookupObjects method allows components access to the standard lookup dialog, allowing users to pick one or more rows.

- **webAPI** - Provides basic create, read, update, and delete access to Dataverse table data.

The following is an example of using the device pickFile capabilities:
```
 private onUploadButtonClick(event: Event): void {
    this._context.device.pickFile().then(this.processFile.bind(this), this.showError.bind(this));
  }
```

It's important to note that some of these services require enabling them in the feature usage section of the manifest for them to work. Some may also only be available in specific types of hosting apps. For example, webAPI is only available in model-driven apps and Power Pages and isn't available to canvas apps. Check the individual service reference page for details.

## Use React

There are many UI frameworks you can choose from; however, there are benefits to using React. React is favored because the underlying Power Apps platform uses React internally. The Power Apps component framework also has built-in support for using the same infrastructure. This capability means you won't have to package in manually the React and Fluent UI libraries into each control. All controls will share a common library instance and version to provide a seamless and consistent experience.

The following command shows how to initialize a component and use the React framework:

`pac pcf init -n ReactSample -ns SampleNamespace -t field -fw react -npm`

The only difference you might notice is the -fw (or--framework) option that enables using React. This option will cause the initial files generated for you to include the necessary React configurations. 

Later in this module, you'll build a code component using this React capability.
