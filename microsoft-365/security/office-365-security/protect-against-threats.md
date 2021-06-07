---
title: Protect against threats
f1.keywords: 
  - NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview

localization_priority: Normal
ms.date: 09/08/2020
search.appverid: 
  - MOE150
  - MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection: 
  - M365-security-compliance
  - m365initiative-defender-office365
description: Admins can learn about threat protection in Microsoft 365 and configure how to use it for your organization.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
---

# Protect against threats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks. If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.

> [!IMPORTANT]
> **Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**. Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.

## Requirements

### Subscriptions

Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features. The table below lists the protection features included in this article together with the minimum subscription requirements.

> [!TIP]
> Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**). This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.

<br>

****

|Protection type|Subscription requirement|
|---|---|
|Audit logging (for reporting purposes)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Anti-malware protection|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Anti-phishing protection|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Anti-spam protection|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Zero-hour auto purge (for email)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads|[Microsoft Defender for Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Advanced anti-phishing protection|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### Roles and permissions

To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Take a look at the table below for roles that can do these actions.

<br>

****

|Role or role group|Where to learn more|
|---|---|
|global administrator|[About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md)|
|Security Administrator|[Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organization Management|[Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> and <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### Turn on Audit logging for reporting and investigation

- Start your audit logging early. You'll need auditing to be **ON** for some of the following steps. Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*. To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).

## Part 1 - Anti-malware protection in EOP

For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Open <https://security.microsoft.com/antimalwarev2>.

2. On the **Anti-malware** page, select the policy named **Default** policy by clicking on the name.

3. In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:
   - Select **Enable the common attachments filter** to turn on the common attachments filter. Click **Customize file types** to add more file types.
   - Verify that **Enable zero-hour auto purge for malware** is selected.
   - Verify that none of the settings in the **Notification** section are selected.

   When you're finished, click **Save**.

4. Back on the policy details flyout, click **Close**.

For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

## Part 2 - Anti-phishing protection in EOP and Defender for Office 365

[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

The following procedure describes how to configure the default anti-phishing policy. Settings that are only available in Defender for Office 365 are clearly marked.

1. Open <https://security.microsoft.com/antiphishing>.

2. On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.

3. In the policy details flyout that appears, configure the following settings:

   - **Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the **Edit protection settings** flyout that opens:
     - **Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).
     - **Impersonation** section<sup>\*</sup>: Configure the following values:
       - Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.
       - Select **Enable domains to protect**, and then configure the following settings that appear:
         - Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.
         - To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.
     - **Add trusted senders and domains** section<sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.
     - Mailbox intelligence settings<sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.
     - **Spoof** section: Verify **Enable spoof intelligence** is selected.

     When you're finished, click **Save**.

   - **Actions** section: Click **Edit actions** and configure the following settings in the **Edit actions** flyout that opens:
     - **Message actions** section: Configure the following settings:
       - **If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.
       - **If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.
       - **If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).
       - **If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).
     - **Safety tips & indicators** section: Configure the following settings:
       - **Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).
       - **Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).
       - **Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).
       - **Show (?) for unauthenticated senders for spoof**: Select (turn on).
       - **Show "via" tag**: Select (turn on) if this setting is available.

     When you're finished, click **Save**.

   <sup>\*</sup> This setting is available only in Defender for Office 365.

4. Click **Save** and then click **Close**

For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## Part 3 - Anti-spam protection in EOP

For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

1. Open <https://security.microsoft.com/antispam>.

2. On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.

3. In the policy details flyout that appears, do the following steps:
   - **Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**. In the **spam threshold and properties** flyout that appears, set the **Bulk email threshold** value to 5 (Strict) or 6 (Standard). When you're finished, click **Save**.
   - **Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains.

4. When you're finished, click **Close**.

For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)

Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.

### Safe Attachments policies in Microsoft Defender for Office 365

To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.

1. In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.

2. In the **New Safe Attachments policy** wizard that appears, configure the following settings:

   - In the **Name** box, type `Block malware`, and then click **Next**.

   - On the **Settings** page, configure the following settings:
     - In the **Safe attachments unknown malware response** section, choose **Block**.
     - In the **Redirect attachment** section, select the option **Enable redirect**. Specify the email address for your organization's security administrator or operator, who will review detected files.

     Click **Next**.

3. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

4. Review your settings and then click **Finish**.

### Safe Links policies in Microsoft Defender for Office 365

To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.

1. In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:

   - Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).
   - **Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).
   - **Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).

   When you're finished, click **Save**.

2. Back on the main Safe Links page, click **Create**.

3. In the **Create Safe Links policy** wizard that appears, configure the following settings:

   - In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.

   - On the **Settings** page, configure the following settings:
     - **Select the action for unknown potentially malicious URLs in messages**: Choose **On**.
     - **Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.
     - **Apply safe links to email messages sent within the organization**
     - **Wait for URL scanning to complete before delivering the message**
     - **Apply safe links to email messages sent within the organization**
     - **Do not allow users to click through to original URL**

     Click **Next**

4. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

5. Review your settings and then click **Finish**.

To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).

## Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on

Workloads like SharePoint, OneDrive, and Teams are built for collaboration. Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries. You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> **Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!

1. In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.

2. Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.

3. Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).

4. (Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.

   - `$true` blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files.
   - `$false` blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file.

   > [!TIP]
   > To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.

### Now set up alerts for detected files

To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.

1. In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.

2. Choose **New alert policy**.

3. Specify a name for the alert. For example, you could type Malicious Files in Libraries.

4. Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.

5. In the **Send this alert when...** section, set:

   a. In the **Activities** list, choose **Detected malware in file**.

   b. Leave the **Users** field empty.

6. In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.

7. **Save**.

To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).

> [!NOTE]
> When you're finished configuring, use these links to start workload investigations:
>
>- [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)
>- [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Manage quarantined messages and files as an administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## Part 6 - Additional settings to configure

Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.

### Zero-hour auto purge for email in EOP

[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). This protection is turned on by default; however, the following conditions must be met for protection to be in effect:

- Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).

- Users have kept their default [junk email settings](configure-junk-email-settings-on-exo-mailboxes.md), and haven't turned off junk email protection.

To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).

## Post-setup tasks and next steps

After configuring the threat protection features, make sure to monitor how those features are working! Review and revise your policies so that they do what you need them to. Also, watch for new features and service updates that can add value.

****

|What to do|Resources to learn more|
|---|---|
|See how threat protection features are working for your organization by viewing reports|[Security dashboard](security-dashboard.md) <p> [Email security reports](view-email-security-reports.md) <p> [Reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) <p> [Threat Explorer](threat-explorer.md)|
|Periodically review and revise your threat protection policies as needed|[Secure Score](../defender/microsoft-secure-score.md) <p> [Smart reports and insights](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 threat investigation and response features](./office-365-ti.md)|
|Watch for new features and service updates|[Standard and Targeted release options](../../admin/manage/release-options-in-office-365.md) <p> [Message Center](../../admin/manage/message-center.md) <p> [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Service Descriptions](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365|[Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md)|
