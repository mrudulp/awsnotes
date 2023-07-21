---
title: "AWS WAF vs AWS Shield vs AWS Firewall Manager"
datePublished: Thu Jul 13 2023 12:03:53 GMT+0000 (Coordinated Universal Time)
cuid: clk13qhoj000r09l2a3oz8gnw
slug: aws-waf-vs-aws-shield-vs-aws-firewall-manager
tags: aws, aws-certified-solutions-architect-associate, aws-waf, aws-shield, aws-firewall

---

### WAF -- Web Application Framework. Protects access to content

Web Application Firewall that lets you monitor HTTP & HTTPs requests that are forwarded to your protected web application resources. Protection against web attacks using criteria

* IP addresses that requests originate from.
    
* Country that requests originate from.
    
* Values in request headers.
    
* Strings that appear in requests, either specific strings or strings that match regular expression (regex) patterns.
    
* Length of requests.
    
* Presence of SQL code that is likely to be malicious (known as *SQL injection*).
    
* Presence of a script that is likely to be malicious (known as *cross-site scripting*).
    
* web ACLs in WAF can be used to minimise DDoS attacks, but for advanced use case AWS Shield should be used
    

### AWS Shield

It is primarily used to provide Advanced protection against DDoS attack

Shield Standard which comes automatically and Shield Advanced paid option are two services that AWS offers.

It should be used for websites that are highly visible and prone to DDoS attacks

### AWS Firewall Manager

Simplifies administration and maintenance tasks across multiple accounts and resources for a variety of protections including WAF, Shield, VPC SGs, Network Firewall & Route 53 Resolver DNS Firewall.

### Sample Question(s):

Q: If you want to protect your application from Cross Site Scripting and SQL Injection attacks will you use AWS WAF or AWS Shield or AWS Firewall?

A: AWS WAF

## Reference:

* [https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)