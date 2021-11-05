---
title: Assign roles and permissions in Microsoft Defender for Business
description: Learn how to assign roles and permissions in Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp 
audience: Admin
ms.topic: overview
ms.date: 11/04/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH 
ms.collection: 
- SMB
- M365-security-compliance
---

# Assign roles and permissions in Microsoft Defender for Business

> [!IMPORTANT]
> Some information in this article relates to prereleased products/services that might be substantially modified before they are commercially released. Microsoft makes no warranties, express or implied, for the information provided here. This article includes links to online content that might describe some features that are not included in Microsoft Defender for Business (preview).

To perform tasks in the Microsoft 365 Defender portal, such as configuring Microsoft Defender for Business, viewing reports, or taking response actions on detected threats, appropriate permissions must be assigned to your security team. Permissions are granted through roles that are assigned in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) or in [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal). 

## What to do

1. [Learn about roles in Defender for Business](#roles-in-defender-for-business)
2. [View or edit role assignments](#view-or-edit-role-assignments)
3. [Proceed to your next steps](#next-steps) 

## Roles in Defender for Business

The following table describes the three roles that can be assigned in Defender for Business. [Learn more about admin roles](../../admin/add-users/about-admin-roles.md). <br/><br/>

| Permission level | Description |
|:---|:---|
| **Global administrators** (also referred to as global admins) <br/><br/> *As a best practice, limit the number of global admins.* | Global admins can perform all kinds of tasks. The person who signed up your company for Microsoft 365 or for Microsoft Defender for Business is a global administrator by default. <br/><br/> Global admins are able to access/change settings across all Microsoft 365 portals, such as: <br/>- The Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) |
| **Security administrators** (also referred to as security admins) | Security admins can perform the following tasks: <br/>- View and manage security policies and settings <br/>- View and manage security threats and alerts (these activities include taking response actions on endpoints) <br/>- View security information and reports |
| **Security reader** | Security readers can perform the following tasks: <br/>- View security policies and settings <br/>- View security threats and alerts <br/>- View security information and reports  |


## View or edit role assignments

> [!NOTE]
> If you are working through the initial setup and configuration process for Defender for Business, you'll be prompted to grant people access when you sign in. 

:::image type="content" source="media/mdb-grant-access.png" alt-text="Screenshot of granting people access to Defender for Business.":::

1. Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.

2. In the navigation pane, choose **Permissions & roles**, and then under **Azure AD**, select **Roles**.

3. Select one of the following roles to open its side pane:

   - Global administrator
   - Security administrator
   - Security reader

   > [!IMPORTANT]
   > Microsoft recommends granting people access to only what they need to perform their tasks. We call this concept *least privilege* for permissions. To learn more, see [Best practices for least-privileged access for applications](/azure/active-directory/develop/secure-least-privileged-access). 

4. In the side pane, select the **Manage members in Azure AD** link. This action takes you to Azure Active Directory (Azure AD) where you can view and manage your role assignments.

5. Select a user to open their profile, and then choose **Assigned roles**.

   - To add a role, choose **+ Add assignments**.
   - To remove a role, choose **X Remove assignments**. 

## Next steps

Proceed to:

- [Step 3: Set up email notifications](mdb-email-notifications.md)

- [Step 4: Onboard devices to Microsoft Defender for Business](mdb-onboard-devices.md)