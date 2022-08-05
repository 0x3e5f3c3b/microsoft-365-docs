---
title: Build queries using guided mode
description: Learn about advanced hunting queries in Microsoft 365 and how to use them to proactively find threats and weaknesses in your network
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords: 
  - NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
  - M365-security-compliance
  - m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
---

# Build hunting queries using guided mode in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Applies to:**
- Microsoft 365 Defender

Advanced hunting is a query-based threat hunting tool that lets you explore up to 30 days of raw data. You can proactively inspect events in your network to locate threat indicators and entities. The flexible access to data enables unconstrained hunting for both known and potential threats.

To reduce the learning curve for hunting, remove the KQL challenge, and enable all analysts to hunt,  **Guided hunting** experience is supported. This is a hunting mode that enables all analysts to hunt—without knowing KQL or the data schema. In this mode, you can use a query builder to write your queries. You just need to know what you are looking for and you can easily filter for it. 

## Query in builder
In the **Advanced hunting** page, select **Create new** to open a new query tab and select **Query in builder**. This brings you to the guided mode, where you can then construct your query by selecting different components using dropdown menus.

[IMAGE: HIGHLIGHTED QUERY IN BUILDER]

### Specify the data domain to hunt in
By default, guided hunting includes a few basic filters to get you started fast.

You can control the scope of the hunt by selecting the **View in** control:

[IMAGE: View in]

**View in** controls the filters. Selecting **All** allows you to filter the entire dataset. narrowing down to a specific domain allows filters relevant to that domain only. 

You can choose from:
- All domains - to look through all available data in your query
- Endpoints - to look through endpoint data as provided by Microsoft Defender for Endpoint
- Apps and identities - to look through application and identity data as provided by Microsoft Defender for Cloud Apps and Microsoft Defender for Identity; users familiar with Activity log can find the same data here
- Email and collaboration - to look through email and collaboration apps data like SharePoint, OneDrive and others; users familiar with Threat Explorer can find the same data here



### Create conditions

To add a condition to your query, select **Select a filter**. Explore the different filter sections to find what is available to you.
 
[IMAGE: select a filter]

Type the section's titles to find the filter or use the search box at the top of the list. _* Info_ sections contain filters that provide information about the different components you can look at. _* Events_ sections contain filters that allow you to look for any system or network event. 

You can also create AND, OR conditions. Select **AND** to include results that  

## Try some queries

### Hunt for successful connections to specific IP
to hunt for successful network communications to a specific IP address, start typing “ip” to get suggested filters:
[IMAGE]
To look for events involving this IP address where this IP is the destination of the communication, select DestinationIPAddress under the IP Address Events section. Then select the **equals** operator and type the IP and press **Enter**:

[IMAGE]

Then, to add a second condition which searches for successful network communication events, search for the filter of a specific event type:

[IMAGE]

**Event** filter is filtering for the different event types logged. It is equivalent to the **ActionType** column which exists in most of the tables in advanced hunting. Select it to select one or more event types to filter for. To look for successful network communication events, expand the **DeviceNetworkEvents** section and then choose **ConnectionSuccess**:

[IMAGE]

Finally, select **Run query** to hunt for all successful network communications to the 52.168.117.170 IP address:

[IMAGE]

### Hunt for high confidence phish or spam emails delivered to inbox

tT look for all high confidence phish and spam emails that were delivered to the inbox folder at the time of delivery, first select ConfidenceLevel under Email Events, select **equals** and choose **High** under both **Phish** and **Spam** from the suggested closed list which supports multi-selection:

[IMAGE]

Then, add another condition this time specifying the folder or **DeliveryLocation, Inbox/folder**. 

[IMAGE]

## Load sample queries

Another way to get familiar with guided hunting is to load sample queries pre-created in guided mode. 

In the **Getting started** section of the hunting page, we have provided three guided query examples that you can load. The query examples contain some of the most common filters and inputs you would typically need in your hunting. Loading any of the three sample queries opens a guided tour of how you would construct the entry using guided mode.

[IMAGE]

## See also