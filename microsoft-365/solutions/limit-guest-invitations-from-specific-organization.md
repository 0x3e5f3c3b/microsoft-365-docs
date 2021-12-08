---
title: "Limit who can be invited by an organization"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: 
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 
---

# Limit who can be invited by an organization


## Create a security group



1. Sign in to the [Azure portal](https://portal.azure.com) using a Global administrator or Security administrator account. Then open the **Azure Active Directory** service.
1. On the **Active Directory** page, select **Groups** and then select **New group**.
1. Choose **Security** for the **Group type**.
1. Type a **Group name.** 
1. Optionally, add a description for the group.
1. For **Azure AD roles can be assigned to the group**, choose **No**.
1. Select a pre-defined **Membership type (required).** For more information on membership types, see [Group and membership types](#membership-types).
1. Add group owners and members or a dynamic query if you're using dynamic user membership.
1. Select **Create**. Your group is created and ready for you to add members.



## Add an organization


1. Sign in to the [Azure portal](https://portal.azure.com) using a Global administrator or Security administrator account. Then open the **Azure Active Directory** service.
2. Select **External Identities**, and then select **Cross-tenant access settings (preview)**.
3. Select **Organizational settings**.
4. Select **Add organization**.
5. On the **Add organization** pane, type the full domain name (or tenant ID) for the organization.
1. Select the organization in the search results, and then select **Add**.
2. The organization appears in the **Organizational settings** list. At this point, all access settings for this organization are inherited from your default settings.

## Choose who can be invited as guests by an organization



1. Sign in to the [Azure portal](https://portal.azure.com) using a Global administrator or Security administrator account. Then open the **Azure Active Directory** service.
2. Select **External Identities**, and then select **Cross-tenant access settings (preview)**.
3. Select the outbound access link for the organization that you want to modify.
4. On the **B2B collaboration** tab, choose **Customize settings**.
5. Under **Access status**, choose **Allow access**.
6. Under **Target**, choose **Select external users and groups**.
7. Select the link to add users and groups.
8. Search for and select the security group that you want to use.
9. Choose **Select**.
10. Select **Save** and close the **Outbound access settings** blade.


## Related topics

