---
title: View or edit device policies in Microsoft Defender for Business
description: See how to set up and configure Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp 
audience: Admin
ms.topic: overview
ms.date: 09/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH 
ms.collection: 
- SMB
- M365-security-compliance
---

# View or edit device policies in Microsoft Defender for Business

Microsoft Defender for Business was designed to simplify setup, configuration, and management. Your Microsoft Defender for Business plan comes with default policies that are based on Microsoft’s recommendations for security and productivity. You can view and edit your default policies, and you can define new policies. You can also change the order of priority for policies that you create. 

The following sections provide more information about your security policies in Microsoft Defender for Business:

- [View your policies](#view-your-policies)
- [Define a new policy](#define-a-new-policy)
- [Edit an existing policy](#edit-an-existing-policy)
- [Learn more about policy order](#what-about-policy-order)

## View your policies

1. Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in. You’re now in the Microsoft 365 Defender portal.

2. In the navigation pane, choose **Device configuration**. Policies are organized by operating system and policy type. 

3. Select an operating system tab (for example, **Windows clients**). 

4. Expand a category to view the list of policies for that operating system and policy type. 

5. Select a policy to view more details about the policy.

## Define a new policy

1. Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in. You’re now in the Microsoft 365 Defender portal.

2. In the navigation pane, choose **Device configuration**. Policies are organized by operating system and policy type. 

3. Select an operating system tab, and then expand a category. 

4. Select **+ Add**.

5. On the **General information** tab, specify a name and description. This information will help you and your team identify the policy later on.

6. Review the policy order and edit if necessary. For more information, see [Policy order](#edit-an-existing-policy).

7. On the **Device groups** tab, either create a new device group, or use an existing group. Policies are assigned to devices through device groups. Here are some things to keep in mind:

   - Initially, you might only have your default device group, which includes the devices people in your company are using to access company data and email.
   - Create a new device group to apply a policy with specific settings that are different from the default policy. 
   - When you set up your device group, you specify certain criteria, such as the operating system version. Devices that meet the criteria are included in that device group, unless you exclude them. 
   - All device groups—including the default and custom device groups that you define—are stored in Azure Active Directory (Azure AD).

8. On the **Configuration settings** tab, specify the settings for your policy, and then choose Next. For more information about the individual settings, see [Configuration settings for Microsoft Defender for Business](mdb-configuration-settings.md).

9. On the **Review your policy** tab, review the general information, targeted devices, and configuration settings. 

   - Make any needed changes by selecting **Edit**.
   - When you’re ready to proceed, choose **Create policy**.

## Edit an existing policy

1. Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in. You’re now in the Microsoft 365 Defender portal.

2. In the navigation pane, choose **Device configuration**. Policies are organized by operating system and policy type. 

3. Select an operating system tab, and then expand a category. 

4. Select a policy, and then choose **Edit**.

5. On the **General information** tab, review the information. If need be, edit the policy name and description. Then choose **Next**.

6. On the **Device groups** tab, determine which device groups should receive this policy. Take one or more of the following steps: 

   - Keep the selected device group as is
   - Remove a device group from the policy
   - Create a new device group
   - Select another existing device group

7. On the **Configuration settings** tab, review and if need be, edit the settings for your policy, and then choose **Next**.

   For more information about the individual settings, see [Configuration settings for next-generation protection](#understand-configuration-settings-for-next-generation-protection).

8. On the **Review your policy** tab, review the general information, targeted devices, and configuration settings. 

   - Make any needed changes by selecting **Edit**.
   - When you’re ready to proceed, choose **Update policy**.

## What about policy order?

Microsoft Defender for Business includes predefined policies to help ensure the devices your employees use are protected. You can add new policies as well. For example, suppose that you want to apply certain settings to some devices, and different settings to other devices. You can do that by adding policies.

As you define policies, you’ll notice that an order of priority is assigned. You can edit the order of priority for the policies that you define, but you cannot change the order of priority for default policies. For example, suppose that for your Windows client devices, you have three next-generation protection policies. In this case, your default policy is number 3 in priority. You can change the order of your policies that are numbered 1 and 2, but the default policy will remain number 3 in your list. 

**The important thing to remember about multiple policies is that devices will receive the first applied policy only.** Referring to our earlier example of three next-generation policies, suppose that you have devices that are targeted by all three policies. In this case, those devices will receive policy number 1, but will not receive policies numbered 2 and 3. 

## Next steps

- [Get started using Defender for Business](mdb-get-started.md)

- [Manage devices](mdb-manage-devices.md)