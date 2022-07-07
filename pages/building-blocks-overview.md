---
layout: page
title: Building Blocks Overview
permalink: /building-blocks-overview/
---

# What is an Building Block?

A Building Block is an environment for hosting your workloads, preprovisioned through code. Watch the following video to learn more.

Building Blocks are the output of a multisubscription Azure environment that accounts for scale, security governance, networking, and identity. Building Blocks **enable application migration, modernization, and innovation at enterprise-scale in Azure**. These building blocks consider all platform resources that are required to support the customer's application portfolio and don't differentiate between infrastructure as a service or platform as a service.

![Diagram that shows a Building Block design.](../assets/img/media/lz-design.png)

## Scalable and modular

No single solution fits all technical environments. A few Building Block implementation options can help you meet the deployment and operations needs of your growing cloud portfolio.

- **Scalable:** All Building Blocks support cloud adoption at scale by providing repeatable environments, with consistent configuration and controls, regardless of the workloads or Azure resources deployed to each Building Block instance.
- **Modular:** All Building Blocks provide a modular approach to building out your environment, based on a common set of design areas. Each design area can be easily extended to support the distinct needs of various technology platforms like Azure SQL Database, Azure Kubernetes Service, and Azure Virtual Desktop.

Whether you're looking to deploy your first production application to Azure or you're operating a complex portfolio of tech platforms and workloads, the Building Block implementation options can be tailored to your needs.

## Building Block conceptual architecture

For many organizations, the Building Block conceptual architecture below represents the destination in their cloud adoption journey. It's a mature, scaled-out target architecture intended to help organizations operate successful cloud environments that drive their business while maintaining best practices for security and governance.

This conceptual architecture represents scale and maturity decisions based on a wealth of lessons learned and feedback from customers who have adopted Azure as part of their digital estate.

While your specific implementation might vary, as a result of specific business decisions or existing investments in tools that need to persist in your cloud environment, this conceptual architecture will help set a direction for the overall approach your organization takes to designing and implementing a Building Block.

![Diagram that shows a Building Block design.](../_docs/caf-ready/enterprise-scale/media/

Use this architecture as a starting point. Download the [Visio file](../assets/files/enterprise-scale-architecture.vsdx) and modify it to fit your specific business and technical requirements when planning your Building Block implementation.

## Building Block accelerators

The accelerator is an Azure-portal-based deployment that will provide a full implementation of the conceptual architecture, along with opinionated configurations for key components such as management groups and policies.

Find below the main Contoso Building Blocks Accelerators

## Implementation options

The following table describes some of the implementation options for landing zones and the variables that might drive your decision.

| Implementation option                                                                                      | Description                                                                                                                                                               | Deployment velocity | Deeper design principles                                         | Deployment instructions                                                                               |   |
|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|---|
| ---                                                                                                        | ---                                                                                                                                                                       | ---                 | ---                                                              | ---                                                                                                   |   |
| [CAF Migration landing zone blueprint](./migrate-landing-zone.md)                                          | Deploys the basic foundation for migrating low risk assets.                                                                                                               | Start small         | [Design principles](./migrate-landing-zone.md#design-principles) | [Deploy](./migrate-landing-zone.md)                                                                   |   |
| [CAF Foundation blueprint](./foundation-blueprint.md)                                                      | Adds the minimum tools need to begin developing a governance strategy.                                                                                                    | Start small         | [Design principles](./foundation-blueprint.md#design-principles) | [Deploy](./foundation-blueprint.md)                                                                   |   |
| [CAF enterprise-scale landing zone (hybrid connectivity with Virtual WAN)](../enterprise-scale/index.md)   | Deploys an enterprise-ready platform foundation with all the necessary shared services to support the full IT portfolio, including hybrid connectivity (Virtual WAN).     | Enterprise-scale    | [Design principles](../enterprise-scale/design-principles.md)    | [Deploy](https://github.com/Azure/Enterprise-Scale/blob/main/docs/reference/contoso/Readme.md)        |   |
| [CAF enterprise-scale landing zone (hybrid connectivity with hub and spoke)](../enterprise-scale/index.md) | Deploys an enterprise-ready platform foundation with all the necessary shared services to support the full IT portfolio, including hybrid connectivity (hub and spoke).   | Enterprise-scale    | [Design principles](../enterprise-scale/design-principles.md)    | [Deploy](https://github.com/Azure/Enterprise-Scale/blob/main/docs/reference/adventureworks/README.md) |   |
| [CAF enterprise-scale landing zone (foundation)](../enterprise-scale/index.md)                             | Deploys an enterprise-ready platform foundation with all the necessary shared services to support the full IT portfolio, where connectivity can be added later as needed. | Enterprise-scale    | [Design principles](../enterprise-scale/design-principles.md)    | [Deploy](https://github.com/Azure/Enterprise-Scale/blob/main/docs/reference/wingtip/README.md)        |   |

The following table looks at some of these implementation options from a slightly different perspective to guide more technical decision processes.

| Implementation option                                                                  | Hub               | Spoke    | Deployment technology                                                   | Deployment instructions                         |   |
|----------------------------------------------------------------------------------------|-------------------|----------|-------------------------------------------------------------------------|-------------------------------------------------|---|
| ---                                                                                    | ---               | ---      | ---                                                                     | ---                                             |   |
| [Cloud Adoption Framework enterprise-scale landing zone](../enterprise-scale/index.md) | Included          | Included | Azure Resource Manager templates, Azure portal, Azure Policy and GitHub | [Deploy](../enterprise-scale/implementation.md) |   |
| [CAF Migration landing zone blueprint](./migrate-landing-zone.md)                      | Refactor required | Included | Azure Resource Manager templates, Azure portal, and Azure Blueprints    | [Deploy](./migrate-landing-zone.md)             |   |

There are other deployment options available, some that deliver the full architecture using third-party deployment technologies, and others that start from a smaller footprint. For more information, see [Implementation options](./implementation-options.md).

# Welcome to the Building Blocks

[AKS Landing Zone Accelerator](../_docs/building-blocks-docs/aks-accelerator-lz/aks-accelerator-lz-overview.md)
