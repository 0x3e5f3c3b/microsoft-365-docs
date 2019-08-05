---
title: "Microsoft 365 Enterprise workloads and scenarios"
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
description: Onboard your organization's users to the productivity workloads of Microsoft 365 Enterprise.
---

# Microsoft 365 Enterprise workloads and scenarios

To get the creativity and teamwork benefits of Microsoft 365 Enterprise, deploy these workloads over your foundation infrastructure:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

See the [migration](migration-microsoft-365-enterprise-workload.md) workload for a general roadmap to migrate your entire organization to Microsoft 365 Enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.

Scenarios use features and services from across Microsoft 365 Enterprise in an integrated way to address a business need. One such need is to protect highly regulated data stored in Microsoft 365. Highly regulated data includes digital assets that are:

- Subject to regional regulations.
- The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.

To protect this data from internal and external threats, see the instructions in [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md). This scenario steps you through configuring a SharePoint Online site or a Microsoft Teams team to securely store your most valuable data.

Here are the workloads and scenarios in the overall Microsoft 365 Enterprise deployment guide:

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

See the [Microsoft 365 Productivity Library](https://www.microsoft.com/microsoft-365/success/) for additional scenarios. From this web page, type a search string or click **Filter by** and specify industry, roles (departments), and products within Microsoft 365.

From the results, click a card to see the steps that can get you started.

## Foundation infrastructure prerequisites

*Ideally*, you should deploy workloads and scenarios after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md). This ensures that all of the underlying layers are in place to provide integration, security, and the best experience for your users and their devices.

| Phase | Result |
|:-------|:-----|
| Network | Your network is updated for optimum performance to Microsoft 365 cloud services. |
| Identity | Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts. |
| Windows 10 Enterprise | Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise. |
| Office 365 ProPlus | Your existing users of Microsoft Office can upgrade to Office 365 ProPlus. |
| Mobile device management | Your devices can be enrolled and managed. |
| Information protection | Office 365 security features are enabled and your sensitivity or Azure Information Protection labels are ready to protect documents. |

Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations. Putting all of these layers in place in all locations is not necessary for you to more quickly get business value from Microsoft 365 Enterprise. 

Here are some common workloads to deploy right away: 

- After the **Identity** layer of the foundation infrastructure is rolled out to users, many organizations deploy:
  - [Office 365 ProPlus](office365proplus-infrastructure.md) combined with [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Office 365 ProPlus provides the security of modern authentication and the user experience of the latest Microsoft Office client. The migration of user's personal files to OneDrive for Business reduces infrastructure and the need to support home folders and drives.
  - [Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.
- If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint Online](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** layer.

You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to best meet your business needs.

### Best practice

We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.

The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access. Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.

Although foundational and very important to overall performance, the rollout of the **Networking** phase on your network can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 application and service performance will improve over time.

This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.
