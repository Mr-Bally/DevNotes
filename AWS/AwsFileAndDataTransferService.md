# AWS File storage and data transfer services

- - - -

## Table of Contents

* [Amazon S3](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-s3)
* [Amazon S3 Glacier](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-s3-glacier)
* [EC2 File Storage](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#ec2-file-storage)
* [AWS Snowball](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-snowball)

## Amazon S3

Amazon Simple Storage Service (S3)

* Stores files as objects in buckets
* Provides different storage classes for different use cases
* Stores data across multiple availability zones
* Enables URL access for files
* Can serve as a static web host
* There is no archival storage clas for S3

### S3 Class types

* __S3 Standard:__ Defauly and used for frequently accessed data
* __S3 Intelligent-tiering:__ Will move your data into the correct storage class based on usage
* __S3 Standard Infrequent Access (IA):__ For infrequently accessed data
* __S3 One Zone IA:__ Infrequently access data only stored in a single availability zone
* __Intelligent tiering:__
  * Automatically moves files based on access frequency
  * Moves between infrequent and frequently accessed classes

### S3 Lifecycle Policies

* Objects in a bucker can expire based on policies
* Transitions enable objects to move to a different storage class based on time
* Expiration can expire objects when they reach a certain age

### S3 Transfer Acceleration

* Feature which can be enabled per bucket
* Allows for the optimised uploading of data through Edge location utilising Amazon Cloud Front

## Amazon S3 Glacier

* Designed for archiving data within S3 as a separate storage class
* Can send files there directly or move them through lifecycle rules in S3

### S3 Glacier vs Glacier Deep Archive

* Both designed for archiving rarely accessed data
* Both pay a retrieval fee per GB of data returned
* With Deep Archive:
  * Data is stored for a minimum of 180 days vs 90 days
  * Data is retrieved in hours vs minutes to hours
  * Data storage is 23 times cheaper than standard S3 storage vs 5 times cheaper

## EC2 File Storage

### Elastic Bloc Storage (EBS)

* Enables redundancy within an availability zone
* Block storage to be connected to a single EC2 instance
* Allows users to take snapshots of the data
* Offers encyptions of data
* __EBS Volume Types:__
  * __General Purpose SSD:__ Cost effective for general workloads
  * __Provisioned IOPS SSD:__ High performance for low latency apps
  * __Throughput Optimised HDD:__ For frequently accessed data
  * __Cold HDD:__ For less frequently accessed volumes

### Elastic File System (EFS)

* Elastic file system for Linux workloads
* Fully managed network file system (NFS) across multiple EC2 instances
* Supports upto petabyte scale workloads
* Can store data across multiple availability zones
* __Storage classes:__
  * Standard
  * Infrequently accessed
* Configurable life cycle rules
* Can span multiple availability zones and EC2 instances

## AWS Snowball

* Data transfer service
* Physically migrate petabytes of data onto the cloud
* __Snowmobile:__ A service to physically migratione exabytes of data onto the cloud
