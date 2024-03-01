While attended desktop flows require a user to be signed in to implement actions that are associated with the flow, an unattended desktop flow can't run if active Microsoft Windows user sessions are present, even a locked one. For this reason, many users choose to run unattended flows on a virtual machine. This approach allows users to run unattended workflows while keeping all physical devices available for use. 

For an unattended desktop flow to run smoothly, you'll need to have:

- All users completely signed out.

- A locked screen (enabling the flow to run without users being able to see the actions that are performed).

- A gateway with the user sign-in information to the desktop.

You can choose to run multiple unattended desktop flows sequentially on the same device by viewing and manually changing the run queue; however, desktop flows that don't run within three hours of being requested will time out. Essentially, if you trigger multiple unattended desktop flows, they'll perform one after another unless the queue is backed up by more than three hours. While you can't run desktop flows concurrently with the same user because multiple users can be signed in simultaneously on Windows Server 2016 and Windows Server 2019, Microsoft Power Automate can run several unattended desktop flows simultaneously on a single device. With this feature, your organization can save on infrastructure costs by using two or more user accounts to create desktop flow connections that target the gateway on a single device.

Now that you're aware of the details and benefits of unattended desktop flows, you can learn how to run them.
