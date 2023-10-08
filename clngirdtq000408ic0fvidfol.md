---
title: "EC2 Instance Families and when to use"
seoDescription: "Different EC2 Instance Families and their use case"
datePublished: Sat Oct 07 2023 21:00:09 GMT+0000 (Coordinated Universal Time)
cuid: clngirdtq000408ic0fvidfol
slug: ec2-instance-families-and-when-to-use
tags: aws-ec2

---

### General Purpose Instance

Provides a balance of computing, memory and networking resources.

**Use Case:**

Ideal for web servers & code repositories

### Compute Optimized

Ideal for compute-bound applications that benefit from high-performance processors

Use Case:

Well suited for --

* Batch processing workloads
    
* Media transcoding
    
* High-performance computing (HPC)
    
* Scientific modeling
    
* Dedicated Gaming servers
    
* Ad server engines
    
* Machine learning inference
    

### Memory Optimized

Designed for workloads that process large datasets in memory

**Use Case:**

Well suited for --

* High-Performance Databases
    
* Distributed web-scale in-memory caches
    
* Mid-size in-memory databases
    
* Real-Time big-data analytics
    

### Accelerated Computing

Uses Hardware Accelerators or Coprocessors to perform functions such as floating-point number calculations, graphics processing or data pattern matching

**Use Case:**

* Machine learning
    
* HPC
    
* Computational Fluid dynamics
    
* Computational Finance
    
* Seismic Analysis
    
* Speech Recognition
    
* Autonomous Vehicles
    
* Drug Discovery
    

### Storage Optimized

Designed for workloads that require high sequential read & write access to large datasets on local storage. They are optimized to deliver tens of thousands of low-latency random I/O operations per second (IOPS)

**Use Case:**

* NoSQL databases
    
* In-Memory databases
    
* Scale-out transactional databases
    
* Data warehousing
    
* Elasticsearch & Analytics
    

### HPC Optimized

Designed to offer the best price for running HPC workloads at scale

**Use Case:**

* Large, complex simulations and deep learning workloads