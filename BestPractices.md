---
title: "Security Best Practices"
description: "Best Practices for Configuring Virtual Machines, Lab Profile, and Cloud Subscriptions"
isPublished: true
---

# Security Best Practices

Skillable is commited to ensuring a high degree of security on our platform. With this in mind, customers should also be aware that some configurations 
may not have an optimal security posture for particular audiences or industries. For high security industries, such as banking or finance, or for those 
customers who want to ensure as high a degree as security as possible, this document provides recommendations and explanations of some of the best practices 
you should follow when creating labs on the Skillable platform.

# VM Based Labs

## Disable Enhanced Session Mode (ESM)

For Windows virtual machines running on the Hyper-V platform, you can enable Enhanced Session Mode in the Virtual Machine Profile Settings. This setting allows you to copy text from a local 
device to the clipboard and then to the virtual machine. If you have concerns about people being able to copy data from a local machine, you should 
not enable this setting. You can find infromation on the setting here: [Create a Virtual Machine Profile ](https://docs.learnondemandsystems.com/lod/vm-profiles.md#hyper-v-1)

## Disable or restrict Internet access

Skillable incorporates a number of controls to ensure network stability and security. You can find an overview of these controls here: 
[Lab Network Restrictions](https://docs.learnondemandsystems.com/lod/lab-networks.md)

You control whether or not virtual machines have Internet access. If Internet access is not required on a virtual machine, you should not enable it. 
If a virtual machine does require Internet access and you have a concern that it could be used to bypass your corporate policies, you can attach an 
Access Control List (ACL) to the lab profile to ensure only a subset of authorized web sites are accessible. It is recommended that you create an Allow list that 
blocks all web sites except those you explicitly authorize.

For information on configuring Internet access in a lab profile, see the documentation on creating [networks](https://docs.learnondemandsystems.com/lod/feature-focus/lab-profiles/create.md#networks)
For information on configuring Access Control Lists to restrict Internet access, see the documentation on Access Control Lists (https://docs.learnondemandsystems.com/lod/access-control-lists.md)

## Disable or limit authenticated launch links

On the Advanced tab of the lab profile properties, you are able to give access to accounts that use a variety of authentication providers. These include Microsoft and Gmail accounts. 
You should use authenticated launch links only when absolutely necessary for testing purposes. Furthermore, you should limit these links to expire 
after a set period or remove them when the testing period has completed. 

 
# Cloud Slice Labs 

## Use a separate cloud subscription for integration with our platform

The Skillable platform allows you to integrate subscriptions from other cloud providers such as AWS or Azure. You should not use the same
subscription and billing account that use in a production environment. Furthermore, if possible, you should set billing caps on your subscriptions
that throttle usage after certain thresholds are triggered. 


## Do not use Life Cycle Actions (LCA) to modify permissions in the cloud subscription

LCAs can run scripts against your lab environment in the security context of the account you provided to enable integration with the Skillable platform.
Consequently, these scripts are capable in some cases of changing permissions and roles that are otherwise not available in the lab environment. If you 
have to add more permissions to a cloud subscription in order to perform the lab steps, you should consider althernatives. 

## Restrict guest invitations (Azure)

By default, Azure Active Directory allows you to invite guests from other domains. You should change this setting to prevent lab users from 
inviting unauthorized accounts to access the lab resources in your cloud subscription. 

## Ensure Access Control Policies (ACPs) are as restrictive as possible

When creating Access Control Policies for labs, ensure that the ACPs allow the creation of only the resources that are required to 
complete the lab. For more information on ACPs and related topics, see [Cloud Security & Best Practices] (https://docs.learnondemandsystems.com/lod/cloud-security/cloud-security-home.md). 



[Back to top.](#security-best-practices)
