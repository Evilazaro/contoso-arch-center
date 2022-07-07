---
layout: page
title: Enterprise Scale Landing Zone 
permalink: /es-lz/
---

# Contoso Enterprise-scale Accelerator Landing Zone 

The Enterprise-scale architecture provides prescriptive guidance coupled with Azure best practices, and it follows design principles across the critical design areas for organizations to define their Azure architecture. It will continue to evolve alongside the Azure platform and is ultimately defined by the various design decisions that organizations must make to define their Azure journey.

The Enterprise-scale architecture is modular by design and allows organizations to start with foundational landing zones that support their application portfolios, and the architecture enables organizations to start as small as needed and scale alongside their business requirements regardless of scale point.

![hippo]({{ site.baseurl }}/assets/img/media/ESLZ.gif)

---

_The Enterprise-scale architecture represents the strategic design path and target technical state for your Azure environment._

---

Not all enterprises adopt Azure in the same way, so the Enterprise-scale architecture may vary between customers. Ultimately, the technical considerations and design recommendations of the Enterprise-scale architecture may lead to different trade-offs based on the customer's scenario. Some variation is expected, but if core recommendations are followed, the resulting target architecture will put the customer on a path to sustainable scale.

The Enterprise-scale reference implementations in this repository are intended to support Enterprise-scale Azure adoption and provides prescriptive guidance based on authoritative design for the Azure platform as a whole.

| Key customer landing zone requirement | Enterprise-scale reference implementations |
|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Timelines to reach security and compliance requirements for a workload | Enabling all recommendations during setup, will ensure resources are compliant from a monitoring and security perspective |
| Provides a baseline architecture using multi-subscription design | Yes, for the entire Azure tenant regardless of customer’s scale-point |
| Best-practices from cloud provider | Yes, proven and validated with customers |
| Be aligned with cloud provider’s platform roadmap | Yes |
| UI Experience and simplified setup | Yes, Azure portal |
| All critical services are present and properly configured according to recommend best practices for identity & access management, governance, security, network and logging | Yes, using a multi-subscription design, aligned with Azure platform roadmap |
| Automation capabilities (IaC/DevOps) | Yes: ARM, Policy, GitHub/Azure DevOps CICD pipeline option included |
| Provides long-term self-sufficiency | Yes, enterprise-scale architecture -> 1:N landing zones. Approach & architecture prepare the customer for long-term self-sufficiency, the RIs are there to get you started |
| Enables migration velocity across the organization | Yes, enterprise-scale architecture -> 1:N landing zones, Architecture includes designs for segmentation and separation of duty to empower teams to act within appropriate landing zones |
| Achieves operational excellence | Yes. Enables autonomy for platform and application teams with a policy driven governance and management |

## Conditions for success

To fully leverage this reference implementation in this repository, readers must have a collaborative engagement with key customer stakeholders across critical technical domains, such as identity, security, and networking. Ultimately, the success of cloud adoption hinges on cross-discipline cooperation within the organization, since key requisite Enterprise-scale design decisions are cross cutting, and to be authoritative must involve domain Subject Matter Expertise (SME) and stakeholders within the customer. 

## Deployment Model

The Enterprise-scale architecture is modular by design and allows customers to start with foundational Landing Zones that support their application portfolios, regardless of whether the applications are being migrated or are newly developed and deployed to Azure. The architecture can scale alongside the customer's business requirements regardless of scale point. In this repository we are providing the following four templates representing different scenarios composed using ARM templates.

| Example deployment                                                                                	| Description                                             	| GitHub repo                   	| Deploy to Azure                      	|
|---------------------------------------------------------------------------------------------------	|---------------------------------------------------------	|-------------------------------	|--------------------------------------	|
| Contoso Enterprise-scale Accelerator Landing Zone 	| The suggested foundation for enterprise-scale adoption. 	| [GitHub Repo][GitHub-WingTip] 	| [![Dta-button-wingtip]][dta-wingtip] 	|

<!-- The following section is used to store references to external images and links to reduce maintenance overhead and enable tooltips -->

[/]: # (*******************************)
[/]: # (External image references below)
[/]: # (*******************************)

[DTA-Button-WingTip]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy WingTip reference implementation (foundation) to Azure."
[DTA-Button-AdventureWorks]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy AdventureWorks reference implementation (hybrid connectivity with hub and spoke) to Azure."
[DTA-Button-Contoso]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy Contoso reference implementation (hybrid connectivity with virtual wan) to Azure."
[DTA-Button-TreyResearch]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy TreyResearch reference implementation for small organizations to Azure."
[DTA-Button-AzureGov]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy Enterprise-scale reference implementation for Azure Government."
[DTA-Button-AKS]: https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true "Deploy AKS Landing Zone  reference implementation for Azure."

[/]: # (**************************)
[/]: # (External link labels below)
[/]: # (**************************)

[GitHub-WingTip]: https://github.com/evilazaro/Enterprise-scale/blob/main/docs/reference/wingtip/README.md
[GitHub-AdventureWorks]: https://github.com/evilazaro/Enterprise-scale/blob/main/docs/reference/adventureworks/README.md
[GitHub-Contoso]: https://github.com/evilazaro/Enterprise-scale/blob/main/docs/reference/contoso/Readme.md
[GitHub-TreyResearch]: https://github.com/evilazaro/Enterprise-scale/blob/main/docs/reference/treyresearch/README.md
[Github-AzureGov]: https://aka.ms/enterprisescale
[Github-AKS]: https://github.com/evilazaro/Aks-Construction

[DTA-WingTip]: https://portal.azure.com/#blade/Microsoft_Azure_CreateUIDef/CustomDeploymentBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2FeslzArm.json/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2Feslz-portal.json
[DTA-AdventureWorks]: https://portal.azure.com/#blade/Microsoft_Azure_CreateUIDef/CustomDeploymentBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2FeslzArm.json/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2Feslz-portal.json
[DTA-Contoso]: https://portal.azure.com/#blade/Microsoft_Azure_CreateUIDef/CustomDeploymentBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2FeslzArm.json/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2Feslz-portal.json
[DTA-TreyResearch]: https://portal.azure.com/#blade/Microsoft_Azure_CreateUIDef/CustomDeploymentBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2Fdocs%2Freference%2Ftreyresearch%2FarmTemplates%2Fes-lite.json/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2Fdocs%2Freference%2Ftreyresearch%2FarmTemplates%2Fes-portal.json
[DTA-AzureGov]: https://portal.azure.us/#blade/Microsoft_Azure_CreateUIDef/CustomDeploymentBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2FeslzArm.json/uiFormDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FEnterprise-scale%2Fmain%2FeslzArm%2Feslz-portal.json
[DTA-AKS]: https://evilazaro.github.io/AKS-Construction/

