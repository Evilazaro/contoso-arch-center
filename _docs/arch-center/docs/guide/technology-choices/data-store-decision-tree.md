
# Select an Azure data store for your application

Azure offers a number of managed data storage solutions, each providing different features and capabilities. This article will help you to choose a managed data store for your application.

If your application consists of multiple workloads, evaluate each workload separately. A complete solution may incorporate multiple data stores.

## Select a candidate

Use the following flowchart to select a candidate Azure managed data store.

![Data store decision tree](./images/data-store-decision-tree.svg)

The output from this flowchart is a **starting point** for consideration. Next, perform a more detailed evaluation of the data store to see if it meets your needs. Refer to [Criteria for choosing a data store](./data-store-considerations/) to aid in this evaluation.

## Choose specialized storage

Alternative database solutions often require specific storage solutions. For example, SAP HANA on VMs often employs Azure NetApp Files as its underlying storage solution. Evaluate your vendor's requirements to find an appropriate storage solution to meet your database's requirements. For more information about selecting a storage solution, see [Review your storage options](/azure/cloud-adoption-framework/ready/considerations/storage-options).