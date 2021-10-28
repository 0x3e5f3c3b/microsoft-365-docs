---
title: Set up Microsoft Viva Learning (Preview) in the Teams admin center
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: 
ms.prod: microsoft-365-enterprise
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-viva-learning
ms.custom: admindeeplinkTEAMS
ms.localizationpriority: medium
description: Learn how to configure Microsoft Viva Learning (Preview) in the Teams admin center.
---

# Set up Microsoft Viva Learning (Preview) in the Teams admin center

> [!NOTE]
> The information in this article relates to a preview product that may be substantially modified before it's commercially released.

> [!NOTE]
> [Preview is currently closed to new participants.]

The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant. These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center-preview.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center-preview.md#private-preview-tenants).

## Public Preview tenants

### Administrator steps for Public Preview tenants

Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.

1. Enable Public Preview features for Viva Learning (Preview) users.

   1. Modify Teams update policy to enable Public Preview features. See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).

   1. Enable the update policy for users or groups who will perform Viva Learning (Preview) testing. See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).

2. Modify the app permission policy for Viva Learning (Preview) users.

    a. Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy. See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).

   1. Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing. See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).

3. Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center-preview.md#user-steps-for-public-preview-tenants).

> [!IMPORTANT]
> For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release. However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.

### User steps for Public Preview tenants

Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center-preview.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.

1. Users must select their profile image > **About** > **Public Preview**.

    ![Upper navigation in the Teams application showing user's profile.](../media/learning/learning-app-select-profile-teams.png)

2. Users must accept the Public Preview terms and conditions.

    ![Switch to public preview build.](../media/learning/learning-app-switch-to-public-preview.png)

3. Users can now find Viva Learning (Preview) in the Teams app store and start using it.

## Private Preview tenants

### Administrator steps for Private Preview (or Beta) tenants

For Private Preview tenants, there are no additional policies that need to be enabled. However, Viva Learning (Preview) must be made available for users in your organization.

1. In the left navigation of the Teams admin center, go to **Teams apps** > <a href="https://go.microsoft.com/fwlink/?linkid=2172960" target="_blank">**Manage apps**</a>.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

## Next step

[Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center](content-sources-365-admin-center.md)
