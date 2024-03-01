By using containers to deploy Text Analytics for health, you can bring the service closer to your data for compliance, security, and other operational reasons. A common reason for using containers with Text Analytics for health is to allow the protected health information (PHI) data to stay on-premises while you're analyzing the data with Text Analytics for health. In such a scenario, only the billing data will upload to the cloud. After you've deployed the container, you'll be able to access the service by using the REST API or an SDK.

You can find the Text Analytics for health container images on the [container registry syndicate](https://mcr.microsoft.com/product/azure-cognitive-services/textanalytics/healthcare/tags/?azure-portal=true). It resides within the `azure-cognitive-services/textanalytics/` repository and is named *healthcare*. The fully qualified container image name is `mcr.microsoft.com/azure-cognitive-services/textanalytics/healthcare`.

The container that you choose will determine the languages and health AI model that's available for use. You can find the current container by using the latest tag to pull the image for use. Before deploying the container, you should [review the container languages](/azure/cognitive-services/language-service/text-analytics-for-health/language-support?azure-portal=true#details-of-the-supported-model-versions-for-each-language) that are available on the container.

You can deploy the containers on-premises or in a cloud-hosting service. Some common container deployment options are:

- Docker Desktop

- Azure Web App for Containers

- Azure Container Instance

You should review the [current recommendations](/azure/cognitive-services/language-service/text-analytics-for-health/how-to/use-containers?azure-portal=true#host-computer-requirements-and-recommendations) for host computer memory and processor requirements to ensure that your performance needs are achieved. The memory and processor requirements can affect the number of documents for each request and the allowable transactions per second (TPS).

## Configuration settings

As part of setting up the container, you'll need to set up the following required and optional settings to successfully run the service from the container:

- **API key** - You're required to provide an Azure resource key for your language service. When you run the service in a container, the processing happens locally in the container, but the usage is billed to your Azure subscription. The container periodically sends usage and must always be able to contact Azure; otherwise, the service will stop functioning.

- **Billing** - This setting indicates the endpoint URI for the language resource on Azure for billing usage. You'll use this setting in combination with the API key to implement metered billing for your usage in the container.

- **Eula** - This setting allows you to accept the license for the container. For example, you would specify `Eula=accept` if you accepted the license.

- **RAI Terms** - This setting allows you to indicate if you accept the terms for Responsible AI. For example, you would specify `rai_terms=accept` if you accepted the terms.

If any of these four settings are invalid or aren't provided, your container service won't initialize properly. For example, the following message indicates that you didn't provide **rai_terms** properly.

> Missing `RAI_TERMS=accept` command line option. You must provide this to continue.

In addition to the required settings are the [optional configuration settings](/azure/cognitive-services/language-service/text-analytics-for-health/how-to/configure-containers#configuration-settings/?azure-portal=true) that you can set up.

## Container provisioning

Watch the following video, which demonstrates the process of deploying the container to Azure Web App for Containers.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWXhEe]

You can also use the [PowerShell script](/azure/cognitive-services/language-service/text-analytics-for-health/how-to/use-containers?azure-portal=true#install-the-container-using-azure-web-app-for-containers) from the video to deploy a container to your own Azure subscription.

No security is provided when you're using the container API. Containers typically run inside a controlled network. Depending on the container host, you can set up your own security for your API. For more information, see [Secure ACI connectivity](/azure/cognitive-services/language-service/text-analytics-for-health/how-to/use-containers?azure-portal=true#secure-aci-connectivity) for an example of setting up your own security with Azure Container Instances.

When using containers, you take on the responsibility of updating to the latest container image. When you use the cloud service, the service updates will happen automatically.
