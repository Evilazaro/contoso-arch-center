# Checklist for architecting and building multitenant solutions on Azure

When you build your multitenant solution in Azure, there are many elements that you need to consider. Use this checklist as a starting point to help you design and build your multitenant solution. This checklist is a companion resource to the [Architecting multitenant solutions on Azure](./overview/) series of articles. The checklist is structured around the business and technical considerations, and the five pillars of the [Azure Well-Architected Framework](/azure/architecture/framework).

## Business considerations

* Understand what kind of solution you're creating, such as business-to-business (B2B), business-to-consumer (B2C), or your enterprise software, and [how tenants are different from users](./overview/).
* [Define your tenants](./considerations/tenancy-models/#define-a-tenant). Understand how many tenants you'll support initially, and your growth plans.
* [Define your pricing model](./considerations/pricing-models/) and ensure it aligns with your [tenants’ consumption of Azure resources](./considerations/measure-consumption/).
* Understand whether you need to separate your tenants into different [tiers](./considerations/pricing-models/#feature--and-service-level-based-pricing). Tiers might have different pricing, features, performance promises, geographic locations, and so forth.
* Based on your customers’ requirements, decide on the [tenancy models](./considerations/tenancy-models/) that are appropriate for various parts of your solution.
* When you're ready, sell your B2B multitenant solution using the [Microsoft Commercial Marketplace](/azure/marketplace/plan-saas-offer).

## Reliability considerations

* Review the [Azure Well-Architected Reliability checklist](/azure/architecture/framework/resiliency/design-checklist), which is applicable to all workloads.
* Understand the [Noisy Neighbor antipattern](../../antipatterns/noisy-neighbor/noisy-neighbor/). Prevent individual tenants from impacting the system's availability for other tenants.
* [Design your multitenant solution](./approaches/overview/) for the level of growth that you expect. But don't overengineer for unrealistic growth.
* Define service-level objectives (SLOs) and optionally [service-level agreements (SLAs)](/learn/modules/choose-azure-services-sla-lifecycle/2-what-are-service-level-agreements) for your solution. SLAs and SLOs should be based on the requirements of your tenants, as well as the [composite SLA of the Azure resources in your architecture](/azure/architecture/framework/resiliency/business-metrics).
* Test the [scale](./approaches/compute/#scale) of your solution. Ensure that it performs well under all levels of load, and that it scales correctly as the number of tenants increases.
* Apply [chaos engineering principles](./approaches/compute/#isolation) to test the reliability of your solution.

## Security considerations

* Apply the [Zero Trust](/security/zero-trust) and least privilege principles in all layers of your solution.
* Ensure that you can [correctly map user requests](./considerations//map-requests/) to tenants. Consider including the tenant context as part of the identity system, or by using another means, like application-level tenant authorization.
* Design for [tenant isolation](./considerations/tenancy-models/#tenant-isolation). Continuously [test your isolation model](./approaches/compute/#isolation).
* Ensure that your application code prevents any cross-tenant access or data leakage.
* Perform ongoing penetration testing and security code reviews.
* Understand your tenants' [compliance requirements](./approaches/governance-compliance/), including data residency and any compliance or regulatory standards that they require you to meet.
* Correctly [manage domain names](./considerations/domain-names/) and avoid vulnerabilities like [dangling DNS and subdomain takeover attacks](./considerations/domain-names/#dangling-dns-and-subdomain-takeover-attacks).
* Follow [service-specific guidance](./service/overview/) for multitenancy.

## Cost Optimization considerations

* Review the [Azure Well-Architected Cost Optimization checklist](/azure/architecture/framework/cost/design-checklist), which is applicable to all workloads.
* Ensure you can adequately [measure per-tenant consumption](./considerations/measure-consumption/) and correlate it with [your infrastructure costs](./approaches/cost-management-allocation/).
* Avoid [antipatterns](./approaches/cost-management-allocation/#antipatterns-to-avoid). Antipatterns include failing to track costs, tracking costs with unnecessary precision, real-time measurement, and using monitoring tools for billing.

## Operational Excellence considerations

* Review the [Azure Well-Architected Operational Excellence checklist](../../checklist/data-ops/), which is applicable to all workloads.
* Use automation to manage the [tenant lifecycle](./considerations/tenant-lifecycle/), such as onboarding, [deployment, provisioning, and configuration](./approaches/deployment-configuration/).
* Find the right balance for [deploying service updates](./considerations/updates/). Consider both your tenants' requirements and your own operational requirements.
* Monitor the health of the overall system, as well as each tenant.
* Configure and test alerts to notify you when specific tenants are experiencing issues or are exceeding their consumption limits.
* [Organize your Azure resources](./approaches/resource-organization/) for isolation and scale.
* Avoid [deployment and configuration antipatterns](./approaches/deployment-configuration/#antipatterns-to-avoid). Antipatterns include running separate versions of the solution for each tenant, hardcoding tenant-specific configurations or logic, and manual deployments.

## Performance Efficiency considerations

* Review the [Azure Well-Architected Performance Efficiency checklist](/azure/architecture/framework/scalability/performance-efficiency), which is applicable to all workloads.
* If you use shared infrastructure, plan for how you'll mitigate [Noisy Neighbor](../../antipatterns/noisy-neighbor/noisy-neighbor/) concerns. Ensure that one tenant can't reduce the performance of the system for other tenants.
* Determine how you'll scale your [compute](./approaches/compute/), [storage](./approaches/storage-data/), [networking](./approaches/networking/), and other Azure resources to match the demands of your tenants.
* Consider each Azure resource's scale limits. [Organize your resources](./approaches/resource-organization/) appropriately, in order to avoid [resource organization antipatterns](./approaches/resource-organization/#antipatterns-to-avoid). For example, don't over-architect your solution to work within unrealistic scale requirements.

## Next steps

* Review [architectural considerations for multitenant solutions](./considerations/overview/).
* Review [architectural approaches for multitenancy](./approaches/overview/).
* Review [service-specific guidance for multitenancy](./service/overview/).
* Review additional [resources for architects and developers of multitenant solutions](related-resources/).