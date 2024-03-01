A donor commitment represents the actual or prospective agreement between a donor and your organization for the donor to make a gift to the organization in the future, also known as a pledge. Donor commitments can be recorded against a contact or organization in Fundraising and Engagement, and then converted to a transaction once the pledge is fulfilled.

## Create a donor commitment for a one-off donation

A donor commitment record can be created to track a constituent's one-off donation pledge, recording the pledge amount, book date, and originating campaign. Other details including the source can be added if you wish to use them to track and report. Once the donor is specified, their contact address details will autopopulate in the form.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Fundraising and Engagement with the pledge entry section highlighted.](../media/3-1-pledge.png)](../media/3-1-pledge.png#lightbox)

Donor commitments are linked to a campaign and a designation. Campaigns allow you to track and report on activities, responses, and gifts in response to your fundraising efforts in a particular area. Designations allow you to connect debit and credit GL codes to gifts, to indicate how funds will be allocated and to help with reconciliation with the financial system.

The Fundraising Attributes section on a donor commitment record, as with transactions, allows you to store related appeal, package, solicitor, constituent, and opportunity information to enable more connections in your data and more detailed campaign tracking.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Fundraising and Engagement with the Fundraising Attributes section highlighted.](../media/3-2-attributes.png)](../media/3-2-attributes.png#lightbox)

Tribute information can also optionally be recorded against a donor commitment if the pledge was made in tribute or memory of someone.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Tribute information section.](../media/3-3-tribute.png)](../media/3-3-tribute.png#lightbox)

Once the donor commitment is ready to be created, clicking the **Process** button will create a new record, but no transaction record will be created yet. The record will remain as a donor commitment until it's ready to be converted to a donation.

> [!div class="mx-imgBorder"]
> [![Screenshot of the New Donor Commitment with the Process button highlighted.](../media/3-4-commitment.png)](../media/3-4-commitment.png#lightbox)

Certain columns become read-only and will be locked on the donor commitment record. Read-only columns include the donor details, contact address, and pledge amount.

## Convert a donor commitment into a donation

Once a pledge is ready to be fulfilled, the donor commitment record can be converted into a donation. This will create a new transaction record for the donation. The donor commitment record displays a list of linked donations (that is, transactions) related to the pledge. Pressing the **Convert to Donation** button will generate a corresponding donation record.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Fundraising and Engagement with Convert to Donation and the Linked Donations section highlighted.](../media/3-5-convert.png)](../media/3-5-convert.png#lightbox)

Before processing the new transaction record, details for the transaction can be added and changed. As shown in the screenshot below, the linked pledge (donor commitment record) can be seen on the top right of the screen. Gift entry and donor details will be autopopulated. You can edit the autopopulated information on the transaction record, including the amount of the donation.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Fundraising and Engagement transaction details that can be edited.](../media/3-6-transaction.png)](../media/3-6-transaction.png#lightbox)

Clicking **Process** on the transaction record will generate the transaction and process it through the payment gateway.

> [!div class="mx-imgBorder"]
> [![Screenshot of the total transaction amount with the Process button highlighted.](../media/3-7-process.png)](../media/3-7-process.png#lightbox)

The transaction record will now appear in the donation information tab of the donor's contact or organization record.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Fundraising and Engagement Donation Information tab showing the transaction in the list.](../media/3-8-donation.png)](../media/3-8-donation.png#lightbox)
