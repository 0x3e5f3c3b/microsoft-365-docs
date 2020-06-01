---
title: "Turning Integrated Apps on or off"
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: "Learn about Integrated Apps and how to turn them on to allow third-party apps to access users' Microsoft 365 information."
---

# Integrated apps in Microsoft 365

This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data. An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.

If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it. If you turn this setting off, then admins must consent to those apps before users may use them. In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.

A user can give access only to apps they own that access their Office 365 information. They can't give an app access to any other user's information.

## Turning Integrated apps on or off
<a name="__toc379982114"> </a>

Here's how to turn Integrated Apps on or off.

1. In the admin center, go to the **Settings** \> **Settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **Integrated apps**.

2. On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.

## More info on Integrated Apps
<a name="__toc379982114"> </a>

To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/configure-admin-consent-workflow).

To learn about managing consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/manage-consent-requests).