---
title: "Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use this Test Lab Guide to enable additional Microsoft 365 security settings your Microsoft 365 Enterprise test environment.
---

# Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment

With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.

![Test Lab Guides for the Microsoft cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.
  
## Phase 1: Build out your Microsoft 365 Enterprise test environment

If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization. 


## Phase 2: Configure increased Microsoft 365 security

In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### Configure SharePoint Online to block apps that don’t support modern authentication

Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets. 

1. Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.
    
  - If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.
    
  - If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.
 
2. From the **Microsoft 365 admin center** tab, click **Admin**.
3. On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.
4. On the new **SharePoint admin center** tab, click **Access control**.
5. Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.


### Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams

Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.

1. Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.

2. In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**. 

3. Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.

4. Click **Save**.


### Enable anti-malware

Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author. 

Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

To ensure that anti-malware processing is being performed on files with common attachment file types:

1. Click the back button on your browser to get back to the **Policy** page.
2. Click **Anti-malware**.
3. Double-click the policy named **Default**.
4. In the **Anti-malware policy** window, click **Settings**.
4. Under **Common Attachment Types filter**, click **On > Save**.


## Phase 3: Examine Office 365 security tools and logs

In this phase, you look at built-in services that inform you about security events and measure your overall security posture.

### Threat management dashboard

Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).


### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## Next steps

See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.

Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.

## See also

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md)

[Deploy Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise documentation](https://docs.microsoft.com/microsoft-365-enterprise/)

