In this exercise you'll be creating a security model for Fabrikam to track visitors. Review the information presented about Fabrikam Robotics and complete the tasks. This could be completed as small groups as well.

You're building a solution for Fabrikam to track visitors to a showroom and manufacturing site. Some of the visitors are potential purchasers and some are there to see the magic of the robots working. This exercise should be completed after the data modeling exercise from this Learning Path.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4U8T6]

If you're completing this exercise independently:

- Take notes.

- Put yourself in the mindset of both customer and Solution Architect.

- Draw your security model, put pen to paper (actual pen to paper, or virtual pen to paper) and evaluate options. Draw a diagram, make a list of considerations. Everyone thinks through the process differently, use the tools that work for you.

- Consider bigger picture items, if you build this security model do you have data model considerations to worry about? Will your ideas still work?

- If given the opportunity, share this assignment with colleagues who are also architects and seek their feedback to your security model.

## Requirements

You're building a solution for Fabrikam to track visitors to a showroom and manufacturing site. Some of the visitors are potential purchasers and some are there to see the magic of the robots working.

Review the requirements here and address the concerns listed later in this document.

- **Requirement 1** - Fabrikam has been rapidly moving to the cloud and already uses Office 365 for their email. They're adopting the use of Microsoft Teams at a rapid pace.

- **Requirement 2** - You've already architected the solution to include the following Power Apps:

    - A model-driven app named Sales Central to be used by the sales staff and sales managers.
    - A canvas app to check in guests visiting the showroom to be used by the reception staff.
    - A portal that visitors can use to request to visit.

- **Requirement 3** - Fabrikam is going to use Power Apps per app licenses for reception staff and Dynamics 365 Sales app licenses for the sales staff.

- **Requirement 4** - Fabrikam’s IT security team wants to make sure the new solution doesn’t open up any security exposure from potential data leaks. You must ensure that your security setup prevents users from building their own cloud flows in Power Automate that send data to outside services that aren’t approved. You could almost see the panic on their faces when your sales team did the demo of how easy it was to build a cloud flow using random third party connectors.

- **Requirement 5** - The sales staff handles their own leads and opportunities. They're compensated by commission on close of sales and are competitive. The staff that works on small deals all work together and receive commission on all closed deals in their department. The large deals sales staff mostly works by themselves; except on large deals where there's a team of them assigned.

- **Requirement 6** - Reception staff must not have access to the sales data.

- **Requirement 7** - Sales managers need to have access to the deals of their team members.

- **Requirement 8** - Discounts can only be approved and applied by one of the sales managers. The app should ensure the sales staff can’t approve their own discounts. In the data model, there's a discount field of type currency and a required lookup field to the approver.

- **Requirement 9** - Fabrikam’s organization has the following divisions and departments:

    - Sales
        - Small Deals
        - Large Deals
        - Wholesale

    - Marketing
    - Operations
        - Manufacturing
        - Showroom (has all the reception staff)
        - Shipping

    - Customer Service

## Tasks

Create a security model for the above requirements. You can sketch this on a whiteboard, build a small proof of concept, or evaluate and take notes with other tools that you like to work with.

- How do you calm the concerns of the security staff and the rogue connector use?

- How do you handle ensuring only sales managers approve and apply discounts?

- How would you control access to each of the Power Apps?

- What do you need to do to accommodate that Power Apps per app licenses are used for the reception staff?

- What Dataverse security roles would you have the team create?

- What business units can you begin to define to support your solution?

- How will you handle so portal users can only see their own visit request records to check the status and potentially cancel the visit?

- How would you ensure the small sales department can see all the data for all sales staff, but the large deals sales staff can only see their own except when a team is put together to handle large deals?

In the following video we evaluate the requirements and key considerations for providing a solution for Fabrikam.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TTLV]

## Other considerations

- How strict should the Data Loss Prevention policies be?

- Have you properly secured data (did you avoid security by obscurity?)?

- Did you introduce any issues for users?

- Did you make decisions that will impact performance?

- How would you test your security decisions?

Review your security model

There isn't a single right way to model this solution. We have offered thoughtful consideration for the specific topics listed of how you might approach solving this set of requirements. Compare the examples to what you designed and review the differences.