In this exercise, you will develop a flow that connects to an Active Directory server, creates a new user and object, and then adds the user to a group.

You will complete the following tasks:

- Open an Active Directory connection.
- Create a user with information based on the provided details.
- Add the user to an existing group.
- Add a computer based on the provided details.

## Connect to an Active Directory server

Create a new flow and then add the **Connect to server** action. Enter information in the **LDAP path** field, specifying the domain controllers.

If authentication is required, select the **Use authentication** check box, and then provide your **Authentication type** and credentials.
  
![Screenshot of Connect to server action properties.](..\media\connect-to-ad-server-properties-exercise.png)

## Create an Active Directory user

The **Create user** action requires the location where the user will be created. Enter the location of the user's container.

Provide the user’s personal details and credentials, as follows, and then select the **Disable account** and **Password never expires** check boxes.

- **First name** — Norbert
- **Last name** — Varga
- **Initials** — NV
- **Username** — nvarga
- **Password** — Password123

![Screenshot of Create user action properties.](..\media\create-ad-user-properties-exercise.png)

## Add the user to a group

Now that an Active Directory user has been created, the next step is to add this user to a group with the **Modify group** action.

Specify the group by filling in the **Distinguished name** field and then set the **Operation** option to **Add user**, again specifying the user’s distinguished name.
  
![Screenshot of Modify group action properties.](..\media\modify-ad-group-properties-exercise.png)

## Create a computer object

Next, you will add the **Create object** action. Set the **Object name** field to **NVBOT** (in uppercase). The object’s location should be the computer's container, and the **Object type** option should be set to **Computer**.
  
![Screenshot of Create object action properties.](..\media\create-ad-object-properties-exercise.png)

## Close connection

The last step in the flow, **Close connection**, will disconnect from the Active Directory server.
  
![Screenshot of Close connection action properties.](..\media\close-ad-connection-properties-exercise.png)

## Run the flow

Run the flow, and an Active Directory connection will be established. To determine if the flow was successful, you should notice that a user was created based on your input, the user was added to a group, a computer was created, and then the connection was closed.

## Active Directory check

You can check that the objects have been created by going to **Active Directory Users and Computers** on the server machine. Under **Users**, check for the user and group and also confirm that the user is a member of the specified group. Under **Computers**, you can also confirm that the new computer object was created.
