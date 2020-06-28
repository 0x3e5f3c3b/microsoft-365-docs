---
title: "Get started with retention policies and retention labels"
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: 
- M365-security-compliance
- SPO_Content
search.appverid: 
- MOE150
- MET150
description: Ready to start implementing retention policies and retention labels to govern your organization's data, but not sure where to start? Read some practical guidance to get started.
---

# Get started with retention policies and retention labels

>*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*

Ready to start governing your organization's data by retaining the content that you need to keep, and deleting the content that you don'? Use the following high-level guidance to get started:

1. **Understand how retention works** in Microsoft 365, by using retention policies and retention labels. Identify whether you need to use retention policies, or retention labels, or a combination: [Learn about retention](retention.md)

2. **Identify the retention settings and actions** that are required by your organization policies or industry regulations.
    
    As part of this assessment, determine whether you will use [records management](records-management.md).

3. **Create retention policies and retention labels**, based on the retention settings and actions that you identified.
    
    For retention labels, you might find it useful to use [file plan](file-plan-manager.md) to define and refine your retention labels in a spredtsheet that you can then import to create your labels.
    
3. **Publish and apply your retention labels**. While retention policies are designed for "set it and forget it" configuration, retention labels are reusable building blocks that can be used in multiple policies and can be incorporated into user workflows. See the list of [common scenarios](#common-scenarios-for-retention-policies-and-retention-labels) to help you identify how retention labels can be used. 

## Subscription and licensing requirements for retention policies and retention labels

A number of different subscriptions support retention policies and retention labels and the licensing requirements for users depend on the features you use.

To see the options for licensing your users to benefit from Microsoft 365 compliance features as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD). For retention, see the [Information Governance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section and related PDF or Excel download.

## Permissions required to create and manage retention policies and retention labels

Members of your compliance team who will create and manage retention policies and retention labels need permissions to the [Microsoft 365 compliance center](https://compliance.microsoft.com/). By default, the tenant admin (global administrator) has access to this location and can give compliance officers and other people access without giving them all the permissions of a tenant admin. To grant permissions for this limited administration, we recommend that you add users to the **Compliance Administrator** admin role group. For instructions, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

These permissions are required only to create and apply a retention policy. The person configuring the retention policy doesn't require access to the content.

## Common scenarios for retention policies and retention labels

Use the following table to help you map your business requirements to retention scenarios supported by retention policies and retention labels.

|I want to ...|Documentation|
|----------------|---------------|
|Efficiently set retain and delete actions for the organization, or by location: <br />-  Exchange email and public folders <br />- SharePoint sites <br />- OneDrive accounts <br />- Microsoft 365 groups <br />- Skype for Business accounts <br />- Teams channels and chats |[Create and configure retention policies](create-retention-policies.md)|
|Let admins and users manually apply a set of retain and delete actions for documents and emails: <br />-  SharePoint <br />- OneDrive <br />- Outlook and Outlook on the web|[Create retention labels and apply them in apps](create-apply-retention-labels.md)|
|Let site admins set a default retention label for all content in a SharePoint library, folder, or document set|[Create retention labels and apply them in apps](create-apply-retention-labels.md)|
|Let users automatically apply a retention label to emails by using rules|[Create retention labels and apply them in apps](create-apply-retention-labels.md)|
|Automatically apply a set of retain and delete actions at the item level (documents and emails) |[Apply a retention label to content automatically](apply-retention-labels-automatically.md)|
|Start the retention period when an event occurs | [Apply a retention label to content automatically](apply-retention-labels-automatically.md)|
|Use a single records management solution for both documents and emails |[Records management in Microsoft 365](records-management.md) |
|Comply with SEC Rule 17a-4|[Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|Make sure somebody reviews and approvals before content is deleted at the end of it's retention period|[Disposition reviews](disposition.md#disposition-reviews) |
|Have proof of disposition for content that is deleted at the end of it's retention period|[Disposition of records](disposition.md#disposition-of-records) |

## End-user documentation for retention labels

The most effective end-user documentation will be customized guidance and instructions you provide for the label names and configurations you choose. However, you can use the following information for basic instructions:

- [Manually apply retention labels](create-apply-retention-labels.md#manually-apply-retention-labels)
