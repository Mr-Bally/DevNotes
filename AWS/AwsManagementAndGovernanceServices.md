# AWS Management and Governance Services

- - - -

## Table of Contents

* [AWS CloudTrail](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-cloudtrail)
* [AWS CloudWatch](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-cloudwatch)
* [AWS Config](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-config)
* [AWS Systems Manager](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-systems-manager)
* [AWS Cloud Formation](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-cloud-formation)
* [AWS OpsWorks](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-opsworks)
* [AWS Organisation and Control Tower](https://github.com/Mr-Bally/DevNotes/blob/main/AWS/AwsContentAndNetworkDeliveryServices.md#aws-organisation-and-control-tower)

## AWS CloudTrail

* Log, monitor and retain account activity across your AWS infrastructure
* Provides an event history for your AWS account history no matter whether it's through SDK, console etc
* Inserts audit trails into an S3 bucket or CloudWatch logs
* Meets many compliance requirements for infrastructure auditing
* Logs events in the regions they occurred

## AWS CloudWatch

* Provides metric, logs and alarms for infrastructure
* Monitoring and management services
* Collects logs, mertric and events from most AWS Services
* Enables alarms based on metrics
* Provides visualisation capabilities for metrics
* Can create custom dashboards

## AWS Config

* Continually evalutates infrastructure against a set of rules
* Provides configuration history for infrastructure
* Works against rules that you can customize or even custom validation
* Includes confirmation packs for compliance including PCI-DSS (payments standards)

## AWS Systems Manager

* Provides operational data and automation across infrastructure
* Unified interface so you can view operational data from multiple AWS Services and allows you to automate operation tasks accross your AWS resources
* Enables automation tasks for common maintainance tasks
* Gives you a secure way to access servers using only AWS creds
* Stores commonly used parameters securely for operational use (e.g. connection string)

## AWS Cloud Formation

* Managed service for provisioning infrastructure based on templates
* No additional charge
* Only pay for the resource you launch but not launching it through cloud formation
* Templates can be YAML or Json
* Enabled infrastructure as code
* Manages dependencies between resources
* Provides drift detection to find changes in your infrastructure

## AWS OpsWorks

* Configuration management service
* Provides managed instances of Chef and Puppet
* Configuration defined as code for servers
* Chef and Puppet manage the lfecycle for both cloud-based on on-premise servers
* Made up of
  * AWS OpsWorks for Chef Automate
  * AWS OpsWorks for Puppet Enterprice
  * AWS OpsWorks Stacks

## AWS Organisation and Control Tower

* Allows organisations to manage multiple accounts under a single master account
* Provides organisations with the ability to leverage consiladated billing for all accounts
* Enables organisations to centralise logging and securit standards accross accounts
* Control Tower helps best practice
  * Centralise users across all AWS accounts
  * Provides a way to create new AWS account based on templates
  * Integrate Guardrails for accounts (e.g. cloudtrail turned on)
  * INcludes dashboard to gain operation insights from a single view
  