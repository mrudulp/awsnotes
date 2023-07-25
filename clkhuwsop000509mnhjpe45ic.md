---
title: "VPC Endpoints"
datePublished: Tue Jul 25 2023 05:28:56 GMT+0000 (Coordinated Universal Time)
cuid: clkhuwsop000509mnhjpe45ic
slug: vpc-endpoints
tags: aws-vpc, vpc-endpoints, aws-private-link, vpc-peering

---

## AWS PrivateLink

AWS PrivateLink is a highly available, scalable technology that you can **use to privately connect your VPC to services as if they were in your VPC**. You do not need to use an internet gateway, NAT device, public IP address, AWS Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with the service from your private subnets. \[1\]

With PrivateLink you can create your endpoint service to make it available to your customers.

![
Using interface VPC endpoints to access an AWS service, an endpoint
service hosted by another AWS account, and a partner service from
AWS Marketplace.
](https://docs.aws.amazon.com/images/vpc/latest/privatelink/images/use-cases.png align="left")

*(Image Credit: AWS Gateway Endpoints \[3\] )*

In the diagram, VPC has 3 endpoints connecting to 3 PrivateLink services.

* The topmost endpoint connects to AWS Services
    
* The middle one connects to a service exposed by a VPC in another account
    
* The bottom one connects to a 3rd party service exposed on the AWS Marketplace partner service
    

## Gateway VPC Endpoints

Gateway VPC endpoints provide reliable connectivity to Amazon S3 and DynamoDB without requiring an internet gateway or a NAT device for your VPC \[1\].

Gateway endpoint does not use PrivateLink, unlike other types of endpoints.

### Comparing VPC Endpoints with the traditional approach

If a private subnet needs to access data on S3 or DynamoDB, it will have to go through the NAT gateway, then to Internet Gateway and finally to S3

But with VPC Endpoints private subnet can directly connect to VPC Endpoints and get data from S3.

![
With gateway endpoints, traffic from your VPC to Amazon S3 or DynamoDB is routed to
the gateway endpoint.
](https://docs.aws.amazon.com/images/vpc/latest/privatelink/images/gateway-endpoints.png align="left")

*(Image Credit: AWS Gateway Endpoints \[1\] )*

Another advantage of using VPC Endpoints is that it can also define a policy on what actions VPC endpoint can do against the service/s3.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689999047067/b402df54-d252-4de0-b47d-d9217be6b17f.png align="center")

*(Image Credit: AWS Gateway Endpoints \[1\] )*

## Interface VPC Endpoints

Interface VPC endpoints are used to connect to services powered by AWS PrivateLink. For each subnet that you specify from your VPC, AWS creates an endpoint network interface in the subnet and assigns it a private IP address from the subnet address range.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690262718618/ad7698b1-7b4f-46f9-b2ca-80de63ec5c11.png align="center")

*(Image Credit: AWS Gateway Endpoints \[1\] )*

An endpoint network interface is a requester-managed network interface, one can view in their AWS account, but can't manage it themselves.

## References -

1. [Gateway endpoints - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/gateway-endpoints.html)
    
2. [AWS re: Invent 2018: Your Virtual Data Center: VPC Fundamentals and Connectivity Options (NET201) - YouTube](https://www.youtube.com/watch?v=jZAvKgqlrjY)
    
3. [What is AWS PrivateLink? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)
    
4. [Access an AWS service using an interface VPC endpoint - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html)