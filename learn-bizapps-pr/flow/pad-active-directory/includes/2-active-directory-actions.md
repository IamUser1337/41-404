Power Automate for desktop provides Active Directory actions allowing users to add, remove, or update users, user roles and objects in the Active Directory server.

## Connect to an Active Directory server

Active Directory-related flows require a connection to an Active Directory server. Establish the connection by using the **Connect to server** action, which requires the LDAP path to specify the domain controllers.

![Screenshot of Connect to server action properties.](..\media\connect-to-ad-server-action-properties.png)

Select the **Use Authentication** check box to show additional fields. If authentication is required, provide the **Authentication type** along with your **Username** and **Password**. The password can be entered directly or as a variable.
  
![Screenshot of Connect to server action properties with Use authentication switched on.](..\media\connect-to-ad-server-action-properties-continued.png)

The action stores the output which contains the Active Directory connection, **Parent entry**, into a variable; therefore, other Active Directory actions can reference it.

> [!NOTE]
> The **LDAP Path** field should have the following format:
> LDAP://DC=contoso,DC=demo

## Close the Active Directory connection

Close the Active Directory connection with the **Close connection** action. The only input that this action requires is the variable that stores the Active Directory Parent Entry.
  
![Screenshot of Close connection action properties.](..\media\close-ad-connection-action-properties.png)

> [!NOTE]
> All Active Directory actions require the Active Directory Parent Entry. The name of the variable from the **Connect to Active Directory Server** action where the parent entry is stored will be populated automatically into any Active Directory action, even if the default variable name has been changed.

## User management

Use Active Directory user management actions to create, modify, update, and unlock users and retrieve information about them.

Create a user with the **Create user** action. The **Location** field must contain the location of the user's container. Enter the user’s details, as necessary. You can provide the password directly or by specifying a variable.
  
![Screenshot of Create user action properties.](..\media\create-ad-user-action-properties.png)

> [!NOTE]
> The **Location** field should have the following format:
> CN=Users,DC=contoso,DC=demo

The **Modify user** action allows you to perform the following operations on a user account:

- Enable/Disable
- Rename
- Delete
- Reset Password
  
![Screenshot of Modify user action properties.](..\media\modify-ad-user-action-properties.png)

> [!NOTE]
> All Active Directory user management actions require the user’s distinguished name. The **Distinguished Name** field should have the following format:
> CN=nvarga,CN=Users,DC=contoso,DC=demo,
> where **nvarga** is the username.

You can use the **Update user info** action to add more details to, or modify existing details of, an Active Directory user.
  
![Screenshot of Update user info action properties.](..\media\update-ad-user-action-properties.png)

The **Unlock user** action behaves in a similar manner as the **Update user** action, except that the required inputs are limited to the parent directory and distinguished name.
  
![Screenshot of Unlock user action properties.](..\media\unlock-active-ad-user-action-properties.png)

To get a user's info, use the **Get user info** action, which requires the same inputs. The action stores the retrieved information in a variable.
  
![Screenshot of Get user info action properties.](..\media\get-ad-user-info-action-properties.png)

> [!NOTE]
> To list the distinguished names of all Active Directory users, open the command prompt and run the following command:
dsquery user

## Group management

Create and modify Active Directory groups in a similar way to users. Create groups with the **Create group** action. The action requires filling in the **Group name** and **Location** fields, as for the previously described actions. Optionally provide a description and define a group scope and type.
  
![Screenshot of Create group action properties.](..\media\create-ad-group-action-properties.png)

Modify groups with the **Modify group** action, which requires the distinguished name of the group and, if the operation applies to users, the distinguished name of the user.
  
![Screenshot of Modify group action properties.](..\media\modify-ad-group-action-properties.png)

Get information, or the members of an Active Directory with the **Get group info** and **Get group members** actions respectively. These actions require the distinguished name of the group and store the retrieved information in a variable.

> [!NOTE]
> To list the distinguished names of all Active Directory groups, open the command prompt and run the following command:
> dsquery group

## Object management

Create, move, rename, or delete Active Directory computers and organizational units with the corresponding actions. To create an object, use the **Create object** action. The object’s name, location, and type must be specified in the action properties.
  
![Screenshot of Create object action properties.](..\media\create-ad-object-action-properties.png)

In all Active Directory object management actions, specify the object by its distinguished name. When moving or renaming and object, specify the new location and new name.

> [!NOTE]
> To list the distinguished names of all Active Directory computers, open the command prompt and run the following command:
> ```dsquery computer```
>
> To list the distinguished names of all Active Directory organizational units, open the command prompt and run the following command:
> ```dsquery ou```
