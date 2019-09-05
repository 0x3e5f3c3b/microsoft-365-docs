---
title: Approve or reject actions related to automated investigation and remediation in Microsoft Threat Protection 
description: Use the Action Center to manage actions related to automated investigation and response
keywords: action, center, autoair, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
- M365-security-compliance 
ms.topic: conceptual
---

# Approve or reject actions related to automated investigation and remediation in Microsoft Threat Protection

Pending actions for machines or user accounts can be reviewed and approved (or rejected) within the Action center, within the context of an incident, or in an investigation details view. Pending actions for email content can be reviewed and approved (or rejected) in the Office 365 Security & Compliance Center.

> [!NOTE]
> You must be a global administrator, security administrator, or security operator to approve or reject an action. Security readers can view, but not approve or reject, actions. To learn more about roles and permissions, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/permissions-microsoft-365-compliance-security).

## Review a pending action in the Action center

![Action Center](../images/air-actioncenter.png)

1. Go to [https://securityoperations.microsoft.com](https://securityoperations.microsoft.com) and sign in. 

2. In the navigation pane, choose **Action center**. 

2. In the Action Center, on the **Pending** tab, select an item. Depending on the item, one of the following occurs:

    - If the action pertains to email content, you are taken to the investigation in the Office 365 Security & Compliance Center, where you can view more information and then either approve or reject the recommended action.
 
    - If the action pertains to a machine or user account, a flyout opens, where you can view more information, click links to an associated alert or investigation,and approve or reject the action.<br/>![Approve or reject an action](../images/air-actioncenter-itemselected.png)

## Review a pending action in the investigation details view

In the investigation details view, you can review and approve pending actions. 

![Investigation details](../images/mtp-air-investdetails.png)

1. On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.

2. Select an item in the list, and then choose **Approve** or **Reject**.