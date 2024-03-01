Power Automate for desktop provides six scripting actions that satisfy almost every automation scenario. Through these actions, you can run complex Microsoft Windows and web operations using short blocks of code.

## Run VBScript

The **Run VBScript** action allows you to execute VBScript scripts in your flows. This kind of scripting is widely used as a testing and automation tool for administrative tasks on the Windows platform.

For example, you can develop scripts in VBScript to manage and monitor computer hardware or handle event logs.

The action accepts a VBScript block of code as input and stores the result of the implementation in the **VBScriptOutput** variable. Additionally, the action creates the **ScriptError** variable that stores potential errors.

![Screenshot of the Run VBScript action.](..\media\run-vbscript-action.png)

## Run JavaScript

While JavaScript is mainly a web development language, the **Run JavaScript** action enables you to use it as a general-purpose one. You can develop JavaScript scripts to perform calculations and conversions, such as complex arithmetical expressions and date conversions.

The action accepts a JavaScript block of code as input and stores the result of the implementation in the **JavascriptOutput** variable. Additionally, the action creates the **ScriptError** variable that stores potential errors.

![Screenshot of the Run JavaScript action.](..\media\run-javascript-action.png)

## Run JavaScript function on webpage

If you want to use JavaScript to handle and alter web elements, you can deploy the **Run JavaScript Function on web page** action. This action functions similarly to the **Run JavaScript** action, but it executes code on loaded web pages. Using JavaScript, you can handle virtually any element on web pages, such as text boxes and images.

The main difference about the input parameters is the browser instance that the **Run JavaScript Function on web page** also requires. The result is stored in the **Result** variable, while the action doesn't provide separate variables for the potential errors.

The **JavaScript function** field automatically creates the structure of a predefined JavaScript function.

![Screenshot of the Run JavaScript Function on web page action.](..\media\run-javascript-function-on-web-page-action.png)

## Run PowerShell script

PowerShell enables you to execute commands that handle the Windows file system, registry, and other system-related aspects. More precisely, it includes every command provided in the Windows PowerShell console.

Like the other scripting actions, the**Run PowerShell script** action accepts a PowerShell block of code as input and stores the result of the implementation in the **PowershellOutput** variable.

Additionally, the action creates the **ScriptError** variable that stores potential errors.

![Screenshot of the Run PowerShell script action.](..\media\run-powershell-script-action.png)

## Run Python script

The last supported scripting language in Power Automate for desktop is Python. Python is considered a general-purpose programming language, but it's favorable in arithmetic operations and matrix calculations.  

The **Run Python script** action accepts a Python block of code as input and stores the result of the implementation in the **PythonScriptOutput** variable.

Additionally, the action creates the **ScriptError** variable that stores potential errors.

![Screenshot of the Run Python script action.](..\media\run-python-script-action.png)

## Run DOS command

To run a DOS command, use the **Run DOS command** action. This action can run a DOS command or a console application in invisible mode. The action waits for the command or application to complete and retrieves its output into a text variable. The **DOS command or application** field is required input, whereas the **Working folder** field is optional. The output, error output, and exit code are stored into separate variables.

![Screenshot of the Run DOS coomand action.](..\media\run-dos-command-action.png)
