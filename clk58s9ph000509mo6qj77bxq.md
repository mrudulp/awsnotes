---
title: "AWS Account Security"
datePublished: Sun Jul 16 2023 09:36:19 GMT+0000 (Coordinated Universal Time)
cuid: clk58s9ph000509mo6qj77bxq
slug: aws-account-security
tags: iam, saa-c03, iam-identities, aws-organizations, iam-group

---

## AWS Organisations

AWS Organisations -- Container account that can have multiple AWS accounts for a single organisation. Organisations can centrally manage Billing, Management of AWS Services at scale, and Service Control Policies.

Service Control Policies -- They are used to allow or deny access to certain AWS services. If a service(for eg: S3 or DynamoDB) is denied in Service Control Policy and allowed in the IAM role/group, the user will not get access to the service(for eg: S3 or DynamoDB)

## AWS Identity & Access Management

IAM -- AWS Identity and Access Management (IAM); you can specify who or what can access services and resources in AWS, centrally manage fine-grained permissions and analyze access to refine permissions across AWS. Each AWS account has its pool of identities. An IAM identity provides access to an AWS account. An IAM identity represents a human user or programmatic workload and can be authenticated and then authorized to perform actions in AWS.

* IAM User is an identity within your AWS account that has specific permissions for a single person or application. It is recommended to use temporary credentials instead long-term credentials. If there is a need to have a long-term credential then one should rotate keys.
    
* IAM User Group is a collection of IAM users. User groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users. You cannot identify a user group as a `Principal` in a policy (such as a resource-based policy) because groups relate to permissions, not authentication, and principals are authenticated IAM entities (2).
    
* IAM Roles are short-term credentials that provide temporary permission(s) to specific service(s) defined in the role. They cannot be used to authenticate into AWS but are used to authorise access to a resource based on the policy defined for the role.
    
* IAM Policies are authorisation rules for accessing a resource on AWS. By default, all resources are denied permission. Also in case of conflict between different policies assigned to a user/group or role when one policy allows access and another denies, AWS decides to deny permission.
    

For a user to gain access to the service, the user should be allowed to access in Service Control Policy and IAM role/group.

## References

1. [IAM Identities (users, user groups, and roles) - AWS Identity and Access Management (](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)[amazon.com](http://amazon.com)[)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)
    
2. [IAM user groups - AWS Identity and Access Management (](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html)[amazon.com](http://amazon.com)[)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html)