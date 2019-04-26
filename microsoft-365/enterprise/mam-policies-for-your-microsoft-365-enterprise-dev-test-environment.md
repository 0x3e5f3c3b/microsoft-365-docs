---
title: "Device compliance policies for your Microsoft 365 Enterprise test environment"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use this Test Lab Guide to add Intune device compliance policies to your Microsoft 365 Enterprise test environment.
---

# Device compliance policies for your Microsoft 365 Enterprise test environment

With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.

![Test Lab Guides for the Microsoft cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.

## Phase 1: Build out your Microsoft 365 Enterprise test environment

If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization. 
>  

## Phase 2: Create a device compliance policy for Windows 10 devices

In this phase, you create a device compliance policy for Windows 10 devices.
  
1. Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.
    
2. On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).

3. On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.
    
4. If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.
    
5. In the left navigation pane, click **Groups**.
    
6. On the **Groups-All groups** blade, click **+ New Group**.
    
7. On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**. 
    
8. Close the **Group** blade.
    
11. Close the **Groups-All groups** blade.
    
12. On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.
    
13. On the **Compliance Policy Profiles** blade, click **Create Policy**.
    
14. On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.
    
15. On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.
    
16. On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.
    
17. On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.
    
18. Click **Save**, and then close the **Windows 10 - Assignments** blade.
    
19. Close the **Compliance Policy Profiles** blade.
    
20. On the **Microsoft Intune** blade, click **Client apps** in the left navigation.
    
21. On the **Client Apps** blade, click **Apps**, and then click **Add**. 

22. In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.

23. Click **Configure App Suite**, and then click **OK**.

24. Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.

25. Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.

26. On the **Add app** blade, click **Add**.

You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group. 
  
## Next step

Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.

## See also

[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Deploy Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
