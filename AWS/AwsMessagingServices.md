# AWS Messaging Services

- - - -

## Table of Contents

* [Amazon SNS](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-sns)
* [Amazon SQS](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-sqs)
* [AWS Step Functions](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#amazon-step-functions)

## Amazon SNS

Amazon Simple Notification Service

* Fully managed publish/ subscribe messaging service
* Decouples applications
* Organised according to topics
* Integrates with multiple AWS services
* Provides end user notification across SMS, email and push notifications

## Amazon SQS

Amazon Simple Queue System

* Fully managed message queue services
* Enables the building of decoupled and fault tolerant applications
* Supports 256KB payload
* Messages can be stored for upto 14 days
* __Queue types:__
  * Standard queue
  * FIFO queue (makes sure of the order)

## AWS Step Functions

* Enables orchestration of workflows through a fully managed service
* Supports servless architectures
* Can support complex workflows including error handling
* Charged per state transitions along with any of the other AWS Services used
  * E.g. If you have 4 steps in a workflow each transition gets charged
* Workflows defined using Amazon States Language

* __Integrations:__
  * Compute services e.g. lambda
  * DB service e.g. Dynamo
  * Messaging services
  * Data processing services
  * Machine learning
