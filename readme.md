# RIO Technology Radar

* [RIO Radar Q3 2019 (current)](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fraw.githubusercontent.com%2Frio-cloud%2Ftech-radar%2Fmaster%2FRIO%2520Radar%2520Q3%25202019.csv)

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

#### Tools
* AWS CloudFormation
*<br/>CloudFormation is our default tool to model and provide AWS infrastructure.*
* ESLint and TSLint (*)
* Gradle
* Maven
* DataDog
* AWS SNS/SQS
*br/><a href="https://aws.amazon.com/sqs/">AWS SQS</a> allows easy integration with Lambdas and therefore allowing multiple consumers of the same asyncronous event, independent from the number of partitions like Kafka, with guaranteed at least once consumption in case of successful processing and controlled mechanism for retries other via the visibility timeout or retry policy with the option of an out of the box dead-letter queue. If in-order processing is required it allows it through the FIFO variant (this does not integrate with lambdas).*

#### Languages & Frameworks
* Kotlin
* Java
* Spring Boot
* TypeScript
* JavaScript
* React
* Redux

## Archived

### Last in adopt

#### Platforms

* Amazon Cognito
*<br/>Cognito is used as part of our IAM solution. No other team is affected by Cognito and any change would be limited to this context.* 

#### Techniques

* TDD, BDD
*<br/>No agreement on a strong adopt recommendation. Will be addressed as part of a code quality initiative.* 

### Last in trial

#### Tools
* ApiCenter
*<br/>We still have the requirements for an API registry, but currently we do not have the priority for pushing this forward.*

#### Platforms

* Amazon Kinesis Data Streams
*<br/>We did not try it.* 

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

#### Platforms
* Amazon Redshift
*<br/>We are focusing on Athena.* 
* AWS AppSync
*<br/>No real assessment happend.* 
* WSO2
*<br/>Decommissioned.* 

#### Techniques

* Consumer-driven contract testing
*<br/>No real assesment happend.*
* Security gamification
*<br/>No real assesment happend.*
* API Gateway as sidecar
*<br/>No real assesment happend.*


### Last in hold

#### Tools
* Self-hosted ELK
*<br/>Decommissioned.* 

#### Languages & Frameworks
* Avro
*<br/>ADR to not use Avro is accepted and Avro was never introduced.* 

#### Platforms
* AWS IoT Core
*<br/>After investigating the viability of IoT core for our vehicle connectivity we decided not to migrate now.*
* Spark Streaming
*<br/>Not in use and no need to emphasis "on hold" anymore.* 

##### Techniques
* CoP theater
*<br/>Has improved and does not need to be called out anymore.*
* MSRT - Microservices Runtime
*<br/>Migration to multi-account is underway and there is no danger of MSRT resurfacing again.*
