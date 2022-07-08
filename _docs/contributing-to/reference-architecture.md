### Title  - State the scenario

> Example: "Connect an on-premises network to Azure using ExpressRoute"

After the title, there is an introductory section, consisting of:

#### Intro paragraph

A short paragraph that describes the scenario and the solution that is deployed. This should be very concise, so that the diagram (next item) appears close to the top of the page.

Example:

> This reference architecture shows a set of proven practices for running multiple Linux virtual machines (VMs) behind a load balancer, to improve availability and scalability. This architecture can be used for any stateless workload, such as a web server, and is a foundation for deploying n-tier applications.

#### Architecture diagram

 The diagram shows the Azure resources that get deployed. The level of detail will depend on the scenario.

> Example: For an IaaS deployment, the diagram _should_ include the network topology (VNet, subnets, gateways, public IP addresses), VMs or VM scale sets, plus load balancers, Traffic Manager, and App Gateway, as appropriate. It _might_ include other elements such as NICs, storage accounts, or VHDs, but only if the document contains specific guidance related to those elements. For example, if some VMs need multiple NICs, include those in the diagram. Otherwise, it can be assumed that each VM has a NIC.

### Section: Architecture

This section is a bullet list that describes the elements in the diagram. In most cases, there should be a 1:1 correspondence. Everything in the diagram should be described here, and vice versa.

For each element, describe its purpose within the context of the overall solution.

- **Weak:** "A subnet is a way to segment a VNet into multiple address spaces." **← This is just a description of subnets.**

- **Better:** "Put each application tier into a separate subnet."  **← This is specific to the scenario.**

It's OK to do both, describing _what_ something is and _why_ it's there. But avoid repeating a lot of information that is already in the product documentation for that service/feature. Instead, link to the product documentation.

### Section: Recommendations

This section describes in more detail a set of recommendations for the elements listed in the previous section. This is the place for the gory details, gotchas, and detailed explanations of things.

This section can have subheadings (H3) to organize the recommendations. e.g., "VM recommendations", "SQL Server recommendations", "Networking recommendations"

Examples of recommendations:

> - For each tier, put two or more VMs in an availability set.
> - Create a separate storage account for diagnostic logs.
> - For SQL Server high availability, we recommend using Always On Availability Groups.

As much as possible, provide the justification or rationale for each recommendation. Examples:

> - Put two or more VMs in an availability set. This makes the VMs eligible for a higher SLA.
> - Create a separate storage account for diagnostic logs to avoid hitting IOPS limits.

Recommendations should be definite when possible.

- **Weak:** To restrict traffic between the subnets, you can create network security groups. **← Are we recommending this or not?**

- **Better:** Use an NSG to isolate the data tier. The data tier should only accept network traffic from the middle tier. **← Concrete and actionable**

In practice, sometimes you'll need a qualifier like "depending on your workload..."

### Considerations (pillars or "-ilities")

These are four sections (H2) that describe non-functional characteristics of the architecture.

- Scalability
- Availability
- Manageability
- Security

These correspond to 4 of our 5 [pillars of software quality](https://docs.microsoft.com/azure/architecture/guide/pillars).

Only include the sections that are relevant for the reference architecture. In some cases, there won't be anything to say for a particular pillar, especially if a reference architecture builds on a previous reference architecture, as part of a series.

These sections may include whatever discussion points are relevant for that pillar, with respect to the architecture that's being described. Including:

- What the architecture gives you.

  >"Scale out by adding more VMs to the load balancer pool." (Scalability) **← A capability that this architecture gives you.**

- What the architecture does not give you. When possible, point to a possible alternative.

  > "If you need higher availability, replicate the application across two regions and use Traffic Manager for failover." (Availability) **← What this architecture does _not_ give you (availability during a regional outage), along with a pointer to something actionable.**

- Things to keep in mind in order to achieve the pillar, when using this architecture. This might include app dev or operational considerations.

  > "If your VMs run an HTTP server, create an HTTP health probe. Otherwise, create a TCP health probe." (Availability) **← A best practice that depends on the specific application workload**

  > "The web front end should be stateless, to avoid the need to maintain client affinity." (Scalability) **← An app dev consideration.**

- Additional options to consider, which may not be part of the golden path.

  > "If you need additional throughput, consider creating additional Event Hubs and sharding the messages." (Scalability) **← Advanced option, not shown in the reference architecture.**

### Section: Deploy the solution

If there is a deployable asset (Azure Resoure Manager template or script), include instructions for how to deploy.