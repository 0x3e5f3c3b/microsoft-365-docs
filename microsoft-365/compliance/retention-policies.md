---
title: "Learn about retention policies to automatically retain or delete content"
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
description: Learn about using a retention policy to retain or delete content, and how to apply a single policy to the entire organization or to specific locations or users.
ms.custom: seo-marvel-apr2020
---

# Learn about retention policies

>*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*

For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:
  
- **Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years. 
    
- **Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep. 
    
- **Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them. 
    
A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:
  
- **Retaining** content so that it can't be permanently deleted before the end of the retention period. 
    
- **Deleting** content permanently at the end of the retention period. 
    
With a retention policy, you can:
  
- Decide proactively whether to retain content, delete content, or both—retain and then delete the content.
    
- Apply a single policy to the entire organization or specific locations or users.
    
- Apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).
    
When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page
  
Additionally, some organizations have to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4. This regulation requires that after a retention policy is turned on, it cannot be turned off or made less restrictive. To meet this requirement, you can use **Preservation Lock**. After a retention policy's been locked, no one (including an administrator) can turn off the retention policy or make it less restrictive. For more information, see the [Use Preservation Lock to comply with regulatory requirements](#use-preservation-lock-to-comply-with-regulatory-requirements) section on this page.

## How a retention policy works with content in place

When you include a location such as a site or mailbox in a retention policy, the content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.
  
- For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library. Be aware that the Preservation Hold library consumes storage quota for the site.

- For email and public folders: The copy is retained in the **Recoverable Items** folder. 

- For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.

- For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)): 
    - The group mailbox is retained in the Exchange **Recoverable Items** folder.
    - Any site content is retained in the **Preservation Hold** library.

> [!NOTE]
> The Preservation Hold library consumes storage that isn't exempt from a site's storage quota. You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.
> 
These secure locations and the retained content are not visible to most people. With a retention policy, people do not even need to know that their content is subject to the policy.

For more detailed information about how retention policies work with different workloads, see the following articles:

- [Learn about retention policies for SharePoint and OneDrive](retention-policies-sharepoint.md)
- [Learn about retention policies for Microsoft Teams](retention-policies-teams.md)
- [Learn about retention policies for Exchange](retention-policies-exchange.md)

## The principles of retention, or what takes precedence?

It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or retain and then delete) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one retention policy can't be permanently deleted by another retention policy.
  
![Diagram of the principles of retention](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
To understand how different retention policies are applied to content, keep these principles of retention in mind:
  
1. **Retention wins over deletion.** Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted. 
    
2. **The longest retention period wins.** If content is subject to multiple retention policies that retain content, it will be retained until the end of the longest retention period. 
    
3. **Explicit inclusion wins over implicit inclusion.** This means: 
    
    1. If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned by the document library. For example, if the explicit retention label is configured to retain content for 10 years, but the retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence. Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.
    
    2. If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.
    
4. **The shortest deletion period wins.** Similarly, if content is subject to multiple retention policies that delete content without a retention period, that content will be deleted at the end of the shortest retention period. 
    
Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all retention policies or retention labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.
  
Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.

## Use Preservation Lock to comply with regulatory requirements

Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive. 

Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy or make it less restrictive.
  
When a retention policy is locked:

- No one can it turn off
- Locations can be added but not removed 
- Content subject to the policy can't be modified or deleted during the retention period
- You can extend a retention period but not decrease it

In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.
  
> [!IMPORTANT]
> Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet compliance requirements.

## Releasing a retention policy

Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time. 

When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted. Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed. Additionally, you can't manually delete this content during the grace period.

You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.

This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange. For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## Use a retention policy instead of older features

A single retention policy can easily apply to an entire organization and locations across Microsoft 365, including Exchange Online, SharePoint Online, OneDrive, and Microsoft 365 groups. If you need to retain or delete content anywhere in Microsoft 365, we recommend that you use a retention policy and optionally supplement this with [retention labels](labels.md).
  
If you have previously used other configurations to retain or delete content in Microsoft 365, they will continue to work side by side with retention policies and retention labels. However, we recommend that going forward, you use retention policies and retention labels instead. They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.

The older features that you might have used:
  
**Older features from Exchange Online:**

- [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold) 
    
- [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold) 

- [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)
    
**Older features from SharePoint and OneDrive:**

- [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold) 
    
- [Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold) 
    
- [Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)
    
- [Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only) 
    
- [Use policies for site closure and deletion](https://support.microsoft.com/en-us/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only) 
    
- [Information management policies](intro-to-info-mgmt-policies.md) (deletion only)
     
If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead. Use eDiscovery for holds only.
  
### Retention policies and SharePoint content type policies or information management policies

If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect. 
  
### Preservation policies are converted to retention policies

If you were using a preservation policy to retain data in mailboxes, SharePoint or OneDrive sites, or public folders: That policy has been automatically converted to a retention policy that uses only the retain action—the policy won't delete content. No changes are needed from you for the same outcome as your configured preservation policy.

You can find any configured preservation policies on the **Policies** page in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), or on the **Retention** page under **Information governance** in the [Security &amp; Compliance Center](https://protection.office.com/). You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations. 


## Related information

- [Learn about retention labels](labels.md)
- [SharePoint Online Limits](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Comply with SEC Rule 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## Next steps

If you are ready to create retention polices, see [Create and configure retention policies](create-retention-policies.md).

