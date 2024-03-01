

## Project specification
Northwind Traders basketball club needs a solution to track the player recruiting process.  You are building the relational database with Microsoft Dataverse.  From there, you'll compose a model-driven Power App for their office staff.  The Northwind Traders have scouts in the field that watch players in action and create scouting reports. The scouts need a canvas app to quickly find the players they're scouting and track information about them in reports.  The scouts also need to be able to send reports about the players on-demand.
Here's a high-level summary of the requirements to use later in the exercises.

## Microsoft Dataverse requirements
- Create tables and columns for players and scouting reports.
- Create relationships for contacts, players, scouts (Users), and scouting reports.
- Create needed forms and views.
- Add new column to the contact table.

## Model-driven application requirements
Compose a model-driven app that is appropriate for office staff to use to complete their needed tasks.  Include tables, forms, views, and all needed components.
- Users should be able to create/edit new player records, create/edit contacts, and create/edit scout reports.

## Canvas application requirements
Compose a canvas app that is appropriate for scouting to use in the field.
- Show players.
- Allow to create or edit existing players.
- Allow to create new scouting reports and edit reports they created.
- Allow to add or edit contacts that are related to the player.
- Scouts shouldn't be able to edit a player record of a player who failed the drug test.

## Power Automate Cloud Flow requirements
Create a cloud flow that is triggered from a button on the canvas application.
- When the flow is triggered, it should get the player record, and then send an email that includes some information about the player to someone (You may use your own user’s email).
- Add a button to the edit player form of the canvas application that triggers this flow.
- This button shouldn't be visible when creating a new player.

> [!NOTE]
> Remember to test your work often and compare your work against the requirements.
