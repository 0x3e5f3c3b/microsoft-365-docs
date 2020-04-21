---
title: "Report spam, non-spam, and phishing messages to Microsoft"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date:
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: "Admins can learn about the different ways to report good and bad messages to Microsoft."
---

# Report messages and files to Microsoft

Users and admins in Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have several different methods for reporting messages and files to Microsoft.

|||
|---|---|
|**Method**|**Description**|
|[Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md)|The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).|
|[Enable the Report Message add-in in Office 365](enable-the-report-message-add-in.md)|Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in. <br/><br/> Depending on your subscription, messages that users reported with the add-in are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions). <br/><br/> You can configure reported messages to be copied or redirected to a mailbox that you specify. For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).|
|[Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Only works in Outlook.|
|[Report junk and phishing email in Outlook on the web in Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP). <br/><br/> You can configure reported messages to be copied or redirected to a mailbox that you specify. For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).|
|[Manually submit messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing. <br/><br/> Also learn how to create a mail flow rule (also known as a transport rule) that notifies you when users send messages to these reporting email addresses.|
|[Submit malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use the Microsoft Security Intelligence site to submit attachments and other files.|
|

If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center. For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).