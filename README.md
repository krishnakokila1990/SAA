Analytics:

- Amazon Athena
    - Multi-tenancy approach might trigger throttling from time to time, leading to potential issues.
    - Amazon Athena doesn’t include any kind of Data Manipulation interface for inserting, deleting, and updating data.
    - Indexing is not natively supported within Amazon Athena, which is built upon AWS
- AWS Data Exchange
    - You'll receive an Amazon CloudWatch Events event from AWS Data Exchange every time the provider publishes new revisions. You can use this CloudWatch event to automate consumption of new data
- AWS Data Pipeline
    - AWS Data Pipeline is a web service that you can use to automate the movement and transformation of data
    - AWS Data Pipeline helps you sequence, schedule, run, and manage recurring data processing workloads reliably and cost-effectively
- Amazon EMR
    - You can run workloads on Amazon EC2 instances, on Amazon Elastic Kubernetes Service (EKS) clusters, **or on-premises using EMR on AWS Outposts.**
    - Runs in one Availability Zone within an Amazon VPC.
    - Most used for log analysis, financial analysis, or extract, translate and loading (ETL) activities.
    - Running big data frameworks, such as [Apache Hadoop](https://aws.amazon.com/elasticmapreduce/details/hadoop) and [Apache Spark](https://aws.amazon.com/elasticmapreduce/details/spark), on AWS to process and analyze vast amounts of data
- AWS Glue
    - AWS Glue is a fully managed [extract, transform, and load (ETL)](https://docs.aws.amazon.com/glossary/latest/reference/glos-chap.html#extracttransformload) service that you can use to catalog data and load it for analytics. With AWS Glue, you can discover your data, develop scripts to transform sources into targets, and schedule and run ETL jobs in a serverless environment.
    - AWS Glue Studio makes it easier to visually create, run, and monitor AWS Glue ETL jobs. You can build ETL jobs that move and transform data using a drag-and-drop editor, and AWS Glue automatically generates the code.
    - Each AWS account has one AWS Glue Data Catalog per region.
    - AWS Glue comes with three worker types to help you select the configuration that meets your job latency and cost requirements. Workers come in Standard, G.1X, G.2X, and G.025X configurations.
- Amazon Kinesis
    - Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data
    - each shard able to ingest 1000 records per second. There is a default limit of 500 shards, but you can request an increase to unlimited shards.
    - A record consists of a partition key, sequence number, and data blob (up to 1 MB).
    - Transient data store – default retention of 24 hours but can be configured for up to 7 days.
    - **Kinesis Video Streams**
        - Securely stream video from connected devices to AWS for analytics, machine learning (ML), and other processing.
        - Stores data in shards – 5 transaction per second for reads, up to a max read rate of 2MB per second and 1000 records per second for writes up to a max of 1MB per second.
    - **Kinesis Data Streams**
        - build custom applications that process or analyze streaming data
        - Partition keys are used to group data by shard within a stream.
    - Kinesis Data Firehose
        - For Amazon Redshift destinations, streaming data is delivered to your S3 bucket first. Kinesis Data Firehose then issues an Amazon Redshift **COPY** command to load data from your S3 bucket to your Amazon Redshift cluster.
        - For Amazon Elasticsearch destinations, streaming data is delivered to your Amazon ES cluster, and it can optionally be backed up to your S3 bucket concurrently
        - For Splunk destinations, streaming data is delivered to Splunk, and it can optionally be backed up to your S3 bucket concurrently
    - Kinesis Data Analytics
        - process and analyze real-time, streaming data.
        - Use cases:
            - Generate time-series analytics.
            - Feed real-time dashboards.
            - Create real-time alerts and notifications.
- AWS Lake Formation
    - Lake Formation **provides comprehensive audit logs with CloudTrail to monitor access and show compliance with centrally defined policies**
- Amazon Managed Streaming for Apache Kafka (Amazon MSK)
    - **fully managed service that enables you to build and run applications that use Apache Kafka to process streaming data**.
    - 
- Amazon OpenSearch Service
    - The Amazon OpenSearch Service is the successor to the Amazon Elasticsearch Service.
    - limitations:
        - If you launch a new domain within a VPC, you can’t later switch it to use a public endpoint. The reverse is also true.
        - You can either launch your domain within a VPC or use a public endpoint, but you can’t do both.
        - You can’t launch your domain within a VPC that uses dedicated tenancy. You must use a VPC with tenancy set to **Default**.
        - After you place a domain within a VPC, you can’t move it to a different VPC, but you can change the subnets and security group settings.
        - To access the default installation of OpenSearch Dashboards for a domain that resides within a VPC, users must have access to the VPC.
- Amazon QuickSight
    - Amazon Quicksight is a business analytics service that delivers insights into data at scale.
    
    Amazon Quicksight service is prices are based on the following plans:
    
    - Standard
    - Enterprise
        - Provides additional permissions for account administration.
        - Makes it possible to share dashboards with readers.
        - Makes it possible to connect to data sources in virtual private clouds
- Amazon Redshift
    - Amazon RedShift is a clustered peta-byte scale data warehouse and is an SQL based data warehouse used for **analytics applications**.
    - Online Analytics Processing (OLAP) type of Database
    - Columnar data storage
    - Only available in one AZ but you can restore snapshots into another AZ.
    - Amazon RedShift always keeps three copies of your data:
        - The original.
        - A replica of compute nodes (within the cluster).
        - A backup copy on S3.
    - best HA option is to use a multi-node cluster which supports data replication and node recovery.
    - Manual backups are not automatically deleted when you delete a cluster.
    - Use Cases of Amazon RedShift
        
        A data warehouse for enterprise operations: Many organizations work with data from multiple sources, such as advertising, customer relationship management, and customer support.
        
        As a centralized repository, Redshift can be used to store data from multiple sources in a unified schema and structure. This can then feed enterprise-wide reporting and analytics.
        
        In business intelligence and analytics, Redshift’s fast query execution against terabyte-scale data makes it an excellent selection. BI tools such as Tableau often use Redshift as the underlying database (which would otherwise struggle to perform queries and joins of large datasets).
        
        Organizations may choose to monetize their data by exposing it to their customers through embedded analytics and analytics as a service. In these scenarios, Redshift’s data sharing, search, and aggregation capabilities make it ideal, as it allows customers to access only relevant subsets of data while keeping other databases, tables, or rows confidential.
        
        As long as the cluster is adequately resourced, Redshift’s performance is consistent and predictable. It is therefore a popular choice for data-driven applications, such as reporting and calculations.
        
        Database migration and change data capture: AWS Database Migration Service (DMS) can be used to replicate changes in an operational data store into Amazon Redshift. It is typically done to provide more flexibility in analysis, or when migrating from legacy data warehouses.
        

Application Integration:

- Amazon AppFlow
    - Amazon AppFlow is a fully managed integration service that enables you to securely transfer data between Software-as-a-Service (SaaS) applications like Salesforce, Marketo, Slack, and ServiceNow, and AWS services like Amazon S3 and Amazon Redshift, in just a few clicks.
- AWS AppSync
    - AWS AppSync simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources. AppSync is a managed service that uses GraphQL to make it easy for applications to get exactly the data they need, including from multiple DynamoDB tables.
    - AWS AppSync is designed for real-time and offline data access which makes it an ideal solution for this scenario
- Amazon EventBridge
- Amazon MQ
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)
    - default visibility timeout is 30 seconds. The maximum is 12 hours.
    - To ensure strict ordering between messages, specify a MessageGroupId.
    - A delay queue postpones delivery of new messages to a queue for a number of seconds
    - Default delay is 0 seconds, maximum is 900 seconds (15 minutes).
    - For standard SQS queues, changing this setting doesn’t affect the delay of messages already in the queue, only new messages.
    - For FIFO queues, this affects the delay of messages already in the queue
    
    | Standard Queue | FIFO Queue |
    | --- | --- |
    | Unlimited Throughput: Standard queues support a nearly unlimited number of transactions per second (TPS) per API action. | High Throughput: FIFO queues support up to 300 messages per second (300 send, receive, or delete operations per second). When you batch 10 messages per operation (maximum), FIFO queues can support up to 3,000 messages per second |
    | Best-Effort Ordering: Occasionally, messages might be delivered in an order different from which they were sent | First-ln-First-out Delivery: The order in which messages are sent and received is strictly preserved |
    | At-Least-Once Delivery: A message is delivered at least once, but occasionally more than one copy of a message is delivered | Exactly-Once Processing: A message is delivered once and remains available until a consumer processes and deletes it. Duplicates are not introduced into the queue |
- AWS Step Functions
- SWF - web service that makes it easy to coordinate work across distributed application components.

AWS Cost Management:

- AWS Budgets
    - Used to track cost, usage, or coverage and utilization for your Reserved Instances and Savings Plans, across multiple dimensions, such as service, or Cost Categories
- AWS Cost and Usage Report
    - Reports break down costs by Hour, day, month, product, product resource, tags.
- AWS Cost Explorer
    - allows you to view charts of your costs
    - past 13 months and forecast how much you are likely to spend over the next three months.
- Savings Plans

Compute:

- AWS Batch
    - AWS Batch is a set of batch management capabilities that **enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS**
- Amazon EC2
- Amazon EC2 Auto Scaling
- AWS Elastic Beanstalk ———————————-
- AWS Outposts
    - An Outpost is **a pool of AWS compute and storage capacity deployed at a customer site**. AWS operates, monitors, and manages this capacity as part of an AWS Region. You can create subnets on your Outpost and specify them when you create AWS resources such as EC2 instances, EBS volumes, ECS clusters, and RDS instances.
    - **Unlike Outposts, which you deploy within your datacenter or a co-location of your choice, Local Zones are owned, managed, and operated by AWS**. Local Zones eliminate the need for you to manage power, connectivity, and capacity using the exact same set of APIs and tools that you are already using for an AWS Region
- AWS Serverless Application Repository
    - The AWS Serverless Application Repository (SAR) is **a managed repository for serverless applications**. It enables teams, organizations, and individual developers to store and share reusable applications, and easily assemble and deploy serverless architectures in powerful new ways
- VMware Cloud on AWS
    - VMware Cloud on AWS (VMC on AWS) is **a managed cloud offering that provides dedicated VMware vSphere-based Software Defined Data Centers (SDDC) that are hosted within AWS facilities**
- AWS Wavelength
    - Wavelength — **A new type of AWS infrastructure designed to run workloads that require low latency or edge resiliency**. Wavelength Zone — A zone in the carrier location where the Wavelength infrastructure is deployed. Wavelength Zones are associated with an AWS Region.

Containers:

- Amazon ECS Anywhere
    - **Amazon ECS Anywhere is a feature of Amazon ECS** that enables you to run and manage container-based applications on-premises, including on your own virtual machines (VMs) and bare metal servers
- Amazon EKS Anywhere
    - ***Amazon EKS Anywhere*** is container management software built by AWS that makes it easier to run and manage Kubernetes on-premises and at the edge
- Amazon EKS Distro
    - **EKS is a fully managed Kubernetes platform, while EKS-D is available to install and manage yourself**. You can run EKS-D on-premises, in a cloud, or on your own systems. EKS-D provides a path to having essentially the same Amazon EKS Kubernetes distribution running wherever you need to run it
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Elastic Kubernetes Service (Amazon EKS)

Database:

- Amazon Aurora
    - An outage occurs if you change the backup retention period from zero to a non-zero value or the other way around.
    - Automated backups are only supported for InnoDB storage engine for MySQL (not for myISAM).
- Amazon Aurora Serverless
- Amazon DocumentDB (with MongoDB compatibility)
- Amazon DynamoDB
    - *Compared to DynamoDB Accelerator (DAX) remember that DAX is optimized for DymamoDB specifically and only supports the write-through caching strategy (does not use lazy loading).*
    
    Amazon DynamoDB is not ideal for the following situations:
    
    - Traditional RDS apps.
    - Joins and/or complex transactions.
    - BLOB data.
    - Large data with low I/O rate.
    - DynamoDB uses eventually consistent reads by default.
    - You can configure strongly consistent reads with the GetItem, Query and Scan APIs by setting the –consistent-read (or ConsistentRead) parameter to “true”.
    - DAX
        - DAX is a managed service that provides in-memory acceleration for DynamoDB tables.
        - You do not need to modify application logic, since DAX is compatible with existing DynamoDB API calls.
        - Ideal for read-heavy and bursty workloads such as auction applications, gaming, and retail sites when running special sales / promotions.
    - if your workload is mainly reads consider offloading using DAX or ElastiCache.
    - If your workload is mainly writes consider increasing the WCUs for the table.
    - Optimistic locking is a strategy to ensure that the client-side item that you are updating (or deleting) is the same as the item in Amazon DynamoDB

| DynamoDB Feature | Benefit |
| --- | --- |
| Serverless | Fully managed, fault tolerant service |
| Highly available | 99.99% Availability SLA – 99.999% for Global tables |
| NoSQL type of database with Name / Value structure | Flexible Schema, good for when data is not well structured or unpredictable |
| Horizontal scaling | Seamless scalability to any scale with push button scaling or Auto scaling |
| DynamoDB Streams | Captures a time-ordered sequence of item-level modifications in a DynamoDB table and durably stores the information for 24 hours. Often used with Lambda and the Kinesis Client Library (KCL). |
| DynamoDB Accelerator (DAX) | Fully managed in-memory cache for DynamoDB that increases performance (microsecond latency) |
| Transaction options | Strongly consistent or eventually consistent reads, support for ACID transactions |
| Backup | Point-in-time recovery down to the second in last 35 days; On-demand backup and restore |
| Global Tables | Fully managed multi-region, multi-master solution |
- Amazon ElastiCache
    - Best for scenarios where the DB load is based on Online Analytics Processing (OLAP) transactions.
    - Can be on-demand or reserved instances too (but not Spot instances).
    - When not using a VPC, Amazon ElastiCache allows you to control access to your clusters through Cache Security Groups (you need to link the corresponding EC2 Security Groups).
    - *ElastiCache is an in-memory database and it’s a managed service (so you can’t run it on EC2).*
    - Memchached
        - Ideal front-end for data stores (RDS, Dynamo DB etc.).
        
        Use cases:
        
        - Cache the contents of a DB.
        - Cache data from dynamically generated web pages.
        - Transient session data.
        - High frequency counters for admission control in high volume web apps.
    - Does not support multi-AZ failover or replication.
    - Does not support snapshots.
    - You can place nodes in different AZs.
    - 
- Amazon Keyspaces (for Apache Cassandra)
    - Amazon Keyspaces (for Apache Cassandra) is **a scalable, highly available, and managed Apache Cassandra–compatible database service**. With Amazon Keyspaces, you can run your Cassandra workloads on AWS using the same Cassandra application code and developer tools that you use today
- Amazon Neptune
    - Amazon Neptune Analytics is an analytics database engine for **quickly analyzing large volumes of graph data to get insights and find trends from data stored in Amazon S3 buckets or a Neptune database**
- Amazon Quantum Ledger Database (Amazon QLDB)
    - With QLDB, **the history of changes to your data is immutable**—it can't be overwritten or altered in place. And using cryptography, you can verify that there have been no unintended changes to your application's data. QLDB uses an immutable transactional log, known as a journal
- Amazon RDS
    - you can scale storage and change the storage type for all DB engines except MS SQL.
    - For MS SQL the workaround is to create a new instance from a snapshot with the new configuration.
    - Amazon RDS uses EBS volumes (never uses instance store) for DB and log storage
    - to initiate a manual RDS DB instance failover is to reboot selecting the option to failover.
    - A DB instance reboot is required for changes to take effect when you change the DB parameter group or when you change a static DB parameter.
    
    The process for implementing maintenance activities is as follows:
    
    - Perform operations on standby.
    - Promote standby to primary.
    - Perform operations on new standby (demoted primary).
    - By default upgrades will take effect during the next maintenance window.
    - You can take snapshots of PostgreSQL read replicas but cannot enable automated backups.
    - You can enable automatic backups on MySQL and MariaDB read replicas.
    - You can have read replicas of read replicas for MySQL and MariaDB but not for PostgreSQL.
    - If a source DB instance is deleted without deleting the replicas each replica becomes a standalone single-AZ DB instance.
- Amazon Redshift

Developer
Tools:

- AWS X-Ray
    - AWS X-Ray **helps developers analyze and debug production, distributed applications**, such as those built using a microservices architecture. With X-Ray, you can understand how your application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors

Front-End
Web and Mobile:

- AWS Amplify
    - The AWS Amplify is **a complete solution that allows frontend web and mobile developers to easily build, connect, and host fullstack applications**
- Amazon API Gateway ——- Revise again
    - AWS also offers the “ANY” method as a catch-all.
    - You can add caching to API calls by provisioning an Amazon API Gateway cache and specifying its size in gigabytes.
    - The cache capacity is between 0.5GB to 237GB.
    - Clients can invalidate the cache with the header: Cache-Control: max-age=0 .
    
    Limits:
    
    - By default API Gateway limits the steady-state request rate to 10,000 requests per second.
    - The maximum concurrent requests is 5,000 requests across all APIs within an AWS account.
    - If you go over 10,000 requests per second or 5,000 concurrent requests you will receive a 429 Too Many Requests error response
    - 
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/828628b0-1eef-4484-89d0-6a7315cad598/c320efb6-303e-42b4-b583-432c777da02b/5dd2b971-72e3-451c-a5b5-6cfeeaf6f153.png)
    
    | API Gateway Feature | Benefit |
    | --- | --- |
    | Support for RESTful APIs and WebSocket APIs | With API Gateway, you can create RESTful APIs using either HTTP APIs or REST APIs |
    | Private integrations with AWS ELB & AWS Cloud Map | With API Gateway, you can route requests to private resources in your VPC. Using HTTP APIs, you can build APIs for services behind private ALBs, private NLBs, and IP-based services registered in AWS Cloud Map, such as ECS tasks. |
    | Metering | Define plans that meter and restrict third-party developer access to APIs. |
    | Security | API Gateway provides multiple tools to authorize access to APIs and control service operation access. |
    | Resiliency | Manage traffic with throttling so that backend operations can withstand traffic spikes. |
    | Operations Monitoring | API Gateway provides a metrics dashboard to monitor calls to services. |
    | Lifecycle Management | Operate multiple API versions and multiple stages for each version simultaneously so that existing applications can continue to call previous versions after new API versions are published. |
    | AWS Authorization | Support for signature version 4 for REST APIs and WebSocket APIs, IAM access policies, and authorization with bearer tokens (e.g., JWT, SAML) using Lambda functions. |
- AWS Device Farm
    - AWS Device Farm is **an app testing service that enables you to test your iOS, Android and Fire OS apps on real, physical phones and tablets that are hosted by AWS**. The service allows you to upload your own tests or use built-in, script-free compatibility tests
- Amazon Pinpoint
    - Amazon Pinpoint is **an AWS service that you can use to engage with your customers across multiple messaging channels**. You can use Amazon Pinpoint to send push notifications, in-app notifications, emails, text messages, voice messages, and messages over custom channels

Machine
Learning:

- Amazon Comprehend
    - Amazon Comprehend **uses natural language processing (NLP) to extract insights about the content of documents**. It develops insights by recognizing the entities, key phrases, language, sentiments, and other common elements in a document
- Amazon Forecast
    - Amazon Forecast **automates much of the time-series forecasting process, enabling you to focus on preparing your datasets and interpreting your predictions**
- Amazon Fraud Detector
    - Amazon Fraud Detector is a fully managed service that makes it easy to **identify potentially fraudulent online activities such as online payment fraud and fake account creation**
- Amazon Kendra
    - Amazon Kendra **provides search functionality to your application**. It indexes your documents directly or from your third-party document repository and intelligently serves relevant information to your users. You can use Amazon Kendra to create an updatable index of documents of a variety of types
- Amazon Lex
    - Amazon Lex is an AWS service for **building conversational interfaces for applications using voice and text**. With Amazon Lex, the same conversational engine that powers Amazon Alexa is now available to any developer, enabling you to build sophisticated, natural language chatbots into your new and existing applications
- Amazon Polly
    - Amazon Polly is a service that **turns text into lifelike speech**. Amazon Polly enables existing applications to speak as a first class feature and creates the opportunity for entirely new categories of speech-enabled products, from mobile apps and cars, to devices and appliances
- Amazon Rekognition
    - Amazon Rekognition uses **Deep-learning to accurately interpret images, compare and find faces in an image, and recognize scenes and objects in images and videos**
- Amazon SageMaker
    - Amazon SageMaker helps data scientists and ML engineers build FMs from scratch, evaluate and customize FMs with advanced techniques, and deploy FMs with fine-grain controls for generative AI use cases that have stringent requirements on accuracy, latency, and cost
- Amazon Textract
    - Amazon Textract is a machine learning (ML) service that **automatically extracts text, handwriting, and data from scanned documents**. It goes beyond simple optical character recognition (OCR) to identify, understand, and extract data from forms and tables
- Amazon Transcribe
    - Amazon Transcribe **converts audio input into text, which opens the door for various text analytics applications on voice input**. For instance, by using Amazon Comprehend on the converted text data from Amazon Transcribe, you can perform sentiment analysis or extract entities and key phrases
- Amazon Translate
    - Amazon Translate is **a text translation service that uses advanced machine learning technologies to provide high-quality translation on demand**. You can use Amazon Translate to translate unstructured text documents or to build applications that work in multiple languages

Management
and Governance:

- AWS Auto Scaling
    - 
    
    | AWS service | Console access¹ | CLI access | SDK access | CloudFormation access |
    | --- | --- | --- | --- | --- |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-appstream.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-aurora.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-comprehend.html | No | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-dynamodb.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-ecs.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-elasticache.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-automatic-scaling.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-keyspaces.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-lambda.html | No | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-msk.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-neptune.html | No | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-sagemaker.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-ec2.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-workspaces.html | Yes | Yes | Yes | Yes |
    | https://docs.aws.amazon.com/autoscaling/application/userguide/services-that-can-integrate-custom.html | No | Yes | Yes | Yes |
- AWS CloudFormation
    - *with mappings you can, for example, set values based on a region. You can create a mapping that uses the region name as a key and contains the values you want to specify for each specific region*
    - AWS::Serverless transform, which is a macro hosted by AWS CloudFormation, takes an entire template written in the AWS Serverless Application Model (AWS SAM) syntax and transforms and expands it into a compliant AWS CloudFormation template
    - *https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html*
    - The user data script logs are stored in /var/log/cloud-init-output.log
    - The cfn-init helper script reads template metadata from the AWS::CloudFormation::Init key and acts accordingly to:
        - Fetch and parse metadata from AWS CloudFormation
        - Install packages
        - Write files to disk
        - Enable/disable and start/stop services
        - cfn-init does not require credentials, so you do not need to use the –access-key, –secret-key, –role, or –credential-file options.
        - Logs go to /var/log/cfn-init.log
    - cfn-signal:
        - The cfn-signal helper script signals AWS CloudFormation to indicate whether Amazon EC2 instances have been successfully created or updated.
        - If you install and configure software applications on instances, you can signal AWS CloudFormation when those software applications are ready.
        - You use the cfn-signal script in conjunction with a [**CreationPolicy**](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-creationpolicy.html) or an Auto Scaling group with a [**WaitOnResourceSignals**](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-updatepolicy.html) update policy.
        - When AWS CloudFormation creates or updates resources with those policies, it suspends work on the stack until the resource receives the requisite number of signals or until the timeout period is exceeded.
        - You can signal a creation policy ([**CreationPolicy**](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-creationpolicy.html)) or a wait condition handle ([**WaitOnResourceSignals**](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-updatepolicy.html)).
- AWS CloudTrail
- Amazon CloudWatch
- AWS Command Line Interface (AWS CLI)
- AWS Compute Optimizer
- AWS Config
    - AWS Config is a fully managed service that provides you with an AWS resource inventory, configuration history, and configuration change notifications to enable security and governance.
- AWS Control Tower
    - What is AWS Control Tower? AWS Control Tower **offers the easiest way to set up and govern a secure, multi-account AWS environment**. It establishes a landing zone that is based on best-practices blueprints, and it enables governance using controls you can choose from a pre-packaged list
- AWS Health Dashboard
    - AWS Health notifies you about service events, planned changes, and account notifications to help you manage and take actions. Sign into your AWS Health Dashboard to **view account-specific health information or receive AWS Health event updates using Amazon EventBridge**
- AWS License Manager
    - AWS License Manager is a service that makes it easier for you to manage your software licenses from software vendors (for example, Microsoft, SAP, Oracle, and IBM) centrally across AWS and your on-premises environments
- Amazon Managed Grafana
    - Amazon Managed Grafana natively integrates with AWS services to ensure that you can **securely add, query, visualize, and analyze your AWS data across multiple accounts and regions with a few clicks in the AWS Console**
- Amazon Managed Service for Prometheus
    - **Prometheus-compatible service that monitors and provides alerts on containerized applications and infrastructure at scale**
- AWS Management Console
- AWS Organizations
    - AWS Organizations helps you centrally manage and govern your environment as you grow and scale your AWS resources
- AWS Proton
    - AWS Proton is the first fully managed application deployment service for Container and Serverless Applications. We can use AWS Proton to connect and coordinate all the different tools needed for infrastructure provisioning, code deployments, monitoring, and updates.
- AWS Service Catalog
    
    AWS Service Catalog enables organizations to create and manage catalogs of IT services that are approved for use on AWS. It allows centrally managed service portfolios, which clients can use on a self-service basis.
    
    AWS Service Catalog provides a single location where organizations can centrally manage catalogs of IT services, which simplifies the organizational process and helps ensure compliance.
    
- AWS Systems Manager
    - provides a unified interface through which you can view operational data from multiple AWS services.
- AWS Trusted Advisor
    - Trusted Advisor is an online resource that helps to reduce cost, increase performance, and improve security by optimizing your AWS environment.
- AWS Well-Architected Tool
    - service in the cloud that **provides a consistent process for measuring your architecture using AWS best practices**. AWS WA Tool helps you throughout the product lifecycle by: Assisting with documenting the decisions that you make

Media Services:

- Amazon Elastic Transcoder
    - convert (or “transcode”) video and audio files from their source format into versions that will playback on devices like smartphones, tablets and PC
    - charged based on the duration of the content and the resolution or format of the media
- Amazon Kinesis Video Streams
    - Kinesis Video Streams **automatically provisions and elastically scales all the infrastructure needed to ingest streaming video data from millions of devices**. It durably stores, encrypts, and indexes video data in your streams, and allows you to access your data through easy-to-use APIs

Migration and Transfer:

- AWS Application Discovery Service
    - AWS Application Discovery Service collects and presents configuration, usage, and behavior data from your servers to help you better understand your workloads.
- AWS Application Migration Service
    - AWS Application Migration Service **minimizes time-intensive, error-prone manual processes by automating the conversion of your source servers to run natively on AWS**.
- AWS Database Migration Service (AWS DMS)
- AWS Server Migration Service
    - AWS Server Migration Service (SMS) is an agentless service which makes it easier and faster for you to migrate thousands of on-premises workloads to AWS.
    - AWS SMS allows you to automate, schedule, and track incremental replications of live server volumes, making it easier for you to coordinate large-scale server migrations.
- AWS DataSync
    - AWS Data Sync allows you to transfer between on-premises and AWS, between AWS storage services and even between different cloud providers
    - 
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/828628b0-1eef-4484-89d0-6a7315cad598/4a7b1232-088a-4024-82d3-24aba19e5db0/e95ec952-c756-4cfd-b2fb-7457dfcb8f0b.png)
    
- AWS Migration Hub
    - AWS Migration Hub (Migration Hub) **provides a single place to discover your existing servers, plan migrations, and track the status of each application migration**. The Migration Hub provides visibility into your application portfolio and streamlines planning and tracking
- AWS Snow Family
    - AWS Snow Family is a service for customers who want to transport terabytes or petabytes of data to and from AWS, or who want to access the storage and compute power of the AWS Cloud locally and cost effectively in places where connecting to the internet might not be an option
    - **AWS Snowcone, AWS Snowball, and AWS Snowmobile**
- AWS Transfer Family
    - AWS Transfer Family **securely scales your recurring business-to-business file transfers to AWS Storage services using SFTP, FTPS, FTP, and AS2 protocols**. Seamlessly migrate, automate, and monitor your file transfer workflows into and out of Amazon S3 and Amazon EFS using the SFTP, FTPS, and FTP protocols
    - AWS Transfer Family is a secure transfer service that stores your data in Amazon Simple Storage Service or Amazon Elastic File System and simplifies the migration of Secure File Transfer Protocol (SFTP), File Transfer Protocol Secure (FTPS), File Transfer Protocol (FTP), and Applicability Statement 2 (AS2) workflows to AWS

Networking and Content Delivery:

- AWS Client VPN
    - AWS Client VPN **provides users with secure access to applications both on premises and in AWS**. This is helpful during a cloud migration when applications move from on-premises locations to the cloud. With AWS Client VPN, users don't have to change the way they access their applications during or after migration
- Amazon CloudFront
    - web service that gives businesses and web application developers an easy and cost-effective way to distribute content with low latency and high data transfer speeds.
    - CloudFront supports wildcard CNAME, wildcard SSL certificates, Dedicated IP, Custom SSL and SNI Custom SSL (cheaper)
    - Perfect Forward Secrecy which creates a new private key for each SSL session.
    - Dynamic content goes straight to the origin and does not flow through Regional Edge caches
    - Origins can be either an S3 bucket, an EC2 instance, an Elastic Load Balancer, or Route 53 – can also be external (non-AWS)
    - A custom origin server is a HTTP server which can be an EC2 instance or an on-premises/non-AWS based web server
    - Most CloudFront features are supported for custom origins except RTMP distributions (must be an S3 bucket)
        - Real-Time Messaging Protocol, otherwise known as RTMP, plays a crucial role in enabling the smooth transmission of data over the internet, **delivering live video content globally**
    - Static websites on Amazon S3 are considered custom origins
    - To delete a distribution it must first be disabled (can take up to 15 minutes)
    - The default cache behavior only allows a path pattern of /*.
    - **Origin Access Identity (OAI)** can be used to restrict access to content in an Amazon S3 bucket
    - You cannot invalidate media files in the Microsoft Smooth Streaming format when you have enabled Smooth Streaming for the corresponding cache behavior.
    
    Methods of improving the cache hit ratio include:
    
    - Use the Cache-Control max-age directive to increase the time objects remain in the cache
    - Use Origin Shield.
    - Forward only the query string parameters for which your origin will return unique objects.
    - Configure CloudFront to forward only specified cookies instead of forwarding all cookies.
    - Configure CloudFront to forward and cache based on only specified headers instead of forwarding and caching based on all headers.
- AWS Direct Connect
    - network service that provides an alternative to using the Internet to connect a customer’s on-premises sites to AWS.
    - Data is transmitted through a private network connection between AWS and a customer’s datacenter or corporate network
    - Cannot do layer 2 over Direct Connect (L3 only).
    - You can only have one 0.0.0.0/0 (all IP addresses) entry per route table.
    - Uses 802.1q VLANs
    
    Benefits:
    
    - Reduce cost when using large volumes of traffic.
    - Increase reliability (predictable performance).
    - Increase bandwidth (predictable bandwidth).
    - Decrease latency.
- AWS Direct Connect Gateway
    - Grouping of Virtual Private Gateways (VGWs) and Private Virtual Interfaces (VIFs) that belong to the same AWS account.
    - enables you to interface with VPCs in any AWS Region (except AWS China Region)
    
    You associate an *AWS Direct Connect gateway* with either of the following gateways:
    
    - A transit gateway when you have multiple VPCs in the same Region.
    - A virtual private gateway.
    - Can share private virtual interface to interface with more than one Virtual Private Clouds (VPCs) reducing the number of BGP sessions.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/828628b0-1eef-4484-89d0-6a7315cad598/e0648773-fe0c-44e4-b3f4-e8ff3d615c62/45e5743b-2e5c-40b8-92cc-dc3b83e67c64.png)
    
- Elastic Load Balancing (ELB)
- AWS Global Accelerator
    - The addresses are assigned to your accelerator for as long as it exists, even if you disable the accelerator and it no longer accepts or routes traffic.
    - Does health checks for TCP only – not UDP.
    - By default, AWS Global Accelerator is protected by AWS Shield Standard, which minimizes application downtime and latency from denial-of-service attacks by using always-on network flow monitoring and automated in-line mitigation.
    - You can also enable AWS Shield Advanced for automated resource-specific enhanced detection and mitigation, as well as 24×7 access to the AWS DDoS Response Team (DRT) for manual mitigations of sophisticated DDoS attacks.
- AWS PrivateLink
    - AWS PrivateLink **provides private connectivity between virtual private clouds (VPCs), supported AWS services, and your on-premises networks without exposing your traffic to the public internet**
- Amazon Route 53
    - Offers
        - Domain name registry.
        - DNS resolution.
        - Health checking of resources.
    - Changes to Name Servers may not take effect for up to 48 hours due to the DNS record Time To Live (TTL) values.
    - It is possible to have the domain registered in one AWS account and the hosted zone in another AWS account.
    - AWS offer a 100% uptime SLA for Route 53.
    - default limit of 50 domain names
    - Amazon Route 53 creates a set of 4 unique name servers (a delegation set) within each hosted zone.
    - You cannot extend Route 53 to on-premises instances.
    - Health checks can be pointed at:
        - Endpoints.
        - Status of other health checks.
        - Status of a CloudWatch alarm.
    - To associate a Route 53 private hosted zone in one AWS account (Account A) with a virtual private cloud that belongs to another AWS account (Account B), follow these steps using the AWS CLI:
        - From an instance in Account A, authorize the association between the private hosted zone in Account A and the virtual private cloud in Account B.
        - From an instance in Account B, create the association between the private hosted zone in Account A and the virtual private cloud in Account B.
        - Delete the association authorization after the association is created.
    - You can create the following types of health checks:
        - **HTTP**: Route 53 tries to establish a TCP connection. If successful, Route 53 submits an HTTP request and waits for an HTTP status code of 200 or greater and less than 400.
        - **HTTPS**: Route 53 tries to establish a TCP connection. If successful, Route 53 submits an HTTPS request and waits for an HTTP status code of 200 or greater and less than 400.
        - **HTTP_STR_MATCH**: Route 53 tries to establish a TCP connection. If successful, Route 53 submits an HTTP request and searches the first 5,120 bytes of the response body for the string that you specify in SearchString.
        - **HTTPS_STR_MATCH**: Route 53 tries to establish a TCP connection. If successful, Route 53 submits an HTTPS request and searches the first 5,120 bytes of the response body for the string that you specify in SearchString.
        - **TCP**: Route 53 tries to establish a TCP connection.
        - **CLOUDWATCH_METRIC**: The health check is associated with a CloudWatch alarm. If the state of the alarm is OK, the health check is considered healthy. If the state is ALARM, the health check is considered unhealthy. If CloudWatch doesn’t have sufficient data to determine whether the state is OK or ALARM, the health check status depends on the setting for InsufficientDataHealthStatus: Healthy, Unhealthy, or LastKnownStatus.
        - **CALCULATED**: For health checks that monitor the status of other health checks, Route 53 adds up the number of health checks that Route 53 health checkers consider to be healthy and compares that number with the value of HealthThreshold.
    - 
- AWS Site-to-Site VPN
    - AWS Site-to-Site VPN is **a fully-managed service that creates a secure connection between your data center or branch office and your AWS resources using IP Security (IPSec) tunnels**
- AWS Transit Gateway
    - AWS Transit Gateway **connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub**. This connection simplifies your network and puts an end to complex peering relationships. Transit Gateway acts as a highly scalable cloud router—each new connection is made only once
- Amazon VPC
    - Components of a VPC:
        - **A Virtual Private Cloud:** A logically isolated virtual network in the AWS cloud. You define a VPC’s IP address space from ranges you select.
        - **Subnet:** A segment of a VPC’s IP address range where you can place groups of isolated resources (maps to an AZ, 1:1).
        - **Internet Gateway:** The Amazon VPC side of a connection to the public Internet.
        - **NAT Gateway:** A highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet.
        - **Hardware VPN Connection:** A hardware-based VPN connection between your Amazon VPC and your datacenter, home network, or co-location facility.
        - **Virtual Private Gateway:** The Amazon VPC side of a VPN connection.
        - **Customer Gateway:** Your side of a VPN connection.
        - **Router:** Routers interconnect subnets and direct traffic between Internet gateways, virtual private gateways, NAT gateways, and subnets.
        - **Peering Connection:** A peering connection enables you to route traffic via private IP addresses between two peered VPCs.
        - **VPC Endpoints:** Enables private connectivity to services hosted in AWS, from within your VPC without using an Internet Gateway, VPN, Network Address Translation (NAT) devices, or firewall proxies.
        - **Egress-only Internet Gateway:** A stateful gateway to provide egress only access for IPv6 traffic from the VPC to the Internet.
    - The VPC router performs routing between AZs within a region
    - Up to 200 route tables per VPC
    - Up to 50 route entries per route table
    - Each subnet can only be associated with one route table
    - The first 4 and last 1 IP addresses in a subnet are reserved
        - 10.0.0.0: Network address.
        - 10.0.0.1: Reserved by AWS for the VPC route.
        - 10.0.0.2: Reserved by AWS.
        - 10.0.0.3: Reserved by AWS for future use.
        - 10.0.0.255: Network broadcast address (broadcast not supported).
    - You can only attach one Internet gateway to a custom VPC
    
    It is recommended these come from the private IP ranges specified in RFC 1918:
    
    - 10.0.0.0 – 10.255.255.255 (10/8 prefix)
    - 172.16.0.0 – 172.31.255.255 (172.16/12 prefix)
    - 192.168.0.0 – 192.168.255.255 (192.168/16 prefix)
    
    To enable access to or from the Internet for instances in a VPC subnet, you must do the following:
    
    - Attach an Internet Gateway to your VPC.
    - Ensure that your subnet’s route table points to the Internet Gateway (see below).
        - To all destinations, e.g. 0.0.0.0/0 for IPv4 or ::/0for IPv6.
        - To specific public IPv4 addresses, e.g. your company’s public endpoints outside of AWS.
    - Ensure that instances in your subnet have a globally unique IP address (public IPv4 address, Elastic IP address, or IPv6 address).
    - Ensure that your network access control and security group rules allow the relevant traffic to flow to and from your instance.
    - When creating NAT instances always disable the source/destination check on the instance
    - Can’t use a NAT Gateway to access VPC peering, VPN or Direct Connect, so be sure to include specific routes to those in your route table
    - **security groups operate at the network interface level**
    - There is an implicit deny rule at the end of the security group
    - Security groups are stateful
    - Up to 5 security groups can be added per EC2 instance interface
    - **Network ACL’s function at the subnet level**
    
    Zonal redundancy indicates that the architecture should be split across multiple Availability Zones. Subnets are mapped 1:1 to AZs.
    
    A public subnet should be used for the Internet-facing web servers and a separate private subnet should be used for the internal-only DB servers. Therefore you need 4 subnets – 2 (for redundancy) per public/private subnet.
    
    There are several methods of connecting to a VPC. These include:
    
    - AWS Managed VPN.
    - 
        
        
        | What | AWS-provided network connectivity between two VPCs |
        | --- | --- |
        | When | Multiple VPCs need to communicate or access each other’s resources |
        | Pros | Uses AWS backbone without traversing the public internet |
        | Cons | Transitive peering is not supported |
        | How | VPC Peering request made; acceptor accepts request (either within or across accounts) |
    - AWS Direct Connect.
        - AWS Direct Connect makes it easy to establish a dedicated connection from an on-premises network to Amazon VPC.
        - AWS Direct Connect does not encrypt your traffic that is in transit.
        
        | What | Dedicated network connection over private line straight into the AWS backbone |
        | --- | --- |
        | When | Requires a large network link into AWS; lots of resources and services being provided on AWS to your corporate users |
        | Pros | More predictable network performance; potential bandwidth cost reduction; up to 10 Gbps provisioned connections; supports BGP peering and routing |
        | Cons | May require additional telecom and hosting provider relationships and/or network circuits; costly |
        | How | Work with your existing data networking provider; create Virtual Interfaces (VIFs) to connect to VPCs (private VIFs) or other AWS services like S3 or Glacier (public VIFs) |
    - AWS Direct Connect plus a VPN.
        - 
        
        | What | IPSec VPN connection over private lines (Direct Connect) |
        | --- | --- |
        | When | Need the added security of encrypted tunnels over Direct Connect |
        | Pros | More secure (in theory) than Direct Connect alone |
        | Cons | More complexity introduced by VPN layer |
        | How | Work with your existing data networking provider |
    - AWS VPN CloudHub.
        - 
        
        | What | Connect locations in a hub and spoke manner using AWSs Virtual Private Gateway |
        | --- | --- |
        | When | Link remote offices for backup or primary WAN access to AWS resources and each other |
        | Pros | Reuses existing Internet connections; supports BGP routes to direct traffic |
        | Cons | Dependent on Internet connections; no inherent redundancy |
        | How | Assign multiple Customer Gateways to a Virtual Private Gateway, each with their own BGP ASN and unique IP ranges |
    - Software VPN.
        - 
        
        | What | You must provide your own endpoint and software |
        | --- | --- |
        | When | You must manage both ends of the VPN connection for compliance reasons or you want to use a VPN option not supported by AWS |
        | Pros | Ultimate flexibility and manageability |
        | Cons | You must design for any needed redundancy across the whole chain |
        | How | Install VPN software via Marketplace on an EC2 instance |
    - Transit VPC.
        - 
        
        | What | Common strategy for connecting geographically dispersed VPCs and locations to create a global network transit center |
        | --- | --- |
        | When | Locations and VPC-deployed assets across multiple regions that need to communicate with one another |
        | Pros | Ultimate flexibility and manageability but also AWS-managed VPN hub-and-spoke between VPCs |
        | Cons | You must design for any redundancy across the whole chain |
        | How | Providers like Cisco, Juniper Networks, and Riverbed have offerings which work with their equipment and AWS VPC |
    - VPC Peering.
        - For inter-region VPC peering there are some limitations:
            - You cannot create a security group rule that references a peer security group.
            - Cannot enable DNS resolution.
            - Maximum MTU is 1500 bytes (no jumbo frames support).
            - Limited region support.
        - VPC peering connection can be added to route tables – shows as a target starting with “pcx-“
        
        | What | AWS-provided network connectivity between VPCs |
        | --- | --- |
        | When | Multiple VPCs need to connect with one another and access their resources |
        | Pros | Uses AWS backbone without traversing the internet |
        | Cons | Transitive peering is not supported |
        | How | VPC Peering request made; accepter request (either within or across accounts) |
    - AWS PrivateLink.
        - 
        
        | What | AWS-provided connectivity between VPCs and/or AWS services using interface endpoints |
        | --- | --- |
        | When | Keep private subnets truly private by using the AWS backbone rather than using the public internet |
        | Pros | Redundant; uses AWS backbone |
        | Cons |  |
        | How | Create endpoint for required AWS or Marketplace service in all required subnets; access via the provided DNS hostname |
    - VPC Endpoints
    - You can’t enable flow logs for VPC’s that are peered with your VPC unless the peer VPC is in your account.
    - Not all traffic is monitored, e.g. the following traffic is excluded:
        - Traffic that goes to Route53.
        - Traffic generated for Windows license activation.
        - Traffic to and from 169.254.169.254 (instance metadata).
        - Traffic to and from 169.254.169.123 for the Amazon Time Sync Service.
        - DHCP traffic.
        - Traffic to the reserved IP address for the default VPC router.

Security, Identity, and Compliance:

- AWS Artifact
    - AWS Artifact is **a web service that enables you to download AWS security and compliance documents such as ISO certifications and SOC reports**
- AWS Audit Manager
    - AWS Audit Manager **helps you continuously audit your AWS usage to simplify how you assess risk and compliance with regulations and industry standards**. Audit Manager automates evidence collection to make it easier to assess if your policies, procedures, and activities, also known as controls, are operating effectively
- AWS Certificate Manager (ACM)
    - Create, store, and renew SSL/TLS X.509 certificates
    - **Public certificates** are signed by the AWS public Certificate Authority.
- AWS CloudHSM
    - cloud-based hardware security module that provides secure cryptographic key storage and operations within a tamper-resistant hardware device. This service helps you meet corporate, contractual, and regulatory compliance requirements for data security by using FIPS 140-2 Level 3 validated HSMs
    - AWS CloudHSM is recommended when you need to control and manage your own encryption keys in single-tenant hardware, or when you have compliance requirements that cannot be met by AWS KMS.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/828628b0-1eef-4484-89d0-6a7315cad598/03053286-1d27-47b4-bace-14115e7edaf3/859c2f8d-ea7f-4465-a5be-0e9907a3659a.png)
    
- Amazon Cognito
    - Amazon Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.
    - Amazon Cognito provides authentication, authorization, and user management for your web and mobile apps.
    - Your users can sign in directly with a user name and password, or through a third party such as Facebook, Amazon, or Google.
    - Two main components of AWS Cognito are user pools and identity pools:
        - User pools are user directories that provide sign-up and sign-in options for your app users.
        - Identity pools enable you to grant your users access to other AWS services.
    - Amazon Cognito Sync is an AWS service and client library that enables cross-device syncing of application-related user data.
- Amazon Detective
    - Amazon Detective **helps you analyze, investigate, and quickly identify the root cause of security findings or suspicious activities**. Detective automatically collects log data from your AWS resources
- AWS Directory Service
    - AWS Directory Service **provides multiple directory choices for customers who want to use existing Microsoft AD or Lightweight Directory Access Protocol (LDAP)–aware applications in the cloud**. It also offers those same choices to developers who need a directory to manage users, groups, devices, and access
- AWS Firewall Manager
    - AWS Firewall Manager is **a security management service which allows you to centrally configure and manage firewall rules across your accounts and applications in AWS Organization**
- Amazon GuardDuty
    - Intelligent threat detection service.
- AWS IAM Identity Center (AWS Single Sign-On)
    - It is **a single place where you can assign your workforce users, also known as workforce identities, consistent access to multiple AWS accounts and applications**. IAM Identity Center is offered at no additional charge
    - **IAM Identity Center is not a Principal like IAM Users and Roles**. Instead it's a way to connect a human user to a Role, which can then be used to access the AWS console or services via the cli or sdk. The users that are managed in IAM Identity Center are not IAM Users
- AWS Identity and Access Management (IAM)
    - By default, all requests are implicitly denied.
    - An explicit allow in an identity-based or resource-based policy overrides this default.
    - If a permissions boundary, Organizations SCP, or session policy is present, it might override the allow with an implicit deny.
    - An explicit deny in any policy overrides any allows.
    - Lock away your AWS account root user access keys.
    - Use roles to delegate permissions.
    - Grant least privilege.
    - Get started using permissions with AWS managed policies.
    - Validate your policies.
    - Use customer managed policies instead of inline policies.
    - Use access levels to review IAM permissions.
    - Configure a strong password policy for your users.
    - Enable MFA.
    - Use roles for applications that run on Amazon EC2 instances.
    - Do not share access keys.
    - Rotate credentials regularly.
    - Remove unnecessary credentials.
    - Use policy conditions for extra security.
    - Monitor activity in your AWS account.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/828628b0-1eef-4484-89d0-6a7315cad598/421bc326-2141-4f5d-9fb3-3f622958ba26/223b7a95-df37-4d6b-b81e-6f500c585d61.png)
    
- Amazon Inspector
    - automated security assessment service that helps improve the security and compliance of applications deployed on AWS.
    - Amazon Inspector produces a detailed list of security findings prioritized by level of severity.
- AWS Key Management Service (AWS KMS)
    - aws kms encrypt
    - aws kms decrypt
    - aws kms re-encrypt
    - aws kms generate-data-key
    - generate-data-key-without-plaintext
    - **KMS Envelope Encryption - KMS generates data keys which are used to encrypt data and are themselves encrypted using your master keys in KMS**
    - 1000 KMS keys per account per region.
- Amazon Macie
    - Amazon Macie is a data security service that discovers sensitive data using machine learning and pattern matching, provides visibility into data security risks, and enables automated protection against those risks
- AWS Network Firewall
    - AWS Network Firewall (ANF) **provides the customer deep packet inspection (DPI), application protocol detection, domain name filtering, and intrusion prevention system (IPS)**
- AWS Resource Access Manager (AWS RAM)
    - AWS Resource Access Manager (RAM) is a service that enables you to share AWS resources easily and securely with any AWS account or within your AWS Organization.
- AWS Secrets Manager
    - 
- AWS Security Hub
    - AWS Security Hub is a cloud security posture management (CSPM) service that performs automated, continuous security best practice checks against your AWS resources to help you identify misconfigurations, and aggregates your security alerts (i.e. findings) in a standardized format so that you can more easily enrich, investigate, and remediate them
    - **AWS Security Hub provides a broader view of security and compliance across your AWS accounts, while Amazon GuardDuty focuses on threat detection within your AWS environment**
- AWS Shield
    - AWS Shield provides expanded DDoS attack protection for your AWS resources. Get 24/7 support from our DDoS response team and detailed visibility into DDoS events.
    - two tiers of AWS Shield – Standard and Advanced.
        - Advanced - Provides higher levels of protection against attacks targeting applications running on Amazon Elastic Compute Cloud (EC2), Elastic Load Balancing (ELB), Amazon CloudFront, AWS Global Accelerator and Amazon Route 53 resources
- AWS WAF
    - AWS WAF is a web application firewall service that helps protect your web apps from common exploits that could affect app availability, compromise security, or consume excessive resources.
    - When you use AWS WAF on Amazon CloudFront, rules run in all AWS Edge Locations, located around the world close to end users.

Serverless:

- AWS AppSync
    - AWS AppSync **enables developers to connect their applications and services to data and events with secure, serverless and high-performing GraphQL and Pub/Sub APIs**. You can do the following with AWS AppSync: Access data from one or more data sources from a single GraphQL API endpoint
- AWS Fargate
- AWS Lambda
    
    Services that Lambda reads events from:
    
    - [**Amazon Kinesis**](https://docs.aws.amazon.com/lambda/latest/dg/with-kinesis.html)
    - [**Amazon DynamoDB**](https://docs.aws.amazon.com/lambda/latest/dg/with-ddb.html)
    - [**Amazon Simple Queue Service**](https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html)
    - *for other services such as Amazon S3 and SNS, the function is invoked asynchronously, and the configuration is made on the source (S3/SNS) rather than Lambda.*
    - Lambda aliases are pointers to a specific Lambda version
    - With the introduction of alias traffic shifting, it is now possible to trivially implement canary deployments of Lambda functions
    - By updating additional version weights on an alias, invocation traffic is routed to the new function versions based on the weight specified
    - Upload the zip file straight to Lambda if it’s less than 50MB, otherwise upload to S3.
    - With Application Auto Scaling, you can create a target tracking scaling policy that adjusts provisioned concurrency levels automatically, based on the utilization metric that Lambda emits.
    - *If a Lambda function needs to connect to a VPC and needs Internet access, make sure you connect to a private subnet that has a route to a NAT Gateway (the NAT Gateway will be in a public subnet).*
    - Functions can be registered to target groups using the API, AWS Management Console or the CLI.
    - By default, health checks are disabled for target groups of type lambda

Storage:

- AWS Backup
    - Applies on
        - Amazon EC2 instances.
        - Amazon EBS volumes.
        - Amazon RDS databases.
        - Amazon DynamoDB tables.
        - Amazon Neptune databases.
        - Amazon DocumentDB databases.
        - Amazon EFS file systems.
        - Amazon FSx for Lustre and Windows File Server file systems.
        - AWS Storage Gateway volumes.
        - VMware workloads on-premises and in VMware Cloud on AWS.
        - Amazon S3 buckets.
    - AWS Backup can be used to copy backups across multiple AWS services to different Regions.
- Amazon Elastic Block Store (Amazon EBS)
    - 
    
    RAID can be used to increase IOPS, however RAID 1 does not. For example:
    
    – RAID 0 = 0 striping – data is written across multiple disks and increases performance but no redundancy.
    
    – RAID 1 = 1 mirroring – creates 2 copies of the data but does not increase performance, only redundancy.
    
    HDD, Cold – (SC1) provides the lowest cost storage and low performance
    
- Amazon Elastic File System (Amazon EFS)
    - You can mount an AWS EFS filesystem from on-premises systems ONLY if you are using AWS Direct Connect or a VPN connection
- Amazon FSx (for all types)
    - Amazon FSx for Windows File Server for Windows-based applications
    - Amazon FSx for Lustre for compute-intensive workloads.
        - Lustre provides a high-performance file system optimized for fast processing of workloads such as machine learning, high performance computing (HPC), video processing, financial modeling, and electronic design automation (EDA).
        - Amazon FSx works natively with Amazon S3, letting you transparently access your S3 objects as files on Amazon FSx to run analyses for hours to months.
        - Can be deployed in persistent or scratch.
            - Scratch is designed for best performance for short term or temporary use cases
            - Auto heals when hardware failure occurs
            - Longer term use cases — Persistant
                - Provides HA in one AZ and self-healing
    - Amazon FSx for NetApp ONTAP.
    - Amazon FSX for OpenZFS.
- Amazon S3 ————————————————————————-
- Amazon S3 Glacier —————————————————————————-
- AWS Storage Gateway
    - enables hybrid storage between on-premises environments and the AWS Cloud.
    - 
    
    | New Name | Old Name | Interface | Use Case |  |
    | --- | --- | --- | --- | --- |
    | File Gateway | None | NFS, SMB | Allow on-prem or EC2 instances to store objects in S3 via NFS or SMB mount points | Used for flat files only, stored directly on S3. 
    The maximum size of an individual file is 5 TB |
    | Volume Gateway Stored Mode | Gateway-Stored Volumes | iSCSI | Asynchronous replication of on-prem data to S3 | block-based volumes |
    | Volume Gateway Cached Mode | Gateway-Cached Volumes | iSCSI | Primary data stored in S3 with frequently accessed data cached locally on-prem |  |
    | Tape Gateway | Gateway-Virtual Tape Library | ISCSI | Virtual media changer and tape library for use with existing backup software | media changer and tape drives. Supported by NetBackup, Backup Exec, Veeam etc |
- AWS Ops Works
    - AWS OpsWorks is a configuration management service that provides managed instances of these two open-source tools (Chef and Puppet).
    - End of life on May 26

Understand all gateways

NAT
Virtual
Direct Connection
