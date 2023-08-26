---
title: "Serverless AWS"
seoTitle: "Summary of AWS Serverless"
seoDescription: "Quick overview of AWS Serverless services. Kinesis, SQS, SNS, EventBridge"
datePublished: Sat Aug 26 2023 03:36:16 GMT+0000 (Coordinated Universal Time)
cuid: cllrgz5ql000e09l5gsor2p0u
slug: serverless-aws
tags: aws, serverless, sqs, kinesis, sns

---

# Introduction

Serverless offers the benefit of -

* No Infrastructure Management
    
* Auto Scaling
    
* Pay only for the amount one uses
    
* Highly available and secure
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691948571764/8bf7908a-2562-49b5-bbe3-46dd6d27cde9.png align="center")

Image Reference: [https://www.youtube.com/watch?v=d9Jb1WKCLd8](https://www.youtube.com/watch?v=d9Jb1WKCLd8)

### Common Use cases

* Calling a backend API for Web or Mobile. Amazon API Gateway can be used in such case
    
* Automate an action, once a file is received in S3 for eg: Create a thumbnail or transform the image after upload
    
* Amazon SQS can be used to queue up requests and process the requests one by one.
    
* To process Streaming data with low latency one can use Amazon Kinesis
    
* Subscribers are notified when there is something to publish for a topic. Amazon SNS can be used for this service.
    
* Amazon Eventbridge can receive near real-time notifications when data from AWS services changes. It can be used to route events from AWS Services, Custom applications and 3rd party SASS applications.
    
* Cloudwatch can be used to schedule jobs at specific times of the day
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691948351946/fde9dbc8-7139-447f-bae6-b9fb5f3df99f.png align="center")

Image Reference: [https://www.youtube.com/watch?v=d9Jb1WKCLd8](https://www.youtube.com/watch?v=d9Jb1WKCLd8)

# SQS vs SNS vs EventBridge

## SQS -- Simple Queue System

Should be used for Reliable 1 to 1 Async Communication

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692417286599/c66480ca-7ba5-4992-b47f-60ce77196c48.png align="center")

Image Reference: [https://www.youtube.com/watch?v=RoKAEzdcr7k](https://www.youtube.com/watch?v=RoKAEzdcr7k)

* Requires polling mechanism to deliver messages.
    
* Helps decouple sending and receiving applications/service.
    
* There are standard and FIFO queues.
    
* FIFO queues preserve order while standard queues are designed for massive scale.
    
* FIFO queues are exactly-once-processed while standard queues are at least-once-processed which means the same message can arrive in the queue for more than one time.
    
* Provides constructs like dead-letter queues and poison-pill management. For more info [https://aws.amazon.com/sqs/](https://aws.amazon.com/sqs/)
    

## SNS -- Simple Notification System

Should be used for the publish-subscribe messaging paradigm.

Benefits of SNS --

* Eliminates the need to periodically poll for new information.
    
* Instant push-based delivery
    

Use Cases for SNS --

* Event notification, monitoring applications, and time-sensitive information updates.
    

Upto 24 hrs messages could be persisted

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692074525588/37543654-4eec-4a78-8efe-90dea11fc53b.png align="center")

Image Reference: [https://www.youtube.com/watch?v=RoKAEzdcr7k](https://www.youtube.com/watch?v=RoKAEzdcr7k)

## Event bridge

* Similar to SNS but it has messagebus and not topics. The main advantage is its **ability to integrate with 3rd party applications**
    
* It is built to not only capture events from AWS but also for third-party applications
    
* Amazon EventBridge is a service that provides [real-time access to changes](https://aws.amazon.com/eventbridge/integrations/) in data in AWS services, your applications, and software as a service (SaaS) applications without writing code.
    
* Upto 24hrs messages could be persistent
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692074694843/e0f6bfb4-f174-4366-9c3f-b080887ba8f9.png align="center")

Image Reference: [https://www.youtube.com/watch?v=RoKAEzdcr7k](https://www.youtube.com/watch?v=RoKAEzdcr7k)

### Head-to-Head Event Bridge vs SNS

* Easy SAAS integration for Event Bridge
    
* There is an Upper limit(5 targets per rule) for Fanout compared to millions of subscribers for SNS
    
* Can filter full event body while SNS can only filter on message attribute
    
* Event Bridge is slower compared to SNS
    
* Event Bridge is costlier compared to SNS
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692506816652/6a13bbc2-86a1-4686-85b8-f49137641f36.png align="center")
    
    Image reference: [Choosing Events, Queues, Topics, and Streams in Your Serverless Application - AWS Online Tech Talks - YouTube](https://www.youtube.com/watch?v=d9Jb1WKCLd8)
    

### When to use EventBridge vs X

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692506740764/bcd0772a-e625-4a6c-8909-9a06788ba9af.png align="center")

Image reference: [Choosing Events, Queues, Topics, and Streams in Your Serverless Application - AWS Online Tech Talks - YouTube](https://www.youtube.com/watch?v=d9Jb1WKCLd8)

# Summary

If one needs to **process millions of messages** use **SQS**

If one needs to **monitor and get notified without the need to poll** for information use **SNS**

If one needs to **process a large-scale real-time stream** of data use **Kinesis**

If one needs to **capture events from 3rd party SAAS** application use **EventBridge**