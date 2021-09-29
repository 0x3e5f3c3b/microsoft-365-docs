---
title: Submit suspected files in Microsoft Defender for Endpoint
description: Learn how to use the Submissions feature in the Microsoft 365 Defender to submit suspicious emails, suspected phishing mails, spam, and other potentially harmful messages, URLs, and files to Microsoft for scanning.
keywords: antivirus, spam, phish, Microsoft Defender for Endpoint, false positive, false negative, blocked file, blocked url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.date: 06/15/2021
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
manager: dansimp
localization_priority: Normal
audience: ITPro
ms.topic: how-to
ms.collection: 
- m365-security-compliance 
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.custom: FPFN
---

# Submit suspected files in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146806)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Want to experience Microsoft Defender for Endpoint? [Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-usewdatp-abovefoldlink).

In Microsoft Defender for Endpoint, admins can use the Submissions feature in the Microsoft 365 Defender to submit files and file hashes (SHAs) to Microsoft for review.

## Microsoft Defender for Endpoint interactive guide

In this interactive guide, you'll learn how Microsoft Defender for Endpoint can help you identify suspicious activities, investigate risks to your organization, and remediate threats.

[Check out the interactive guide](https://aka.ms/MSDE-IG)

## What do you need to know before you begin?

- To submit files to Microsoft, you need to be a member of one of the following role groups:

  - **Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](../office-365-security/permissions-microsoft-365-security-center.md).

- For more information about how you can submit spam, phish, URLs, files, and file hashes (SHAs) to Microsoft, see [Report messages and files to Microsoft](../office-365-security/report-junk-email-messages-to-microsoft.md).

## Report suspicious content to Microsoft

If you have a file that you suspect might be malware or is being incorrectly detected, you can submit it to Microsoft for analysis using Microsoft 365 Defender at https://security.microsoft.com/.

### Submit a suspected file or file hash

1. Open the Microsoft 365 Defender at <https://security.microsoft.com/>, click **Submissions**, and then select **Add new submission**. 

> [!div class="mx-imgBorder"]
> ![Add new submission](../../media/unified-admin-submission-new.png) (Image not final)

2. Use the **Submit items to Microsoft for review** flyout that appears to submit the **File** or **File hash**.  

3. In the **Submission type** box, select **File** or **File hash** from the drop-down list. 

4. Click **Browse files**. In the dialog that opens, find and select the file, and then click **Open**. Note that for **File hash** submissions, you'll either have to copy or type in the file hash. 

5. In the **How would you categorize this submission?** section, choose either **Malware**, or **Unwanted software**, or **Clean** (false positive).
  
6. Next, **Choose the priority**. Note that for **File hash** submissions, **Low - bulk files and file hash submissions** is the only choice, and is automatically selected.

> [!div class="mx-imgBorder"]
> ![Submit items to Microsoft for review](../../media/unified-admin-submission-file.png) (Image not final)

8. Click **Submit**. 
 
 If you want to view the details of your submission, select your submission from the **Submissions name** list to open the **Result details** flyout.

## Submit items to Microsoft from the Alerts page

You can also submit a file or file hash directly from the list of alerts on the **Alerts** page. 

1. Open the Microsoft 365 Defender at <https://security.microsoft.com/>, click **Incidents & alerts**, and then click **Alerts** to view the list of alerts.

2. Select the alert you want to report.  

3. Click the ellipses next to **Consult a threat expert** to see additional options. Select **Submit items to Microsoft for review**.

> [!div class="mx-imgBorder"]
> ![Submit items from alerts queue](../../media/unified-admin-submission-alerts-queue.png) (Image not final)

4. In the next flyout that opens, select the submission type, upload the file, categorize your submission, and choose the priority. 

> [!div class="mx-imgBorder"]
> ![Complete the required fields](../../media/unified-admin-submission-alert-queue-flyout.png) (Image not final)
 
5. Click **Submit**. 

## Related information

- [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)
- [Address false positives/negatives](defender-endpoint-false-positives-negatives.md)
- [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide)
- [View and organize alerts queue in Microsoft Defender for Endpoint](alerts-queue.md)