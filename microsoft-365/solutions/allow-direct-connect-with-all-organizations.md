---
title: "Enable shared channels with all organizations"
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

# Enable shared channels with all organizations



## Allow users to invite people in other organizations to participate in shared channels


1. Sign in to the [Azure portal](https://portal.azure.com) using a Global administrator or Security administrator account. Then open the **Azure Active Directory** service.
2. Select **External Identities**, and then select **Cross-tenant access settings (preview)**.
3. On the **Default settings** tab, under **Inbound access settings**, select **Edit inbound defaults**.
4. Select the **B2B direct connect** tab.
5. On the **Users and groups** tab, under **Access status**, choose **Allow access**.
6. On the **External applications** tab, under **Access status**, choose **Allow access**.
7. Select **Save**.
8. Select the **Trust settings** tab.
9. Choose if you want to trust multifactor authentication, compliant devices, or hybrid Azure AD joined devices from other organizations.
10. Select **Save**.
11. Close the **Default settings** blade.


## Allow users to participate in shared channels in other organizations


1. Sign in to the [Azure portal](https://portal.azure.com) using a Global administrator or Security administrator account. Then open the **Azure Active Directory** service.
2. Select **External Identities**, and then select **Cross-tenant access settings (preview)**.
3. On the **Default settings** tab, under **Outbound access settings**, select **Edit outbound defaults**.
4. Select the **B2B direct connect** tab.
5. On the **Users and groups** tab, under **Access status**, choose **Allow access**.
6. On the **External applications** tab, under **Access status**, choose **Allow access**.
7. Select **Save**.
8. Close the **Default settings** blade.





## Related topics

