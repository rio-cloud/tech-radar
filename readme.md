# RIO Technology Radar

* [RIO Radar Q2 2018 (current)](https://radar.thoughtworks.com/?sheetId=https%3A%2F%2Fdocs.google.com%2Fspreadsheets%2Fd%2F1w4OgqpVAIADD3vXvMvq5n5F5q7w6_rspVgqmJVy5xGc%2Fedit)


## Defaults
Blips that are adopted at RIO by default and are not mentioned in every radar.

#### Techniques
* Microservices

#### Platforms
* Amazon Web Services - AWS
*<br/>AWS is our default provider for IaaS and PaaS. We prefer AWS platform services over other managed services, over self-hosted OSS and over self-built solutions.*
* [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
*<br/>MongoDB Atlas is a highly available, fully managed database. Our default option for all services requiring a document database.*
* Amazon ECS
*<br/>Most of our workloads are running as containers on ECS. We like that the fully managed container scheduler frees us of the operational burden.*   
* Amazon CloudWatch
*<br/>Although we recognise the limitation of CloudWatch, we also acknowledge that it is highly integrated with all other AWS services and provides a baseline monitoring and reaction capability valuable to us.* 
* Amazon RDS
*<br/>Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. We mostly use the PostgreSQL engine.*

#### Tools
* AWS CloudFormation
*<br/>CloudFormation is our default tool to model and provide AWS infrastructure.*
* React
* Redux

#### Languages & Frameworks
* Java
* Spring Boot
* JavaScript
