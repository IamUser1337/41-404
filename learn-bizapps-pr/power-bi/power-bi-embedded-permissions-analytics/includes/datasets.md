When you're enforcing RLS by using the *For your customers* scenario, your app must set effective identity. How you set effective identity depends on the type of Power BI dataset that the app requires.

Four different types of datasets are available for consideration. These types are determined by where the model is hosted and the model framework. The remainder of this unit will describe these four different types of datasets.

By definition, a Power BI dataset is an artifact that represents a source of data for visualization in Power BI. Commonly, datasets represent *data models*, which are queryable data resources that are optimized for analytical reporting.

## Model architecture

Most Microsoft data models are *tabular*. Tabular models comprise one or more tables. Other Microsoft data models are *multidimensional*. Multidimensional models rely on older (yet still relevant) technology, and they're composed of dimensions and measure groups. Often, multidimensional models are called *cubes*.

> [!NOTE]
> Like tabular models, multidimensional models enforce data permission by using roles. However, they don't define filters by using rules, and they rely on Multidimensional Expressions (MDX) instead of DAX. While multidimensional models don't enforce RLS (because multidimensional models don't store rows of data), they enforce equivalent requirements that produce the same result of (static and dynamic) tabular model rules.

## Model hosting

Data models are either *internal-hosted* or *external-hosted*. Internal-hosted models reside **inside** Power BI, while external-hosted models are hosted **outside** Power BI.

Internal-hosted models reside in Power BI workspaces. Microsoft external-hosted models reside in [Azure Analysis Services](/azure/analysis-services/analysis-services-overview/?azure-portal=true) or [SQL Server Analysis Services](/analysis-services/analysis-services-overview). SQL Server Analysis Services can host tabular and multidimensional models, and Power BI requires a [gateway](/power-bi/connect-data/service-gateway-onprem/?azure-portal=true) to connect to them.

> [!NOTE]
> Power BI connections to external-hosted models are referred to as *live connections*.

## Model framework

Each table (except calculated tables) in a tabular model has a storage mode setting that's either *Import*, *Dual*, or *DirectQuery*.

A model table that’s set to use the **Import** storage mode will physically load and store source data. It relies on a regular data refresh to keep data current. Import storage provides the fastest query performance, but it can be inefficient (or expensive) when you have large volumes of data. Also, when users want up-to-date data, it might not be possible (due to daily limits) to refresh the dataset often enough.

Conversely, a model that uses DirectQuery storage mode never stores source data. Instead, when model tables are queried, the model will query the source data. It's known as a *passthrough query*. DirectQuery storage mode can be a good choice when you have large data volumes or if you have a need to report on up-to-date data.

When a table is set to use **Dual** storage mode, it can behave as an import or a DirectQuery table. For each query, the model query engine determines the most efficient (fastest) mode to use.

## Summary

To correctly set effective identity, you must determine which type of dataset that you have:

- Internal-hosted with import tables

- Internal-hosted with DirectQuery tables

- Azure Analysis Services, which is an external-hosted model

- SQL Server Analysis Services, which is an external-hosted model
