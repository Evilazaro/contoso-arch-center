---
layout: page
title: Bicep Accelerator 
permalink: /bicep-accelerator/
---

# AKS Bicep Accelerator

Building Kubernetes clusters can be hard work! The AKS Bicep Accelerator focuses on expediting customers onboarding of Azure Kubernetes Service workloads using best practices and a flexible templating approach to suit differing requirements.

This project unifies guidance provided by the [AKS Secure Baseline](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/secure-baseline-aks), [Well Architected Framework](https://docs.microsoft.com/en-us/azure/architecture/framework/), [Cloud Adoption Framework](https://azure.microsoft.com/en-gb/cloud-adoption-framework/) and [Enterprise-scale](https://github.com/Evilazaro/Enterprise-scale) by providing tangible artifacts to deploy Azure resources from CLI or CI/CD systems.

The AKS Bicep Accelerator is part of the official [Contoso AKS Landing Zone Accelerator (Enterprise Scale)](https://github.com/Evilazaro/kaas-lz) architectural approach. To read more about this project and how the AKS Bicep Accelerator fits with Enterprise Scale and the AKS Secure Baseline, look [here](referencearchs.md).

## The 3 Components

This projects focus is split equally over 3 areas, configuration, modular templating and CI implementation.

![project component areas]({{ site.baseurl }}/assets/img/media/images/AKSBicepComponents.png)

### Wizard experience

To help guide your AKS configuration, use the [Deployment Helper](https://evilazaro.github.io/AKS-Construction/), which will provide a set of parameters and scripts to make deployment simple. It uses several preset configurations to guide configuration decisions.
The deployment helper provides links to the official Microsoft documentation to help provide additional context for each feature.

[![preview screenshot of the helper wizard]({{ site.baseurl }}/assets/img/media/images/helper_preview_es.png)](https://evilazaro.github.io/AKS-Construction/)

### IaC - Bicep code files

IaC (Infrastructure as Code) code files have been modularised into their component areas. [Main.bicep](bicep/main.bicep) references them and they are expected to be present in the same directory. The Deployment Helper leverages an Arm json compiled version of all the bicep files.

Releases are used to version the bicep code files, they can be leveraged directly for use in your project or you can opt to Fork the repo if you prefer.

### DevOps - GitHub Actions

A number of [GitHub actions](https://github.com/evilazaro/AKS-Construction/tree/main/.github/workflows) are used in the repo that run on push/pr/schedules. These can be copied into your own repo and customised for your CI/CD pipeline. A robust deployment pipeline is essential when coordinating the deployment of multiple Azure services that work together, additionally there is configuration that cannot be set in the template and that needs to be automated (and tested) consistently.
![preview screenshot of the helper wizard]({{ site.baseurl }}/assets/img/media/images/ghactionworkflow.jpg)

CI Name | Actions Workflow | Parameter file | CI Status | Notes
|--------|--------|--------|-----------|------|
| Starter cluster | [StandardCI.yml](https://github.com/evilazaro/AKS-Construction/blob/main/.github/workflows/StandardCI.yml) | [ESLZ Sandbox](.github/workflows_dep/AksDeploy-Basic.parameters.json) | [![AksStandardCI](https://github.com/evilazaro/AKS-Construction/actions/workflows/StandardCI.yml/badge.svg)](https://github.com/evilazaro/AKS-Construction/actions/workflows/StandardCI.yml) | A simple deployment example, good for first time users of this project to start with  |
| BYO Vnet | [ByoVnetCI.yml](https://github.com/evilazaro/AKS-Construction/blob/main/.github/workflows/ByoVnetCI.yml) | [ESLZ Byo peered vnet](.github/workflows_dep/AksDeploy-ByoVnet.parameters.json) | [![ByoVnetCI](https://github.com/evilazaro/AKS-Construction/actions/workflows/ByoVnetCI.yml/badge.svg?branch=main)](https://github.com/evilazaro/AKS-Construction/actions/workflows/ByoVnetCI.yml) | Comprehensive IaC flow deploying multiple smoke-test apps |
| Private cluster | [ByoVnetPrivateCI.yml](https://github.com/Evilazaro/Aks-Construction/blob/main/.github/workflows/ByoVnetPrivateCI.yml) | [ESLZ Byo private vnet](.github/workflows_dep/AksDeploy-ByoVnetPrivate.parameters.json) | [![ByoVNetPrivateCI](https://github.com/Evilazaro/Aks-Construction/actions/workflows/ByoVnetPrivateCI.yml/badge.svg)](https://github.com/evilazaro/AKS-Construction/actions/workflows/ByoVnetPrivateCI.yml)| A private AKS cluster that deploys a vnet with private link services. |

For a more in depth look at the GitHub Actions used in this project, which steps are performed and the different CI practices they demonstrate, please refer to [this page](docs/GhActions.md).

## Getting Started

### Basic

If this is the first time you're using the project, follow these steps.

1. Use the [Deployment Helper](https://evilazaro.github.io/AKS-Construction/) to guide your AKS configuration.
1. Run the commands in the *Provision Environment* tab to create your AKS Environment in your Azure subscription
1. Run the commands in the *Post Configuration* tab to complete your implementation
1. [Connect to your AKS Cluster](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough#connect-to-the-cluster), and deploy your applications as you see fit.

### Mature

If you're looking to use this project as part of your deployments, follow these steps.

1. Use the [Deployment Helper](https://evilazaro.github.io/AKS-Construction/) to guide your AKS configuration.
1. Capture the parameters on the *Template Parameters File* tab to a file - this is your configuration
1. Check the *Post Configuration* tab for any commands and save them to a file
1. Grab the [latest release](https://github.com/evilazaro/AKS-Construction/releases) of the bicep code
1. (optionally) Author an Application Main bicep to represent *your application* (see [here](https://github.com/evilazaro/AKS-Construction/blob/main/samples/SampleAppMain.bicep) for an example)
1. In your CI/CD system, either using one of the GitHub Action Workflow files as a base, or by coding it yourself - initiate a deployment of the bicep code, using your parameter file
1. In your CI/CD system, deploy your application(s) to the AKS cluster

## Project Principals

The guiding principal we have with this project is to focus on the the *downstream use* of the project (see [releases](https://github.com/evilazaro/AKS-Construction/releases)). As such, these are our specific practices.

1. Deploy all components through a single, modular, idempotent bicep template Converge on a single bicep template, which can easily be consumed as a module
2. Provide best-practice defaults, then use parameters for different environment deployments
3. Minimise "manual" steps for ease of automation
4. Maintain quality through validation & CI/CD pipelines that also serve as working samples/docs
5. Focus on AKS and supporting services, linking to other repos to solve; Demo apps / Developer workstations / Jumpboxes / CI Build Agents / Certificate Authorities