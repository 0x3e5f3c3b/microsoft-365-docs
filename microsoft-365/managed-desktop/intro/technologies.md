---
title: Microsoft Managed Desktop technologies
description:  This topic lists the technologies and apps used in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
---

# Microsoft Managed Desktop technologies

This topic lists the technologies and apps used in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users. For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).

This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices. Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation. 

## Office 365 E3
 |
 --- | ---
Office 365 standard suite(64-bit) | The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>The 64-bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in Office 365. However, since the installation of these applications depends on the standard Office suite installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users. For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md)  
Store Apps |	Microsoft Sway and Power BI are not shipped with the device. These apps are available for download from Microsoft Store.
Win32 Applications |	Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices. Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment. 
Web Applications |	Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device. Users can access the web version of these applications with a browser.


## Windows 10 Enterprise E5

 |
 --- | ---
Application Virtualization (App-V) |	Microsoft Managed Desktop does not support this type of deployment as it is not supported by Microsoft Intune.
Microsoft Defender Advanced Threat Protection |	 Microsoft Managed Desktop uses this to monitor device security. 

## Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |	You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.
Microsoft Cloud App Security |	You can use this optional feature with Microsoft Managed Desktop.
Azure Information Protection P2	 | You can use this optional feature with Microsoft Managed Desktop.
