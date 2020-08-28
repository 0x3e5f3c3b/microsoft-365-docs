---
title: "Empower remote workers with Microsoft 365"
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/08/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection: 
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: seo-marvel-jun2020
description: Make sure you have enabled all features in Microsoft 365 to maximize remote worker productivity and maintain secure access to your servers, data, and cloud.
---

# Empower remote workers with Microsoft 365

Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes. Allowing workers to work away from the office is important for many organizations to:

- Save on office space.
- Hire and retain workers who are unwilling to relocate.
- Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.

Microsoft 365 has the capabilities to empower your workers to work remotely.

![Empower your remote workers with Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)


| | |
|:-------|:-----|
| Connected | From anywhere in the world and at any time, remote workers are able to access: <ul><li>Cloud-based services and data in your Microsoft 365 subscription. </li><li>Organization resources, such those offered by on-premises application datacenters.</li></ul> |
| Secure | Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss. |
| Managed | Your remote worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health. |
| Collaborative and productive | Your remote workers can be as productive as on-premises in a highly collaborative way with: <ul><li>Online meetings and chat sessions with Teams. </li><li>Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive. </li><li>Shared tasks and workflows to divide up the work and get things done. </li></ul> |
|||

For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD). To protect your Windows 10 devices, they should be enrolled in Intune. Here is a high-level view of the infrastructure.

![The basic infrastructure for remote workers with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

To meet the criteria for remote workers, use these Microsoft 365 capabilities and features.

| Capability or feature | Description | Licensing |
|:-------|:-----|:-------|
| MFA enforced with security defaults	| Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.	| Microsoft 365 E3 and E5 |
| MFA enforced with Conditional Access| Require MFA based on the properties of the sign-in with Conditional Access policies.	| Microsoft 365 E3 and E5 | 
| MFA enforced with risk-based Conditional Access	| Require MFA based on the risk of the user sign-in with Azure Advanced Threat Protection. | Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses | 
| Self-Service Password Reset (SSPR)	| Allow your users to reset or unlock their passwords or accounts.	| Microsoft 365 E3 and E5 |
| Azure AD Application Proxy	| Provide secure remote access for web-based applications hosted on intranet servers.	| Requires separate paid Azure subscription |
| Azure Point-to-Site VPN	| Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.	| Requires separate paid Azure subscription |
| Windows Virtual Desktop	| Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure. | Requires separate paid Azure subscription |
| Remote Desktop Services (RDS)	| Allow employees to connect into Windows-based computers on your intranet.	| Microsoft 365 E3 and E5 | 
| Remote Desktop Services Gateway	| Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.	| Requires separate Windows Server licenses |
| Microsoft Intune | Manage devices and applications.	| Microsoft 365 E3 and E5 | 
| Configuration Manager	| Manage software installations, updates, and settings on your devices | Requires separate Configuration Manager licenses |
| Desktop Analytics	| Determine the update readiness of your Windows clients.	| Requires separate Configuration Manager licenses |
| Windows Autopilot	| Set up and pre-configure new Windows 10 devices for productive use.	| Microsoft 365 E3 and E5 |
| Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Create, communicate, and collaborate. | Microsoft 365 E3 and E5 |
||||

Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.

1. [Increase sign-in security with MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Provide remote access to on-premises apps and services](empower-people-to-work-remotely-remote-access.md)
3. [Deploy security and compliance services](empower-people-to-work-remotely-security-compliance.md)
4. [Deploy endpoint management for your devices, PCs, and other endpoints](empower-people-to-work-remotely-manage-endpoints.md)
5. [Deploy remote worker productivity apps and services](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Train remote workers and address usage feedback](empower-people-to-work-remotely-train-monitor-usage.md)

![The steps to empower remote workers with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
