The three types of Power Automate buttons are:

- An app-based virtual button with a flow with no user input

- An app-based virtual button with a flow with user input or trigger tokens

- A physical button

### App-based virtual button with a flow with no user input

An example of an app-based button with no user input would be if you
use the Power Automate virtual button to send a notification email to your manager
that you'll be late for work. This virtual button
is available on the Power Automate app for your smart devices. For this flow not to require user input, you'll need to have necessary
data connections, such as Office 365 users, to find your manager's
contact information and also have the email action pre-populated with
the subject line and email body.

> [!div class="mx-imgBorder"]
> [![Diagram of a contact manager button flow with no user input.](../media/flow-no-input.png)](../media/flow-no-input.png#lightbox)

### App-based button with a flow with user input or trigger tokens

Power Automate with user input or trigger tokens is a quick way
to send notifications. Consider the scenario where you have a
virtual button that provides you with the
opportunity to notify and alert the maintenance department about
damage to equipment, for example. The flow has a drop-down data type to select the location, such
as a building or department, and a text data type to write a note. Upon
submission, a notification is sent to the key people.

### Use a physical button

Several third-party companies, such as [Flic](https://flic.io/?azure-portal=true)
and [Bttn](https://bt.tn/?azure-portal=true), provide physical buttons that integrate
with smart phones and can trigger your flows. The Power Automate mobile
app must be installed on your smartphone to use these physical buttons. These flows don't require any user
input.
