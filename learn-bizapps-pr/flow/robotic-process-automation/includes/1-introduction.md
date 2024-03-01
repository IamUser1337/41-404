This unit introduces robotic process automation (RPA) and the use cases for Microsoft Power Automate for desktop flows.

Many legacy applications don't have a method for accessing their data or functionality except through their user interface. RPA solutions operate by generating a list of actions by capturing the steps that a user performs in an application's user interface. The RPA solution then performs the automation by repeating the steps in the application's UI, effectively simulating the user's actions in software. RPA enables the automation of applications that don't have an API that can be used for such automation tasks.

Robotic process automation (RPA) has garnered much interest and attention. By automating simple tasks, RPA solutions can lower costs while helping to reduce errors.

## Legacy automation issues

Analysis of work that has been performed by users has resulted in the following statistical observations:

- 60 percent of all occupations have at least 30 percent automatable activities.
- Almost 50 percent of global work activities can be automated by using current technology.
- Data collection and processing times can improve by 64 percent with automation.

The best organizations are powered by strategic and creative people, but they're often forced to spend nearly half their time on repetitive tasks that could be automated with current technology.

A major barrier in automating systems and workflows can be that legacy and other external applications have no modern API data access that allows tools such as Microsoft Power Automate to include them in their cloud flows.

It isn't always possible to replace the legacy applications because of difficulty or the costs to replace them. In addition, many legacy applications are on-premises, and linking to the on-premises applications and combining them with cloud services in an end-to-end automation process can be difficult.

Many RPA solutions have been developed to solve this problem. Power Automate for desktop flows are the answer to this problem.

## Automation with Power Automate

Many software as a service (SaaS) solutions can be accessed with modern REST APIs that automation tools such as Power Automate can connect to and orchestrate for the purposes of integration and automation of tasks.

By using Power Automate, a solution architect can create innovative solutions. If a connector isn't available, you can create a custom connector if the service has a modern REST API. If an API isn't available, then Power Automate for desktop flows are available.

Microsoft has an approach to automation:

- **Accelerate productivity** - Minimize repetitive, manual, time-consuming tasks and create more time for your teams to focus on strategic work.
- **Automate at scale** - Allow everyone in your organization (from users, professional developers, to IT) to automate workflows by using connectors for their favorite on-premises and cloud-based apps and services. 
- **Apply intelligent automation** - Streamline how you work by combining the power of AI with automated workflows and business processes.
- **Integrate automation more securely** - Enable users to build automated workflows that comply with established policies and focus your skilled IT resources on more complex, strategic work.

The following flowchart can help you determine how to build your automation.

![Flowchart that shows decision-making for your design.](../media/1-decision-making-flow.png)

## Use cases for Power Automate for desktop flows

Power Automate for desktop flows automate repetitive tasks, and you can use Power Automate Desktop flows in several scenarios. Some use cases for desktop flows are as follows:

- **Invoice processing** - Processing invoices includes many repetitive tasks that, if performed incorrectly, can lead to delayed or incorrect payments. For instance, invoices need to be checked against the corresponding purchase orders. Desktop flows can process invoices and automatically perform the required validation checks.
- **Recruitment** - Desktop flows could gather and collate applications from multiple job portals into a single applicant list.
- **New user onboarding process** - New joiners to an organization must be set up on many systems. While you can use tools, such as Microsoft PowerShell, to perform some setup, some applications don't have available automation. Desktop flows can be used to add users and configure their settings automatically through the applications' user interfaces.

## Solution architect’s role

By using Power Automate cloud and desktop flows, a solution architect can design end-to-end processes that encompass modern cloud services, legacy desktop, and web applications.

Solution architects should look for opportunities for automation. Good opportunities exhibit the following characteristics:

- **Standard process** - Determine whether the process is well understood and consistent in how it needs to be implemented.
- **High frequency** - Assess if a process is one that runs frequently and if the ROI exists to spend build cycles on it.
- **Predictable processes** - Check if outcomes are predictable or if they might require judgment calls by humans.
- **Prone to human error** - A risk might exist that a human might introduce errors as a result of manually completing the process. In this situation, the solution architect should evaluate whether users can easily perform many steps out of order.
- **High risk of failures and impact** - Determine if a high risk and/or impact of a failure could be mitigated through automation.

Desktop flows have many uses. Consider any scenario where the processing of forms, extracting data from systems, or processing claims has occurred where the data needs to be verified for automation with desktop flows. If you have rule-based processing, desktop flows are viable candidates for automating those processes.

The introduction of Power Automate for desktop produces many scenarios that wouldn't have been possible or would have been difficult and expensive to achieve.

Desktop flows can also be used for situations where an API is available, but the API doesn't expose all operations that are available in the application's UI. In such circumstances, Power Automate for desktop might be the answer.

During design, the solution architect should separate flows into smaller automations so that you don't have a single automation that covers the entire process. Reasons why you should make multiple, smaller flows are:

- Multiple people can work on the automation.
- Small flows with common steps might be reusable.
- Error handling doesn't need to be as sophisticated.
- Maintenance is simpler.
- Managing the automation is easier if a step fails.
