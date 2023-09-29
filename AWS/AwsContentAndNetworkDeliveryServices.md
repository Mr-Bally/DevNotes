# AWS Content and Network Delivery Services

- - - -

## Table of Contents

* [AWS VPC](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-vpc)
* [AWS Direct Connection](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-direct-connection)
* [Route 53](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#route-53)
* [Elastic Load Balancing](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#elastic-load-balancing)
* [Definitions](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#definitions)

## AWS VPC

* __Amazon VPC:__ Amazon Virtual Private Cloud
  * Logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define
  * Enables virtual networks in AWS
  * Supports IPv4 and IPv6
  * Allows configuration for IP address ranges, subnets, route tables and network gateways
  * Supports public and private subnets (IE accessible to the internet or not)
  * Can connect to a specific data centre, other VPCs and private connections to many AWS services

## AWS Direct Connection

Allows you to establish a dedicated network connection from your data centre to AWS

## Route 53

* AWS DNS service
* Utilises Amazon Edge infrastructure
* Global AWS service (not regional) as it's highly available and any changes are applied globally
* Global resource routing (e.g. go to this particular server because you are coming from this country)

## Elastic Load Balancing

* Ability for infrastructure to grow and contract based on how much it is used at a point in time
* Distributes traffic accross multiple targets
* Integrates with EC2, ECS and Lambda
* Supports one or more availabilty zone in a region
* Types of load balancer:
  * Application Load Balancer (ALB)
  * Network Load Balancer (NLB)
  * Classic Load Balancer (CLB)

## Definitions

* __Verticle Scaling:__ Scale up your instance type to a larger instance with more resources
  * Means taking down the instance, creating a new instance and spinning back up which isn't ideal
* __Horizontal Scaling:__ Add more instances to handle demand
