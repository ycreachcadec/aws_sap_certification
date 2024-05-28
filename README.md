# Cheat sheet 
- Lambda Alias supports canary deployments
- EFS allows cross region replication
- Aurora Global Database provides cross-region read replicas and failover capabilities
- RDS supports cross-region read replicas which can be promoted to master in case of a disaster. This can be done using Route 53, CloudWatch, and lambda functions
- Cloudformation stack policy can prevent stack resources from being unintentionally updated or deleted during a stack update. Stack Policy only applies for Stack updates and not stack deletion
- Amazon WorkSpaces provides a virtual workspace for varied worker types, especially hybrid and remote workers
- Amazon OpenSearch est le successeur du service ElasticSearch
- AmazonOpensearch = Stack ELK full managé
- AmazonOpensearch a une GUI pour afficher des dashboards (Intégrable avec Cognito ou SAML)
- Amazon Connect : Central d'appel as a service
- Amazon Pinpoint est un service de communication marketing flexible et évolutif qui vous connecte avec vos clients par e-mail, SMS, notifications push
- built-in time series analytics : utiliser TimeStreams
- You can use WorkSpaces to provision virtual desktops for users
- AWS Step Functions can help coordinate a series of Lambda functions in a specific order. Multiple functions can be invoked sequentially, passing the output of one to the other, and/or in parallel, while the state is being maintained by Step Functions.
- Export logs from Cloudwatch to S3 can take up to 12hours
- GuardDuty can automatically respond to threats by taking actions such as blocking IP addresses, disabling IAM users, or sending notifications to you with the help of services like Lambda, Eventbridge, etc.
- Amazon Detective : investigation tools for security issues (ML based)
- Amazon GuardDuty : parse metrics & logs to detect security breach (ML based)
- Aurora scale de 64To à 128To (based on Engine)
- Amazon Outposts propose S3
- In an active-active configuration, requests made to an S3 Multi-Region Access Point’s global endpoint automatically route over the AWS global network to the nearest S3 bucket.
- RDS Cross-Region Read Replicas create an asynchronously replicated read-only DB instance in a secondary AWS Region.
- RDS cross region replications : A source DB instance can have cross-region read replicas in multiple AWS Regions.
- Blue/Green deployment is possible in RDS GUI
- AWS Kinesis Data Streams : synchronously replicates data across three AZs in an AWS Region
- Multiple Kinesis Data Streams applications can consume data from a stream, so that multiple actions, like archiving and processing, can take place concurrently and independently.
- Kinesis Data Streams s'intègre à KMS
- Kinesis Data Streams s'intègre aux VPC endpoints
- Kinesis Data Streams s'intègre à CloudTrail
- Kinesis Agent is a pre-built Java application that offers an easy way to collect and send data to the Kinesis stream.
- Kinesis Producer Library (KPL) : is an easy-to-use and highly configurable library that helps to put data into a Kinesis stream.
- Kinesis Client Library (KCL)is a pre-built library with multiple language support
- Kinesis Connector Library : is a pre-built library that helps you easily integrate Kinesis Streams with other AWS services and third-party tools. (deprecated by Firehose)
- AWS RAM permet de partager des outbounds resolver 
- Token Vending Machine = Cognito ( Cognito renvoi un token Cognito que le client utilise sur l'API STS pour récupérer ses credentials temporaires )
- AWS Simple : Pas de MFA, RDS SQL Server ou de AwS SSO
- Redshift est multi AZ
- 250 MB of storage max for lambda
- Lambda container (max 10Go of all uncompressed layers)
- Lambda 50mo via GUI for upload (use S3 up to 250mo) 
- SCP does not impact service linked roles
- SNI does not work for Classic load balancer ( work for ALB / NLB )
- AWS Step Functions : Standard Workflow state machine does not support multiple concurrent executions with the same name.
- CloudWatch Synthetics canaries are configurable scripts that run on a schedule, to monitor endpoints and APIs.
- Timestream can periodically and automatically schedule queries to perform real-time analytics on incoming data.
- AWS batch peut avoir des dépendances entres ces jobs 
- you can’t deploy an application to your on-premises servers using Elastic Beanstalk.
- AWS Systems Manager est très orienté AWS et on-prem
- The Route 53 health check has an overall lower request count compared to using the target group health check.
- Amazon EKS Anywhere is not designed to run in the AWS cloud. It does not integrate with the Kubernetes Cluster API Provider for AWS.
- Amazon ECS Anywhere isn’t designed to run on AWS Outposts
- Route53 has now a full integration of DNSSEC 
-  multicast domain is primarily used in delivering a single stream of data to multiple receiving computers simultaneously.
- CNAME record cannot be used for apex domain configuration in Amazon Route 53. 
- Alexa for Business != Amazon Lex (Alexa for Business est un facilitateur d'usage de Alexa dans un contexte Business)
- AWS Elemental MediaConnect is a high-quality transport service for live video.
- Amazon Polly is a machine learning service, it is quite limited as it just turns text into lifelike speech
-  Amazon Comprehend is used to derive and understand valuable insights from text within documents
- When you configure an Amazon S3 bucket for website hosting, you must give the bucket the same name as the record that you want to use to route traffic to the bucket. (No CloudFront scenario)
- SSM patch manager : You can install patches individually or to large groups of instances by using Amazon EC2 tags
- AWS VM Import/Export does not support synching incremental changes from the on-premises environment to AWS
- You cannot modify the trust policy of a service-linked role
- For billing purposes, the consolidated billing feature of AWS Organizations treats all the accounts in the organization as one account
- AWS does not recommend to attach the SCPs at root level
- Multi-account, multi-region data aggregation in AWS Config enables you to aggregate AWS Config data from multiple accounts and regions into a single account.
- An aggregator is a new resource type in AWS Config that collects AWS Config data from multiple source accounts and regions. Create an aggregator in the Region where you want to see the aggregated AWS Config data. While creating an aggregator, you can choose to add either individual account IDs or your organization.
- Amazon Inspector is used as an automated vulnerability management service that continually scans AWS workloads for software vulnerabilities
- With Amazon Aurora global Database, you can promote one of the secondary Regions to the primary role to take full read/write workloads in under a minute
- You can create CNAME records only for subdomains
- The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database.
- CloudFront a son propre mécanisme de géorestriction IP
- Traffic miroring peut être setup au niveau de l'ENI
- Cloudwatch Tail - équivalent du tail -f dans un OS
- DMS allows to migrate from relational database to Dynamodb
- Cloudwatch Metric filters - Permet de convertir un string pattern dans les logs en une metric (à mettre derrière une alarme par exemple)
- AWS Global tables : multi master (multi writes possible) 
- AWS SAM is an extension of AWS CloudFormation
- AWS SCT can be used on-prem to prepare data to be injected to S3 or snowball edge
- ECS task - possibility to pass ARN of parameter store or secret in secretsmanager to pass sensitive secret
- Redshift do not provide real-time data analytics
- AWS Config allows to track changes to WAF
- AWS Firewall Manager is primarily used to manage your Firewall across multiple AWS accounts under your AWS Organizations
- CodeCommit - can configure for code pushes or other events trigger actions, such as SNS or invoking a function in AWS Lambda
- AWS Fargate only supports the “awsvpc” network mode
- You can enable API caching in Amazon API Gateway to cache your endpoint’s responses (default ttl : 300sec, max 3600sec)
- DynamoDB Accelerator can be expensive (careful on COST related question)
- Amazon Cognito identity pools provide temporary AWS credentials for users who are guests (unauthenticated) and for users who have been authenticated and have received a token.
- IAM Identity Center supports single sign-on to business applications through web browsers only
- AWS IAM Identity Center supports only SAML 2.0–based applications
- Amazon Cognito Identity Pool will provide temporary tokens to federated users for accessing AWS resources
- Cloudfront - multiple origins with failover possible (origin group with two origins with one as the primary origin and the other as the second origin which CloudFront automatically switches to when the primary origin fails)
- SQS Dead-letter queues : debugging your application or messaging system - let you isolate unconsumed messages to determine why their processing doesn’t succeed.
- sqs delivery delay : delay before a consumer of the queue can access the message
- Cloudfront field-level encryption intercepts the form POST and encrypts sensitive data with the public RSA key and replaces fields in the form post with encrypted ciphertext. The form POST ciphertext is then sent to origin servers.
- Cloudfront : The shorter the cache duration, the more frequently CloudFront forwards another request to your origin to determine whether the object has changed and, if so, to get the latest version.
- After you configure a bucket to be a Requester Pays bucket, requesters must include x-amz-request-payer in their requests either in the header, for POST, GET and HEAD requests, or as a parameter in a REST request to show that they understand that they will be charged for the request and the data download.
-  Amazon Fraud Detector uses machine learning that automates the detection of potentially fraudulent activities online
- RedShift is not applicable to OLTP but rather with OLAP.
- With API Gateway, you can send the stream to an Amazon Kinesis data stream on which you can group requests in batches so there will be a decrease in requests in Lambda.
Geoproximity vs Geolocation WTF
- AWS Migration Hub (Migration Hub) provides a single place to discover your existing servers, plan migrations, and track the status of each application migration. ( AWS discovery service is part of this service )
-  Application Load Balancer cannot serve traffic to EC2 instances on a different region even with Inter-Region VPC peering
Cloufront can target API Gateway?
- You can use CRR to change account ownership for the replicated objects to protect data from accidental deletion.
- AWS Backup supports continuous backups and point-in-time recovery (PITR) in addition to snapshot backups.
- AWS Backup continuous backups - works by first creating a full backup of your resource and then constantly backing up your resource’s transaction logs - 1sec restauration precision - up to 35 days in the past
- Timestream services do not have the capacity to analyze real-time streaming data
- CHAP is primarily used to authenticate iSCSI
- API Gateway WebSocket APIs are bidirectional. A client can send messages to a specific service, and services can independently send messages to clients
- AWS IoT Greengrass enables your devices to collect and analyze data closer to where that data is generated, react autonomously to local events, and communicate securely with other devices on the local network
- Route53 - multivalue answer routing also lets you check the health of each resource, so Route 53 returns only value for healthy resources
- For transferring small files to Snowball edge, AWS recommends transferring in batches. Each copy operation has some overhead because of encryption. To speed up the process of transferring small files to your AWS Snowball Edge device, you can batch them together in a single archive. (auto-extracted when they are imported into Amazon S3)
- NLB + EIP - Maximum 1 EIP / AZ
- Amazon Transcribe is an AWS service that makes it easy for customers to convert speech to text.
- AWS IQ is a freelancing platform that provides hands-on help from AWS experts
- Amazon AppFlow : sync SaaS applications like Salesforce, SAP, Zendesk, Slack, and ServiceNow, and AWS services
- Amazon SageMaker build and train machine learning models.
- Amazon SageMaker : integrated Jupyter notebook instance.
- AWS Proton : A managed delivery service for deploying container and serverless applications.
- Conditional forwarder = conf DNS AD pas route53 - équivalent avec AWS outbound resolver : forwarding rule
- Import a certificate from a third-party certificate authority into ACM or the IAM certificate store
- OpenSearch : un fork d'Elasticsearch et de Kibana.
- ACM : you can generate public or private SSL/TLS certificates that you can use to secure your site.
- Amazon RDS database does not support Oracle RAC.
- You can attach all your hybrid connectivity (VPN and Direct Connect connections) to a single Transit Gateway
- Transit Gateway enables customers to connect thousands of VPCs
- Transit Gateways within an AWS Region cannot be peered
- The default limit for shared VPC subnets is 100
- There is a default limit of 50 VPC peering for each VPC
- Lambda - In a single account with the default concurrency limit of 1000 concurrent execution
- Amazon Translate is  a text translation service that uses machine learning to provide translation on demand (Amazon Translate != Amazon Transcribe)
- dynamic website and not static - Client can POST or PUT 
- If your workloads require fast, POSIX-compliant file system access to your S3 buckets => FSx for Lustre to link your S3 buckets to a file system and keep data synchronized between the file system and S3 in both directions
- A multi-attached EBS volume can only be attached in 16 EC2 instances simultaneously
- AWS Config provides AWS managed rules, which are predefined, customizable rules
- An Aurora cluster can recover in less than 1 minute even in the event of a complete regional outage
- MySQL promote read replica in another region - non automatisé + necessite reboot de la RDS
- Amazon EMR -> spot on task nodes reste quelque chose de high available
- Direct Connect require a network device in data center on-prem that supports Border Gateway Protocol (BGP) and BGP MD5 authentication
- A Throughput Optimized EBS volume cannot be shared between EC2 instances
- The Amazon EBS Multi-Attach feature is only applicable for Provisioned IOPS SSD volumes.
- API Gateway : Resource policies let you create resource-based policies to allow or deny access to your APIs and methods from specified source IP addresses or VPC endpoints
- Possibilité depuis la console Cost de creer des generated tags ajoutés automatiquement aux ressources (depuis le compte master d'une orga) 
- AWS Tag Editor is a feature that allows you to add, edit, or remove tags from your AWS resources
- Amazon Lightsail is a cost-effective solution for deploying simple web applications. AWS recommends it for DEV/Test environments only
- You can’t use a self-signed certificate for HTTPS communication between CloudFront and your origin.
- Jupyter notebooks are primarily used to prepare your data and write code to train models. 
- Most of the time, you need to set up a custom Kinesis Video Streams Producer client in order to send data to a Kinesis Video Stream
- AWS SFTP -> S3 est possible (aws recommande https plutôt que sftp)
- Redshift - solution native de copy de snapshot cross region ( définir une clé KMS de la région destination si donnée chiffrée avec KMS )
- Rolling updates enable you to specify whether AWS CloudFormation updates instances that are in an Auto Scaling group 
- VPC flow log data only contain OSI Layer 4 (Transport) information.
- ALB access logs only contains the request path and some headers on the logs. The payload itself, not the payload
- CloudFront is case-sensitive when caching objects. There is no "case-insensitive" option in CloudFront.
- Cloudtrail logs to S3 -> SSE-S3 ou SSE-KMS
- AWS AppSync service is a fully managed service for developing GraphQL APIs
- AWS Storage Gateway offers file-based file gateways (Amazon S3 File and Amazon FSx File)
- You need to enable “All features” on the AWS Organization to be able to create and apply SCP for each subsidiary.
- Organization : la création du role OrganizationAccountAccessRole  n'est pas automatique
- Amazon WorkSpaces secure Desktop-as-a-Service (DaaS)
- AWS Application Migration Service is a migration tool, it is used to replicate or mirror your on-premises VMs to the AWS cloud. 
- S3DistCp tool is used to copy large amounts of data from Amazon S3 into HDFS.
- Amazon Data Lifecycle Manager (DLM) for EBS Snapshots provides a simple, automated way to back up data stored on Amazon EBS volumes. You can define backup and retention schedules for EBS snapshots by creating lifecycle policies based on tags. With this feature, you no longer have to rely on custom scripts to create and manage your backups.
- AWS SSM Automation compatible avec event bridge cron 
- Enabling object versioning on S3 does not invalidate presigned URL
- one virtual private gateway (VGW) can be attached to a VPC at a time.
- AWS IoT rules to route data from your connected things. A rule includes one or more actions that AWS IoT performs when enacting the rule. For example, you can insert data into a DynamoDB table, write data to an Amazon S3 bucket, publish to an Amazon SNS topic, or invoke a Lambda function.
- If you configure CloudFront to serve HTTPS requests using SNI, CloudFront associates your alternate domain name with an IP address for each edge location. The IP address to your domain name is determined during the SSL/TLS handshake negotiation and isn’t dedicated to your distribution.
- By default, an SCP named FullAWSAccess is attached to every root, OU, and account.
- Aurora : automated backups only occur once every day during the defined backup window. You can’t configure it to run every 5 minutes.
- Amazon MQ is a managed message broker service that provides compatibility with many popular message brokers. AWS recommends Amazon MQ for migrating applications from existing message brokers that rely on compatibility with APIs such as JMS or protocols such as AMQP, MQTT, OpenWire, and STOMP.
- An Oracle Real Application Clusters (RAC) One Node option provides virtualized servers on a single machine. This provides an ‘always on’ availability for single-instance databases for a fraction of a cost.
- Amazon FSx for Windows server does not have option to Dynamically Allocate the file system size
- AWS IoT Core is a managed cloud service that enables connected devices to securely interact with cloud applications and other devices.
- With AWS IoT Core, your applications can interact with all your devices even when disconnected.
- AWS CodeBuild is a fully managed build service in the cloud. CodeBuild compiles your source code, runs unit tests, and produces artifacts that are ready to deploy.
- Amazon EFS uses the NFS protocol which is primarily used by Linux AMIs. This filesystem does not support Windows ACLs.
- Amazon FSx for Lustre is POSIX-compliant file system that runs on Lustre. It can only be used by Linux-based instances.
- Amazon Kinesis Data Stream: You can make your streaming data available to multiple real-time analytics applications, to Amazon S3, or to AWS Lambda within 70 milliseconds of the data being collected.
- Kinesis Client Library (KCL) : For custom consumers -> take care of many of the complex tasks associated with distributed computing. (load balancing across multiple consumer application instances, responding to failures, reacting to resharding...)
- You can’t use Amazon Quicksight to query data lakes from AWS Lake Formation. 
- API Gateway peut s'intégrer avec SQS (anti pattern lors d'usage real time, les messages n'étant pas traités dans l'ordre)
- Amazon EMR clusters can read and process Amazon Kinesis streams directly
- Dynamodb supports document stores such as JSON, XML, or HTML in these data types
- DocumentDb does not offer a native cross-region replication or multi-region operation. You can only automate snapshots to another region which can take some time to restore in the event of regional failure
- s3  there is a delay of up to 15 minutes in Cross-Region Replication
- Amazon S3 will reject any requests made over HTTP when using SSE-C
- PowerUserAccess permet de creer des service link roles
- Import de CMK dans KMS gen dans on-prem HSM : prerequis: creer dans KMS CMK with no key materials and EXTERNAL origin
- S3 bucket policy : aws:SourceIp n'est valable que pour les IP publiques 
- EFS has file locking capabilities, it does not have file versioning features
- Amazon EventBridge cannot directly invoke AWS Fargate tasks
- AWS Step Function can be trigger for Amazon EventBridge
- AWS Audit Manager is used to map compliance requirements to AWS usage data with prebuilt and custom frameworks and automated evidence collection
- AWS Step Functions offers built-in mechanisms for error handling and retry policies, which are essential for managing failures in any of the workflow steps
- Migration Evaluator (formerly TSO Logic) is a migration assessment service that customers can request a business case from when considering to move on-premise workloads to the cloud. The service helps identify the least expensive deployment and purchasing options and helps predict future-state cloud costs
- AWS Trusted Advisor is primarily used to check if your cloud infrastructure is in compliance with the best practices and recommendations across five categories: cost optimization, security, fault tolerance, performance, and service limits
- AWS VPN CloudHub allows to connect your on-premises network to multiple VPCs in different AWS Regions using a central hub configuration
- AWS Application Migration Service (MGN) is a highly automated lift-and-shift (rehost) solution 
- By default, the burst concurrency for Lambda functions is between 500-3000 requests per second (depending on region)
- AWS Amplify Console offers a simple Git-based workflow for building and deploying static web apps to AWS
- Alexa for Business gives you the tools you need to manage Alexa devices, enroll your users, and assign skills at scale for your organization
- Amazon Rekognition is used to identify persons on photos or videos
- OpenSearch is a fully open-source search and analytics engine for use cases such as log analytics, real-time application monitoring, and clickstream analysis
- Neptune DB is designed for graph application and loading CSV formatted data.
- Amazon Kinesis Data Firehose has a feature to buffer data and supports data transformation in near-real-time
- Amazon Kinesis Data Stream offer longer-term, durable storage
- You cannot set Auto Scaling for the master database on Amazon Aurora. You can only manually resize the instance size of the master node
- Aurora : scaling sur les replicas uniquement
- Amazon Aurora does not need to replay the redo log from the last database checkpoint (typically five minutes) so restart is very fast
- Amazon RDS Proxy instance maintains a pool of established connections to your RDS database instances, reducing the stress on database compute and memory resources that typically occurs when new connections are established.
- With RDS Proxy, you can build applications that can transparently tolerate database failures without needing to write complex failure-handling code. The proxy automatically routes traffic to a new database instance while preserving application connections. It also bypasses Domain Name System (DNS) caches to reduce failover times by up to 66% for Aurora Multi-AZ databases
- Optimized Reads and Optimized Writes exists in Amazon RDS
- You can use Glacier Select to perform filtering operations using simple Structured Query Language (SQL)
- ASG porte une fonction "Scheduled scaling" intégrée 
- AWS Application Migration Service (MGN) is a highly automated lift-and-shift (rehost) solution
- Amazon Redshift only has cross-region backup feature (using snapshots), not Cross-Region Replication. Redshift can't replicate to another Redshift cluster 
- There are a lot of features in IBM MQ that are not available in Amazon SQS
---
- AWS Batch is designed to easily and efficiently run hundreds of thousands of batch computing jobs on AWS but not with Lambda functions
- By reserving your read and write capacity units ahead of time, you realize significant cost savings compared to on-demand provisioned throughput settings
- AppSync supports real-time chat applications
- With managed GraphQL subscriptions, AWS AppSync can push real-time data updates over Websockets to millions of clients
- It is possible to write TypeScript or Python code that will define AWS resources. Convert these codes to AWS CloudFormation templates by using AWS Cloud Development Kit (AWS CDK)
- Consided billing - only work if both accounts match the same AZ
- EC2Rescue can help you diagnose and troubleshoot problems on Amazon EC2 Linux and Windows Server instances
- It is possible to configure the database tier to use sharding, which will distribute the incoming load to multiple RDS MySQL instances.
- An Internet gateway is not required to establish a hardware VPN connection
- AWS AppSync is recommended for applications that are written for GraphQL APIs, not REST APIs
- Amazon API gateway - possibility to switch from regional to edge endpoints ( improve performances )
- Amazon S3 Transfer Acceleration on the S3 bucket permet d'accélérer les uploads
- When using AWS Lambda, initializing the database connection outside the event handler leverages Lambda’s ability to reuse containers for multiple invocation
- Consider using least outstanding requests (LOR) when the requests for your application vary in complexity or your targets vary in processing capability
- is not possible to update the deployment type of the FSx file system once it is created
- Amazon FSx can be mono or multi AZ
- if you want to sync an SMB to the AWS cloud. AWS DataSync offers a managed service that is designed for copying data from SMB shares to AWS
- Apache Parquet is an open-source file format that is optimized for use with big data processing frameworks. It stores data in a columnar format, which means it organizes the data by columns rather than by rows. This can lead to significant performance improvements when executing analytical queries
-  AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy to prepare and load your data for analytics
- RAM can share TGW
- AWS AppSync ne s'intègre pas directement à Lambda
- S3 Replication Time Control (S3 RTC) helps you meet compliance or business requirements for data replication and provides visibility into Amazon S3 replication times
- S3 RTC replicates most objects that you upload to Amazon S3 in seconds and 99.99 percent of those objects within 15 minutes
- S3 replication can sometimes take a couple of hours
- AWS Elemental MediaConvert is a new file-based video transcoding service aimed to replace Amazon Elastic Transcoder
- AWS Budgets can be cross account using organization
- Glue crawlers are automated data discovery tools that scan a data source to classify, group, and catalog the data within it automatically
-  Lambda functions do not, and cannot, have public IP addresses
- GW load balancer -> TG -> ASG est une archi possible 
- Amazon WorkSpaces allows you to control which IP addresses your WorkSpaces can be accessed from
- Route 53 health check can uses Amazon SNS to invoke the Lambda function in case of any issues
- you can configure CloudFront to return a custom error page
- Use origin failover to designate a primary origin for CloudFront plus a second origin that CloudFront automatically switches to when the primary origin returns specific HTTP status code failure responses.
- You can add a lifecycle hook to your Auto Scaling group so that you can perform custom actions when instances launch or terminate
- OpsCenter is more oriented towards incident management rather than an operational activity like capturing logs
---
- RDS Data API is designed to be used for Aurora Serverless service, not for RDS instances
- Cost & Usage Reports can be integrate with Amazon Athena, Redshift et Quicksight
- AWS Migration Hub helps you understand your IT environment by letting you explore information stored in the AWS Application Discovery Service repository
- AWS Systems Manager Explorer is a customizable operations dashboard that reports information about your actual AWS resources (e.g., Amazon EC2, Amazon RDS, etc.)
- AWS Data Pipeline can load data from S3 to RDS
- AWS DataSync can facilitate the copying of data from on-premises data stores to the AWS cloud, but it can’t be used to replicate an on-premises database to AWS
- AWS Well-Architected Tool allows you to monitor the status of multiple workloads across your organization and helps you understand potential risks
- CodeGuru : code review and performance optimization
- AWS Trusted Advisor is a service that gives guidance in provisioning resources that follows AWS best practices
- AWS Compute Optimizer utilisable avec EC2, EBS, task sizes of (ECS) services on AWS Fargate et lambda
- Amazon Forecast, a service that uses machine learning to generate precise time-series predictions
- serverless caching, which automatically scales a Redis cluster is possible with ElasticCache
- AWS Step Functions with Map and Parallel states can indeed help break down tasks into smaller parts
- Amazon Aurora cloning allows you to create a new cluster that uses the same Aurora cluster volume and has the same data as the original
- Amazon Aurora can be share in RAM (for a source/destination in a same region, aurora cloning is faster than snapshot copy)
- EKS Distro is a Kubernetes distribution built and powered by Amazon EKS managed, allowing you to deploy secure and reliable Kubernetes clusters in any environment (opensource)
- Amazon S3 Storage Lens is a cloud-storage analytics feature that you can use to gain organization-wide visibility into object-storage usage and activity
-  Storage Class Analysis can help in optimizing storage costs by suggesting what objects to move between storage classes
- AWS DirectConnect gateway require to set prefix lists
- AWS Migration Hub, which offers data exploration features integrated with Amazon Athena
- S3 Select is simply used to retrieve specific subsets of data from within an S3 object
- Cloudformation stackset - automatic deployment possible at organization level
- Security Hub has integration with Organizations, so you can use one single Security Hub dashboard to monitor for both security issues in one place
- Audit Manager to automate evidence collection and to provide continuous auditing and compliance
- Timestream can be up to a thousand times faster than a relational database
-  Timestream can periodically and automatically schedule queries to perform real-time analytics on incoming data
-  resource-based policies are not available for DynamoDB tables
---
- Cloudfront - Field-level encryption :  The sensitive information provided by your clients is encrypted at the edge closer to the user and remains encrypted throughout your entire application stack, ensuring that only applications that need the data—and have the credentials to decrypt it—are able to do so
- EC2 instances in an EMR cluster are organized into node types. There are three: the master node, the core node, and task nodes
- EMR : The collection of EC2 instances that host each node type is called either an instance fleet or a uniform instance group. The instance fleets or uniform instance groups configuration is a choice you make when you create a cluster (cant change after)
- Aurora : all DB instances in a multi-master cluster must be in the same AWS Region and you can’t enable cross-region replicas from multi-master clusters
- RDS Multi-AZ deployments does is synchronous replication
- auto healing exists in opswork
- AWS Systems Manager Maintenance Windows which lets you define a schedule
- CodeDeploy permet de déployer sur des machines on-prem
- Beanstalk ne permet pas de déployer sur des machines on-prem
- AWS SAM is an extension of AWS CloudFormation, you get the reliable deployment capabilities of AWS CloudFormation
- You can also use AWS CodeStar to get started with a project structure, code repository, and a CI/CD pipeline that’s automatically configured for you
- Amazon S3 Select can only retrieve a subset of data using SQL statements
-  tape gateway in AWS Storage Gateway service is primarily used as an archive solution
- Proxy Protocol, when enabled on the ELB, allows the application server to access the original client IP address even behind the load balancer. This is crucial for recording client IPs
- AWS Data Pipeline to poll for tasks and then performs those tasks using Task Runner
- AWS Server Migration Service allows you to automate, schedule, and track incremental replications of live server volumes, making it easier for you to coordinate large-scale server migrations
- VM Import/Export permet de déployer des VMs on-prem depuis AWS
- Elastic Cache : If you require data durability, you can enable the Redis append-only file feature (AOF). When this feature is enabled, the node writes all of the commands that change cache data to an append-only file. When a node is rebooted and the cache engine starts, the AOF is “replayed”; the result is a warm Redis cache with all of the data intact
- AWS Config detection -> Event bridge -> lambda
- ASG health check type can be of type ELB
- Amazon Redshift workload management (WLM) enables users to flexibly manage priorities within workloads so that short, fast-running queries won’t get stuck in queues behind long-running queries
- An in-place upgrade involves performing application updates on live Amazon EC2 instances. A disposable upgrade, on the other hand, involves rolling out a new set of EC2 instances by terminating older instances
- An Internet gateway is not required to establish a hardware VPN connection
- AWS AppSync is recommended for applications that are written for GraphQL APIs, not REST APIs
---
- Snowball edge : You cannot export data directly from S3 Glacier. It should be first restored to S3
- You can use DataSync to copy data from on-prem over AWS Direct Connect or Internet links to AWS
- DMS allows you to stream data to Amazon Redshift from any of the supported sources including Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle, SAP ASE, and SQL Server
- Amazon Cognito supports enterprise identity providers such as Microsoft Active Directory using SAML
- AWS CodePipeline actions occur in a specified order, in serial or in parallel, as determined in the configuration of the stage
- With AWS IAM Identity Center, you can assign permissions based on the group membership in your IdP’s directory
- AWS IAM allows you to enable a separate SAML 2.0 or an Open ID Connect (OIDC) IdP for each AWS account you manage and use federated user attributes for access control.
- For convenience, use Amazon Cognito as your identity broker for almost all web identity federation scenario
- CloudFront - The proportion of requests that are served from caches to all requests is called the cache hit ratio
- Solutions to improve your cache hit ratio:
  - Increase the duration that your objects stay cached in CloudFront edge locations. You can configure your origin to add a Cache-Control max-age header to your objects, and specify the longest practical value for max-age. The shorter the cache duration, the more frequently CloudFront checks if the object has changed to get the latest version
  - Configure CloudFront to forward only the query string parameters for which your origin will return unique objects
  - Configure CloudFront to forward only specific cookies instead of all cookies to your origin. Create separate cache behaviors for static and dynamic content, and forward cookies to your origin only for dynamic content
  - Configure CloudFront to forward and cache objects based on specific headers only instead of forwarding and caching objects based on all headers
  - Remove Accept-Encoding Header when compression is not needed. When you use this configuration, CloudFront removes the header from the cache key and doesn’t include the header in origin requests
---
- You can use latency and weighted records in Amazon Route 53 together
- Step Functions : A workflow is a series of steps, with the output of one step acting as input into the next step (In Step Functions, we refer to the workflow as State machines)
- EC2ThrottledException est le message d'erreur en limitation d'IP
- Nom du LLM de AWS : Titan
- You can only use SCPs if you have enabled all features in your AWS Organization
- If you are using AWS Managed Microsoft AD Directory, you can share this directory to other VPCs and AWS accounts **within the same Region**
- CloudFormation : stacksets can be deployed to your entire organization or specific OUs
- Products created in Service Catalog are **regional**
- Transit Gateway supports both Static and BGP-based Dynamic VPN connections
- After you create a set of DHCP options, you can't modify them
- DHCP option sets for your VPCs -> passer une conf DNS aux VMs
- AmazonProvidedDNS is an Amazon Route 53 Resolver server, and this option enables DNS for instances that need to communicate over the VPC's Internet gateway.
- Si le serveur DNS d'une EC2 est on-prem, pour permettre à l'EC2 de résoudre des ressources privées Amazon, définir dans le serveur DNS on-prem forward les requêtes vers un inbound endpoint.
- Appstream require HTML5.
- Orgin Cloudfront possibe : API Gateway
- AWS Transfer Family ( FTP / SFTP / FTPS ) transfer data **in and out** of S3
- 2 solutions to migrate an on-premises ELK stack to AWS:
  - Create Amazon OpenSearch domain in AWS -> Use DMS to migrate from on-prem database (Postgre, Mysql, Mongodb... ) to OpenSarch
  - Export your data and indexes from your existing Elasticsearch. Then import it into your new OpenSearch cluster 
- use **CloudWatch Logs subscriptions** to gain access to a real-time feed of log events from CloudWatchLogs and have it delivered to other services such as an Amazon Kinesis stream, an Amazon Data Firehose, or AWS Lambda.
