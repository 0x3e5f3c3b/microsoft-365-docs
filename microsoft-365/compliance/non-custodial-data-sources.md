---
title: "Add non-custodial data sources to an Advanced eDiscovery case"
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance 
search.appverid: 
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW 
description: ""
---

# Add non-custodial data sources to an Advanced eDiscovery case

In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case. But you may still need to associate that data with a case so that you search it, add it to review set, and review it. The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian. It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian. Two of the most useful features that you can apply to non-custodial is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).

## Add non-custodial data sources to a case

Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.

1. On the **Advanced eDiscovery** home page, click the case that you want to add the data to.

2. On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.

3. Click **Add data location** and choose the data sources that you want to add to the case. You can add mailboxes and sites.

4. On the **Choose locations** page in the wizard, you can add mailboxes and sites as non-custodial data sources to the case.

5. After adding the data sources, click **Next**.

6. On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.

7. Verify the hold selections and then click **Submit**.

   A job named *Re-indexing non-custodial data* is created and displayed on the **Jobs** tab of the case. After the job is created, the Advanced indexing process in initiated and the data sources are re-indexed.

## Managing the hold on non-custodial data sources

After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created. When you place additional non-custodial data sources on hold, they are added to this hold policy.

1. On the **Home** page of the case, click the **Holds** tab.

2. On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.

3. On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.

You can perform the following management task on non-custodial data sources:

- You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.

- You can release a non-custodial data source from the hold. Releasing a data source doesn't remove the non-custodial data source from the case. It just removes the hold that was placed on the data source.
