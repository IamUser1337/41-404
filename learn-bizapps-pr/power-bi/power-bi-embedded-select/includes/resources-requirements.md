To ensure good responsiveness and performance of Power BI embedded analytics, you need to buy the right *capacity size*. Capacity size relates to the product SKU. For Premium, SKUs range from P1 to P5. For Power BI Embedded, SKUs range from A1-A8. The larger the SKU, the more memory and computing power and cost.

Buying the right product SKU is a matter of optimization. Too few resources can result in slow performance and, worse, an inability for Power BI to render analytics. Too many resources can result in wasted money.

It's unusual for apps to experience consistent use, and thus consistent demand for embedded analytics. Some apps experience peak load during office hours on working days and in specific time zones. Other apps might experience usage peaks that are associated with a different rhythm, such as during end-of-month reporting, while other apps might experience peaks on an irregular basis, such as during a marketing-campaign launch.

To reduce costs, you need to undergo capacity planning. The capacity-planning process involves establishing a baseline to understand typical resource usage and workload activity. We recommend that you buy the product SKU that can handle the baseline workload. Then, you can adopt elasticity strategies that temporarily scale up the capacity in response to increases in app usage. You can temporarily scale Premium or Power BI Embedded capacities by using different techniques.

> [!TIP]
> For a complete discussion on capacity planning, see [Capacity planning in Power BI embedded analytics](/power-bi/developer/embedded/embedded-capacity-planning). This article applies to Power BI Premium also.

For more information, see the following articles:

- [SKU memory and computing power](/power-bi/developer/embedded/embedded-capacity?tabs=gen2?azure-portal=true#sku-memory-and-computing-power)
- [Power BI pricing](https://powerbi.microsoft.com/pricing/?azure-portal=true)
- [Power BI Embedded pricing](https://azure.microsoft.com/pricing/details/power-bi-embedded/?azure-portal=true)
- [Managing Premium capacities](/power-bi/enterprise/service-premium-capacity-manage)

## Premium autoscale

As a product, Premium is about scale and performance. Premium supports a feature called *Autoscale*. When enabled, Autoscale automatically adds compute capacity to avoid slowdowns under heavy use.

An Azure subscription is required to set up Autoscale. It's used to automatically add more virtual CPU cores (v-cores) when the Power BI workload would otherwise be slowed by the Premium capacity. The other compute resources apply for a 24-hour period and are billed to the Azure subscription.

For more information, see the following articles:

- [What is Power BI Premium?](/power-bi/enterprise/service-premium-what-is)
- [Using Autoscale with Power BI Premium](/power-bi/admin/service-premium-auto-scale/?azure-portal=true)

## Power BI embedded flexible scale

Power BI Embedded doesn't support the Autoscale feature. Instead, you can set up flexible scaling by using the following components:

- The Power BI Embedded Azure Resource Manager (ARM) REST API, and specifically, the [Capacity operations](/rest/api/power-bi-embedded/capacities/?azure-portal=true). You can use the [Update](/rest/api/power-bi-embedded/capacities/update/?azure-portal=true) operation to scale a capacity resource. For example, when a sudden increase in demand occurs for computational resources, you can scale up the capacity from A1 to A2 to double the number of v-cores. You can also pause and resume the service.
- The Power BI Embedded [capacity metrics](/power-bi/developer/embedded/monitor-power-bi-embedded-reference?azure-portal=true#capacities). You can monitor and react to metrics such as CPU, CPU per workload, and Overload to measure demand for computational resources.
- [Azure alerts](/azure/azure-monitor/alerts/alerts-overview/?azure-portal=true), to receive proactive notifications of conditions or issues. You can create (or trigger) alerts in response to metric values, like CPU or Overload.

For more information, see the following articles:

- [Power BI Embedded Azure Resource Manager REST API reference](/rest/api/power-bi-embedded/?azure-portal=true)
- [Monitoring Power BI Embedded data reference (Capacities)](/power-bi/developer/embedded/monitor-power-bi-embedded-reference?azure-portal=true#capacities)
- [What are Azure Monitor alerts?](/azure/azure-monitor/alerts/alerts-overview/?azure-portal=true)
