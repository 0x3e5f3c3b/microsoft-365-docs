---
title: Set up users and cases in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: Mark Johnson - MSFT
manager: laurawi
ms.date: 
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: "Learn how to configure user roles, create cases, and assign users to cases in Advanced eDiscovery."
ms.custom: seo-marvel-apr2020
---

# Set up users and cases in Advanced eDiscovery (classic)

This topic describes how to set up users and cases for Advanced eDiscovery (classic).
  
> [!IMPORTANT]
> As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*. If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible. Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets. To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
## Requirements to set up users and cases

Before setting up cases and users in Advanced eDiscovery, the following is required:
  
- To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license. 
    
- You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:
    
  - [Permissions in the Microsoft 365 Security &amp; Compliance Center](~/security/office-365-security/protect-against-threats.md)
    
  - [Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md)
    
## Step 1: Assign users eDiscovery permissions

The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.
  
To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## Step 2: Create an eDiscovery case and add members

The next step is to create a new eDiscovery case in the Security & Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.
  
1. To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).

2. To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

## Step 3: Go a case in Advanced eDiscovery

After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).
  
## See also

[Advanced eDiscovery (classic)](office-365-advanced-ediscovery.md)
  
[Preparing data for Advanced eDiscovery (classic)](prepare-data-for-advanced-ediscovery.md)
 
