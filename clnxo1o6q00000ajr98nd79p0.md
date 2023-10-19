---
title: "Quick EC2 AWS Networking notes"
seoTitle: "Quick AWS Networking notes"
seoDescription: "NACL vs SG2
AWS Networking"
datePublished: Thu Oct 19 2023 21:00:12 GMT+0000 (Coordinated Universal Time)
cuid: clnxo1o6q00000ajr98nd79p0
slug: quick-ec2-aws-networking-notes
tags: ec2, aws, aws-security-group, aws-nacl

---

Each VPC can have one or more subnets

Subnets can be private or public

The difference between private and public subnets is that public subnets are accessible over the internet

Internet Gateway and VPC gateway are two ways to get traffic out of the VPC.

With Internet Gateway (IGW) you can send and receive traffic from internet while with VPC gateway you exchange traffic between VPCs

IGW should have an entry in the route table of VPC to associate with VPC.

Public subnets should have a related entry in the route table to redirect traffic from the subnet to IGW and back.

Network Access Control List (NACL) acts like a firewall for each subnet.

* By default, NACL allows all inbound and outbound traffic.
    
* They are stateless, which means if we want to open or close access to specific ports then both input and output entries in the NACL need to be made.
    

Each **Security group** acts as a firewall for each EC2 instance.

* By default, they block access to EC2 instances.
    

* They are stateful, which means one needs to only open access for a port and SG will allow traffic to go out