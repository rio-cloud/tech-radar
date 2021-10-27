# RIO Technology Radar

* [RIO Radar Q1 2020 (current)](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fraw.githubusercontent.com%2Frio-cloud%2Ftech-radar%2Fmaster%2FRIO%2520Radar%2520Q1%25202020.csv)

* [RIO Radar Q3 2019](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fraw.githubusercontent.com%2Frio-cloud%2Ftech-radar%2Fmaster%2FRIO%2520Radar%2520Q3%25202019.csv)

* [RIO Radar Q4 2018](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fraw.githubusercontent.com%2Frio-cloud%2Ftech-radar%2Fmaster%2FRIO%2520Radar%2520Q4%25202018.csv)

* [RIO Radar Q2 2018](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fraw.githubusercontent.com%2Frio-cloud%2Ftech-radar%2Fmaster%2FRIO%2520Radar%2520Q2%25202018.csv)


## Defaults
Blips that are adopted at RIO by default and are not mentioned in every radar. New defaults are marked with (*).

#### Techniques
* Microservices

#### Platforms
* Amazon Web Services - AWS
*<br/>AWS is our default provider for IaaS and PaaS. We prefer AWS platform services over other managed services, over self-hosted OSS and over self-built solutions.*
* [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
*<br/>MongoDB Atlas is a highly available, fully managed database. Our default option for all services requiring a document database.*
* Amazon ECS
*<br/>Most of our workloads are running as containers on ECS. We like that the fully managed container scheduler frees us of the operational burden.*   
* Kafka
*<br/>Kafka is our central infrastructure, that powers our streaming, messaging, queueing and replication.*
* Amazon CloudWatch
*<br/>Although we recognise the limitation of CloudWatch, we also acknowledge that it is highly integrated with all other AWS services and provides a baseline monitoring and reaction capability valuable to us.*
* Amazon Athena (*)
*<br/>[AWS Athena](https://aws.amazon.com/de/athena/) is a managed Presto service. In combination with the AWS Glue Data Catalog it enables you to query S3 data with SQL. It supports CSV, JSON, ORC, Avro and Parquet. It is especially useful to do first data explorations.*
* Amazon Code Tools (*)
*<br/>New deployments started to use AWS CodeBuild, CodePipeline and CodeDeploy as CI/CD tool chain. This allows, that the pipelines are created via code, that is part of the service repsository.*
* Amazon Fargate (*)
*<br/>AWS Fargate is a recent entry into the docker-as-a-service space, currently limited to the US-East-1 region. For teams using AWS Elastic Container Service (ECS), AWS Fargate is a good alternative without having to manage, provision and configure any underlying EC2 instances or clusters. Fargate allows defining (ECS or EKS – ECS for Kubernetes) tasks as a Fargate type, and they will run on the AWS Fargate infrastructure. If you like the focus on business functionality that AWS Lambda gives you, Fargate is the closest you can get when applications can't be deployed as single functions.*
* Amazon Glue ETL (*)
*<br/>[AWS Glue](https://aws.amazon.com/de/glue/) is a managed ETL service. It can be used to batch process data in reoccurring jobs. Under the hood Glue runs your code in Apache Spark.*
* Amazon Quicksight (*)
*<br/>[AWS Quicksight](https://aws.amazon.com/de/quicksight/) is a cloud based BI service. In an AWS environment it is lightweight and it is able to connect to S3, S3 via Athena, Redshift and many other data sources. Quicksight enables users to query data either with SQL or with a graphical tool. Results can be visualized on Dashboards.*
* AWS DynamoDB (*)
*<br/>DynamoDB is used for all services where its capabilities are sufficient, we recommend to use it. It is a fully managed, highly scalable, low latency NoSQL database.*

#### Tools
* AWS CloudFormation
*<br/>CloudFormation is our default tool to model and provide AWS infrastructure.*
* ESLint
* Gradle
* npm
* DataDog
* AWS SNS/SQS
*<br/><a href="https://aws.amazon.com/sqs/">AWS SQS</a> allows easy integration with Lambdas and therefore allowing multiple consumers of the same asyncronous event, independent from the number of partitions like Kafka, with guaranteed at least once consumption in case of successful processing and controlled mechanism for retries other via the visibility timeout or retry policy with the option of an out of the box dead-letter queue. If in-order processing is required it allows it through the FIFO variant (this does not integrate with lambdas).*
* OpenAPI (*)
*<br/>The <a href="https://github.com/OAI/OpenAPI-Specification">OpenAPI Specification</a> (formerly known as Swagger) is a community-driven open specification within the OpenAPI Initiative, a Linux Foundation Collaborative Project.
<br/>The OpenAPI Specification (OAS) defines a standard, programming language-agnostic interface description for REST APIs, which allows both humans and computers to discover and understand the capabilities of a service without requiring access to source code, additional documentation, or inspection of network traffic. When properly defined via OpenAPI, a consumer can understand and interact with the remote service with a minimal amount of implementation logic. Similar to what interface descriptions have done for lower-level programming, the OpenAPI Specification removes guesswork in calling a service.*

#### Languages & Frameworks
* Kotlin
* Spring Boot 2
* TypeScript
* React
* Redux
* Amazon Corretto

#### Techniques
* DDD
* Continuous Delivery (*)
*<br/>If you are wondering “What comes after agile?,” you should look towards continuous delivery. While your development processes may be fully optimized, it still might take your organization weeks or months to get a single change into production. Continuous delivery focuses on maximizing automation including infrastructure as code, environment management and deployment automation to ensure your system is always ready for production. It is about tightening your feedback loops and not putting off anything until the end. Continuous delivery is not the same as continuous deployment, which means deploying every change to production. Continuous delivery is not a cowboy show. It puts you in charge of your production environment. The business can pick and choose what and when to deploy. If you think you’ve nailed agile development, but aren’t considering how to achieve continuous delivery, you really haven’t even started.*
* Multi AWS accounts (*)
*<br/>To decouple our bounded contexts and to limit the blast radius, we are moving from a single production account to multiple accounts.  One AWS account per bounded context.*
* Serverless (*)
*<br/>We want to avoid operating infrastructure ourself as much as possible, because we want to focus on writing code relevant for our business. Servless services from AWS are other service providers help with that.
<br/>Our decision to use Kafka instead of Kinesis is limiting are capability to embrace some serverless use cases.
<br/>See AWS Lambda description for more details*
* SSO federated to AD (*)
*<br/>We want to avoid the work and securty risk of manual user management in services used by employees and instead federate all logins to our AD.*
* [Feature Toggles](https://martinfowler.com/articles/feature-toggles.html) (*)
*<br/> We use [split.io](https://www.split.io/) to manage feature toggles of released applications. For short living toggles or for prototypes one could also cosider to use url based feature toggles instead.*

## Defaults on Hold
Blips that should not be adopted at RIO by default and are already removed from the radar. New defaults are marked with (*).

#### Tools
* Custom Build Images for CodeBuild (*)
*<br/>As custom build images always bear the risk to be outdated, we use the <a href="https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html">docker build images</a> provided by AWS wherever possible.*
#### Languages & Frameworks
* Node.js for services
* Spring Boot 1

#### Techniques
* Shared libraries (*)
*<br/>"Common", "General" or similar sounding libraries should be avoided if they could not be opensourced since upgrading an (internal) common library is poarticularly complex to almost impossible.*

## Archived

### Last in adopt

#### Tools
* Detekt (*)
*<br/>Decommissioned as some teams complained about the overhead compared to the value add. WE don't want to put in on hold but let the specific teams decide whether they use it or not.*

#### Languages & Frameworks

* MockK (*)
*<br/>Is used in almost every kotlin project and does not need to be mentioned as a single library.*
* Python (*)
*<br/>We don't discourage to use Python for prototyping etc. But for lambdas we prefer TypeScript over Python and Kotlin for standard services.*
* React Testing Library (*)
*<br/>Is used in almost every React project and does not need to be mentioned as a single library.*
#### Platforms

* Amazon Cognito
*<br/>Cognito is used as part of our IAM solution. No other team is affected by Cognito and any change would be limited to this context.*
* Amazon API Gateway (*)
*<br/>It should only be used by Lambdas if needed, but not for Services, where a Load balancer is more appropriate*
* Kafka Streams (*)
*<br/>We did not see enough value for the effort.*
* AWS Glue Data Catalog (*)
*<br/>We use Glue as Data Catalog for our data lake, but as typical BigData is not our daily business, we remove it from the radar.*
#### Techniques 

* TDD, BDD
*<br/>No agreement on a strong adopt recommendation. Will be addressed as part of a code quality initiative.*
* Immutable data structures (*)
*<br/>It is in use but as a programming style, does not need to be enforced via the Technology Radar*
*Sidecar pattern (*)
*<br/>It is a solution provided by AWS and Fargate container, therefore, does not need to be enforced via the Technology Radar*
* 4 key metrics (*)
*<br/>Important metrics as published results in <a href="https://itrevolution.com/book/accelerate/">Accelerate</a>.* 
* Proper bounded contexts (*)
*<br/>Has improved. Also decommissioned in favor of DDD as default at RIO.*

### Last in trial

#### Tools
* ApiCenter
*<br/>We still have the requirements for an API registry, but currently we do not have the priority for pushing this forward.*
* cfn-lint
*<br/>Low adoption rate*
* Arrow (*)
*<br/>No real trial happend.*

#### Platforms

* Amazon Kinesis Data Streams
*<br/>We did not try it.* 
* Cloud watch for alarming (*)
*<br/>Was rejected by the Macro Architecture Guild.*

#### Techniques
* Feature toggle service (*)
*<br/>A managed tool was selected to manage the feature toggles*
* Reactive programming/ ReactiveX in the backend (*)
*<br/>No real trial happend for ReactiveX.*
* Resilience patterns (*)
*<br/>No real trial happend.*
* Threat Modeling (*)
*<br/>No real trial happend.*
* Container Security Scanning (*)
*<br/>No real trial happend. Decomissioned as build everything on top of AWS provided images.*

### Last in assess

#### Tools

* Kong API Gateway
*<br/>Kong is moving in the right direction, but there are no immediate plans for a proper assessment.*
* pivio.io
*<br/>We did not see enough value for the effort.* 
* Cloud Conformity
*<br/>We are focusing on AWS Config Rules.* 
* Cloud Custodian
*<br/>We are focusing on AWS Config Rules.* 
* Laconia (*)
*<br/>No real assessment happend.*
* Snyk.io (*)
*<br/>We are focusing on Split.*

#### Languages & Frameworks

* Elixer
*<br/>No real assessment happend.*
* Lagom
*<br/>No real assessment happend.*
* RxJava
*<br/>No real assessment happend.*
* F#
*<br/>No real assessment happend.*
* Flow
*<br/>We are focusing on TypeScript.* 
* Golang for Lambda
*<br/>No need and no real assessment happend.* 
* Ktor
*<br/>No real assessment happend.* 
* Mithril (*)
*<br/>No real assessment happend.*
* Coroutines (*)
*<br/>No real assessment happend.*
* Micronaut (*)
*<br/>Stopped as it was used in conjunction with JVM Lambdas and GraalVM native images. For standard use cases we stick with Spring Boot*
* Kotless
*<br/>No real assessment happend.*

#### Platforms

* Amazon Redshift
*<br/>We are focusing on Athena.* 
* AWS AppSync
*<br/>No real assessment happend.* 
* WSO2
*<br/>Decommissioned.* 
* Event bridge
*<br/>No real assessment happend.*

#### Techniques

* Consumer-driven contract testing
*<br/>No real assesment happend.*
* Security gamification
*<br/>No real assesment happend.*
* API Gateway as sidecar
*<br/>No real assesment happend.*
* GraphQL (*)
*<br/>No real assesment happend.*
* Chaos engineering
*<br/>No real assessment happend.*

### Last in hold

#### Tools
* Self-hosted ELK
*<br/>Decommissioned.* 
* Ranorex (*)
*<br/>Decommissioned.*
* Sonar theater (*)
*<br/>Decommissioned.*
* A single CI instance for all teams (*)
*<br/>Decomissioned as CodeBuild and CodePipeline are almost completely adopted.*
* Custom Build Images
*<br/>Decomissioned.*
* Maven (*)
*<br/>Decomissioned with Gradle as our default.*
* Oracle JDK (*)
*<br/>Decomissioned with Amazon Corretto as our default.*

#### Languages & Frameworks
* Avro
*<br/>ADR to not use Avro is accepted and Avro was never introduced.* 
* Java (*)
*<br/>Decomissioned with Kotlin as our default.*
* JavaScript (*)
*<br/>Decomissioned with TypeScript as our default.*

#### Platforms
* AWS IoT Core
*<br/>After investigating the viability of IoT core for our vehicle connectivity we decided not to migrate now.*
* Spark Streaming
*<br/>Not in use and no need to emphasis "on hold" anymore.* 
* .NET Core (*)
*<br/>Not in use and no need to emphasis "on hold" anymore.*
* Adobe Experience Manager (*)
*<br/>The contract was not renewed and the replacement is under construction
* Amazon RDS (*)
*<br/>Not in use and no need to emphasis "on hold" anymore.*
* ECS on EC2
*<br/>Decomissioned with Fargate as our default.*

##### Techniques
* CoP theater
*<br/>Has improved and does not need to be called out anymore.*
* MSRT - Microservices Runtime
*<br/>Migration to multi-account is underway and there is no danger of MSRT resurfacing again.*
* Entity service
*<br/>Decomissioned.*
* Event Sourcing with DDB and Lambdas
*<br/>Decomissioned as now Axon is used in such cases.*
* Layered architecture
*<br/>Decomissioned with Ports and Adapters broadly adopted and our default.*
* Scrum theater
*<br/>Has improved and does not need to be called out anymore.*
