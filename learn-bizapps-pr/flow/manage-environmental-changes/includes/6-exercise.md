In this exercise, you will connect to Power
Apps and Power Automate PowerShell cmdlets to list all connections
that are in your tenant. You can use this information to determine which
users are making connections through different connectors.

> [!NOTE] 
> Running the Install-Module command downloads one or more modules from Microsoft's repository, and installs them on the local computer. This gives you access to more
> commands to manage your Power Apps tenant that will be used in this exercise. Managing environment-scoped assets requires the person who is administrating these assets
> to possess environment admin permissions. In regard to managing tenant-scoped assets, the person who is administrating these assets must possess tenant admin permissions.

1. Launch **Windows PowerShell** and select **Run as Administrator**.

    ![Screenshot of Windows Start menu with search for powershell with Run as Administrator highlighted.](../media/14-runadmin.png)

2. Import the required modules by using the following commands:

    **Install-Module -Name Microsoft.PowerApps.Administration.PowerShell**

    **Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber**

3. If you are prompted to accept the change to the *InstallationPolicy*
    value of the repository, accept this change for all modules by entering
    **A** and then pressing **Enter** for each module.

4. List all connections by using the **Get-AdminPowerAppConnection** command.

5. At this point, you should be prompted for credentials. Enter your
    credentials while accounting for the prerequisites that were
    discussed at the beginning of this module.

6. After you have entered your credentials, the cmdlet will run and
    all of the connections will be returned. Data that is returned
    includes the name of the connector, who created the connection, the
    environment, and its current status.

    ![Screenshot of Windows PowerShell showing returned data.](../media/15-exercise.png)
