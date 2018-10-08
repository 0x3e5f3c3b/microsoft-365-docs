---
title: "About AutoPilot Profile settings"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 6/15/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'ZTDProfileSettings'
- 'O365E_ZTDProfileSettings'
- 'BCS365_ZTDProfileSettings'
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: "AutoPilot profiles help you control how Windows gets installed on user devices. The profiles contain default and optional settings like skip Cortana installation."
---

# About AutoPilot Profile settings

## AutoPilot profile settings

You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.
  
 **AutoPilot default features (required) that are set automatically:**
  
|**Setting**|**Description**|
|:-----|:-----|
|Skip Cortana, OneDrive and OEM registration  <br/> |Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.  <br/> |
|Sign in experience with your company brand  <br/> |If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.  <br/> |
|MDM auto-enrollment with configured AAD accounts.  <br/> |The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.  <br/> |
   
 **Optional settings:**
  
|**Setting**|**Description**|
|:-----|:-----|
|Skip privacy settings (Off by default)  <br/> |If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.  <br/> |
|Don't allow the user to become the local admin  <br/> |If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.  <br/> |
   
## See also

[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Get started with Microsoft 365 Business](microsoft-365-business-0.md)
  
[Manage Business Microsoft 365 Business](manage.md)

