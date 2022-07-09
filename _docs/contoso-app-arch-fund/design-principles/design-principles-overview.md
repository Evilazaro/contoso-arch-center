---
layout: page
title: Design Principles Overview
permalink: /design-principles-overview/
---
# Ten design principles for Azure applications

Follow these design principles to make your application more scalable, resilient, and manageable.

{% include doc.html name="Design for self healing" path="self-healing" %}. In a distributed system, failures happen. Design your application to be self healing when failures occur.

{% include doc.html name="Make all things redundant" path="redundancy" %}. Build redundancy into your application, to avoid having single points of failure.

{% include doc.html name="Minimize coordination" path="minimize-coordination-content" %}. Minimize coordination between application services to achieve scalability.

{% include doc.html name="Design to scale out" path="scale-out" %}. Design your application so that it can scale horizontally, adding or removing new instances as demand requires.

{% include doc.html name="Partition around limits" path="partition" %}. Use partitioning to work around database, network, and compute limits.

{% include doc.html name="Design for operations" path="design-for-operations" %}. Design your application so that the operations team has the tools they need.

{% include doc.html name="Use managed services" path="managed-services" %}. When possible, use platform as a service (PaaS) rather than infrastructure as a service (IaaS).

{% include doc.html name="Use the best data store for the job" path="use-best-data-store" %}. Pick the storage technology that is the best fit for your data and how it will be used.

{% include doc.html name="Design for evolution" path="design-for-evolution" %}. All successful applications change over time. An evolutionary design is key for continuous innovation.

{% include doc.html name="Build for the needs of business" path="build-for-business" %}. Every design decision must be justified by a business requirement.