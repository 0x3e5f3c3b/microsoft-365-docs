---
title: "Advanced Audit in Microsoft 365"
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: "Advanced Audit in Microsoft 365 provides new auditing capabilities to help your organization with forensic and compliance investigations."
---

# Advanced Audit in Microsoft 365

The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365. Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.

> [!NOTE]
> Advanced Audit is available for organizations with an Office 365 E5 or Microsoft 365 Enterprise E5 subscription. Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.

This article provides an overview of Advanced Audit capabilities.

## Long-term retention of audit logs

Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year. This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year. Retaining audit records for longer periods can help with on-going forensic or compliance investigations. For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).

If your organization is in a highly regulated industry with long-term retention requirements, you can also use an audit log retention policy to retain audit records for 10 years.

## Audit log retention policies

All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days. But you can create customized audit log retention policies to retain other audit records for up to 10 years. You can create a policy to retain audit records based on one or more of the following criteria:

- The Microsoft 365 service where the audited activities occur.

- Specific audited activities.

- The user who performs an audited activity.

You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies. Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization. For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).

## Access to crucial events for investigations

Crucial security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations. Advanced Auditing provides the following crucial events:

- [MailItemsAccessed](#MailItemsAccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#SearchQueryInitiatedExchange)

- [SearchQueryInitiatedSharePoint](#SearchQueryInitiatedSharePoint)

### MailItemsAccessed

The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients. The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised. If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).

The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:

- MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions. MailItemsAccessed applies to all logon types.

- MessageBind only covered access by a mail client. It didn't apply to sync activities. MailItemsAccessed events are triggered by both bind and sync access types.

- MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise". In contrast, MailItemsAccessed events are aggregated into fewer audit records.

For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).

To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.

![Searching for MailItemsAccessed actions in the audit log search tool](../media/AdvAudit_MailItemsAccessed.png)

You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.

### Send

The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:

- Sends an email message

- Replies to an email message

- Forwards an email message

Investigators can use the Send event to identify email sent from a compromised account. The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, message attachments, and whether the message is labeled as a [record](records-management.md). This auditing information can help investigators identify information about email messages sent from a compromised account or sent by a malicious user. Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.

To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.

![Searching for Sent message actions in the audit log search tool](../media/AdvAudit_SentMessage.png)

You can also run the [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.

### SearchQueryInitiatedExchange

The SearchQueryInitiatedExchange event is triggered when a person uses the Search bar in Outlook or Outlook on the web to search for items in a mailbox. Investigators can use the SearchQueryInitiatedExchange event to determine if a malicious user who may have compromised an account looked for or tried to access sensitive information in the mailbox. The audit record for a SearchQueryInitiatedExchange event contains information such as the actual search query text and whether the search was performed in Outlook desktop client or in Outlook on the web. By determining if a search event was performed, an investigator can understand the scope of the content that may have been compromised.

To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.

![Searching for Performed email search actions in the audit log search tool](../media/AdvAudit_SearchExchange.png)

You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.

### SearchQueryInitiatedSharePoint

Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in SharePoint. Investigators can use the SearchQueryInitiatedSharePoint event to determine if a malicious user tried to find (and possibly accessed) sensitive information in SharePoint. The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual search query text. By determining if a search event was performed, an investigator can understand the scope of the content that may have been compromised.

To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.

![Searching for Performed SharePoint search actions in the audit log search tool](../media/AdvAudit_SearchSharePoint.png)

You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.

## High-bandwidth access to the Office 365 Management Activity API

Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level. This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.

With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit. The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data. The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.

All organizations are initially allocated a baseline of 2,000 requests per minute. This limit will dynamically increase depending on an organization's seat count and their licensing subscription. E5 organizations will get approximately twice as much bandwidth as non-E5 organizations. There will also be cap on the maximum bandwidth to protect the health of the service.

For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## FAQs for Advanced Audit

**Where can I access Advanced Audit?**

After Advanced Audit is rolled out to your organization, you will be able to create audit log retention policies and search for MailItemsAccessed audit records using the Audit log search tool in the [Security & Compliance Center](https://protection.office.com). We're working to roll out Advanced Audit to the [Microsoft 365 compliance center](https://compliance.microsoft.com) in the coming weeks.

**Does every user need an E5 license to benefit from Advanced Audit?**

To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license. There are some capabilities that will check for the appropriate license to expose the feature for the user. For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.

**Why don't I see Advanced Audit in my organization, even though we have an E5 subscription and users that are assigned E5 licenses?**

It's possible that Advanced Audit features (such as the ability to create audit log retention policies and the logging of crucial audit records) aren't available in your organization, even with the correct licensing in place. If this is happening to you, it's because the Advanced Audit package hasn't been rolled out to your organization yet. This is a temporary licensing backfill issue, which should be resolved for affected organizations soon. To mitigate this issue, please perform the following steps for each E5 user:

1. In the Microsoft 365 admin center, go to **Users > Active users**, and then select a user.

2. On the user properties flyout page, click **Licenses and Apps**.

3. Expand the **Apps** section, and then do one of the following things:

   a. If the **Microsoft 365 Advanced Auditing** checkbox is not selected, select it, and then click **Save changes.** Audit records for MailItemsAccessed actions for this user should be searchable within 24 hours.

   b. If the **Microsoft 365 Advanced Auditing** checkbox is selected, clear it, and then click **Save changes.** See step 4.

4. If you cleared the checkbox in step 3, wait 60 minutes, and then repeat step 3a to enable the Microsoft 365 Advanced Auditing app.

For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group. After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group. Then turn the licensing assignment for the group back on. For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).

**What happens if my organization was in the private preview for one-year retention of audit records?**

Your audit retention policies from the preview program will persist as long as you don't override and change them with custom audit retention policies.

**What if my organization wants to retain audit logs for longer than one year?**

We're exploring options for how and if we can provide longer retention periods for audit records. You can provide any feedback about longer retention of audit records at [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187).

**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**

For eligible customers, there is no action to get access to crucial auditing events. However, as previously explained in this topic, latency caused by the licensing backfill issue may prevent audit records for crucial events from being returned in an audit log search. If this happens, follow the instructions in the previous FAQ about the temporary licensing backfill issue.

**Are you planning to release additional crucial events this year?**

Yes. We plan to continually release new events that are crucial to investigations. We will post information about these new events in the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**

Yes. As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.

**Does higher bandwidth mean better latency or higher SLA?**

At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns. More bandwidth can lead to better latency. But there isn't an SLA associated with high bandwidth. Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.
