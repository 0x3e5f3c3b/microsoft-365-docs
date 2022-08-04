---
title: Try and evaluate Defender for Office 365
description: Learn how to evaluate and try the capabilities of Microsoft Defender for Office 365 without affecting your existing mail flow.
keywords: Try, Evaluate, Trial, Evaluation, Defender for Office 365
f1.keywords:
  - NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
  - MET150
  - MOE150
ms.collection:
  - M365-security-compliance
ms.custom: 
ms.technology: mdo
ms.prod: m365-security
ROBOTS:
---

# Try Microsoft Defender for Office 365

The unified **Trials** portal in the Microsoft 365 Defender portal provides a single point of entry for the formerly separate Trial and Evaluate experiences for Microsoft Defender for Office 365 Plan 2. The intent is to allow you to try the features of Defender for Office 365 Plan 2 before you fully commit to it.

You're invited to try Defender for Office 365 Plan 2 in various feature locations in the Microsoft 365 Defender portal at <https://security.microsoft.com>. The centralized location to start your trial is on the **Evaluation mode** page at <https://security.microsoft.com/atpEvaluation>.

Before you start your trial, there are some key questions that you need to ask yourself:

- Do I want to passively observe what Defender for Office 365 Plan 2 can do for me, or do I want Defender for Office 365 Plan 2 to take direct action on messages?
- How long do I have before I need to make a decision to keep Defender for Office 365 Plan 2?

This article will help you answer those questions so you can take full advantage of your evaluation of Defender for Office 365.

For a companion guide for how to use your trial, see [Trial playbook: Microsoft Defender for Office 365](trial-playbook-defender-for-office-365.md).

## Overview of Defender for Office 365

Defender for Office 365 helps organizations secure their enterprise by offering a comprehensive slate of capabilities. For more information, see [Microsoft Defender for Office 365](defender-for-office-365.md).

You can also learn more about Defender for Office 365 at this [interactive guide](https://aka.ms/MS365D.InteractiveGuide).

![Microsoft Defender for Office 365 conceptual diagram.](../../media/microsoft-defender-for-office-365.png)

Watch this short video to learn more about how you can get more done in less time with Microsoft Defender for Office 365.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMmIe]

## Audit mode vs. blocking mode

How you evaluate Defender for Office 365 Plan 2 features before you buy depends on the nature of your Microsoft 365 organization:

- You already have Microsoft 365 mailboxes, but you're currently using a third-party service or device for email protection. Mail from the internet flows through the protection service before delivery into your Microsoft 365 organization. Microsoft 365 protection is as low as possible (it's never completely off; for example, malware protection is always enforced).

  ![Mail flows from the internet through the third-party protection service or device before delivery into Microsoft 365.](../../media/mdo-migration-before.png)

  In these environments, you can only try Defender for Office 365 in *audit* mode. You don't need to change your mail flow (MX records) to try Defender for Office 365.

- You already have a Microsoft 365 organization. Mail from the internet flows directly Microsoft 365, but your current subscription has only [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) or [Defender for Office 365 Plan 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet).

  ![Mail flows from the internet into Microsoft 365, with protection from EOP and/or Defender for Office 365 Plan 1.](../../media/mdo-trial-mail-flow.png)

  In these environments, you can try Defender for Office 365 in *audit* mode or in *blocking* mode.

## Evaluation vs. trial

Although the terms 'evaluation' and 'trial' are typically synonymous, the terms have different meanings when you try out Defender for Office 365 Plan 2 features. Specifically, the differences have to do with licensing. You don't need to decide whether you want an 'evaluation' or a 'trial'. We make that decision for you based on the nature of your Microsoft 365 organization:

- **A 'trial' is for Microsoft 365 organizations who don't already have Defender for Office 365 Plan 2 features**: These organizations require Defender for Office 365 Plan 2 licenses so the features of Defender for Office 365 Plan 2 are available to them during the trial period. We automatically provision the required Plan 2 trial licenses for you when you enroll in the trial. Manual steps for getting and assigning licensing are no longer required. Affected Microsoft 365 organizations include:

  - Microsoft 365 E3.
  - Standalone Exchange Online Protection (EOP) organizations (no Exchange Online mailboxes).
  - Organizations with Defender for Office 365 Plan 1 licenses (included or as an add-on). These organizations are in a mixed state compared to the others. For example, they already have impersonation protection in anti-phishing policies, Safe Links policies, and Safe Attachments policies that E3 or standalone EOP organizations don't have. But, they also require trial licenses for the [Automation, investigation, remediation, and education capabilities](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) that are available only in Plan 2.

  The important thing to remember about trial licenses for Defender for Office 365 Plan 2 features: they last for 90 days. After 90 days, the Plan 2 licenses are removed (but [extensions are possible](#q-how-do-i-extend-the-trial)).

- **An 'evaluation' is for Microsoft 365 organizations who already have Defender for Office 365 Plan 2 features**: These organizations don't need additional licenses for Defender for Office 365 Plan 2. Affected Microsoft 365 organizations include:

  - Microsoft 365 E5.
  - Organizations with Defender for Office 365 Plan 2 add-on licenses.

  The important thing to remember about an evaluation of Defender for Office 365 Plan 2 features: it never expires.

The differences between an 'evaluation' and a 'trial' are summarized in the following table:

|SKU|Evaluation period|P2 trial<br>provisioned?|Trial period|
|---|:---:|:---:|---|
|Microsoft 365 E3|n/a|Yes|90 days|
|Standalone EOP (no Exchange Online mailboxes)|n/a|Yes|90 days|
|Defender for Office 365 Plan 1|Unlimited<sup>\*</sup>|Yes|90 days <br><br> <sup>\*</sup>After 90 days, P2 capabilities are turned off. Evaluation continues to work.|
|Defender for Office 365 Plan 2|Unlimited|No|n/a|
|Microsoft 365 E5|Unlimited|No|n/a|

> [!IMPORTANT]
> Throughout the rest of this article, we'll use derivatives of the words 'trial' and 'evaluation' synonymously. If we need to call out licensing, we'll clearly state the differences as required. In other words, don't get confused when we say 'try' or 'evaluate'; they mean the same thing.

## Policies for Defender for Office 365 features

When you evaluate Defender for Office 365, the policies that control protection features in Microsoft 365 are present:

- **Exchange Online Protection (EOP)**: No new or special policies are created. Existing EOP policies are able to act on messages (for example, send messages to the Junk Email folder or to quarantine):

  - [Anti-malware policies](anti-malware-protection.md)
  - [Inbound anti-spam protection](anti-spam-protection.md)
  - [Anti-spoofing protection in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings)

  The default policies for these features are always on, apply to all recipients, and are always applied last after any custom policies.

- **Defender for Office 365**: Policies that are exclusive to Defender for Office 365 are created for your evaluation of Defender for Office 365 as needed:

  - [Impersonation protection in anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Safe Attachments for email messages](safe-attachments.md)
  - [Safe Links for email messages and Microsoft Teams](safe-links.md)

  But, the nature of these policies is different in audit mode vs. blocking mode:

  - **Audit mode**: Regular policies are created, but the policies are configured only to *detect* threats. Defender for Office 365 detects harmful messages for reporting, but the messages aren't acted upon (for example, detected messages aren't quarantined).

  - **Blocking mode**: Policies are created using the Standard template for [preset security policies](preset-security-policies.md). Defender for Office 365 *detects* and *takes action on* harmful messages (for example, detected messages are quarantined).

  The default and recommended selection is to scope these Defender for Office 365 policies to all users in the organization. But during or after setup, you can change the policy assignment to specific users, groups, or email domains.

**Notes**:

- Safe Links will detonate URLs during mail flow. To prevent specific URLs from being detonated, use Allow entries in the Tenant Allow/Block List. For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
- Safe Links doesn't wrap URL links in email message bodies.
- The evaluation policy settings are described in the [Evaluation policy settings](#evaluation-policy-settings) section later in this article.

## Set up an evaluation in audit mode

1. Click **Start evaluation**.

2. In the **Turn on protection** dialog, select **No, I only want reporting**, and then click **Continue**.

3. In the **Select the users you want to include** dialog, configure the following settings:

   - **All users**: This is the default and recommended option.
   - **Select users**: If you select this option, you need to select the internal recipients that the evaluation applies to:
     - **Users**: The specified mailboxes, mail users, or mail contacts.
     - **Groups**:
       - Members of the specified distribution groups or mail-enabled security groups.
       - The specified Microsoft 365 Groups.
       - **Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.

     Click in the appropriate box, start typing a value, and select the value that you want from the results. Repeat this process as many times as necessary. To remove an existing value, click remove ![Remove icon.](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.

     For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   > [!NOTE]
   > You can change these selections after you finish setting up the evaluation.

   When you're finished, click **Continue**.

4. In the **Help us understand your mail flow** dialog, configure the following options:

   - **Share data with Microsoft**: This option is selected by default, but you can clear the check box if you like.

   - One of the following options is automatically selected based on our detection of the MX record for your domain:

     - **I'm using a third-party and/or on-premises service provider**: The MX record for your domain points somewhere other than Microsoft 365. This selection requires the following additional settings after you click **Next**:

       1. In the **Third party or on-premises settings** dialog, configure the following settings:

          - **Select a third party service provider**: Select one of the following values:
            - **Barracuda**
            - **IronPort**
            - **Mimecast**
            - **Proofpoint**
            - **Sophos**
            - **Symantec**
            - **Trend Micro**
            - **Other**

          - **The connector to apply this evaluation to**: Select the connector that's used for mail flow into Microsoft 365.

            [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (also known as *skip listing*) is automatically configured on the connector that you specify.

            When a third-party service or device sits in front of Microsoft 365, Enhanced Filtering for Connectors correctly identifies the source of internet messages and greatly improves the accuracy of the Microsoft filtering stack (especially [spoof intelligence](anti-spoofing-protection.md), as well as post-breach capabilities in [Threat Explorer](threat-explorer.md) and [Automated Investigation & Response (AIR)](automated-investigation-response-office.md).

          - **List each gateway IP address your messages pass through**: This setting is available only if you selected **Other** for **Select a third party service provider**. Enter a comma-separated list of the IP addresses that are used by the third-party protection service or device to send mail into Microsoft 365.

          When you're finished, click **Next**.

       2. In the **Exchange mail flow rules** dialog, decide if you need an Exchange Online mail flow rule (also known as a transport rule) that skips spam filtering for incoming messages from the third-party protection service or device.

          It's likely that you already have an SCL=-1 mail flow rule in Exchange Online that allows all inbound mail from the protection service to bypass (most) Microsoft 365 filtering. Many protection services encourage this spam confidence level (SCL) mail flow rule method for Microsoft 365 customers who use their services.

          As explained in the previous step, Enhanced Filtering for Connectors is automatically configured on the connector that you specify as the source of mail from the protection service.

          Turning on Enhanced Filtering for Connectors without an SCL=-1 rule for incoming mail from the protection service will vastly improve the detection capabilities of EOP protection features like [spoof intelligence](anti-spoofing-protection.md), and could impact the delivery of those newly-detected messages (for example, move to the Junk Email folder or to quarantine). This impact is limited to EOP policies; as previously explained, Defender for Office 365 policies are created in audit mode.

          To create an SCL=-1 mail flow rule or to review your existing rules, click the **Go to Exchange admin center** button on the page. For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          When you're finished, click **Finish**.

     - **I'm only using Microsoft Exchange Online**: The MX records for your domain point to Microsoft 365. There's nothing left to configure, so click **Finish**.

5. A progress dialog appears as your evaluation is set up. When set up is complete, click **Done**.

## Set up an evaluation in blocking mode

1. Click **Start evaluation**.

2. In the **Turn on protection** dialog, select **Yes, protect my organization by blocking threats**, and then click **Continue**.

3. In the **Select the users you want to include** dialog, configure the following settings:

   - **All users**: This is the default and recommended option.
   - **Select users**: If you select this option, you need to select the internal recipients that the evaluation applies to:
     - **Users**: The specified mailboxes, mail users, or mail contacts.
     - **Groups**:
       - Members of the specified distribution groups or mail-enabled security groups.
       - The specified Microsoft 365 Groups.
     - **Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.

     Click in the appropriate box, start typing a value, and select the value that you want from the results. Repeat this process as many times as necessary. To remove an existing value, click remove ![Remove icon.](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.

     For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results. For users, enter an asterisk (\*) by itself to see all available values.

   > [!NOTE]
   > You can change these selections after you finish setting up the evaluation.

   When you're finished, click **Continue**.

4. A progress dialog appears as your evaluation is set up. When setup is complete, click **Done**.

## Reporting in audit mode

- The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) shows detections by Defender for Office 365 in the following views:
  - [View data by Email \> Malware and Chart breakdown by Detection Technology](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [View data by Email \> Phish and Chart breakdown by Detection Technology](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- In [Threat Explorer](threat-explorer.md), messages that were detected by the Defender for Office 365 evaluation show the following banner in the details of the entry:

  ![Notification banner in message details that the Defender for Office 365 evaluation detected a malicious email message.](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

The **Microsoft Defender for Office 365 evaluation** page at <https://security.microsoft.com/atpEvaluation> consolidates the reporting for the policies in the evaluation:

- Impersonation protection in anti-phishing policies
- Safe Links
- Safe Attachments

By default, the charts show data for the last 30 days, but you can filter the date range by clicking ![Calendar icon.](../../media/m365-cc-sc-add-internal-icon.png) **30 days** and selecting from following additional values that are less than 30 days:

- 24 hours
- 7 days
- 14 days
- Custom date range

You can click ![Download icon.](../../media/m365-cc-sc-download-icon.png) **Download** to download the chart data to a .csv file.

## Required permissions

Permissions that are required in **Azure AD** to set up an evaluation of Defender for Microsoft 365 are described in the following list:

- **Create, modify or delete an evaluation**: Security Administrator or Global Administrator.
- **View evaluation policies and reports**: Security Administrator or Security Reader.

For more information about Azure AD permissions in the Microsoft 365 Defender portal, see [Azure AD roles in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)

## Evaluation policy settings

The settings in the Defender for Office 365 that are specifically created for the evaluation are described in the following tables:

### Anti-phishing evaluation policy settings

|Setting|Value|
|---|---|
|Name|Evaluation Policy|
|AdminDisplayName|Evaluation Policy|
|AuthenticationFailAction|MoveToJmf|
|Enabled|True|
|EnableFirstContactSafetyTips|False|
|EnableMailboxIntelligence|True|
|EnableMailboxIntelligenceProtection|True|
|EnableOrganizationDomainsProtection|False|
|EnableSimilarDomainsSafetyTips|False|
|EnableSimilarUsersSafetyTips|False|
|EnableSpoofIntelligence|True|
|EnableSuspiciousSafetyTip|False|
|EnableTargetedDomainsProtection|False|
|EnableTargetedUserProtection|False|
|EnableUnauthenticatedSender|True|
|EnableUnusualCharactersSafetyTips|False|
|EnableViaTag|True|
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|ImpersonationProtectionState|Manual|
|IsDefault|False|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|PhishThresholdLevel|1|
|PolicyTag|blank|
|RecommendedPolicyType|Evaluation|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainsToProtect|{}|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|TargetedUsersToProtect|{}|

### Safe Attachments evaluation policy settings

|Setting|Value|
|---|---|
|Name|Evaluation Policy|
|Action|Allow|
|ActionOnError|True|
|AdminDisplayName|Evaluation Policy|
|ConfidenceLevelThreshold|80|
|Enable|True|
|EnableOrganizationBranding|False|
|IsBuiltInProtection|False|
|IsDefault|False|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Evaluation|
|Redirect|False|
|RedirectAddress|blank|
|ScanTimeout|30|

### Safe Links evaluation policy settings

|Setting|Value|
|---|---|
|Name|Evaluation Policy|
|AdminDisplayName|Evaluation Policy|
|AllowClickThrough|True|
|CustomNotificationText|blank|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|False|
|EnableSafeLinksForTeams|False|
|IsBuiltInProtection|False|
|LocalizedNotificationTextList|{}|
|RecommendedPolicyType|Evaluation|
|ScanUrls|True|
|TrackClicks|True|

## Frequently asked questions

### Q: Do I need to get or activate trial licenses?

A: No. The trial automatically provisions Defender for Office 365 Plan 2 licenses if you need them as previously described.

### Q: How do I extend the trial?

A: See [Extend your trial](/microsoft-365/commerce/try-or-buy-microsoft-365#extend-your-trial).

### Q: What happens to my data after the trial expires?

A: After your trial expires, you'll have access to your trial data (data from features in Defender for Office 365 that you didn't have previously) for 30 days. After this 30 day period, all policies and data that were associated with the Defender for Office 365 trial will be deleted.

### Q: How many times can I use the Defender for Office 365 trial in my organization?

A: A maximum of 2 times. If your first trial expires, you need to wait at least 30 days after the expiration date before you can enroll in the Defender for Office 365 trial again. After your second trial, you can't enroll in another trial.

### Q: In audit mode, are there scenarios where Defender for Office 365 will act on messages?

A: Yes. No one in any program or SKU can turn off or bypass acting on messages that are classified as malware or high confidence phishing by the service.

In audit mode, [anti-spoofing protection in EOP](set-up-anti-phishing-policies.md#spoof-settings) also takes action on message. To prevent anti-spoofing protection from acting on messages, create an Exchange mail flow rule (also known as a transport rule) where inbound email bypasses all types of filtering that can be bypassed (including anti-spoofing protection). For instructions, see [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

### Q: In what order are policies evaluated?

A: See [Order of precedence for preset security policies and other policies](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies).
