---
title: Device health and compliance report in Microsoft Defender for Endpoint
description: Use the device health and compliance report to track device health, antivirus status and versions, OS platforms, and Windows 10 versions.
keywords: health state, antivirus, os platform, windows 10 version, version, health, compliance, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
---

# Device health and compliance report in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Want to experience Microsoft Defender for Endpoint? [Sign up for a free trial.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> Information about the features that are _commercially released_ follows the prerelease information in the section titled [Publicly-released: Device health and compliance report in Microsoft Defender for Endpoint](#publicly-released-device-health-and-compliance-report-in-microsoft-defender-for-endpoint).

## Public Preview - Device health and antivirus compliance report in Microsoft Defender for Endpoint

<!-- Hide {this intro with no subsequent list items}
[When the features documented in this "preview" section move out of public preview:  Remove everything from (and including) **_End of section Public Preview: Device health and antivirus compliance report in Microsoft Defender for Endpoint_**  down the very bottom of the page. Remove prerelease !IMPORTANT notice above. Check #-levels and adjust as necessary {I think just need to move everything up one level {- 1 #/ }, move the current ## Public Preview title {deleting "Public Preview -"} to replace the current # title.}. ]
-->

The devices status report provides high-level information about the devices in your organization. The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.
In the Microsoft 365 Security dashboard navigation panel, select **Reports**, and then open **Device health and compliance**.
The Device health and compliance dashboard is structured in two tabs:

- The [**Sensor health** tab](#sensor-health-tab) provides general operating system information, divided into three cards that display the following device attributes:

  - [Sensor health](#sensor-health)
  - [Operating systems and platforms](#os-systems-and-platforms)
  - [Windows 10 versions](#windows-10-versions)

- The [**Microsoft Defender Antivirus health** tab](#microsoft-defender-antivirus-health-tab) has eight cards organized in four columns that report on aspects of Microsoft Defender Antivirus:

| first column | second column | third column | fourth column |
|:---|:---|:---|:---|
| [Antivirus mode](#antivirus-mode) | [Antivirus engine version](#antivirus-engine-version) | [Antivirus security intelligence version](#antivirus-security-intelligence-version) | [Antivirus platform version](#antivirus-platform-version)
| [Recent antivirus scan results](#recent-antivirus-scan-results) | [Antivirus engine updates](#antivirus-engine-updates) | [Security intelligence updates](#security-intelligence-updates) | [Antivirus platform updates](#antivirus-platform-updates) |

### Sensor health tab

Each of the three cards on the **Sensor health** tab have two reporting sections, _Current state_ and _device trends_, presented as graphs:

#### Current state graph

In each card, the Current state (referred to in some documentation as _Device summary_) is the top, horizontal bar graph. Current state is a snapshot that shows information collected about devices in your organization, scoped to the current day. This graph represents the distribution of devices across your organization that report status or are detected to be in a specific state.

#### Device trends graph

The lower graph on each of the three cards is not named, but is commonly known as _device trends_. The device trends graph depicts the collection of devices across your organization, throughout the time span indicated directly above the graph.
By default, the device trends graph displays device information from the 30-day period, ending in the latest full day. To gain a better perspective about trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown. To adjust the time period, open the filter and select a start day and end day.

#### Filtering data

Use the provided filters to include or exclude devices with certain attributes. You can select multiple filters to apply from the device attributes. When applied, filters apply to all three cards in the report.

**Example**
To show data about Windows 10 devices with Active sensor health state:

1. Under **Filters** > **Sensor health state** > **Active**.
2. Then select **OS platforms** > **Windows 10**.
3. Select **Apply**.

#### Sensor health

Displays information about the sensor state on devices, providing an aggregated view of devices that are active, inactive, experiencing impaired communications, or where no sensor data is reported.
Devices that are either experiencing impaired communications, or those from which no sensor data is detected could expose your organization to risks, and warrant investigation. Likewise, devices that are inactive for extended periods of time could expose your organization to threats due to out-of-date software; these also warrant investigation.

#### OS systems and platforms

This card shows the distribution of operating systems and platforms that exist within your organization.
_OS systems and platforms_ can give useful insights into whether devices in your organization are running current or outdated operating systems. When new operating systems are introduced, security enhancements are frequently included that improve your organization's posture against security threats.

For example, Secure Boot, introduced in Windows 8, practically eliminated the threat from some of the most harmful types of malware. Improvements in Windows 10 provide PC manufacturers the option to prevent users from disabling the Secure Boot feature, preventing almost any chance of malicious rootkits or other low-level malware from infecting the boot process.
Ideally, the “Current state” graph shows that the number of operating systems is weighted in favor of more current OS over older versions, or the trends graph indicates that new systems are being adopted and/or older systems are being updated or replaced.

#### Windows 10 versions

The card shows the distribution of Windows devices and their versions in your organization.
In the same way that an upgrade from Windows 8 to Windows 10 improves security in your organization, changing from early releases of Windows to more current versions improves your posture against possible threats.

The Windows version trend graph can help you quickly determine whether your organization is keeping current by updating to the most recent, most secure versions of Windows 10.

### Microsoft Defender Antivirus health tab  

The Microsoft Defender Antivirus health tab contains eight cards that report on several aspects of Microsoft Defender Antivirus in your organization. Two cards, _mode_ and _scan results_, report about Microsoft Defender Antivirus functions. The remaining six cards report about the Microsoft Defender Antivirus versions and updates for devices in your organization, as follows:

|  |  |  |  |
|:---|:---|:---|:---|
| **Versions** | engine versions | security intelligence versions | platform versions |
| **Updates** | engine updates | security intelligence updates | platform updates |

> [!NOTE]
>
> Up-to-date reporting information will be available for Windows devices with engine version: 19000.1 and newer.

#### Card functionality

The functionality is essentially the same for all cards. By clicking on a numbered bar in any of the cards, a **Details** flyout opens enabling you to review information about all the devices configured with that version number. If the version number that you clicked on is:

- A current version, then **Remediation required** and **Security recommendation** are not present
- An outdated version, a notification at the top of the report is present, indicating **Remediation required**, and a **Security recommendation** link is present. Click the security recommendation link to navigate to the threat and vulnerability management console, which can recommend appropriate antivirus updates.

Within the flyout: clicking on the name of the device will redirect you to the "Device page" for that device, where you can access detailed reports.

#### Microsoft Defender Antivirus version card functionality

Following are descriptions for the six cards that report about the _version_ and _update_ information for Microsoft Defender Antivirus engine, security intelligence, and platform components:

##### Full report

In any of the three _version_ cards, click **Full report** to display the nine most recent Microsoft Defender Antivirus _version_ reports for each of the three device types: Windows, Mac, and Linux; if fewer than nine exist, they are all shown. An **Other** category captures recent antivirus engine versions ranking tenth and below, if detected.
A primary benefit of the three _version_ cards is that they provide quick indicators as to whether the most current versions of the antivirus engines, platforms, and security intelligence are being utilized. Coupled with the detailed information that is linked to the card, the versions cards become a powerful tool to check if versions are up to date and to gather information about individual computers, or groups of computers.
Ideally, when you run these reports, they will indicate that the most current antivirus versions are installed, as opposed to older versions.
Use these reports to determine whether your organization is taking full advantage of the most current versions.

To help ensure your antimalware solution detects the latest threats, get updates automatically as part of Windows Update.

For more details on the current versions and how to update the different Microsoft Defender Antivirus components, visit [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md).

#### Antivirus mode

Reports on how many devices in your organization – on the date indicated on the card – are in any of the following modes:

| value | mode |
|---|---|
| 0 | Active |
| 1 | Passive |
| 2 | Disabled ( uninstalled, disabled, or SideBySidePassive {also known as Low Periodic Scan}) |
| 3 | Others (Not running , Unknown and "") |
| 4 | EDRBlocked |
| 5 | PassiveAudit |

Following are descriptions for each mode:

- **Active** mode - In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device. Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.
- **Passive** mode - In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device. Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus. IMPORTANT: Microsoft Defender Antivirus can run in passive mode only on endpoints that are onboarded to Microsoft Defender for Endpoint. See [Requirements for Microsoft Defender Antivirus to run in passive mode](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode).
- **Disabled** mode  - synonymous with: uninstalled, disabled, sideBySidePassive, and Low Periodic Scan. When disabled, Microsoft Defender Antivirus is not used. Files are not scanned, and threats are not remediated. In general, Microsoft does not recommend disabling or uninstalling Microsoft Defender Antivirus.
- **Others** mode -
- **EDRBlocked** mode - In endpoint detection and response (EDR) blocked mode,
- **PasiveAudit** mode -

Devices that are in either passive, LPS, or Off present a potential security risk and should be investigated.

For details about LPS, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

#### Recent antivirus scan results

This card has two bar graphs showing all-up results for quick scans and full scans. In both graphs, the first bar indicates the completion rate for scans, and indicate **Completed**, **Canceled**, or **Failed**. The second bar in each section provides the error codes for failed scans.
By scanning the **Mode** and **Recent scan results** columns, you can quickly identify devices that are not in active antivirus scan mode, and devices that have failed or cancelled recent antivirus scans. You can return to the report with this information and gather additional details and security recommendations.

For more details on the current Microsoft Defender Antivirus versions and how to update the different Microsoft Defender Antivirus components, visit [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

#### Antivirus security intelligence version

Lists the most common _Microsoft Defender Antivirus security intelligence_ versions installed on devices on your network.
Microsoft continually updates Microsoft Defender security intelligence to address the latest threats, and to refine detection logic. These refinements to security intelligence enhance Microsoft Defender Antivirus’ (and other Microsoft antimalware solutions’) ability to accurately identify potential threats. This security intelligence works directly with cloud-based protection to deliver AI-enhanced, next-generation protection that is fast and powerful.

#### Security intelligence updates

This card dentifies devices that have security intellegence versions that are up to date versus out of date.
Definition of ‘**Up to date** – the security intelligence version on the device was written in the past 7 days.

<!-- Hide {this intro with no subsequent list items}
[Confirm that it is versus as apposed to "out of date" only.]
-->

<!-- Hide {this intro with no subsequent list items}
[link - https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus?view=o365-worldwide#security-intelligence-updates]
-->

#### Antivirus engine version

Shows the real-time results of the most current Microsoft Defender Antivirus engine versions installed across Windows Devices, Mac devices, and Linux devices in your organization. Microsoft Defender Antivirus engine is updated monthly.
For more details on the current versions and how to update the different Microsoft Defender Antivirus components, see [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md)

#### Antivirus engine updates

This card dentifies deices that have antivirus engine versions that are up to date versus out of date.
Definition of ‘_Up to date_ – the engine version on the device is the most recent engine release {the Engine is usually released monthly, via Windows Update (WU)}.  There is a 3-day grace period from the day when WU is released.

<!-- Hide {this intro with no subsequent list items}
[Confirm that it is versus as apposed to "out of date" only.]
-->

<!-- Hide {this intro with no subsequent list items}
[https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus?view=o365-worldwide#monthly-platform-and-engine-versions]
-->

#### Antivirus platform version

Shows the real-time results of the most current Microsoft Defender Antivirus platform versions installed across versions of Windows, Mac, and Linux devices in your organization. Microsoft Defender Antivirus platform is updated monthly.
For more details on the current versions and how to update the different Microsoft Defender Antivirus components, see [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md)

### Antivirus platform updates

This card dentifies deices that have Antivirus platform versions that are up to date versus out of date.
Definition of ‘_Up to date_ – the platform version on the device is the most recent platform release (Platform is usually released monthly, via Windows Update).  There is a 3-day grace period from the day when WU is released.

For information about Manage Microsoft Defender Antivirus update versions, see: [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

<!-- Hide {this intro with no subsequent list items}
[Confirm that it is versus as apposed to "out of date" only.]
-->

<!-- Hide {this intro with no subsequent list items}
[@@@ check mail for link]
-->

### Related topics

[Threat protection report](threat-protection-reports.md)

**_End of section, Public Preview: Device health and antivirus compliance report in Microsoft Defender for Endpoint_**

## Publicly-released: Device health and compliance report in Microsoft Defender for Endpoint

The devices status report provides high-level information about the devices in your organization. The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.

The dashboard is structured into two sections:

![Image of the device report.](images/device-reports.png)

****

|Section|Description|
|---|---|
|1|Device trends|
|2|Device summary (current day)|
|||

### Device trends

By default, the device trends graph displays device information from the 30-day period ending in the latest full day. To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown. To adjust the time period, select a time range from the drop-down options:

- 30 days
- Three months
- Six months
- Custom

> [!NOTE]
> These filters are only applied on the device trends section. It doesn't affect the device summary section.

### Device summary

Unlike the device trends graph, the device summary graph shows device information scoped to the current day.

> [!NOTE]
> The data reflected in the summary section is scoped to 180 days prior to the current date. For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.
>
> The filter applied on the trends section is not applied on the summary section.

The device trends section allows you to drill down to the devices list with the corresponding filter applied to it. For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.

### Device attributes

The report is made up of cards that display the following device attributes:

- **Health state**: shows information about the sensor state on devices. This graph provides an all-up view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.
- **Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.
- **OS platforms**: shows the distribution of OS platforms that exists within your organization.
- **Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.

### Filter data

Use the provided filters to include or exclude devices with certain attributes.

You can select multiple filters to apply from the device attributes.

> [!NOTE]
> These filters apply to **all** the cards in the report.

For example, to show data about Windows 10 devices with Active sensor health state:

1. Under **Filters > Sensor health state > Active**.
2. Then select **OS platforms > Windows 10**.
3. Select **Apply**.

### Related topic

- [Threat protection report](threat-protection-reports.md)
