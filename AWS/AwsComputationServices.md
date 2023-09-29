# AWS Computation Services

- - - -

## Table of Contents

* [EC2](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#ec2)
* [AWS Elastic Beanstalk](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#aws-elastic-beanstalk)
* [AWS Lambda](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#aws-lambda)
* [Amazion Cloud Front](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#amazion-cloud-front)
* [Amazon API Gateway](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#amazon-api-gateway)
* [AWS Global Accelorator](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#aws-global-accelorator)
* [Definitions](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsComputationServices.md#definitions)

## EC2

__EC2:__ Amazon Elastic Compute Cloud

Web service which provides resizable compute capacity in the cloud which can be scaled as desired

### Instance Types

* Instance types define the instance capabilities including processors, memory and storage type
  * Cannot be changed with down time to the EC2 instance once the instance is up
* Varied options including optimised storage, general purpose instances vs accelerated computing
  * For example, Maching Learning which utilises a GPU rather than a general purpose instance type
* Pricing is based on the type
* Can define multiple root device types:
  * __Instance store:__ Storage which is physically attached to the host that the virtual server is running on
  * __Elastic Bloc Store:__ Persistant storage that is separate from the host the virtual server is running on

### Amazon Machine Images

* An AMI is a template for an EC2 instance including memory, storage, config and OS
* AWS provides many which can be used
* AMIs can be shared between different AWS accounts

### Purchase Types

* __Reserved:__ Where you commit to a specific type which is reserved for you
  * __Types:__
    * __Standard:__ Works well for steady predictable workloads
    * __Convertible:__ Can change the attributes unlike the standard model
    * __Scheduled:__ Works for a given window of time (good for reliable periodic jobs)
  * __Payment options:__
    * __Up front:__ Largest savings to be made via this option
    * __Parial up front__
    * __No up front:__ Less savings via this option
* __Savings Plan:__ Similar to reserved instances but without reserving capacity
  * Supports EC2, Fargate and Lambda
  * Savings of upto 72%
  * Like reserved it comes in 1 to 3 year terms
* __Spot instances:__ Leverages excess EC2 Capacity
  * Upto 90% savings
  * __Spot Price:__ Price for excess capacity on a sort of stock market
    * Have to bid higher than this price to gain the spot instance
    * The spot instance will be stopped if the spot price exceeds the amount you bid for it
* __Dedicated Host:__ Dedicated physical server in a data centre
  * Can be needed for certain compliance reasons

## AWS Elastic Beanstalk

* Leverages existing AWS technology
* Automates the process of deploying and scaling veriticle workloads in EC2
* Handles load balancing, provisioning, scaling and monitoring
* Support most popular technologies (Docker, .NET, Go ect)

## AWS Lambda

* Allows you to run code with managing the infrastructure
* Only charged for usage based on execution time
* Amount of memory available is the only configuration available
* Works with S3 and Dynamo DB
* Primary service for serverless architecture
* Reduced maintainance (no servers to manage as AWS manages it for you)
* Enables fault tolerance by default
* Scales on demand

## Amazion Cloud Front

* Content delivery network (CDN)
* Designed so resources can be aquired from closest server
* Works for both static and dynamic content
* Uses AWS Edge locations
* __AWS Shield:__ Protects against attack like DOS on the network

## Amazon API Gateway

* Fully managed API service
* Directly integrates with other AWS services
* Monitoring and metrics provided
* Supports VPC and in-house private networks

## AWS Global Accelorator

* Networking service which channels your traffic through AWS's global infrastructure to improve performance
* Uses IP resolution to resolve Edge locations
* Once traffic hits the Edge location it routes the traffic through the AWS infrastructure rather than the public internet
* Can route to:
  * Load balancers
  * Elastic endpoint
  * EC2 instances
* Traffic is optimised through AWS infrastructure rather than traditional web IP address resolution
* No reliance on DNS resolution (I.E. not at the mercy of the cache not updating on a DNS server)

## Definitions

* __Compute Service:__ A service which enabled you to leverage cloud-based virtual machines for workloads
