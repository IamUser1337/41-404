Purchasing licenses involves cost, so it's important that you avoid or minimize cost when evaluating or developing (or testing) a Power BI embedded-analytics solution. Several options are available for you to consider:

- Create a trial tenant
- Use an existing tenant without a capacity-based license
- Use an existing tenant with a capacity-based license

## Trial tenant

Occasionally, you can achieve Power BI embedding for your customers at no cost. Start by creating a [trial tenant](/power-bi/enterprise/service-admin-signing-up-for-power-bi-with-a-new-office-365-trial), which is available at no cost for one month, if it's not used for production purposes.

Two main advantages of using a trial tenant are:

- It's isolated from the organization's tenant (or the customer's tenant).
- You have full tenant privileges as the Global Administrator.

Power BI offers a 60-day free trial of the PPU license to individual users. Therefore, you can create a Power BI workspace and publish content that's ready for embedding at no cost.

When embedding by using the *For your customers* scenario, your app needs to generate embed tokens. In a production environment, it can only generate an embed token when the Power BI content resides in a workspace that has its license mode set to **Premium per capacity** or **Embedded**. Those license modes require purchased products. You can generate *trial embed tokens* at no cost. Remember, if you use a master user account instead of a service principal, it will require a Power BI Pro or PPU license.

> [!NOTE]
> You can generate only a limited number of trial embed tokens that are strictly for evaluation and development purposes. These tokens aren't permitted to be used by production workloads. To track the usage of trial tokens, use the [Available Features](/rest/api/power-bi/available-features/?azure-portal=true) Power BI REST API operation to determine the usage percentage.

## Existing tenant without a capacity-based license

It might make sense to use your organization's tenant (or customer's tenant) to achieve embedding for your customers at no cost. This option requires you to create a workspace with its license mode set to **Pro** or **Premium per user**. It relies on generating trial embed tokens, as described in the previous option.

## Existing tenant with a capacity-based license

When you need longer evaluation periods, or when you require a permanent development environment, consider a low-cost setup. In this case, create a Power BI Embedded A1 node. It's the smallest node type, comprised of a single core with limited memory, and 0.5 front-end and 0.5 back-end cores.

This low-resourced node:

- Is ideal for evaluation, development, and test workloads.
- Is helpful to establish benchmarks when capacity sizing.
- Can be scaled up or down when needed.
- Can be paused when not needed (billing ceases when paused).

For more information, see [Power BI Embedded pricing](https://azure.microsoft.com/pricing/details/power-bi-embedded/?azure-portal=true).

## Setup option comparison

The following table compares characteristics of the three setup options.

|     Setup        |     Trial tenant                              |     Existing tenant    without a capacity-based license                               |     Existing tenant with a   capacity-based license                                                                          |
|------------------|-----------------------------------------------|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
|     **Use cases**    |     Short-term   evaluation or development    |     Short-term   evaluation or development                                            |     Longer-term or   permanent development                                                                                   |
|     **Duration**     |     30 days or less, per tenant               |     60 days or less, per embedding   identity                                         |     Unlimited                                                                                                                |
|     **Cost**         |     No cost                                   |     Possibly no   cost if the embedding identity has a trial Power BI user license    |     Power BI Embedded   A1 node (billed per running hour).     The embedding   identity might require a Pro or PPU license.    |