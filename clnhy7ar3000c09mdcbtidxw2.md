---
title: "EC2 States and Billing"
datePublished: Sun Oct 08 2023 21:00:12 GMT+0000 (Coordinated Universal Time)
cuid: clnhy7ar3000c09mdcbtidxw2
slug: ec2-states-and-billing
tags: aws-ec2

---

### EC2 has the following states --

* **Pending** \-- EC2 is starting
    
* **Running** \-- EC2 is now active and in use. Billing starts when EC2 reaches this state
    
* **Stopping** -- EC2 is entering a stopped state. Billing continues till EC2 does not reach a stopped state
    
* **Stopped** \-- EC2 is not active and is equivalent to shutdown. Note one can start and stop an instance if it has Amazon EBS volume in its root device. IPv4 & IPv6 address is retained in this state and is reused when the EC2 instance is restarted. AWS does not charge usage or data transfer fees for stopped instances. But any Amazon EBS volume is still charged
    
* **Terminate** \-- EC2 instance is destroyed and its IP address is also returned to the pool. One cannot access the instance after the instance is terminated
    
* **Reboot** \-- This state is equivalent to rebooting a machine. It is different from start-stop-start.
    

### Difference between stop & stop-hibernate

In the stop state, one can change attributes of EC2 instances like instance type. However, any data from the instance memory (RAM) is lost.

When you stop-hibernate an instance, any contents from the instance memory (RAM) are stored in the EBS root volume. Instances can be hibernated if instance meet the hibernation prerequisites