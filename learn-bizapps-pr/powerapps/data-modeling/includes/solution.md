Microsoft Dataverse is a flexible data repository that can solve business problems in multiple ways. There isn't a single right way to data model this solution. The following is an example of how you might approach solving this set of requirements. Compare the example data model to what you designed and review the differences.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4UbDB]

In addition to the proposed data model, our architects suggested the following options:

- Upon evaluation and additional information from Fabrikam, Visits might be a custom activity table.
- Not every Visitor should be a Contact record. If the Visitor has low probability as a customer (just here to see the robots), then keep the Contact table data cleaner without the other Visitor records. Keep the Contacts dedicated to the sales process.
- IoT devices such as the tracker mentioned in the requirements, can quickly produce massive amounts of data. We're basing our model on the assumption that the provided API allows us to use the data relevant to our purposes. If that isn't the case, a much deeper discussion will be required.

Even when it seems like the requirements lend themselves to a certain path, it's likely there isn't a single right way to meet those requirements. As solution architects it's important to evaluate the requirements with an eye on offering the simplest solution that meets, or exceeds, the requirements while providing a secure environment that users are delighted to use.
