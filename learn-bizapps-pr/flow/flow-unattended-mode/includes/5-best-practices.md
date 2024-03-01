If you plan to run multiple unattended desktop flows, you can adopt a set of strategies to distribute load and ensure that all your unattended desktop flows run successfully without overloading the target machines or running into timeouts because multiple unattended desktop flows are running simultaneously. 

You can use any of the following strategies:

-   Plan your unattended desktop flows to run at different times of the day, spreading your load over time. This approach works best if you have a single or a limited set of machines that can run workloads, and you can control the triggers (for example, scheduled flows) that start your desktop flows.

-   Create clusters of machines that can run unattended desktop flows with identical configurations in parallel.

-   Create multiple desktop flows, where each uses a separate connection to target different machines.

By following these strategies, you can avoid having unattended desktop flows competing to run on the same device and, in some cases, failing due to timeouts.
