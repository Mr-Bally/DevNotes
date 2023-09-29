# AWS Database Services

- - - -

## Table of Contents

* [Amazon RDS](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-rds)
* [Amazon DMS](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-dms)
* [Amazon Dynamo DB](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-dynam-db)
* [Elastic Cache](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#elastic-cache)
* [Redshift](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#redshift)

## Amazon RDS

Amazon Relational Database Service

* Fully managed service for relational databases
* Handles provisioning, patching, backup and recovery
* Supports deployments across multiple availability zones
* Some platforms support read replicas
* Launches into a VPC
* Supports:
  * MySql
  * PostgressSql
  * Maria DB
  * Oracle DB
  * SQL Server
  * Amazon Aurora

## Amazon DMS

Amazon Database Migration Service

* Enables you to move data into AWS from existing databases
* Supports both one time and continual migration of data
* Supports many populate commerical and open source databases
* Only pay for computation leverged in the migration process

## Amazon Dynamo DB

* Fully managed NoSql database server (Saas)
* Provies key-value and document databases
* Enable low latency at virtually any scale
* Supports automated scaling based on configuration
* Built for Amazon products
* Offers in memory cache alongside the DB

## Elastic Cache

* Fully managed in memory data store
* Supports both Memcached and Redis
* Low latency response times
* Enabled scalcing and replicates to meet application demand

## Redshift

* Scalable data warehouse service
* Support petabyte scale warehousing
* Leverage high perforamnce disk and columnar storage
* Provides isolation with a VPC
* Can full encrypt data
