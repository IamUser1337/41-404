
## Power Platform data privacy and accessibility

Organizations want to know that their data isn't going to be compromised. For example, you don’t want to accidentally pass through sensitive information in an application. The [Microsoft Online Services Terms](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) and the [Microsoft Enterprise Privacy Statement](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx) govern the Power Platform service. For the location of data processing, refer to the Microsoft Online Services Terms and the [Data Protection Addendum](https://www.microsoft.com/download/details.aspx?id=101581).

The [Microsoft Trust Center](https://www.microsoft.com/trustcenter) is the primary resource for Power Platform compliance information. Learn more at [Microsoft Compliance Offerings](/compliance/regulatory/offering-home).

The Power Platform service follows the Security Development Lifecycle (SDL). SDL is a set of strict practices that support security assurance and compliance requirements. Learn more at [https://www.microsoft.com/securityengineering/sdl/practices](https://www.microsoft.com/securityengineering/sdl/practices).

### Data loss prevention policies

Your organization's data is likely one of the most important assets you're responsible for safeguarding as an administrator. The ability to build apps and automation to use that data is a large part of your company's success. You can use Power Apps and Power Automate for rapid build and rollout of these high-value apps so that users can measure and act on the data in real time. Apps and automation are becoming increasingly connected across multiple data sources and multiple services. Some of these apps might be external, third-party services and might even include some social networks. Users generally have good intentions. However, they can easily overlook the potential for exposure from data leakage to services and audiences that shouldn't have access to the data.

Data loss prevention (DLP) policies act as guardrails to help prevent users from unintentionally exposing organizational data. DLP policies can be defined at the environment or tenant level, offering flexibility to craft sensible policies that strike the right balance between protection and productivity. Connectors can be classified as follows: 

- **Business:** Connectors that host business -use data.

- **Non-Business:** Connectors that host personal-use data.

- **Blocked:** Connectors that you want to restrict usage across one or more environments.  

When a new policy is created, all connectors are defaulted to the **non-Business** group. From there, they can be moved to **Business** or **Blocked** based on your preference. You can manage connectors when you create or modify the properties of a DLP policy from the [Microsoft Power Platform admin center](https://admin.powerplatform.microsoft.com/). These affect Microsoft Power Platform canvas apps and Power Automate flows. 

### Compliance and data privacy

Microsoft is committed to the highest levels of trust, transparency, standards conformance, and regulatory compliance. Microsoft’s broad suite of cloud products and services are all built from the ground up to address the most rigorous security and privacy demands of our customers.

Microsoft provides the most comprehensive set of compliance offerings (including certifications and attestations) of any cloud service provider. These offerings help your organization comply with national, regional, and industry-specific requirements governing the collection and use of individuals’ data. There are also tools for administrators to support your organization’s efforts. In this part of the document, we cover in detail the resources available to help you determine and achieve your own organization's requirements.

### Data Protection

Data in transit between user devices and the Microsoft datacenters are secured. Connections established between customers and Microsoft datacenters are encrypted, and all public endpoints are secured using the industry-standard Transport Security Layer (TLS). TLS effectively establishes a security-enhanced browser to server connection to ensure data confidentiality and integrity between desktops and datacenters. API access from the customer endpoint to the server is also similarly protected. Currently, TLS 1.2 (or higher) is required for accessing the server endpoints.

## Accessibility in Microsoft Power Platform

One of the things that Microsoft values the most is making sure that Power Platform is accessible and inclusive to all kinds of users all over the world. An accessible canvas app allows users with vision, hearing, and other impairments to successfully use the app. In addition to being a requirement for many governments and organizations, following the below guidelines increases usability for all users, regardless of their abilities. You can use the [Accessibility Checker](/powerapps/maker/canvas-apps/accessibility-checker) to help review potential accessibility issues in your app. For more details and suggestions on making your canvas apps more accessible, visit [Create accessible canvas apps in Power Apps](/powerapps/maker/canvas-apps/accessible-apps).
