In the previous labs, you created a desktop flow that enters a new invoice entry for Contoso Coffee shop by using the provided input variables. The input variables could come from previous process steps, such as when a new invoice file is being received and processed and data is being extracted from the file. You can automate those steps by using a Microsoft Power Automate cloud flow, which has hundreds of connectors that you can choose from. In this module, you'll learn how to create a cloud flow and connect it with the desktop flow that you've created so that business data for your Contoso Coffee shop can flow from the cloud to your desktop. 

You'll complete the following tasks in this lab:

-   Create your first cloud flow.

-   Set up a machine connection to enable the cloud flow to run the desktop flow on your computer.

-   Add the **Enter invoice with input** desktop flow to this new cloud flow.

-   Perform a test run of the new cloud flow that will run the desktop flow on your computer

## Prerequisites
You'll need to meet the following prerequisites before starting this lab:

- Complete the first module in this Learning Path **Install required software - Online workshop**.

- Complete the module **Use input and output variables - Online Workshop** or import the provided solution in the resources folder

> [!NOTE]
> If you've already registered your machine in Lab 1, you should be ready to begin this lab. Review the following steps to ensure that your machine is registered properly.

## Learn about machines

Machines are the physical or virtual devices that are used to run your Power Automate processes. When you connect your machine to Power Automate, you can instantly start your desktop automation by using any available trigger, such as when you receive an email or on a predefined schedule.

Connecting your machine directly to Power Automate and the cloud will allow you to harness the full power of your robotic process automation (RPA). The easiest way to connect your machine to the cloud is with direct connectivity. With that approach, your only task is to ensure that you've installed and signed in to the latest version of Power Automate for desktop. Then, your machine will be registered with Power Automate automatically. After you've registered your machine, you can create a connection immediately in your cloud flows.

> [!NOTE]
> Direct connectivity is only available for versions of Power Automate for desktop 2.8.73.21119 or newer. If you're using an older version, you'll need to [update to the latest](https://go.microsoft.com/fwlink/?linkid=2102613).

> [!NOTE]
> To complete the exercises, you'll need to use a few
> files. Download the [Automation in a Day files](https://pahandsonlab.blob.core.windows.net/documents/AutomationIAD-Learn-student-files.zip)
> for use in this module. Extract the contents of this download to your local computer.
