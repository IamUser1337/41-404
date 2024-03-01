In this unit, we explore the basic operations using the organization service to interact with data from a Dataverse environment.

## Create a row

To create rows, use the **Create** method. While not required, it's best to provide at least a value for the primary column for the table. The Create operation assigns a GUID value as a primary key for the new row. While supported to provide your own value, it's recommended to allow the automatic assignment for most scenarios.

```csharp
    Entity newAccount = new Entity("account");
    newAccount["name"] = "Contoso";
    Guid accountid = serviceClient.Create(newAccount);
```

You can also use the **RelatedEntities** property on the entity object to create related rows in the same operation. This requires specification of the relationship name and the related entity object that needs to be created at the same time. In the following example, the account and contact rows are both created in a single transaction and are associated together using the relationship specified.

```csharp
Entity newAccount = new Entity("account");
newAccount["name"] = "Contoso";

Entity newContact = new Entity("contact");
newContact["firstname"] = "Jim";
newContact["lastname"] = "S";

newAccount.RelatedEntities.Add(new Relationship("account_primary_contact"),
    new EntityCollection(new List<Entity>() { newContact }));

Guid accountid = serviceClient.Create(newAccount);
```

## Update rows

To update a row, use the **Update** method. You can update table rows using either the primary key or an alternate key. When you update a row, you should only provide the columns that you want to modify data for. If the entity object contains unmodified columns, Dataverse triggers any automation waiting for modification of those columns even though the value didn't change. Here's an example of updating using the primary key, which is a GUID.

```csharp
Entity updateAccount = new Entity("account",accountid);
updateAccount["accountnumber"] ="ABC123";
updateAccount["creditlimit"] = new Money(1000);

serviceClient.Update(updateAccount);
```

You can also use an alternate key to update a table row. You must [define](/power-apps/maker/data-platform/define-alternate-keys-reference-records?azure-portal=true) the alternate key on the table before this will work. The following updates the account table row, using the account number we set on the previous update operation.

```csharp
Entity updateAccount = new Entity("account","accountnumber", "ABC123");
updateAccount["creditlimit"] = new Money(2300);
serviceClient.Update(updateAccount);
```

You can also use the KeyAttributeCollection to provide multiple columns that make up an alternate key.

```csharp
KeyAttributeCollection updateKeys = new KeyAttributeCollection
{
    { "name", "Contoso" },
    { "accountnumber", "Contoso123A" }
};
Entity updateAccount = new Entity("account", updateKeys);
updateAccount["creditlimit"] = new Money(5000);

serviceClient.Update(updateAccount);
```

## Delete rows

To delete a row, use the **Delete** method. You can delete a table row using either the primary key or an alternate key. The following code shows the most basic delete done using the primary key.

```csharp
serviceClient.Delete("account", accountid);
```

If you want to delete by an alternate key, you must use the DeleteRequest message with the Execute method. The following code shows deleting an account row with a specific account number column alternate key.

```csharp
var deleteRequest = new DeleteRequest
{
    Target = new EntityReference("account", "accountnumber", "Contoso123A")
};

serviceClient.Execute(deleteRequest);
```

## Retrieve a single row

To retrieve a row, use the **Retrieve** method. You can retrieve a table row using either the primary key or an alternate key. The following code sample shows the most basic retrieve done using the primary key.

```csharp
var retrieveAccount = serviceClient.Retrieve("account", accountid,
    new ColumnSet("name", "accountnumber", "creditlimit"));
```

If you want to delete by an alternate key, you must use the RetrieveRequest message with the Execute method. The following code sample shows retrieving an account row with a specific account number column alternate key.

```csharp
var altRetrieveKey = new EntityReference("account", "accountnumber",accountNumber);
var retrieveRequest = new RetrieveRequest
{
    Target = altRetrieveKey,
    ColumnSet = new ColumnSet("name", "accountnumber", "creditlimit")
};
var retrieveResult = (RetrieveResponse)serviceClient.Execute(retrieveRequest);

```

## Retrieve multiple rows

To retrieve multiple rows from a table that match your criteria use the **RetrieveMultiple** method. There are multiple options on how you can construct the query criteria for which rows from a Dataverse table or tables. Each option provides advantages depending on your query scenario. The following are the primary options you can use with the RetrieveMultiple method:

- **QueryExpression** - Strongly typed object model for constructing complex queries, includes data from linked (Related) rows but doesn't support aggregates and grouping.
- **QueryByAttribute** - Simpler model than QueryExpression, useful for matching a single table column value criteria, but can only return data from a single table.
- **FetchExpression** - Use Dataverse's FetchXML query language, allowing complex queries with aggregates, grouping, and data inclusion from linked (related) table rows.
- **LINQ** - Uses LINQ syntax to compose queries, with capabilities limited to the same as QueryExpression.

The following examples show the same criteria in each of the options. The criteria queries the account table where the City is Redmond and return the columns City and Line 1/2 of address1.

### QueryExpression example

```csharp
var queryExpression = new QueryExpression("account")
{
    ColumnSet = new ColumnSet("address1_city", "address1_line1", "address1_line2"),
    Criteria = new FilterExpression
    {
        Conditions =
        {
            new ConditionExpression("address1_city", ConditionOperator.Equal, "Redmond")
        }
    }
};
EntityCollection queryExpressionResults = serviceClient.RetrieveMultiple(queryExpression);
```

### QueryByAttribute example

```csharp
var queryByAttribute = new QueryByAttribute("account")
{
    ColumnSet = new ColumnSet("address1_city", "address1_line1", "address1_line2"),
    Attributes = { "address1_city" },
    Values = { "Redmond" }
};
EntityCollection queryByAttributeResults = serviceClient.RetrieveMultiple(queryByAttribute);
```

### FetchExpression example

```csharp
var fetchXml = @"
<fetch version='1.0' output-format='xml-platform' mapping='logical' distinct='false'>
  <entity name='account'>
    <attribute name='address1_city' />
    <attribute name='address1_line1' />
    <attribute name='address1_line2' />
    <filter type='and'>
      <condition attribute='address1_city' operator='eq' value='Redmond' />
    </filter>
  </entity>
</fetch>";

var fetchExpression = new FetchExpression(fetchXml);
EntityCollection fetchResults = serviceClient.RetrieveMultiple(fetchExpression);
```

### LINQ example

```csharp
var context = new OrganizationServiceContext(serviceClient);

var linqQuery = from acc in context.CreateQuery("account")
                where (string)acc["address1_city"] == "Redmond"
                select new
                {
                    Address1_City = (string)acc["address1_city"],
                    Address1_Line1 = (string)acc["address1_line1"],
                    Address1_Line2 = (string)acc["address1_line2"]
                };

var linqResults = linqQuery.ToList();
```
