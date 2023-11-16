---
title: Manual deployment for Microsoft Defender for Endpoint on macOS
description: Install Microsoft Defender for Endpoint on macOS manually, from the command line.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, monterey, ventura, mde for mac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
- m365-security
- tier3
- mde-macos
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.date: 12/18/2020
---

# Manual deployment for Microsoft Defender for Endpoint on macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender XDR](https://go.microsoft.com/fwlink/?linkid=2118804)

> Want to experience Defender for Endpoint? [Sign up for a free trial](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink).

This article describes how to deploy Microsoft Defender for Endpoint on macOS manually. A successful deployment requires the completion of all of the following steps:

- [Download installation and onboarding packages](#download-installation-and-onboarding-packages)
- [Application installation (macOS 11 and newer versions)](#application-installation-macos-11-and-newer-versions)
- [Onboarding Package](#onboarding-package)

## Prerequisites and system requirements

Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.

## Download installation and onboarding packages

Download the installation and onboarding packages from Microsoft Defender portal.

[!INCLUDE [Defender for Endpoint repackaging warning](../../includes/repackaging-warning.md)]

1. In <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft Defender portal</a>, go to **Settings > Endpoints > Device management > Onboarding**.
2. In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.
3. In Section 2 of the page, select **Download installation package**. Save it as wdav.pkg to a local directory.
4. In Section 2 of the page, select **Download onboarding package**. Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.
   :::image type="content" source="images/onboarding-package-step4.png" alt-text="The options to download the installation and onboarding packages.":::

5. From a command prompt, verify that you have the two files.
    Terminal
    - Type *cd Downloads* and press **Enter**.
    - Type *ls* and press **Enter**.
     :::image type="content" source="images/Terminal-image-step5.png" alt-text="Screenshot that displays the two download files.":::
6. Copy the *wdav.pkg* and *MicrosoftDefenderATPOnboardingMacOs.sh* to the device where you want to deploy the Microsoft Defender for Endpoint on macOS.

## Application installation (macOS 11 and newer versions)

To complete this process, you must have admin privileges on the device.

1. - Navigate to the downloaded *wdav.pkg* in **Finder** and open it.
    
     Or
    - You can download the *wdav.pkg*- from **Terminal** *sudo installer -store -pkg /Users/admin/Downloads/wdav.pkg -target /*

   :::image type="content" source="images/monterey-install-1.png" alt-text="The installation process for the application" lightbox="images/monterey-install-1.png":::

2. Select **Continue**.

3. Read through the **Software License Agreement** and select **Continue** to agree with the terms.
    :::image type="content" source="images/software-license-agreement.png" alt-text="Screenshot that shows the Software License Agreement.":::

4. Read through the *End-User License Agreement (EULA)* and select **Agree**.
    :::image type="content" source="images/agree-license.png" alt-text="Screenshot that shows the acceptance of the agreement.":::

5. From **Destination Select**, select the disk where you want to install the Microsoft Defender Software, for example, *Macintosh HD* and select **Continue**.
    :::image type="content" source="images/destination-select.png" alt-text="Screenshot that shows the selection of destination for installation.":::

> [!Note]
> The amount of disk space required for installation is around 777 MB.

6. To change the installation destination, select **Change Install Location...**.
    :::image type="content" source="images/installation-type.png" alt-text="Screenshot that shows the final installation step.":::

7. Click **Install**.

8. Enter the password, when prompted.
    :::image type="content" source="images/password-2g.png" alt-text="Screenshot that shows the password dialog box.":::

9. Click **Install Software**.

3. At the end of the installation process, for macOS Big Sur (11.0) or latest version, you're prompted to approve the system extensions used by the product. Select **Open Security Preferences**.

   :::image type="content" source="images/monterey-install-2.png" alt-text="The system extension approval" lightbox="images/monterey-install-2.png":::

11. To enable system extention, select **Details**.
    :::image type="content" source="images/system-extention-image.png" alt-text="Screenshot that shows the system extention.":::

4. From the **Security & Privacy** window, select the checkboxes next to **Microsoft Defender** and select **OK**.
    :::image type="content" source="images/security-privacy-window-updated.png" alt-text="Screenshot that shows the security and privacy window.":::

5. Repeat steps 11 and 12 for all system extensions distributed with Microsoft Defender for Endpoint on Mac.

6. As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on Mac inspects socket traffic and reports this information to the Microsoft Defender portal. When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.

   :::image type="content" source="images/monterey-install-4.png" alt-text="The system extension security preferences2" lightbox="images/monterey-install-4.png":::

    To troubleshoot System Extention issues, refer [Troubleshoot System Extention](mac-support-sys-ext.md).

## How to Allow Full Disk Access

The macOS Catalina (10.15) requires full disk access to be granted to **Microsoft Defender for Endpoint** in order to be able to protect and monitor.

> [!Note]
> Full disk access grant to **Microsoft Defender for Endpoint** is a new requirement for all the third-party software by Apple for files and folders containing personal data.

To grant full disk access:

1. Open **System Preferences** \> **Security & Privacy** \> **Privacy** \> **Full Disk Access**. Click the lock icon to make changes (bottom of the dialog box).
1. Grant **Full Disk Access** permission to **Microsoft Defender** and **Microsoft Defenders Endpoint Security Extension**.

   :::image type="content" source="images/full-disk-access-security-privacy.png" alt-text="The screenshot shows the full disk access's security and privacy.":::
1. Select **General** \> **Restart** for the new system extentions to take effect.

   :::image type="content" source="images/restart-fulldisk.png" alt-text="Screenshot that allows you to restart the system for new system extentions to be enabled.":::
1. Enable *Potentially Unwanted Application* (PUA) in block mode.

   To enable PUA, refer [configure PUA protection](mac-pua.md).
1. Enable *Network Protection*.

   To enbale *Network protection*, refer [manual deployment](network-protection-macos.md).
1. Enable *Device Control*.

   To enable *Device Control*, refer [device control for macOS](mac-device-control-overview.md).
1. Enable *Tamper Protection* in block mode.

   To enable *Tamper Protection*, refer [Protect MacOS security settings with tamper protection](tamperprotection-macos.md).
1. If you have the *Microsoft Purview – Endpoint data loss prevention license*,  you can review [Get started with Microsoft Purview - Endpoint data loss prevention](/purview/endpoint-dlp-getting-started).

## Onboarding Package

Once you have installed the MDE on macOS client, you must now onboard the package, which registers to your Microsoft Defender for Endpoint tenant and licenses it.

1. Verify if MDE on macOS has already been onboarded.

   Copy *wdav.pkg* and *MicrosoftDefenderATPOnboardingMacOs.sh* to the device where you have deployed Microsoft Defender for Endpoint on macOS.

    The client device isn't associated with *org_id*. The *org_id* attribute is blank.

    ```bash
    mdatp health --field org_id
    ```

2. Run the Bash script to install the onboarding package:

    ```bash
    Sudo bash -x MicrosoftDefenderATPOnboardingMacOs.sh
    ```

3. Verify that the device is now associated with your organization and reports a valid org ID:

    ```bash
    mdatp health --field org_id
    ```

    After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="The Microsoft Defender icon in status bar" lightbox="images/mdatp-icon-bar.png":::

   You can [troubleshoot license issues for Microsoft Defender for Endpoint on macOS](mac-support-license.md).

4. Run the connectivity test.

   ```bash
   mdatp connectivity test
   ```

   You can [troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS](troubleshoot-cloud-connect-mdemac.md).

## AV detection test for verifying device's onboarding and reporting services

   Run an AV detection test to verify that the device is properly onboarded and reporting to the service. Perform the following steps on the newly onboarded device:

1. Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):

```bash
mdatp health --field real_time_protection_enabled
```

2. Open a Terminal window. Copy and execute the following command:

```bash
curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
```

3. The file has been quarantined by Defender for Endpoint on Mac. Use the following command to list all the detected threats:

```bash
mdatp threat list
```

## EDR detection test for verifying device's onboarding and reporting services

Run an EDR detection test to verify that the device is properly onboarded and reporting to the service. Perform the following steps on the newly onboarded device:

1. In your browser, Microsoft Edge for Mac or Safari, download *MDATP MacOS DIY.zip* from [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy)and extract.

      The following prompt appears:

      > Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?<br/>
      > You can change which websites can download files in **Websites Preferences**.

4. Click **Allow**.

5. Open **Downloads**.

6. You must be able to see **MDATP MacOS DIY**.

   > [!TIP]
   > If you double-click **MDATP MacOS DIY**, you will get the following message:
   >
   > > **"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**<br/>
   > > macOS cannot verify that this app is free from malware.<br/>
   > > **\[Move to Trash\]** **\[Cancel\]**

7. Click **Cancel**.

8. Right-click **MDATP MacOS DIY**, and then click **Open**.

    The system displays the following message:

    > **macOS cannot verify the developer of MDATP MacOS DIY. Are you sure you want to open it?**<br/>
    > By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.

9. Click **Open**.

    The system will display the following message:

    > Microsoft Defender for Endpoint - macOS EDR DIY test file<br/>
    > Corresponding alert will be available in the MDATP portal.

10. Click **Open**.

    In few minutes, an alert *macOS EDR Test Alert* is raised.

11. Go to Microsoft Defender portal (https://security.microsoft.com/).

12. Go to the **Alert** Queue.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="An macOS EDR test alert that shows severity, category, detection source, and a collapsed menu of actions" lightbox="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png":::

    The macOS EDR test alert that shows severity, category, detection source, and a collapsed menu of actions.

    Look at the alert details and the device timeline, and perform the regular investigation steps.

 Next steps that you can consider performing are to add AV exclusions as needed for application compatibility or performance:

- [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md)
- [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
- [Manage suppression rules](manage-suppression-rules.md)
- [Create indicators of compromise (IoC)](manage-indicators.md)
- [Create and manage custom detections rules](../defender/custom-detection-rules.md)

Read through [Microsoft Defender for Endpoint Security Operations Guide](mde-sec-ops-guide.md).

## Logging installation issues

For more information on how to find the automatically generated log that's created by the installer, see [Logging installation issues](mac-resources.md#logging-installation-issues).

## Uninstallation

See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.

  > [!Tip]
  > - Do you want to learn more? Engage with the Microsoft Security community in our Tech Community: [Microsoft Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bd-p/MicrosoftDefenderATP).  
  > - If you have any feedback that you will like to share, submit it by opening Microsoft Defender Endpoint on Mac on your device and navigate to **Help** \> **Send feedback**.

## Recommended content

- [Learn how to install, configure, update, and use Microsoft Defender for Endpoint on Mac](microsoft-defender-endpoint-mac.md).
- [Learn how to set up the Microsoft Defender for Endpoint on macOS policies in Jamf](mac-jamfpro-policies.md).
- [Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro](mac-install-with-jamf.md).
- [Learn how to troubleshoot license issues in Microsoft Defender for Endpoint on Mac](mac-support-license.md).
- [Learn how to use resources for Microsoft Defender for Endpoint on Mac, including how to uninstall it, how to collect diagnostic logs, CLI commands, and known issues with the product](mac-resources.md).
- [Learn how to configure Microsoft Defender for Endpoint on Mac in enterprise organizations](mac-preferences.md).
- [Learn how to install Microsoft Defender for Endpoint on Mac on other management solutions](mac-install-with-other-mdm.md).
- [Learn how to detect and block Potentially Unwanted Applications (PUA) using Microsoft Defender for Endpoint on macOS](mac-pua.md).