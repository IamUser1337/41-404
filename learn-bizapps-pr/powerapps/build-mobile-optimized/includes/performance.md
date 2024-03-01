Power Apps provides built-in tools to provide quick feedback for performance issues. This video introduces the most useful tool called **App checker**.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RW1geUk]

In addition to using the **App checker** feature, more advanced users can use **Power Apps Monitor** to help see where bottlenecks are, but **App checker** is the easiest to use feature.

Always remember that the less data that Power Apps needs to access, the more performant your app is. The fewer gates your data needs to travel through, the better. Remember learning about common data sources for your app? There's none more performant than **Dataverse**. Since Power Apps resides in the same environment as your **Dataverse** tables, your data doesn't require an API check for access.

Any other data needs checking through a gate of sorts. If your data resides in an on-premises server, you still need to have it pass through an on-premises data gateway so that Power Apps, which isn't on your local server, can interact with it. Cloud-based SQL is an excellent data source, but your data still requires API calls for access. SharePoint is a good data source when you're pulling in fewer items, but it also requires API calls, and it gets bogged down as the lists grow.

Remember to limit the data that your app is pulling in and try to keep individual galleries and forms pulling their data from a single source.

Take away that performance, though important for any app, is **vitally** important for a mobile app. As your app grows, always keep performance in mind!
