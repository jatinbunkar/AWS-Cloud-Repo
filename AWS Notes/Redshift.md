<!-- Jatin Bunkar Notes For Redshift --> 
## Redshift

### Redshift Simplified:
 Amazon Redshift is a fully managed, petabyte-scale data warehouse service in the cloud. The Amazon Redshift service manages all of the work of setting up, operating, and scaling a data warehouse. These tasks include provisioning capacity, monitoring and backing up the cluster, and applying patches and upgrades to the Amazon Redshift engine.

### Redshift Key Details:
-  An Amazon Redshift cluster is a set of nodes which consists of a leader node and one or more compute nodes. The type and number of compute nodes that you need depends on the size of your data, the number of queries you will execute, and the query execution performance that you need. 
- Redshift is used for business intelligence and pulls in very large and complex datasets to perform complex queries in order to gather insights from the data.
- It fits the use case of Online Analytical Processing (OLAP). Redshift is a powerful technology for data discovery including capabilities for almost limitless report viewing, complex analytical calculations, and predictive “what if” scenario (budget, forecast, etc.) planning.
- Depending on your data warehousing needs, you can start with a small, single-node cluster and easily scale up to a larger, multi-node cluster as your requirements change. You can add or remove compute nodes to the cluster without any interruption to the service. 
- If you intend to keep your cluster running for a year or longer, you can save money by reserving compute nodes for a one-year or three-year period.
- Snapshots are point-in-time backups of a cluster. These backups are enabled by default with a 1 day retention period. The maximum retention period is 35 days.
- Redshift can also asynchronously replicate your snapshots to a different region if desired.
- A Highly Available Redshift cluster would require 3 copies of your data. One copy would be live in Redshift and the others would be standby in S3.
- Redshift can have up to 128 compute nodes in a multi-node cluster. The leader node always manages client connections and relays queries to the compute nodes which store the actual data and perform the queries.
- Redshift is able to achieve efficiency despite the many parts and pieces in its architecture through using columnar compression of data stores that contain similar data. In addition, Redshift does not require indexes or materialized views which means it can be relatively smaller in size compared to an OLTP database containing the same amount of information. Finally, when loading data into a Redshift table, Redshift will automatically down sample the data and pick the most appropriate compression scheme.
- Redshift also comes with Massive Parallel Processing (MPP) in order to take advantage of all the nodes in your multi-node cluster. This is done by evenly distributing data and query load across all nodes. Because of this, scaling out still retains great performance.
- Redshift is encrypted in transit using SSL and is encrypted at rest using AES-256. By default, Redshift will manage all keys, but you can do so too via AWS CloudHSM or AWS KMS.
- Redshift is billed for:
  - Compute Node Hours (total hours your non-leader nodes spent querying for data)
  - Backups
  - Data transfer within a VPC (but not outside of it)
- Redshift is not multi-AZ, if you want multi-AZ you will need to spin up a separate cluster ingesting the same input. You can also manually restore snapshots to a new AZ in the event of an outage.
- When you provision an Amazon Redshift cluster, it is locked down by default so nobody has access to it. To grant other users inbound access to an Amazon Redshift cluster, you associate the cluster with a security group.
- Amazon Redshift provides free storage for snapshots that is equal to the storage capacity of your cluster until you delete the cluster. After you reach the free snapshot storage limit, you are charged for any additional storage at the normal rate. Because of this, you should evaluate how many days you need to keep automated snapshots and configure their retention period accordingly, and delete any manual snapshots that you no longer need. 
- Regardless of whether you enable automated snapshots, you can take a manual snapshot whenever you want. Amazon Redshift will never automatically delete a manual snapshot. Manual snapshots are retained even after you delete your Redshift cluster. Because manual snapshots accrue storage charges, it’s important that you manually delete them if you no longer need them

## Redshift Spectrum:
- Amazon Redshift Spectrum is used to run queries against exabytes of unstructured data in Amazon S3, with no loading or ETL required.
- Redshift Spectrum queries employ massive parallelism to execute very fast against large datasets. Much of the processing occurs in the Redshift Spectrum layer, and most of the data remains in Amazon S3.
- Redshift Spectrum queries use much less of your cluster's processing capacity than other queries.
- The cluster and the data files in Amazon S3 must be in the same AWS Region.
- External S3 tables are read-only. You can't perform insert, update, or delete operations on external tables. 

## Redshift Enhanced VPC Routing:
- When you use Amazon Redshift Enhanced VPC Routing, Redshift forces all traffic (such as COPY and UNLOAD traffic) between your cluster and your data repositories through your Amazon VPC. 
- If Enhanced VPC Routing is not enabled, Amazon Redshift routes traffic through the Internet, including traffic to other services within the AWS network.
- By using Enhanced VPC Routing, you can use standard VPC features, such as VPC security groups, network access control lists (ACLs), VPC endpoints, VPC endpoint policies, internet gateways, and Domain Name System (DNS) servers.
