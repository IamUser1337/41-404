Follow the steps to create and process a recurring donation.

## Learning objectives

At the end of this exercise, you'll be able to accomplish the following:

- Add a credit card to a donor record

- Create and process a recurring gift for a donor

## Sample data

Before you begin, to achieve the maximum effect for this lab and the other labs, we recommended deploying Fundraising and Engagement with the sample data. For more information, see the [Deployment Guide](https://aka.ms/DeployMicrosoftCloudForNonprofit/?azure-portal=true).

## Add a new credit card

1. In Fundraising and Engagement, select the **Development** area from the bottom left of the screen.

1. Use the search bar to find the contact **Gabriella Morales** and go to her record.

1. Select **Add Credit Card** from the task bar at the top of the contact record. A pop-up window will appear to add a new credit card. If not, you may need to enable pop-ups on your browser.

1. Add the following details to the credit card form:

    - **Card Number**: 4111111111111111

    - **Name on the Card**: Should have autopopulated to Gabriella Morales

    - **Credit Card Type**: Visa

    - **Expiry**: 0427

1. Select **Create** to add the credit card.

## Create a recurring donation

1. Select **Payment Schedules** from the left navigation menu.

1. Select **+New** to create a new payment schedule.

1. Enter the following details into the Payment Schedule Entry section of the form:

    - **Gift Type**: Recurring Donation

    - **Payment Type**: Credit/Debit Card

    - **Donor**: Gabriella Morales

    - **Amount**: $50

    - **Channel**: Phone

    - **Book Date**: Current date

    - **Originating Campaign**: Tanzania Health Center

    - **Primary Designation**: Maternal Health

    You will notice that the Contact Address and Total columns have updated and autopopulated on the record.

1. Enter the following details into the Recurrence section of the form:

    - **Start Date**: Current date

    - **End Date**: Enter one year from the current date

    - **Recurrence Start**: Current Day

    - **Run Every**: 1

    - **Time Period**: Months

1. In the Credit Card Information section, select the credit card that was created earlier: Visa-1111.

1. You'll see details about the first and next payment appear on top of the Process button. Select the **Process** button.

1. The payment schedule will be saved, and in the Recent Transactions section, you'll see the donation that was just processed. Double-click the transaction record to open it and view the details.
