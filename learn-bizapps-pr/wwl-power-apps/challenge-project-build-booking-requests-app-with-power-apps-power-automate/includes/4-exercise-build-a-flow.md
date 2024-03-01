Contoso Pet Boarding customers need to receive a confirmation email after submitting booking requests in the app. They also need to receive an email when the Contoso staff has made a decision to accept or decline the booking request. Here, you'll create Power Automate flows that send an email each time a booking request is submitted and each time the booking request decision column has been updated. You'll validate the flow behavior against requirements to check your work.

## Specification

You need to build some automation for your app that meets the following specifications:

- When a customer submits a Booking Request, an email is sent to them confirming that the request was received.
- When a decision has been made on a Booking Request, the customer receives an email to update them on the decision.

You may choose to design your solution with two Power Automate flows or just one. There's no right answer, as long as you have the expected behavior based on the specifications provided. Think through your design and why you chose the number of flows that you did.

## Check your work

To validate that you've completed the work to the requirements, test your flow behavior out by following these steps.

1. In your canvas app, create a new Booking Request with your email address provided as the Owner Email. Confirm that you receive an email once the Booking Request is created.
2. On the same Booking Request row, update the Decision field to Declined. Confirm that you receive an email that the Booking Request was declined.
3. On the same Booking Request row, update the Decision field to Accepted. Confirm that you receive another email that the Booking Request was accepted.

  > [!TIP]
  > If you get stuck here, reviewing [Extend Dataverse with Power Automate](/training/modules/extend-dataverse-power-automate/?azure-portal=true) may help.
