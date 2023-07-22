---
title: "Connectivity UseCases"
datePublished: Fri Jul 21 2023 20:10:51 GMT+0000 (Coordinated Universal Time)
cuid: clkd0njed000009lagdchfoym
slug: connectivity-usecases
tags: aws, aws-vpc, vpc-peering, aws-subnet, aws-direct-connect

---

### Send & Receive Traffic to the Internet

* To send traffic from a subnet to the internet use Internet Gateway
    
* Create a public subnet and a private subnet.
    
* In the route table for the public subnet add an entry for Internet Gateway. This can be achieved by specifying the Target subnet (column) with an entry for internet Gateway and Destination as IP addresses that are allowed to send traffic to the internet. For all addresses specify 0.0.0.0/0
    
* In the route table for private Subnet add an entry for public subnet and/or only to the private subnet itself. This can be achieved by specifying the Target subnet (column) --
    
    * As public subnet in the route table for sending traffic to the public subnet.
        
    * As a local subnet in the route table for sending traffic to the local subnet
        
* One can also lock down traffic by using security groups.
    
    * For public subnets specify the port, protocol and CIDR block for the source traffic
        
    * For private subnets specify the port, protocol and Security Group ID of the public VPC to allow ingress traffic only from the public subnet. By specifying Security Group ID it makes it easy to change VPC but at the same time ensures the same security access is provided for ingress/egress traffic
        

### Outbound-only Internet Access

One might also need a private subnet to reach out to the internet but not want to expose the whole subnet to the internet. For eg to only get updates from the repo on the internet.

We can use Network Access Translation (NAT) gateway to achieve Outbound-Only Internet access.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689968407850/879d6ac6-669d-4510-ab41-46e3cff4a55f.png align="center")

As can be seen above, we map all traffic coming from the private subnet to a public IP in NAT-GW. NAT-GW can then route traffic coming on the public IP back to the private subnet.

For IPv6 there is an egress only Internet Gateway which can be used to achieve the same outbound-only Access

### Connecting to Other VPCs

One can use VPC peering to create full private IP connectivity between two VPCs.

One can peer VPCs across regions, across different accounts. The only thing to take is that CIDR ranges do not overlap.

The below diagram shows Peered VPC entry in the Routing table.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689969755066/c32aa536-8eca-4981-97fd-970efed8d4fe.png align="center")

### Connecting to On-Premise (Corporate Network)

One can use VPN or AWS Direct Connect to connect AWS with on-premise networks.

The diagrams below show how the network is setup for VPN and Direct Connect

**AWS VPN setup**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689970051248/bc5e7623-b03e-4b39-b2d9-ce5c9f7df8c1.png align="center")

AWS Direct Connect

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689970123631/839481d2-ec26-4dd8-a6b2-9bcab242c0da.png align="center")

VPN is a pair of secure IPSec Tunnels over the internet

AWS Direct Connect is a dedicated line with lower per-GB data transfer rates

## References:

1. ## [https://youtu.be/jZAvKgqlrjY](https://youtu.be/jZAvKgqlrjY)