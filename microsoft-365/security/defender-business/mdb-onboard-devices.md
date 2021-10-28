---
title: Onboard devices to Microsoft Defender for Business
description: Understand your configuration settings in Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp 
audience: Admin
ms.topic: overview
ms.date: 10/27/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH 
ms.collection: 
- SMB
- M365-security-compliance
---

# Onboard devices to Microsoft Defender for Business

> [!IMPORTANT]
> Some information in this article relates to prereleased products/services that might be substantially modified before they are commercially released. Microsoft makes no warranties, express or implied, for the information provided here. This article includes links to online content that might describe some features that are not included in Microsoft Defender for Business (preview).

Microsoft Defender for Business is designed with the busy small and medium-sized business in mind. For example, if you are already using Microsoft Endpoint Manager, you can choose from automatic or manual onboarding. Or, if you're not already using Endpoint Manager, you can choose from several different onboarding packages and methods to use.

## What to do

- [Step 1: Choose your security and device management path](#step-1-choose-your-security-and-device-management-path).
- [Step 2: Choose an onboarding process](#step-2-choose-an-onboarding-process).
- [Step 3: Choose a deployment method](#step-3-choose-a-deployment-method). 
- [Step 4: Onboard devices in the Microsoft 365 Defender portal](#step-4-onboard-devices-in-the-microsoft-365-defender-portal). 

## Step 1: Choose your security and device management path

Depending on whether you are already using a security and device management tool, such as Microsoft Endpoint Manager, you can choose the path that best meets your company's needs.
<br/><br/>

|Scenario  |Options  |
|---------|---------|
| You are already using Microsoft Endpoint Manager (or Microsoft Intune) to manage devices and security settings | In this case, you can either continue using Endpoint Manager, or you can switch to the simplified configuration process in Microsoft Defender for Business. If you choose the simplified configuration process, your onboarding process can be streamlined. For example, you can choose between automatic, gradual, or manual onboarding processes with Defender for Business.   |
| You are not currently using Microsoft Endpoint Manager or a non-Microsoft device management tool to manage devices and security settings | We recommend using the [The simplified configuration process in Microsoft Defender for Business](mdb-simplified-configuration.md), with default security policies and settings that are applied to devices from day one. To onboard devices, follow the guidance in the next section, [Onboard devices in the Microsoft 365 Defender portal](#onboard-devices-in-the-microsoft-365-defender-portal).  |
| you are already using another productivity and device management tool    | you can continue using that tool. Or, you can switch to using the simplified configuration process in Defender for Business.        |

## Step 2: Choose an onboarding process

If you are not already using Microsoft Endpoint Manager (or Microsoft Intune), skip to [Step 3: Choose a deployment method](#step-3-choose-a-deployment-method).

If you are already using Microsoft Endpoint Manager (or Microsoft Intune), you can choose from several onboarding processes in Defender for Business. The following table summarizes these processes.

<br/><br/>

| Method | Description |
|:---|:---|
| Automatic onboarding process <br/>(*Recommended*) | If you are already using Microsoft Endpoint Manager (or Microsoft Intune), you can choose the automatic onboarding process in Defender for Business. This process sets up a connection between Defender for Business and Microsoft Endpoint Manager, and then onboards devices to Defender for Business. <br/><br/>We recommend this option because it enables you to onboard devices in Endpoint Manager to Defender for Business efficiently. |
| Gradual device onboarding | If you are already using Microsoft Endpoint Manager (or Microsoft Intune), you can choose gradual device onboarding. This process applies security settings and policies to devices that you select. This option enables you to start with a few devices and then add more later. [Learn more about gradual device onboarding with Microsoft Defender for Business](mdb-gradual-device-onboarding.md).  |
| Manual onboarding with Microsoft Endpoint Manager | If you are already using Microsoft Endpoint Manager (or Microsoft Intune), you can choose the manual onboarding process. This process enables you to choose from the deployment methods that are listed in the following section.  |

## Step 3: Choose a deployment method

You can choose from several deployment methods in Defender for Business, as described in the following table:
<br/><br/>

| Method | Description |
|:---|:---|
| **Microsoft Endpoint Manager** <br/>(*recommended*)  | Microsoft Endpoint Manager is an integrated solution for managing and monitoring devices.  Microsoft Endpoint Manager includes services and tools to manage and monitor mobile devices, desktop computers, virtual machines, embedded devices, and servers. Microsoft Endpoint Manager includes Microsoft Intune, Configuration Manager, Desktop Analytics, co-management, and Windows Autopilot. [Learn more about Microsoft Endpoint Manager](/mem/endpoint-manager-overview). <br/><br/>You can use Microsoft Endpoint Manager to onboard your company's devices, and then use the Microsoft 365 Defender portal to manage your security settings and devices. That way, you can onboard devices efficiently, and then take advantage of the [streamlined configuration process in Microsoft Defender for Business](mdb-simplified-configuration.md). <br/><br/>To learn more about onboarding with Microsoft Endpoint Manager, see [Onboard Windows devices using Mobile Device Management tools](../defender-endpoint/configure-endpoints-mdm.md). |
| **Local script**<br/>(*recommended for a few devices, such as for a pilot program*)  | Microsoft Defender for Business hosts a downloadable script that you can use on Windows devices. With this script, you can onboard up to ten (10) devices that are running Windows 10 or 11. <br/><br/> To use the local script method, you download the script from the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)), extract it on a device, and then run the script using Command Prompt. <br/><br/>To learn more about this method, see [Onboard Windows devices using a local script](../defender-endpoint/configure-endpoints-script.md). |
| **Group Policy** | Group Policy is an infrastructure that allows you to specify managed configurations for users and computers through Group Policy settings and Group Policy Preferences. A Group Policy object (GPO) is a logical object composed a Group Policy container and a Group Policy template. You can create GPOs and apply them to your company's devices. To learn more about group policy, see [Group Policy overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)). <br/><br/>To learn more about this method, see [Onboard Windows devices using Group Policy](../defender-endpoint/configure-endpoints-gp.md). | 
| **VDI onboarding script** | If your company is using non-persistent virtual desktop infrastructure (VDI) devices, you can onboard those endpoints using a downloadable script. <br/><br/>To learn more about this method, see [Onboard non-persistent VDI devices](../defender-endpoint/configure-endpoints-vdi.md).  |
| **System Center Configuration Manager** | System Center Configuration Manager (now part of Microsoft Endpoint Manager) can help you onboard and monitor Windows 10 or later clients through policies. You can deploy a Microsoft Defender policy to a target collection or multiple collections. <br/><br/>To learn more about this method, see [Onboard Windows devices using Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md).  |
| **Mobile Device Management** | You can use Mobile Device Management (MDM) with Microsoft Intune (now part of Microsoft Endpoint Manager) to onboard devices. Devices must be enrolled in MDM in order to onboard those devices with Microsoft Intune. <br/><br/>To learn more about this method, see [Onboard Windows devices using Mobile Device Management tools](../defender-endpoint/configure-endpoints-mdm.md). |

> [!TIP]
> If you're new to all of the onboarding methods described in this section, consider using either **Microsoft Endpoint Manager** or the **local script** method.

## Step 4: Onboard devices in the Microsoft 365 Defender portal

If you are working through the initial setup and configuration process for Microsoft Defender for Business, you'll be prompted to onboard devices after you have [set up email notifications for your security team](mdb-email-notifications.md).

The following video outlines the onboarding process for Microsoft Defender for Endpoint. This process is similar to what you'll do in Microsoft Defender for Business.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Follow these steps to onboard devices:

1. Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)), and then sign in.

2. In the navigation pane,  on the **Onboard devices** step of the setup and configuration process, choose an onboarding method.

2. Depending on whether you are already using Microsoft Endpoint Manager, take one of the following steps:

   - If you are using Microsoft Endpoint Manager, choose between automatic onboarding (recommended), or manual onboarding, and follow the prompts. 

   - If you are not already using Microsoft Endpoint Manager, review the list of [onboarding options](#onboarding-options). Select an option, download the package for that option, and follow the prompts.

After you have onboarded your devices, proceed to [Configure your security settings and policies in Microsoft Defender for Business](mdb-configure-security-settings.md).

## What if I want to offboard a device?

1. Go to the 

See [Offboard a device](mdb-manage-devices.md#offboard-a-device).

## Next steps

Proceed to:

- [Configure your security settings and policies in Microsoft Defender for Business](mdb-configure-security-settings.md)