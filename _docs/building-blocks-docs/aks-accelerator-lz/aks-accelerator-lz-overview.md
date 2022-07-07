---
layout: page
title: AKS Accelerator Landing Zone 
permalink: /aks-accelerator-lz-overview/
---

# Contoso AKS Landing Zone Accelerator

Contoso Landing Zone Accelerators are an architectural approach and a reference implementation that enables effective construction and operationalization of landing zones on Azure, at scale. This approach aligns with the Azure roadmap and the Cloud Adoption Framework for Azure.

Contoso AKS Landing Zone Accelerator represents the strategic design path and target technical state for an Azure Kubernetes Service (AKS) deployment. This solution provides an architectural approach and reference implementation to prepare landing zone subscriptions for a scalable Azure Kubernetes Service (AKS) cluster. 

Below is a picture of what a golden state looks like and open source software like flux and traefik integrate well within the AKS ecosystem.

![Golden state platform foundation with AKS landingzone highlighted in red]({{ site.baseurl }}/assets/img/media/aks-eslz-architecture.png)

---

## Deployment Model

The reference implementations are spread across three repos that all build on top of the [AKS Secure Baseline](https://docs.microsoft.com/azure/architecture/reference-architectures/containers/aks/secure-baseline-aks) and Contoso Landing Zones.

| Example deployment                                                                                                       	| Description                                                                                                                                                                                                                                                                                                                       	| GitHub repo               	| Deploy to Azure              	|
|--------------------------------------------------------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|---------------------------	|------------------------------	|
| Contoso AKS Accelerator Landing Zone 	| Contoso AKS Landing Zone Accelerator represents the strategic design path and target technical state for an Azure Kubernetes Service (AKS) deployment. This solution provides an architectural approach and reference implementation to prepare landing zone subscriptions for a scalable Azure Kubernetes Service (AKS) cluster. 	| [GitHub Repo][GitHub-AKS] 	| [![DTA-Button-AKS]][DTA-AKS] 	|

### This repo

In this repo, you get access to step by step guide covering various customer [scenarios](./Scenarios) that can help accelerate the development and deployment of AKS clusters that conform with Contoso AKS Landing Zone Accelerator best practices and guidelines. This is a good starting point if you are **new** to AKS or IaC. Each scenario aims to represent common customer experiences with the goal of accelerating the process of developing and deploying conforming AKS clusters using Infrastructure-As-Code (IaC). They also provide a step by step learning experience for deploying AKS in an actual Enterprise environment. Most scenarios will eventually have a **Terraform** and **Bicep** version. 

Use [this repo](https://github.com/Evilazaro/AKS-Landing-Zone-Accelerator/tree/main/Scenarios/AKS-Secure-Baseline-PrivateCluster) if you would like step by step guidance on how to deploy secure and well architected AKS clusters using our scenario based model and/or you are new to AKS or IaC. This model promotes a separation of duties, modularized IaC so you can pick and choose components you want to build with your cluster and has implementations in ARM, Terraform and Bicep. It is the best starting point for people new to Azure or AKS.

### Bicep AKS Accelerator

A flexible templating approach using Bicep that enables multiple scenarios using a Web based tool. It provides tangible artifacts to **quickly** enable AKS deployments through CLI or in your CI/CD pipeline.

Driving the configuration experience is a [wizard](https://evilazaro.github.io/Aks-Construction/?default=es) to guide your decision making, it provides presets for the main Contoso Landing Zone deployment modes (Sandbox, Corp & Online). The output of this wizard experience are the parameters and CLI commands to immediately deploy using our maintained Bicep template to deploy your customized AKS environment in one step.

Use [this repo](https://github.com/Evilazaro/Aks-Construction) if you would like to use a guided experience to rapidly create your environment with a maintained Bicep template based on the architecture of the AKS Secure Baseline.

### Baseline Automation Module

This reference implementation demonstrates recommended ways to automate the deployment of the components composing a typical AKS solution. This repository includes information about separation of duties (different teams managing different parts of the deployment process), CI/CD and GitOps best practices. 

Use [this repo](https://github.com/Evilazaro/aks-baseline-automation) if you would like to learn how to quickly setup and get access to templates to help setup your own DevOps environments for AKS workloads. 

## Next Steps to implement Contoso AKS Landing Zone Accelerator

### Leverage one of the Landing Zone Accelerator implementations from our other repos

 [Bicep AKS Accelerator](https://github.com/Evilazaro/Aks-Construction#getting-started)

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


