The solution architect has a unique role in customer implementations of Microsoft Power Platform solutions. Solution architects are among the key people who are responsible for the success of the deployment.

Go-live is the process through which Microsoft Power Platform solution becomes operational. This process goes beyond turning on the production environment and the deployment of the solution files; it also includes the onboarding of users. If you are migrating from a legacy customer relationship management system, the process can include the final production data migration, decommissioning of the old system, and post-deployment support of the new system.

To prepare for a successful project go-live, the solution architect should plan and deliver a Go-live Readiness review. The review can be a meeting or a workshop, but the solution architect should prepare a go-live document for review. The review's goal is to evaluate how prepared the customer is for go-live. The Go-live Readiness review should be scheduled and completed before the customer's go-live date, ideally with enough time to make necessary corrections that the review has revealed.

Getting ready for go-live is one of the busiest times of the project, and you should be respectful and understanding of the pressure that the team is probably experiencing and keep the meeting to its primary purpose. Be prepared to participate in the go/no-go decision process criteria and to help guide the customer toward successful criteria to avoid escalations later.

Go-live is one of the most critical milestones during a deployment. The Go-live Readiness meeting will ensure that the customer is ready for a successful go-live and won't need to postpone the go-live date due to unforeseen issues, bad strategy, or project risks that were not previously identified. Specific activities occur during this phase that you'll want to keep track of and follow up on proactively with the customer to avoid surprises. This approach includes activities such as final user acceptance testing, user training, final data migration, installation of apps for Microsoft Outlook and mobile, and migration of the client configuration to production.

## Navigate to go-live

Rarely will you have issues that are unresolved prior to go-live. The solution architect's role is to work with customer to guide them toward a go-live decision with outstanding issues.

The solution architect will need to evaluate the impact of fixing an issue prior to go-live or fixing after go-live. Additionally, the solution architect will need to plan how to resolve outstanding issues during the post go-live support period.

## Common go-live problems

Common go-live problems include:

- No plan for how to roll back if the deployment goes wrong.
- Incorrect assumptions about a user's workstation or network configurations.
- Insufficient real-world testing, which can lead to customizations that don’t meet real users' needs or performance issues with real user load.

The solution architect should push to reduce the risk of problems with go-live, for example:

- Look for places to streamline and simplify the plan, such as pre-deploying mobile apps.
- Prioritize data migration so that the important data gets in first.
- Have all users access a dummy production environment so that you can resolve access issues before go-live.
- Determine whether you can run the old system and new system in parallel and then slowly move groups of users.

## Automate go-live

The solution architect should consider automating go-live activities to reduce effort and risks. By using automation, you can script and test go-live activities before going live. For instance, you can consider automating the following parameters:

- User, team, and business unit creation
- Reference data creation and updates
- User configuration
- Data migration deltas

All automation must be well tested.

## Deal with problems

The solution architect is often the first call when issues arise with go-live and in the post go-live period. The solution architect will need to proactively triage, isolate, and simplify issues. Often, Microsoft Power Platform tools can prove beneficial to you when fixing problems by using its built-in features.

Before you make changes, consider the immediate impact and long-term impact of mitigation activities that you apply.
