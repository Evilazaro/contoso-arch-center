
# Landing zone implementation options

[Azure landing zones](./index.md) provide cloud adoption teams with a well-managed environment for their workloads. Follow the [landing zone design areas](./design-areas.md) guidance to take advantage of these capabilities.

Each of the following implementation options is designed for a specific set of operating model dependencies to support your nonfunctional requirements. Each implementation option includes distinct automation approaches. When available, reference architectures and reference implementations are included to accelerate your cloud adoption journey. While each option is mapped to a different operating model, they share the same design areas. The difference is how you choose to implement them.

## Platform development velocity

In addition to the recommended design areas, your platform development velocity (how fast your platform team can develop the required skills) is a key factor when choosing the best implementation option. Consider two primary modes:

**Start with enterprise scale:** Use this mode if your business requirements necessitate a rich initial implementation of landing zones with fully integrated governance, security, and operations from the start. With this approach, you can use either the Azure portal or infrastructure-as-code to set up and configure your environment. You can also transition between the Azure portal and infrastructure as code (recommended) when your organization is ready. To use the recommended infrastructure-as-code approach, your organization will require skills in Azure Resource Manager templates and GitHub.

**Start small and expand:** Use this mode if it's more important to develop these skills and commit to your decisions as you learn more about the cloud. In this approach, the landing zones only focus on implementing the basic landing zones considerations required to start cloud adoption. As your adoption expands, modules in the Govern and Manage methodologies will build on top of your initial landing zones. The design principles of any Azure landing zone outline the specific design areas that will require refactoring over time.

## Implementation options

The following table describes some of the implementation options for landing zones and the variables that might drive your decision.

| Example deployment                                                                                                          	| Description                                                                                                                                                                                                                                                                                                                       	| GitHub repo                         	| Deploy to Azure                      	|
|-----------------------------------------------------------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------	|--------------------------------------	|
| Contoso AKS Landing Zone Accelerator                                                                                        	| Contoso AKS Landing Zone Accelerator represents the strategic design path and target technical state for an Azure Kubernetes Service (AKS) deployment. This solution provides an architectural approach and reference implementation to prepare landing zone subscriptions for a scalable Azure Kubernetes Service (AKS) cluster. 	| [Example in GitHub][GitHub-AKS]     	| [![DTA-Button-AKS]][DTA-AKS]         	|
| [Contoso Enterprise-scale Accelerator Landing Zone(https://github.com/Evilazaro/Enterprise-scale/blob/main/docs/reference/wingtip/README.md) 	| The suggested foundation for enterprise-scale adoption.                                                                                                                                                                                                                                                                           	| [Example in GitHub][GitHub-WingTip] 	| [![Dta-button-wingtip]][dta-wingtip] 	|

The following table looks at some of these implementation options from a slightly different perspective to guide more technical decision processes.

| Implementation option | Hub | Spoke | Deployment technology | Deployment instructions |
|---|---|---|---|---|
| [Cloud Adoption Framework enterprise-scale landing zone](../enterprise-scale/index.md) | Included | Included | Azure Resource Manager templates, Azure portal, Azure Policy and GitHub | [Deploy](../enterprise-scale/implementation.md) |
| [CAF Migration landing zone blueprint](./migrate-landing-zone.md) | Refactor required | Included | Azure Resource Manager templates, Azure portal, and Azure Blueprints | [Deploy](./migrate-landing-zone.md) |
| [CAF Terraform modules](./terraform-landing-zone.md) | Included in virtual datacenter module | Included | Terraform | [Deploy](./terraform-landing-zone.md#customize-and-deploy-your-first-landing-zone) |
| [Terraform module for Cloud Adoption Framework enterprise-scale](../enterprise-scale/terraform-module-caf-enterprise-scale.md)  | Excluded | Excluded | Terraform | [Deploy](https://registry.terraform.io/modules/Azure/caf-enterprise-scale/azurerm/latest) |

## Next steps

To proceed, choose one of the implementation options shown in the preceding tables. Each option includes a link to deployment instructions and the specific design principles that guide implementation.
