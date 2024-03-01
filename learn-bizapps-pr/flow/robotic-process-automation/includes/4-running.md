You can run desktop flows in one of two modes:

- Attended
- Unattended

> [!div class="mx-imgBorder"]
> [![Diagram of attended versus unattended modes.](../media/4-unattended-attended.png)](../media/4-unattended-attended.png#lightbox)

## Attended flow

Attended flows automate individual tasks across desktop and web applications. The user can interact with the desktop flow if necessary, such as when a decision is required.

Attended flows are initiated on demand. A user can start an attended desktop flow from their local computer.

The user must be signed in to run an attended desktop flow.

## Unattended flow

Unattended desktop flows are used for high volume automation where no interaction is required. Unattended desktop flows are initiated from Power Automate cloud flows. The cloud flow sets the input variables and receives the output variables.

> [!IMPORTANT]
> If a user is signed in, an unattended desktop flow can't run.

### Virtual machines

One option for running unattended desktop flows is to use the user's computers when they aren't working, for example overnight or on weekends. This approach does require that the user actually signs out and that the software is configured the same on each of the teams' computers. This scenario isn't always the case.

A more robust option is to create virtual machines in Azure, which has the following advantages:

- The software configuration can be consistent across the machines.
- The number of virtual machines can be scaled as necessary.
- The desktop flows can run during working hours.

If using virtual machines, the solution architect will need to define the specification for the virtual machines and then determine the costs of running the virtual machines. The solution architect should ensure autoscaling rules are defined to reduce costs when the virtual machines aren't required and to maximize hardware productivity.

### On-premises data gateway

An on-premises data gateway must be installed on each computer to allow the computer to take part in an unattended desktop flow. After they've been installed, on-premises data gateways are managed from the cloud.

> [!div class="mx-imgBorder"]
> [![Screenshot of gateways in Power Automate.](../media/4-gateways.png)](../media/4-gateways.png#lightbox)

Gateways can be grouped into clusters that will run instances of a desktop flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of a gateway grouped into a cluster.](../media/4-clusters.png)](../media/4-clusters.png#lightbox)

The solution architect should define the clusters that are required and the priorities for desktop flows.
