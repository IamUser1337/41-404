Dataverse for Teams provides organizations with the ability to build applications and use a targeted set of features commonly needed for creating apps, flows, and more directly within Microsoft Teams. It's important to note that the subset of features available in Dataverse doesn't match the specific features that are available in a typical Dataverse environment. The first difference is that Dataverse for Teams has a limit of approximately 1 million rows that it can contain. Organizations that require more data than that would want to consider upgrading to Dataverse.

In addition to the data capacity limitations, Dataverse simply provides more features that are often beneficial when managing business applications. The following table provides the differences between a Dataverse for Teams and Dataverse table features.

|     Feature                                                              |     Dataverse for   Teams    |     Dataverse    |
|--------------------------------------------------------------------------|------------------------------|------------------|
|     Basic data   types                                                   |     Yes                      |     Yes          |
|     Advanced data   types (customer, multiple transaction currencies)    |     No                       |     Yes          |
|     Relational   storage                                                 |     Yes                      |     Yes          |
|     Nonrelational   storage (logs)                                      |     No                       |     Yes          |
|     Managed data   lake                                                  |     No                       |     Yes          |
|     File and   image support                                             |     Yes                      |     Yes          |
|     Find, filter,   sort                                                 |     Yes                      |     Yes          |
|     Advanced and   Dataverse search                                      |     No                       |     Yes          |
|     Mobile   offline                                                     |     No                       |     Yes          |

In addition to the reduced number of tables features available, most of the standard tables provided with a Power Platform environment won't be present as part of Dataverse for Teams.

## Environments

In Dataverse for Teams and Dataverse, data is stored within an environment. Dataverse for Teams creates a single environment for each team in Teams where you create data, apps, chatbots, and workflows. Environments support backups, point-in-time restore, and disaster recovery. With Dataverse for Teams, capacity is measured with relational, image, and file data. The 2-GB capacity provided to a team can typically store up to 1 million rows of data.

To make management easier, the lifecycle of the Dataverse for Teams environment is connected to that of the associated team. For example, when a team is deleted, the associated environment is also deleted.

Whereas Dataverse for Teams focuses on one environment per team for up to 10,000 teams, Dataverse supports unlimited environments in addition to capabilities that are relevant for multiple environments, such as copy and reset.

The following table highlights some of the key environment differences.

|     Environment   lifecycle    |     Dataverse for   Teams       |     Dataverse    |
|--------------------------------|---------------------------------|------------------|
|     Environments               |     1 per Team                  |     Unlimited    |
|     Maximum size               |     1 million   rows or 2 GB    |     Unlimited    |
|     Upgrade to   Dataverse     |     Yes                         |     N/A          |

## Security

Another of the biggest differences between Dataverse for Teams and Dataverse is related to security. In Teams collaboration happens between both people inside and outside your organization. This requires that the security model needed to support this is easy to use. For this reason, security is based on membership type such as owners, members, or guests.

Dataverse includes more options for admin and user roles. It also includes many other security capabilities such as customer-managed keys, field-level security, hierarchical security, sharing, and support for legacy authentication.

The following table provides a more specific breakdown of the specific security feature differences between Dataverse for teams and Dataverse.

|     Security   feature                               |     Dataverse for   Teams                           |     Dataverse                                                                                                                                        |
|------------------------------------------------------|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Admin roles                                      |     System   Administrator and System Customizer    |     System   Administrator and System Customizer and other service admin roles. More   information: [Use service admin roles to manage your tenant](/power-platform/admin/use-service-admin-role-manage-tenant)    |
|     User roles                                       |     Team owners,   members, and guests              |     Several   standard security roles and custom roles can also be created. More   information: [Security roles and privileges](/power-platform/admin/security-roles-privileges)                        |
|     Activity   logging                               |     No                                              |     Yes                                                                                                                                              |
|     Auditing                                         |     No                                              |     Yes                                                                                                                                              |
|     Business   units                                 |     One                                             |     Unlimited                                                                                                                                        |
|     Customer-managed   environment encryption key    |     No                                              |     Yes                                                                                                                                              |
|     Field-level   security                           |     No                                              |     Yes                                                                                                                                              |
|     Hierarchical   security                          |     No                                              |     Yes                                                                                                                                              |
|     Record   sharing                                 |     No                                              |     Yes                                                                                                                                              |
|     Create Owner   Teams**                           |     Yes                                             |     Yes                                                                                                                                              |
|     Create Microsoft Entra ID Group Teams                         |     No                                              |     Yes                                                                                                                                              |
|     Record   sharing to Group Teams                  |     No                                              |     Yes                                                                                                                                              |
|     Assign Teams   Roles to Owner Teams1             |     Yes                                             |     Yes                                                                                                                                              |
|     Change record   ownership**                      |     Yes                                             |     Yes                                                                                                                                              |

For more about integration and other differences see, [Compare Dataverse for Teams and Dataverse](/power-apps/teams/data-platform-compare/?azure-portal=true).
