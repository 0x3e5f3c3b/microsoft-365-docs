---
title: "Close, reopen, and delete Core eDiscovery cases"
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: 
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid: 
- MOE150
- MET150
description: "This article describes how to manage Core eDiscovery cases. This includes closing a case, reopening a closed case, and deleting a case."
---

# Close, reopen, and delete Core eDiscovery cases

This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.

## Close a case

When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case. Here's what happens when you close a case:
  
- If the case contains any content locations on eDiscovery hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.

- Closing a case only turns off the holds that are associated with that case. If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.

- The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center. The details, holds, searches, and members of a closed case are retained.

- You can edit a case after it's closed. For example, you can add or removing members, create searches, and export search results. The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.

To close a case:
  
1. In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.

2. Click the name of the case that you want to close.

    The **Manage this case** flyout page is displayed.

3. Under **Manage case status**, click **Close case**.

    A warning is displayed saying that the holds associated with the case will be turned off.

4. Click **Yes** to close the case.

    The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.

5. Close the **Manage this case** page.

6. On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case. It might take up to 60 minutes for the closing process to complete.

    When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page. Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.

## Reopen a closed case

When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated. After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds. To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.
  
1. In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.

2. Click the name of the case that you want to reopen.

    The **Manage this case** flyout page is displayed. 

3. Under **Manage case status**, click **Reopen case**.

    A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.

4. Click **Yes** to reopen the case.

    The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.

5. Close the **Manage this case** page. 

6. On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case. It might take up to 60 minutes for the reopening process to complete. 

    When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page. 
  
## Delete a case

You can also delete active and closed Core eDiscovery cases. When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center. You can't reopen a deleted case.

Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case. That includes deleting holds with a status of **Off**. 

To delete an eDiscovery hold:

1. Go the **Holds** tab in the case that you want to delete.

2. Click the hold that you want to delete.

3. On the flyout page, click **Delete hold**.

To delete a case:

1. In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.

2. Click the name of the case that you want to delete.

3. Under **Manage case status** on the flyout page, click **Delete case**.

If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message. You'll have to delete all holds associated with the case and then try again to delete the case.
