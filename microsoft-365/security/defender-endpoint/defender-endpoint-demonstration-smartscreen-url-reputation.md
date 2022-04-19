---
title: Microsoft Defender for Endpoint SmartScreen URL reputation demonstrations
description: Demonstrates how Microsoft Defender SmartScreen identifies phishing and malware websites based on URL reputation.
keywords: Microsoft Defender for Endpoint, website phishing protection, website malware protection, URL reputation, demonstration, 
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
---

# SmartScreen URL reputation demonstrations

Test how Microsoft Defender SmartScreen helps you identify phishing and malware websites based on URL reputation.
Scenario requirements and setup

- Windows 10
- Internet Explorer or Edge browser required
- To turn ON/OFF go to Settings -> Update & Security -> Windows Security -> Open Windows Security -> App & browser control >

## SmartScreen for Microsoft Edge URL scenario demos

### Is This Phishing?

Alerts the user to a suspicious page and ask for feedback:

- [Is this Phishing?](https://demo.smartscreen.msft.net/other/areyousure.html)

  Launching this link should render a message similar to the following:

  :::image type="content" source="images/atp-smartscreen-url-reputation-is-this-phishing.png" alt-text="Security for attack surface reduction rule":::

### Phishing Page

A page known for phishing that should be blocked:

- [A known Phishing page](https://demo.smartscreen.msft.net/phishingdemo.html)

  Launching this link should render a message similar to the following:

  :::image type="content" source="images/atp-smartscreen-url-reputation-this-is-phishing.png" alt-text="Security for attack surface reduction rule":::

### Malware page

A page that hosts malware and should be blocked:

- [A known malware page](https://demo.smartscreen.msft.net/other/malware.html)

  Launching this link should render a message similar to the following:

  :::image type="content" source="images/atp-smartscreen-url-reputation-malware-page.png" alt-text="Security for attack surface reduction rule":::

### Blocked download

Blocked from downloading because of its URL reputation

- [Download blocked due to URL reputation](https://demo.smartscreen.msft.net/download/malwaredemo/freevideo.exe)

  Launching this link should render a message similar to the Malware page message.

### Exploit page

A page that attacks a browser vulnerability

- [Known browser exploit page](https://demo.smartscreen.msft.net/other/exploit.html)

  Launching this link should render a message similar to the Malware page message.

### Malvertising

A benign page hosting a malicious advertisement

- [A page known to contain malicious advertisements](https://demo.smartscreen.msft.net/other/exploit_frame.html)

  Launching this link should render a message similar to the following:

  :::image type="content" source="images/atp-smartscreen-url-reputation-malvertising.png" alt-text="Security for attack surface reduction rule":::

## See also

[Microsoft Defender SmartScreen Documentation](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview.md)

[Microsoft Defender for Endpoint - demonstration scenarios](defender-endpoint-demonstrations.md)
