---
title: "AWS Global Accelerator"
seoTitle: "Quick summary of AWS global accelerator"
seoDescription: "Quick summary of AWS global accelerator, use cases, difference between global accelerator and cloudfront"
datePublished: Tue Aug 29 2023 21:00:09 GMT+0000 (Coordinated Universal Time)
cuid: cllwsl68r00070ajuglz4g8jw
slug: aws-global-accelerator
tags: aws, aws-cloudfront

---

AWS Global Accelerator is a networking service that helps you improve the availability, performance, and security of your public applications\[1\]

* GA provides two IP addresses which act as fixed entrypoint for application endpoints such as Application/Network LoadBalancers, EC2 and Elastic IPs
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693279082537/f1a3e30d-1d6b-4787-a08f-a1815a214019.png align="center")

Image Reference: [https://aws.amazon.com/global-accelerator/](https://aws.amazon.com/global-accelerator/)

## Use cases

* Global Traffic Manager -- Route Traffic to the nearest Region or achieve Fast failover across the region
    
* API Acceleration -- Accelerate API workloads by leveraging TCP termination at the edge
    
* Global Static IP -- Simply allow listing in enterprise firewall and IOT use cases
    
* Low-Latency for gaming and media workloads -- Use custom routing to deterministically route traffic to a fleet of EC2 instances
    

## How is AWS Global Accelerator different from CloudFront?

CloudFront improves performance for both **cacheable content** (such as images and videos) and dynamic content (such as API acceleration and dynamic site delivery). Global Accelerator improves performance for a **wide range of applications** over TCP or UDP by proxying packets at the edge to applications running in one or more AWS Regions.

Global Accelerator is a good fit for both non-HTTP and HTTP use cases.

## References

1. [https://aws.amazon.com/global-accelerator/](https://aws.amazon.com/global-accelerator/)