---
title: Secure by default in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date:
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: "Learn how to find and use email security reports for your organization. Email security reports are available in the Security & Compliance Center."

---

# Secure by default in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Secure by default" is a term used to define the default settings that are most secure as possible. 

However, security needs to be balanced with productivity. This can include balancing across:
- Usability: settings should not get in the way of user productivity.
- Risk: security might block important activities.
- Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved. 

Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP). This  protection includes:
1. Email with suspected malware will automatically be quarantined and recipients will be notified. See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).
1. Phishing email identified as "high confidence" will be handled according to the anti-spam policy action. See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).

Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish. These overrides include:
- Allowed sender lists or allowed domain lists (anti-spam policies)
- Outlook Safe senders
- IP Allow List (connection filtering)

More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

## Exceptions
The only overrides that allow all messages include:
- Exchange Transport Rules (ETR)/mail flow rules.  Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.
- Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.

This is useful for:
- Phish simulation: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.
- Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad). Teams can then review to see if they contain malicious content.
- Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.  Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365. 
- False positive that are still being analyzed by Microsoft.
