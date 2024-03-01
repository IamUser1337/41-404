Increasingly, organizations are using Power Pages to reach out to external audiences. Among the many important aspects of the global reach is the ability to deliver solutions that are compliant with the relevant standards, regulations, and applicable laws. Compliance is especially important when Power Pages is used within the government or financial organizations.

## Accessibility

The websites that are built with out-of-the-box templates are accessible. However, customizers must ensure that the website remains accessible after customizations or changes have been made.

You can retrieve specific Power Pages conformance reports by searching for **Dynamics 365 Customer Engagement** at [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/?azure-portal=true). These reports cover the following standards:

- **EN 301 549** - The European standard that establishes accessibility requirements for information and communication technology that is procured by the public sector.

- **Section 508** - Under Section 508 of the Rehabilitation Act, US government agencies must give employees with disabilities and members of the public access to information that's comparable to the access that's available to others.

- **WCAG** - Web Content Accessibility Guidelines are published and maintained by the World Wide Web Consortium (W3C).

For more information, see [Accessibility in Power Pages](/power-pages/admin/accessibility/?azure-portal=true).

## Data protection

You can set up your website to meet data protection standards. Two important parts of data protection standards that are covered by websites are:

- Identifying minor website users and obtaining parental consent
- Agreeing to terms and conditions

### Minor website users

Regulations for identifying minors vary by country/region. Because a minor can only access the website with parental consent, you can set up the website to identify minors by using these columns in the website contact row:

- **Is Minor** - Indicates that the contact is considered a minor in their jurisdiction. By default, **No** is selected.

- **Is Minor with Parental Consent** - Indicates that the contact is considered a minor in their jurisdiction and has parental consent. By default, **No** is selected.

By using more site settings, you can set up the website to deny access to minors or minors without parental consent. Related messages that are displayed to the users are also configurable.

It's up to the organization to define how the information about a user being a minor and having parental consent is collected. For example, you can customize a registration form to include a **Birth Date** column, and if necessary, a parental consent flag. You might want to further enhance the functionality by implementing a Power Automate flow that calculates user age at sign-in time and then set or clear the **Is Minor** flag.

Special considerations must be given when you're using external providers, such as Azure Active Directory B2C. Only limited information is available from the providers, and providers might or might not have a mechanism for minor protection. Therefore, when someone registers by using an external provider, and the website is set up to block minors or minors without parental consent, the contact row won't be created, and the user won't be authenticated.

For more information, see [Identifying minor website users and obtaining parental consent](/power-pages/configure/implement-privacy/?azure-portal=true#identifying-minor-users-and-obtaining-parental-consent).

### Terms and conditions

Your organization has policies regarding rules for using your website. These rules are typically described in Terms and Conditions and include what website users can do, what is prohibited, and a disclaimer to limit your liability when these users access your website. In addition, website users must agree to the terms and conditions to allow marketing, profiling, or access to private information.

You can publish terms and conditions to get the consent of a website user before they're authenticated to the site.

Power Pages uses content snippets to store terms and conditions and to support the process of getting consent from a website user before they're authenticated to the site. Because content snippets are language-aware, it's possible to set up terms and conditions to be displayed in the language of the user's choice.

The contact table includes the **Portal Terms Agreement Date**, which indicates the date and time that the person agreed to the website terms and conditions.

For more information, see [Agreeing to terms and conditions](/power-pages/configure/implement-privacy/?azure-portal=true#agreeing-to-terms-and-conditions).
