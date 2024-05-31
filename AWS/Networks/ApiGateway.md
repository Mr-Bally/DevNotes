# AWS API Gateway

- Fully managed service for deploying, securing, maintaining and monitoring APIs
- Works for both public and private APIs
- Can support serverless, web apps and containerized workloads
- Only pay what you use so it is cost effective

## Endpoint Types

- Edge-Optimised:
  - Ideal for when your API users are distributed geographically
  - Requests are routed to the closest edge endpoint
  - Ideal for web and mobile apps
- Regional
  - Good for if you are using your own CDN or not using one at all
  - Or if you expect all traffic to come from the same region
- Private
  - Can only be accessed from within your VPC via an Interface VPC Endpoint
  - Uses an ENI you create within your VPC
  - Used for internal APIs or backend services

## Supported Protocols

- Web sockets
  - Maintains a duplex connection between the server and the client
  - Use case example might be a web chat service
- HTTP (REST)
  - Supports both REST and HTTP API
  - Integrations with AWS services differ between these two implementations

__NOTE:__ There are a lot of differences between REST and HTTP API so check AWS documentation for the most up to date comparisons

## Integrations

- Proxy Integration:
  - API Gateway passes the request on
  - No changes are made to the request
  - Quick to setup
- Direct Integration:
  - Can modify the request before routing to the backend
  - Can also change the response as it passed back through
  - Means you can decouple API Gateway from the backend service's API

## API Gateway Authorisers

- IAM
  - Uses AWS IAM
  - Allows you to create unique credentials to be distributed to the API clients
- Lambda
  - Run a Lambda function which runs a custom authorisation model
  - Good for running anything legacy
- Cognito
  - Direction integration with Cognito user pools
  - Only available for REST APIs
- JWT
  - Plugins with OAuth 2.0 and OIDC

## Gateway Security

- Integrates with AWS Web Application Firewall (WAF)
- Reduces risk of DDOS and other common web exploits
- Can block specific countries, regions on IP blocks

## Management and Usage

- Can have different usage plans based on API keys (e.g. basic and premium)
- Responses can be cached to reduce latency
- Metrics are available including a number of requests and latency
