---
title: "AWS Storage Types"
datePublished: Thu Feb 29 2024 20:02:33 GMT+0000 (Coordinated Universal Time)
cuid: clt7njucf000209jv4h0dbhot
slug: aws-storage-types

---

Three main types

File Storage

* Data stored as files in a hierarchy
    
* Typical use cases are web application, extended home directories
    

Block Storage

* Data is stored in fixed-size blocks.
    
* Updating data is changing just one part
    
* Suitable for files that need frequent updates or high transaction rates like Containers, Virtual Machines
    

Object Storage

* Data is stored as objects in buckets
    
* The whole file needs to be updated
    
* Suitable for WORM (Write Once Read Many times) models like Data archiving, Backup & recovery
    

Amazon EFS

* Is a file system that automatically grows and shrinks as you add and remove files
    
* One can connect multiple compute instances at the same time without any hit to performance
    
* There are two primary types
    
    * Multi-region -- EFS Standard storage & EFS Standard Infrequent Access
        
    * One zone -- EFS One Zone & EFS One Zone-Infrequent Access
        

Amazon FSx

* Fully managed service to launch, run & scale high performance file systems in the cloud. Four widely used file systems supported -- Lustr, NetApp ONTAP, OpenZFS & Windows File Server