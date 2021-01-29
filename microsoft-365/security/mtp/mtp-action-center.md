---
title: Go to the Action center to view and approve your automated investigation and remediation tasks
description: Use the Action Center to view details about automated investigation and approve pending actions
keywords: Action Center, threat protection, investigation, alert, pending, automated, detection
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords: 
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 01/29/2021
---

# The Action center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Applies to:**
- Microsoft 365 Defender

The improved Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together the results of current and past investigations across your organization's devices, email & collaboration content, and identities. As [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) are taken or are pending approval, such actions are consolidated in a single Action center, providing your security operations team with a "single pane of glass" experience.  

![Action Center](../../media/air-actioncenter.png)

Read this article to get an overview of the Action center, including available actions, required permissions, and next steps.

## A "single pane of glass" experience

The Action center provides a "single pane of glass" experience for tasks, such as:
- Approving pending remediation actions;
- Viewing an audit log of already approved remediation actions; and
- Reviewing completed remediation actions.

Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.

## Go to the Action center

1. Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in. 
2. In the navigation pane, choose **Action center**. 

When you visit the Action center, you see two tabs: Pending actions and History. The following table summarizes what you'll see on each tab:


|Tab  |Description  |
|---------|---------|
|**Pending**     | Displays a list of actions that require attention. You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as Quarantine file). <p>TIP: Make sure to review and approve (or reject) pending actions as soon as possible so that your automated investigations can complete in a timely manner.       |
|**History**     | Serves as an audit log for actions that were taken, such as: <br/>- Remediation actions that were taken as a result of automated investigations <br/>- Remediation actions that were taken on suspicious or malicious email messages, files, or URLs<br/>- Remediation actions that were approved by your security operations team <br/>- Commands that were run and remediation actions that were applied during Live Response sessions<br/>- Remediation actions that were taken by your antivirus protection <p>Provides a way to undo certain actions (see [Undo completed actions](mtp-autoir-actions.md#undo-completed-actions)).        |

## Available actions

As remediation actions are taken, they're listed on the **History** tab in the Action center. Such actions include the following:

- Collect investigation package 
- Isolate device (this action can be undone) 
- Offboard machine 
- Release code execution 
- Release from quarantine 
- Request sample 
- Restrict code execution (this action can be undone) 
- Run antivirus scan 
- Stop and quarantine 

> [!NOTE]
> In addition to remediation actions that are taken automatically, your security operations team can take manual actions to address detected threats. For more information about automatic and manual remediation actions, see [Remediation actions](mtp-remediation-actions.md).

## Action source

(**NEW!**) As you know, Microsoft 365 Defender brings together automated investigation and response capabilities across multiple services, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). The improved Action center now includes an **Action source** column that tells you where each remediation action came from. 

The following table describes possible **Action source** values:

| Action source value | Description |
|:-----|:---|
| **Manual device action** | A manual action taken on a device. Examples include [device isolation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) or [file quarantine](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files). |
| **Manual email action** | A manual action taken on email. An example includes soft-deleting email messages or [remediating an email message](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365). |
| **Automated device action** | An automated action taken on an entity, such as a file or process. Examples of automated actions include sending a file to quarantine, stopping a process, and removing a registry key. (See [Remediation actions in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Automated email action** | An automated action taken on email content, such as an email message, attachment, or URL. Examples of automated actions include soft-deleting email messages, blocking URLs, and turning off external mail forwarding. (See [Remediation actions in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Advanced hunting action** | Actions taken on devices or email with [advanced hunting](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview). |
| **Explorer action** | Actions taken on email content with [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer). |
| **Manual live response action** | Actions taken on a device with [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response). Examples include deleting a file, stopping a process, and removing a scheduled task. |
| **Live response action** | Actions taken on a device with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis). Examples of actions include isolating a device, running an antivirus scan, and getting information about a file. |

## Required permissions for Action center tasks

To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:

|Remediation action |Required roles and permissions |
|--|----|
|Microsoft Defender for Endpoint remediation (devices) |Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- or ---<br/>Active remediation actions role assigned in Microsoft Defender for Endpoint <br/> <br/> To learn more, see the following resources: <br/>- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender for Office 365 remediation (Office content and email)  |Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- and --- <br/>Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) <br/><br/>**IMPORTANT**: If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities. You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center. <br/><br/>To learn more, see the following resources: <br/>- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center. However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned. We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.

## Next steps 

- [Approve or reject pending actions following an automated investigation](mtp-autoir-actions.md)
- [View the results of an automated investigation](mtp-autoir-results.md)

