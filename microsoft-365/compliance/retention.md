---
title: "Learn about retention to automatically retain or delete content"
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
description: Learn how retention policy to retain or delete content, and how to apply a single policy to the entire organization or to specific locations or users.
ms.custom: seo-marvel-apr2020
---

# Learn about retention

>*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*

For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:
  
- **Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years. 
    
- **Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep. 
    
- **Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them. 
    
Retention settings that you configure can help you achieve all these goals. Managing content commonly requires two actions:
  
- **Retaining** content so that it can't be permanently deleted before the end of the retention period. 
    
- **Deleting** content permanently at the end of the retention period. 
    
With retention settings, you can decide proactively whether to retain content, delete content, or both—retain and then delete the content.

When content is subject to retention settings, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page

## How a retention policy works with content in place

After content is assigned your configured retention settings, the content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.
  
- For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library. Be aware that the Preservation Hold library consumes storage quota for the site.

- For email and public folders: The copy is retained in the **Recoverable Items** folder. 

- For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.

- For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)): 
    - The group mailbox is retained in the Exchange **Recoverable Items** folder.
    - Any site content is retained in the **Preservation Hold** library.

> [!NOTE]
> The Preservation Hold library consumes storage that isn't exempt from a site's storage quota. You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.
> 
These secure locations and the retained content are not visible to most people. In most cases, people do not even need to know that their content is subject to retention settings.

For more detailed information about how retention settings work with different workloads, see the following articles:

- [Learn about retention for SharePoint and OneDrive](retention-policies-sharepoint.md)
- [Learn about retention for Microsoft Teams](retention-policies-teams.md)
- [Learn about retention for Exchange](retention-policies-exchange.md)

## Retention policies and retention labels

You can use both retention policies and retention labels to assign your retention settings to content. 

Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at a item level.

For example, if all documents in a SharePoint site should be retained for five years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site. However, if some documents in that site should be retained for five years and others in the same site should be retained for ten years, a retention policy wouldn't be able to do this. When you need to specify retention settings at the item level, use retention labels that have different retention settings. 

Unlike retention settings from retention policies, retention labels persist with the content if it’s copied or moved to a different Microsoft 365 location.  In addition, retention labels have the following capabilities that retention policies don't support: 
 
- Start the retention period from when the content was labeled, rather than the age of the content or when it was last modified. 
- Use trainable classifers to identify content to label.
- Apply a default label for SharePoint documents. 
- Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.
- Mark the content as a [record](records.md) as part of the label settings, and then have [proof of disposition](disposition.mddisposition-of-records) when content is deleted at the end of its retention period.

### Retention policies

Retention policies can be applied to the following locations:
- Exchange email
- SharePoint site
- OneDrive accounts
- Microsoft 365 groups
- Skype for Business
- Exchange public folders
- Teams channel messages
- Teams chats 

You can very efficiently apply a single policy to multiple locations, or to specific locations or users.
    
You can also apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).

#### Use Preservation Lock to comply with regulatory requirements

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

##### Releasing a retention policy

Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time. 

When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted. Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed. Additionally, you can't manually delete this content during the grace period.

You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.

This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange. For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

### Retention labels

Use retention labels for different types of content that require different actions taken on them to comply with industry regulations and internal policies. For example, you might have:
  
- Tax forms that need to be retained for a minimum period of time. 
    
- Press materials that need to be permanently deleted when they reach a certain age. 
    
- Competitive research that needs to be both retained and then permanently deleted. 
    
- Work visas that must be marked as a record so that they can't be edited or deleted. 
    
In all these cases, retention labels can help you take the right actions on the right content. Using retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.
  
With retention labels, you can:
  
- **Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Microsoft 365 Groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied. 
    
- **Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains: 
   
    - Specific types of sensitive information.
    
    - Specific keywords that match a query you create.
    
    - Pattern matches for a trainable classifier.

- **Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.

Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services. You can use a retention label to classify content as a record. When this happens and the content remains in Microsoft 365, the label can't be changed or removed, and the content can't be edited or deleted. 

Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.

There is no limit to the number of retention labels that are supported for a tenant. However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.

#### Classifying content without applying any actions

Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions. In this case, you can use a retention label simply as a text label, without enforcing any actions.
  
For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.
  
![Label settings page with retention turned off](../media/retention-label-retentionoff.png)

#### Using a retention label as a condition in a DLP policy

You can also use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label. 
  
For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

#### Retention labels and policies that apply them

Retention labels are independent, reusable building blocks. The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear. Then, admins and users can apply those labels to content.
  
![Diagram of labels, label policies, and locations](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. When you publish retention labels, they're included in a retention label policy. Retention label names are immutable, which means that they cannot be edited after they're created.

2. A single retention label can be included in many retention label policies.

3. A single location can also be included in many retention label policies.
    
3. Retention label policies specify the locations to publish the retention labels.

In addition to retention label policies, you can also create an auto-apply policy with a retention label. With this policy, a retention label is automatically applied when conditions that you specify in the policy are met. 

#### Retention label policies and locations

Different types of retention labels can be published to different locations, depending on what the retention label does.
  
|**If the retention label is…**|**Then the label policy can be applied to…**|
|:-----|:-----|
|Published to admins and end users  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 Groups  <br/> |
|Auto-applied based on sensitive information types or trainable classifiers  <br/> |Exchange (all mailboxes only), SharePoint, OneDrive  <br/> |
|Auto-applied based on a query  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365 Groups  <br/> |
   
In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.
  
Exchange public folders, Skype, and Teams channel messages and chats do not support retention labels. To retain and delete contain from these locations, use retention policies instead.

#### Only one retention label at a time

An email or document can have only a single retention label assigned to it at a time:
  
- For retention labels assigned manually by end users, people can remove or change the retention label that's assigned.
    
- If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.
    
- If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.
    
- If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.
    
To understand how and why one retention label is applied rather than another, it's helpful to understand the difference between explicitly assign a label, and implicitly assigned a label:

- Manually assigned labels are explicitly assigned
- Automatically applied labels are implicitly assigned

An explicitly assigned retention label takes precedence over an implicitly assigned retention label. For more information, see the [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence) section on this page.

## Compare capabilities for retention policies and retention labels

Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.

|Capability|Retention policy |Retention label|
|:-----|:-----|:-----|:-----|
|Retention settings that can retain and then delete, retain-only, or delete-only |Yes |Yes |
|Automatic labeling (configured by administrators) | Yes | Yes |
|Manual labeling (applied by users and administrators) | No | Yes |
|Apply based on location | Yes| No, with exception of default label for SharePoint |
|Persists if the content is moved | No | Yes, within Microsoft 365 |
|Declare item as a record| No | Yes |
|Condition for automatic labeling: Sensitive info types or exact matches | Yes | Yes |
|Condition for automatic labeling: Trainable classifiers | No | Yes |
|Event-driven retention | No | Yes |
|Disposition review | No| Yes |
|Proof of disposition | No |Yes, when item is declared a record|


## The principles of retention, or what takes precedence?

It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period. What takes precedence? In summary, rest assured that content being retained by one set of retention settings from a retention policy or retention label can't be permanently deleted by another set of retention settings.
  
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


## Use retention policies and retention labels instead of older features

If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features. 
  
If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels. However, we recommend that going forward, you use retention policies and retention labels instead. They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.

**Older features from Exchange Online:**

- [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold) 

- [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)
    
See also [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).


**Older features from SharePoint and OneDrive:**

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

- [SharePoint Online Limits](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Comply with SEC Rule 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## Next steps

If you are ready to create retention polices, see [Create and configure retention policies](create-retention-policies.md).

To create and apply retention labels:
- [Create retention labels and apply them in apps](create-apply-retention-labels.md)
- [Apply a retention label to content automatically](apply-retention-labels-automatically.md)

