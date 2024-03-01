Data modelers can set up roles for individuals or groups to control the data that the report presents to them. Row-level security (RLS) ensures that users can focus on their specific area. It allows for flexible report design so that one report can serve many users without inappropriate sharing of data. The following example shows what you can incorporate into a published Power BI report.

:::image type="content" source="../media/security.png" alt-text="Diagram shows an example of row-level security." lightbox="../media/security.png":::

You can set up RLS in Power BI Desktop by using the **Manage roles** feature on the **Modeling** tab. Typically, the role filters are applied to lookup tables by using the benefit of relationships. Roles dictate which data is shown to which people. They provide business logic for filtering the data for users who belong to a group.

:::image type="content" source="../media/manage-roles.png" alt-text="Screenshot shows the Manage roles dialog box." lightbox="../media/manage-roles.png":::

In this example, the West Coast Region Manager can view offices in the Southwest and Northwest regions.

This feature enables you to only maintain a single data model and a single set of roles. The following example shows the same bar chart and how it displays differently for each user based on RLS roles.

:::image type="content" source="../media/audience.png" alt-text="Diagram shows how different audiences can see different information in a chart." lightbox="../media/audience.png":::

To test RLS in Power BI Desktop, in the **Modeling** tab, select **View As** and then choose the role that you want to test. This feature opens the report from the perspective of that role and allows you to preview how the report appears with row-level security applied.
