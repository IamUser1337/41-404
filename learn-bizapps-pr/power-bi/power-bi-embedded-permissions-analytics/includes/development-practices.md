It's critical that your solution enforces data permissions correctly and efficiently. The following list provides you with good development practices to apply:

- Strive to enforce data permissions by using roles instead of app logic. Client-side filtering, which is achieved with Power BI client APIs, shouldn't be used to enforce data permissions. Client-side filtering is intended for temporarily filtering a subset of the data that the user can view.

- Strive to define fewer datasets (models) with well-designed roles.

- Strive to create fewer roles by using dynamic rules. A data-driven solution is easier to maintain.

- Create rules on dimension tables instead of fact tables whenever possible, which will help you deliver faster query performance.

- Validate that the model design, including its relationships and relationship properties, are correctly set up.

- Use the `USERPRINCIPALNAME` function instead of the `USERNAME` function. It provides consistency when you're validating the roles in Power BI Desktop and the Power BI service.

- Validate model RLS by testing all roles and expected username values. Test what happens when unexpected values are passed as the username. In those instances, ensure that no table rows are returned.

- Ensure that the Power BI Desktop data source connection uses the same credentials that will be applied when it's being set up in the Power BI service.

- Request data modelers' document roles, their purpose, and expected username values for handover to the app developers.
