| **AWS Service** | **Primary Use Case** | **When to use** |
| --- | --- | --- |
| Amazon Athena | Query | Run interactive queries against data directly in Amazon S3 without worrying about formatting data or managing infrastructure. Can use with other services such as Amazon RedShift |
| Amazon RedShift | Data Warehouse | Pull data from many sources, format and organize it, store it, and support complex, high speed queries that produce business reports. |
| Amazon EMR | Data Processing | Highly distributed processing frameworks such as Hadoop, Spark, and Presto. Run a wide variety of scale-out data processing tasks for applications such as machine learning, graph analytics, data transformation, streaming data. |
| AWS Glue | ETL Service | Transform and move data to various destinations. Used to prepare and load data for analytics. Data source can be S3, RedShift or another database. Glue Data Catalog can be queried by Athena, EMR and RedShift Spectrum |

Kinesis Data Streams **stores data** for later processing by applications (key difference with Firehose which delivers data directly to AWS services).

**SQS vs SNS vs Kinesis**

SQS:

- Consumers pull data.
- **Data is deleted after being consumed.**
- Can have as many workers (consumers) as you need.
- No need to provision throughput.
- No ordering guarantee (except with FIFO queues).
- Individual message delay.

SNS:

- Push data to many subscribers.
- Up to 10,000,000 subscribers.
- Data does not persist (lost if not deleted).
- Pub/sub.
- Up to 10,000,000 topics.
- No need to provision throughput.
- Integrates with SQS for fan-out architecture pattern.

Kinesis:

- Consumers pull data.
- As many consumers as you need.
- Possible to replay data.
- Meant for real-time big data, analytics, and ETL.
- Ordering at the shard level.
- Data expires after X days.
- Must provision throughput.

*APPSYNC vs Cognito —- AWS AppSync is a similar service that has additional capabilities. With AppSync you can synchronize mobile app data across devices and users (Cognito Sync cannot synchronize across users, only devices), it has support for additional devices and data types, and is based on GraphQL.*

| **Directory Service Option** | **Description** | **Use Case** |
| --- | --- | --- |
| AWS Cloud Directory | Cloud-native directory to share and control access to hierarchical data between applications | Cloud applications that need hierarchical data with complex relationships |
| Amazon Cognito | Sign-up and sign-in functionality that scales to millions of users and federated to public social media services | Develop consumer apps or SaaS |
| AWS Directory Service for Microsoft Active Directory | AWS-managed full Microsoft AD running on Windows Server 2012 R2 | Enterprises that want hosted Microsoft AD or you need LDAP for Linux apps |
| AD Connector | Allows on-premises users to log into AWS services with their existing AD credentials. Also allows EC2 instances to join AD domain | Single sign-on for on-premises employees and for adding EC2 instances to the domain |
| Simple AD | Low scale, low cost, AD implementation based on Samba | Simple user directory, or you need LDAP compatibility |

Step Functions vs SWF ——- AWS Step Functions is a fully managed service that makes it easy to coordinate the components of distributed applications and microservices using visual workflows. Instead of writing a Decider program, you define state machines in JSON. AWS customers should consider using Step Functions for new applications. If Step Functions does not fit your needs, then you should consider Amazon Simple Workflow (SWF). Amazon SWF provides you complete control over your orchestration logic, but increases the complexity of developing applications. You may write decider programs in the programming language of your choice, or you may use the Flow framework to use programming constructs that structure asynchronous interactions for you. 

| **CloudFormation** | **Elastic Beanstalk** |
| --- | --- |
| “Template-driven provisioning” | “Web apps made easy” |
| Deploys infrastructure using code | Deploys applications on EC2 (PaaS) |
| Can be used to deploy almost any AWS service | Deploys web applications based on Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker |
| Uses JSON or YAML template files | Uses ZIP or WAR files |
| Similar to Terraform | Similar to Google App Engine |

| **CloudWatch** | **CloudTrail** |
| --- | --- |
| Performance monitoring | Auditing |
| Log events across AWS services – think operations | Log API activity across AWS services – think activities |
| Higher-level comprehensive monitoring and events | More low-level granular |
| Log from multiple accounts | Log from multiple accounts |
| Logs stored indefinitely | Logs stored to S3 or CloudWatch indefinitely |
| Alarms history for 14 days | No native alarming; can use CloudWatch alarms |

| **Memcached** | **Redis** |
| --- | --- |
| Simple, no-frills | You need encryption |
| You need to elasticity (scale out and in) | You need HIPAA compliance |
| You need to run multiple CPU cores and threads | Support for clustering |
| You need to cache objects (e.g. database queries) | You need complex data types |
|  | You need HA (replication |
|  | Pub/Sub capability |

| **Feature** | **Memcached** | **Redis (cluster mode disabled)** | **Redis (cluster mode enabled)** |
| --- | --- | --- | --- |
| Data persistence | No | Yes | Yes |
| Data types | Simple | Complex | Complex |
| Data partitioning | Yes | No | Yes |
| Encryption | No | Yes | Yes |
| High availability (replication) | No | Yes | Yes |
| Multi-AZ | Yes, place nodes in multiple AZs. No failover or replication | Yes, with auto-failover. Uses read replicas (0-5 per shard) | Yes, with auto-failover. Uses read replicas (0-5 per shard) |
| Scaling | Up (node type); out (add nodes) | Single shard (can add replicas) | Add shards |
| Multithreaded | Yes | No | No |
| Backup and restore | No (and no snapshots) | Yes, automatic and manual snapshots | Yes, automatic and manual snapshots |

# **DAX vs ElastiCache**

DAX is optimized for DynamoDB.

DAX does not support lazy loading (uses write-through caching).

With ElastiCache you have more management overhead (e.g. invalidation).

With ElastiCache you need to modify application code to point to cache.

ElastiCache supports more datastores.

| **Feature** | **Aurora Replica** | **MySQL Replica** |
| --- | --- | --- |
| Number of replicas | Up to 15 | Up to 5 |
| Replication type | Asynchronous (milliseconds) | Asynchronous (seconds) |
| Performance impact on primary | Low | High |
| Replica location | In-region | Cross-region |
| Act as failover target | Yes (no data loss) | Yes (potentially minutes of data loss) |
| Automated failover | Yes | No |
| Support for user-defined replication delay | No | Yes |
| Support for different data or schema vs. primary | No | Yes |

| **Data Store** | **When to Use** |
| --- | --- |
| Database on EC2 | • Ultimate control over database
• Preferred DB not available under RDS |
| Amazon RDS | • Need traditional relational database for OLTP
• Your data is well formed and structured
• Existing apps requiring RDBMS |
| Amazon DynamoDB | • Name/value pair data or unpredictable data structure
• In-memory performance with persistence
• High I/O needs
• Scale dynamically |
| Amazon RedShift | • Massive amounts of data
• Primarily OLAP workloads |
| Amazon Neptune | • Relationships between objects a major portion of data value |
| Amazon Elasticache | • Fast temporary storage for small amounts of data
• Highly volatile data |
| Amazon S3 | • BLOBs
• Static Websites |

| **Requirement** | **More Suitable Service** |
| --- | --- |
| Lots of large binary objects (BLOBs) | S3 |
| Automated Scalability | DynamoDB |
| Name/Value Data Structure | DynamoDB |
| Data is not well structured or unpredictable | DynamoDB |
| Other database platforms like IBM DB2 or SAP HANA | EC2 |
| Complete control over the database | EC2 |

General Purpose (SSD):

- Use for Database workloads with moderate I/O requirement.
- Cost effective.
- Also called gp2.
- 3 IOPS/GB.
- Burst up to 3000 IOPS.

Provisioned IOPS (SSD):

- Use for I/O intensive workloads.
- Low latency and consistent I/O.
- User specified IOPS (see table below).

| **Database Engine** | **Range of Provisioned IOPS** | **Range of Storage** |
| --- | --- | --- |
| MariaDB | 1,000-80,000 IOPS | 100 GiB-64TiB |
| SQL Server | 1,000-64,000 IOPS | 20 GiB-16TiB |
| MySQL | 1,000-80,000 IOPS | 100 GiB-64TiB |
| Oracle | 1,000-256,000 IOPS | 100 GiB-64TiB |
| PostgreSQL | 1,000-80,000 IOPS | 100 GiB-64TiB |

| **Multi-AZ Deployments** | **Read Replicas** |
| --- | --- |
| Synchronous Replication – highly durable | Asynchronous replication – highly scalable |
| Only database engine on primary instance is active | All read replicas are accessible and can be used for read scaling |
| Automated backups are taken from standby | No backups configured by default |
| Always span two availability zones within a single region | Can be within an Availability Zone, Cross-AZ, or Cross-Region |
| Database engine version upgrades happen on primary | Database engine version upgrade is independent from source instance |
| Automatic failover to standby when a problem is detected | Can be manually promoted to a standalone database instance |

Use signed URLs in the following cases:

- You want to restrict access to individual files, for example, an installation download for your application.
- Your users are using a client (for example, a custom HTTP client) that doesn’t support cookies.

Use signed cookies in the following cases:

- You want to provide access to multiple restricted files, for example, all the files for a video in HLS format or all the files in the subscribers’ area of website.
- You don’t want to change your current URLs.

|  | **NAT Gateway** | **NAT Instance** |
| --- | --- | --- |
| **Managed** | Managed by AWS | Managed |
| **Availability** | Highly available within an AZ | Not highly available (would require scripting) |
| **Bandwidth** | Up to 45 GPS | Depends on the bandwidth of the EC2 instance you selected |
| **Maintenance** | Managed by AWS | Managed by you |
| **Performance** | Optimized for NAT | Amazon Linux 2 AMI configured to perform NAT |
| **Public IP** | Elastic IP cannot be detached | Elastic IP that can be detached |
| **Security Groups** | Cannot associate with a security group | Can associate with a security group |
| **Bastion Host** | Not supported | Can be used as a bastion host |

| **Security Group** | **Network ACL** |
| --- | --- |
| Operates at the instance (interface level) | Operates at the subnet level |
| Supports allow rules only | Supports allow and deny rules |
| Stateful | Stateless |
| Evaluates all rules | Processes rules in order |
| Applies to an instance only if associated with a group | Automatically applies to all instances in the subnet it is associated with |

|  | **Interface Endpoint** | **Gateway Endpoint** |
| --- | --- | --- |
| **What** | Elastic Network Interface with a private IP | A gateway that is a target for a specific route |
| **How** | Uses DNS entries to redirect traffic | Use prefix lists in the route table to redirect traffic |
| **Which Services** | A large amount of AWS services, for full list follow this [link](https://docs.aws.amazon.com/vpc/latest/privatelink/integrated-services-vpce-list.html) | Amazon S3, DynamoDB |
| **Security** | Security Groups | VPC Endpoint Policies |

| **New Name** | **Old Name** | **Interface** | **Use Case** |
| --- | --- | --- | --- |
| **File Gateway** | None | NFS, SMB | Allow on-prem or EC2 instances to store objects in S3 via NFS or SMB mount points |
| **Volume Gateway Stored Mode** | Gateway-Stored Volumes | iSCSI | Asynchronous replication of on-prem data to S3 |
| **Volume Gateway Cached Mode** | Gateway-Cached Volumes | iSCSI | Primary data stored in S3 with frequently accessed data cached locally on-prem |
| **Tape Gateway** | Gateway-Virtual Tape Library | ISCSI | Virtual media changer and tape library for use with existing backup software |

| **Amazon ECS** | **Amazon EKS** |
| --- | --- |
| Managed, highly available, highly scalable container platform | Managed, highly available, highly scalable container platform |
| AWS-specific platform that supports Docker Containers | Compatible with upstream Kubernetes so it’s easy to lift and shift from other Kubernetes deployments |
| Considered simpler and easier to use | Considered more feature-rich and complex with a steep learning curve |
| Leverages AWS services like Route 53, ALB, and CloudWatch | A hosted Kubernetes platform that handles many things internally |
| “Tasks” are instances of containers that are run on underlying compute but more of less isolated | “Pods” are containers collocated with one another and can have shared access to each other |
| Limited extensibility | Extensible via a wide variety of third-party and community add-ons. |

[Untitled](https://www.notion.so/8322ffa384714fd3b5b23804d0704e7a?pvs=21)

**IAM Roles vs Resource Based Policies**

When you assume a role (user, application or service), you give up your original permissions and take the permissions assigned to the role
When using a resource-based policy, the principal doesn’t have to give up any permissions
Example: User in account A needs to scan a DynamoDB table in Account A and dump it in an S3 bucket in Account B.
Supported by: Amazon S3 buckets, SNS topics, SQS queues, Lambda functions, ECR, Backup, EFS, Glacier, Cloud9, AWS Artifact, Secrets Manager,ACM, KMS, CloudWatch Logs, API Gateway, EventBridge etc…

 IAM Access Analyzer helps you identify and remove overly permissive access and resource-sharing across AWS accounts. It helps you ensure that your IAM policies are not granting unintended access. AWS Trusted Advisor: **Trusted Advisor provides security checks that include IAM best practices**
