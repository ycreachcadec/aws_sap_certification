# Cheat sheet 
- Lambda Alias supports canary deployments
- EFS allows cross region replication
- Aurora Global Database provides cross-region read replicas and failover capabilities
- RDS supports cross-region read replicas which can be promoted to master in case of a disaster. This can be done using Route 53, CloudWatch, and lambda functions
- Cloudformation stack policy can prevent stack resources from being unintentionally updated or deleted during a stack update. Stack Policy only applies for Stack updates and not stack deletion
- Amazon WorkSpaces provides a virtual workspace for varied worker types, especially hybrid and remote workers
- Amazon OpenSearch est le successeur du service ElasticSearch
- AmazonOpensearch = OpenSearch managé 
- AmazonOpensearch a une GUI pour afficher des dashboards (Intégrable avec Cognito ou SAML)
- Amazon Connect : Central d'appel as a service
- Amazon Pinpoint est un service de communication marketing flexible et évolutif qui vous connecte avec vos clients par e-mail, SMS, notifications push
- built-in time series analytics : utiliser TimeStreams
- You can use WorkSpaces to provision virtual desktops for users.
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
