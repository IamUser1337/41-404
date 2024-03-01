To make a custom connector available to all users in Logic Apps, Power Automate, and Power Apps as a certified connector, you need to submit your connector to Microsoft for certification. Microsoft reviews the connector and, if it meets the certification criteria, approves it for publishing. After the connector is published, it joins the [full list](/connectors/connector-reference/?azure-portal=true) of publicly available connectors.

This unit examines each step, including some high-level steps, in the certification process. These same steps also apply to later updates, but depending on the scope of the update, they can be considerably quicker.

## Planning

Planning is the first step in the process of certification as you start envisioning what your connector looks like. Building a connector that others use should involve some planning.

The first step in the planning process is to verify that a connector doesn't already exist. If a connector already exists, you should consider contributing your proposed changes to the existing connector because Microsoft doesn't certify multiple connectors for the same API.

A few key planning factors to consider are:

- Identify what triggers and actions are available initially. You don't need 100 percent of your API covered, but the initial set of triggers and actions should be useful. If you're too limiting in what your initial version offers, users might become frustrated that functionality is missing for common scenarios. Consider writing or sketching one or more workflows that you can create in Power Automate by using your connector. This approach can help you decide which APIs to include in the connector.

- Evaluate what changes might be needed to the API to support triggers or otherwise improve the ability of delivering a user-friendly connector.

- Consider how [authentication](/connectors/custom-connectors/define-blank?azure-portal=true#step-2-specify-authentication-type) is handled and the adaptation that's necessary between how your API currently authenticates and the supported capabilities of custom connectors.

- Consider how people who want to use the connector will get a key, if your API uses API keys.

- Review connector [policy templates](/connectors/custom-connectors/policy-templates?azure-portal=true) to determine if implementing templates would help the usability of your connector.

- Review the supported [OpenAPI extensions](/connectors/custom-connectors/openapi-extensions?azure-portal=true) for applicability. For example, certified connectors commonly implement the test connection. Also, using dynamic value extensions can be helpful if you have parameters with lists of values to choose from.

For new connector certification, you don't need to wait until you finish developing the connector to register for certification. For more information, see the [Verified Publisher Certification Process](/connectors/custom-connectors/submit-certification?azure-portal=true#certification-process) or the [Independent Publishers Certification Process](/connectors/custom-connectors/certification-submission-ip) documentation. Expect to receive communication from a Microsoft representative who can help you better understand your custom connector, explain your development progress, and guide you through the certification process.

For updates to a certified connector, the most important part of planning is to not break existing users. This issue is discussed in more detail in a later unit.

## Development

The primary focus in the development step is getting your API and the definition for your custom connector ready for submission. Before you proceed to the next step, make sure that your custom connector definition is refined and has all proper naming that you want to publish.

## Create an open source

The introduction unit covered a high-level overview of how to create an open-source connector. In this process, you put the verified publisher certified connector in the **certified-connectors** folder and the independent publisher connectors in the **independent-publisher-connectors** folder. Prior to submitting a pull request, make sure that you complete the following tasks:

- Edit your connector files to add the [specific required metadata](/connectors/custom-connectors/certification-submission?azure-portal=true#publisher-and-stack-owner). Your connector files must contain specific metadata that describes the connector and its end service.

- Run the [paconn validate](/connectors/custom-connectors/paconn-cli?azure-portal=true#validate-a-swagger-json) command on your downloaded connector and then resolve errors.

To run validation, use the following command:

`paconn validate --api-def [Location of apiDefinition.swagger.json]`

After you pass validation, you can submit your pull request to the **dev** branch of the GitHub repository. This action starts an automated process that conducts initial validation of your pull request and ensures that you have a proper contribution agreement in place. When the automated validation is complete, the system assigns it to Microsoft for initial review. If the reviewers find issues that need correcting, they enter comments on the pull request, after which you're expected to resolve them and resubmit the pull request. When everything looks acceptable, the reviewer merges your pull request into the repository.

## Independent publisher submission

If you're publishing an independent publisher connector, your next steps are: 

1. Submit the connector artifacts to the pull request that you created when you proposed the connector.

1. Fill out the checklist in the pull request template.
 
1. Remove "Proposal -" from your pull request title. 

A Microsoft certification engineer provides feedback within 1-2 weeks of your initial request. If the feedback requires an update to the connector, you need to submit an update to the pull request.

## Verified publisher submission

The next step is to submit your connector for certification in Microsoft Power Platform [ISV Studio](https://isvstudio.powerapps.com/ep/connector/?azure-portal=true) after your Microsoft contact asks you to do so. ISV Studio is a portal for managing the rest of the certification process, and it gives you the health of your connector after it's deployed.

As part of the process for submitting to ISV Studio for certification, you should be prepared to provide the following details:

- Connector testing information, such as an API key, other authentication details, or details that would help a tester use the connector.

- An `Intro.md` file that contains information to include in the public documentation for the connector. The template is in the [Submitting to ISV Studio](/connectors/custom-connectors/certification-submission?azure-portal=true#submitting-to-isv-studio) documentation.

As the certification progresses, you'll get updates in the portal and will receive an email from the primary contact. If issues are encountered, you're expected to resolve them before the certification proceeds. After the connector passes certification, it's scheduled for deployment to the "Preview" region for testing.

## Testing

As part of the certification process, your connector is deployed to the "Preview" region for testing. It's now your opportunity to make sure that the deployed connector works properly before it's deployed to all regions worldwide. Make sure that you test all functionality of your connector in Power Apps, Power Automate, and Logic Apps.

For more information, see [Instructions on testing your connector in certification](/connectors/custom-connectors/certification-testing/?azure-portal=true).

## Deployment

After testing is complete, your connector is deployed to all public regions. Expect this process to take 7-10 business days because Microsoft deploys incrementally in its regions around the world. You receive notifications as each region is deployed.

## Support

Now that your connector is publicly released, for verified publisher connectors, you can monitor its performance from ISV Studio. Ensure that your support staff is aware of how your connector might be used with Power Apps or Power Automate so that they can support users who experience issues.
