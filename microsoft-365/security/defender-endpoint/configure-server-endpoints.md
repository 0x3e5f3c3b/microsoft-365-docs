---
title: Onboard Windows servers to the Microsoft Defender for Endpoint service
description: Onboard Windows servers so that they can send sensor data to the Microsoft Defender for Endpoint sensor.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
---

# Onboard Windows servers to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to:**

- Windows Server 2012 R2
- Windows Server 2016
- Windows Server Semi-Annual Channel
- Windows Server 2019 and later
- Windows Server 2019 core edition

[!include[Prerelease information](../../includes/prerelease.md)]

> Want to experience Defender for Endpoint? [Sign up for a free trial.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)

Defender for Endpoint extends support to also include the Windows Server operating system. This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft 365 Defender console. Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.

This topic describes how to onboard specific Windows Servers to Microsoft Defender for Endpoint. 


For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).

For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).

## Windows Server onboarding overview

You'll need to complete the following general steps to successfully onboard servers.


![Illustration of onboarding flow for Windows Servers and Windows 10 devices](images/server-onboarding-tools-methods.png)

**Windows Server 2012 R2 and Windows Server 2016**
- Download installation and onboarding packages
- Install application
- Follow the onboarding steps for the corresponding tool

**Windows Server Semi-Annual Channel**

- Download the onboarding package
- Follow the onboarding steps for the corresponding tool

### New functionality in the modern unified solution for Windows Server 2012 R2 and 2016
Previous implementation of onboarding Windows Server 2012 R2 and Windows Server 2016 required the use of Microsoft Monitoring Agent (MMA). 

The new unified solution package makes it easier to onboard servers by removing dependencies and installation steps. In addition, this unified solution package comes with the following major improvements:

- [Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows) with [Next-generation protection](/microsoft-365/security/defender-endpoint/next-generation-protection) for Windows Server 2012 R2
- [Attack Surface Reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)
- [Network Protection](/microsoft-365/security/defender-endpoint/network-protection)
- [Controlled Folder Access](/microsoft-365/security/defender-endpoint/controlled-folders)
- [Potentially Unwanted Application (PUA) blocking](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Improved detection capabilities](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
- [Expanded response capabilities](/microsoft-365/security/defender-endpoint/respond-machine-alerts) on devices and [files](/microsoft-365/security/defender-endpoint/respond-file-alerts)
- [EDR in Block Mode](/microsoft-365/security/defender-endpoint/edr-in-block-mode)
- [Live Response](/microsoft-365/security/defender-endpoint/live-response)
- [Automated Investigation and Response (AIR)](/microsoft-365/security/defender-endpoint/automated-investigations)
- [Tamper Protection](/microsoft-365/security/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection)

If you have previously onboarded your servers using MMA, follow the guidance provided in [Server migration](server-migration.md) to migrate to the new solution.

>[!NOTE]
>While this method of onboarding Windows Server 2012 R2 and Windows Server 2016 is in preview, you can choose to continue to use the previous onboarding method using Microsoft Monitoring Agent (MMA). For more information see, [Install and configure endpoints using MMA](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma).

#### Known issues and limitations
The following specifics apply to the new unified solution package:
- On Windows Server 2012 R2, there is no user interface for Microsoft Defender Antivirus. In addition, the user interface on Windows Server 2016 only allows for basic operations. To perform operations on a device locally, please refer to [Manage Microsoft Defender for Endpoint with PowerShell, WMI, and MPCmdRun.exe](/microsoft-365/security/defender-endpoint/manage-atp-post-migration-other-tools). As a result, features that specifically rely on user interaction, such as where the user is prompted to make a decision or perform a specific task, may not work as expected. It is generally recommended to not enable the user interface nor require user interaction on any managed server.
- [Connectivity requirements](configure-proxy-internet.md) match those for Windows Server 2019. Previously, the use of the Microsoft Monitoring Agent (MMA) on Windows Server 2016 and below allowed for the OMS gateway to provide connectivity to Defender cloud services. The new solution, like Microsoft Defender for Endpoint on Windows Server 2019 and Windows 10, does not support this gateway.
- Not all Attack Surface Reduction rules are available on all operating systems. Please review [Attack Surface Reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules).
- To enable [Network Protection](/microsoft-365/security/defender-endpoint/network-protection), additional configuration is required: 
    -- Set-MpPreference -EnableNetworkProtection Enabled
    -- Set-MpPreference -AllowNetworkProtectionOnWinServer 1
    -- Set-MpPreference -AllowNetworkProtectionDownLevel 1
    -- Set-MpPreference -AllowDatagramProcessingOnWinServer 1
  In addition, on machines with a high volume of network traffic, performance testing in your environment is highly recommended.

## Integration with Azure Defender
Microsoft Defender for Endpoint integrates seamlessly with Azure Defender. You can onboard servers automatically, have servers monitored by Azure Defender appear in Defender for Endpoint, and conduct detailed investigations as an Azure Defender customer. 

For more information, see [Integration with Azure Defender](azure-server-integration.md).

>[!NOTE]
For Windows Server 2012 R2 and 2016 running the modern unified solution preview, integration with Azure Security Center / Azure Defender for Servers for alerting and automated deployment is not yet available. Whilst you can install the new solution on these machines, no alerts will be displayed in Azure Security Center.

## Windows Server 2012 R2 and Windows Server 2016

>[!NOTE]
>While this method of onboarding Windows Server 2012 R2 and Windows Server 2016 is in preview, you can choose to continue to use the previous onboarding method using Microsoft Monitoring Agent (MMA). For more information see, [Install and configure endpoints using MMA](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma).


### Prerequisites

**Prerequisites for Windows Server 2012 R2** 
If you have fully updated your machines with the latest [monthly rollup](/troubleshoot/windows-client/deployment/standard-terminology-software-updates.md#monthly-rollup) package, there are **no** additional prerequisites.

The installer package will check if the following components have already been installed via an update:

- [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)
- [Update for Universal C Runtime in Windows](https://support.microsoft.com/topic/update-for-universal-c-runtime-in-windows-c0514201-7fe6-95a3-b0a5-287930f3560c)

**Prerequisites for Windows Server 2016** 

Verify that Microsoft Defender Antivirus is installed, is active and up to date. The minimum version is **4.18.2106.6**. You can download and install the latest platform version using Windows Update. Alternatively, download the update package manually from the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623).

### Download installation and onboarding packages 

1. In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.

2. Select **Windows Server 2012 R2 and 2016**.

3. Select **Download installation package** and save the .msi file. You can run the msi package through the installation wizard, or follow the command-line steps in [Install Microsoft Defender for Endpoint using the command line](#install-microsoft-defender-for-endpoint-using-command-line).
          
   > [!NOTE]
   > Microsoft Defender Antivirus will get installed and will be active unless you set it to passive mode. For more information, see [Need to set Microsoft Defender Antivirus to passive mode?](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server).
 
4. Select **Download onboarding package** and save the .zip file.

5. Install the installation package using any of the options to install Microsoft Defender Antivirus. (See [Microsoft Defender Antivirus on Windows Server](microsoft-defender-antivirus-on-windows-server.md).)

6. Follow the steps provided in the [onboarding steps](#onboarding-steps) section.

## Options to install Microsoft Defender for Endpoint
In the previous section, you downloaded an installation package. The installation package contains the installer for all Microsoft Defender for Endpoint components.

### Install Microsoft Defender For Endpoint using command line
Use the installation package from the previous step to install Microsoft Defender for Endpoint. 

Run the following command to install Microsoft Defender for Endpoint:

```
Msiexec /i md4ws.msi /quiet
```

To uninstall, ensure the machine is offboarded first using the appropriate offboarding script. Then, use Control Panel \> Programs \> Programs and Features to perform the uninstall.

Alternatively, run the following uninstall command to uninstall Microsoft Defender for Endpoint:

```
Msiexec /x md4ws.msi /quiet
```
You must use the same package you used for installation for the above command to succeed.

The `/quiet` switch suppresses all notifications.

> [!NOTE]
> Microsoft Defender Antivirus doesn't automatically go into passive mode. You can choose to set Microsoft Defender Antivirus to run in passive mode if you are running a non-Microsoft antivirus/antimalware solution. For command line installations, the optional `FORCEPASSIVEMODE=1` immediately sets the Microsoft Defender Antivirus component to Passive mode.
>
> For more information, see [Need to set Microsoft Defender Antivirus to passive mode?](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server).

### Install Microsoft Defender For Endpoint using a script

You can also use the [installer script](server-migration.md#installer-script) to help automate installation, uninstallation, and onboarding.

## Windows Server Semi-Annual Channel and Windows Server 2019

The onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script. For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).


### Download package

1. In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.

2. Select **Windows Server 1803 and 2019**.

3. Select **Download package**. Save it as WindowsDefenderATPOnboardingPackage.zip.

4. Follow the steps provided in the [onboarding steps](#onboarding-steps) section. 


## Onboarding steps

1. Now that you have downloaded the required onboarding packages use the guidance listed in [onboarding tools and methods](configure-endpoints.md#endpoint-onboarding-tools) for your server.

2. (Only applicable if you're using a third-party anti-malware solution). You'll need to apply the following Microsoft Defender Antivirus passive mode settings. Verify that it was configured correctly:

    1. Set the following registry entry:
       - Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - Name: ForceDefenderPassiveMode
       - Type: REG_DWORD
       - Value: 1

    2. Run the following PowerShell command to verify that the passive mode was configured:

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    3. Confirm  that a recent event containing the passive mode event is found:

       ![Image of passive mode verification result](images/atp-verify-passive-mode.png)



## Verify the onboarding and installation

Verify that Microsoft Defender Antivirus and Microsoft Defender for Endpoint are running. 


## Run a detection test to verify onboarding
After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service. For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).


## Offboard Windows servers

You can offboard Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.

- [Offboarding using Group Policy](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboard devices using Configuration Manager](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [Offboard and monitor devices using Mobile Device Management tools](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script)

For other Windows server versions, you have two options to offboard Windows servers from the service:

- Uninstall the MMA agent
- Remove the Defender for Endpoint workspace configuration

>[!NOTE]
>*These offboarding instructions for other Windows server versions also apply if you are running the previous Microsoft Defender for Endpoint for Windows Server 2016 and Windows Server 2012 R2 that requires the MMA. Instructions to migrate to the new unfiied solution are at [Server migration scenarios in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/server-migration).

> [!NOTE]
> Running Microsoft Defender Antivirus is not required but it is recommended. If another antivirus vendor product is the primary endpoint protection solution, you can run Defender Antivirus in Passive mode. You can only confirm that passive mode is on after verifying that Microsoft Defender for Endpoint sensor (SENSE) is running. 

1. Run the following command to verify that Microsoft Defender Antivirus is installed:

    >[!NOTE]
    >This verifcation step is only required if you're using Microsoft Defender Antivirus as your active antimalware solution. 

   ```sc.exe query Windefend```

    If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender Antivirus. For more information, see [Microsoft Defender Antivirus on Windows Server](microsoft-defender-antivirus-on-windows-server.md).

    For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](use-group-policy-microsoft-defender-antivirus.md).

2. Run the following command to verify that Microsoft Defender for Endpoint is running:

    ```sc.exe query sense```
    
    The result should show it is running. If you encounter issues with onboarding, see [Troubleshoot onboarding](troubleshoot-onboarding.md).

## Run a detection test
Follow the steps in [Run a detection test on a newly onboarded device](run-detection-test.md) to verify that the server is reporting to Defender for the Endpoint service.


## Next steps
After successfully onboarding devices to the service, you'll need to configure the individual components of Microsoft Defender for Endpoint. Follow the [Adoption order](prepare-deployment.md#adoption-order) to be guided on enabling the various components.

## Related topics
- [Onboard previous versions of Windows](onboard-downlevel.md)
- [Onboard Windows 10 devices](configure-endpoints.md)
- [Onboard non-Windows devices](configure-endpoints-non-windows.md)
- [Configure proxy and Internet connectivity settings](configure-proxy-internet.md)
- [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md)
- [Troubleshooting Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md)
