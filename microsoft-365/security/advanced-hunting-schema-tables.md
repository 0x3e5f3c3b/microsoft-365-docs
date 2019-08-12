---
title: Data tables in the Microsoft 365 security center advanced hunting schema
description: Learn about the tables in the Microsoft 365 advanced hunting schema
keywords: advanced hunting, atp query, query atp data, intellisense, atp telemetry, events, events telemetry, azure log analytics, schema reference
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance 
ms.topic: article
---

# Understand the advanced hunting schema

**Applies to**:
- Microsoft 365 security center

The advanced hunting schema is made up of multiple tables that provide either event information, or information about certain entities. To effectively build queries that span multiple tables, you need to understand the tables and the columns in the Advanced hunting schema.

## Schema tables

The following reference lists all the tables in the schema. Each table name links to a page describing the column names for that table. Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.

| Table name | Description |
|------------|-------------|
| **[AlertEvents](advanced-hunting-alertevents-table.md)** | Alerts on Microsoft Defender Security Center |
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | Machine information, including OS information |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | Process creation and related events |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | Network connection and related events |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | File creation, modification, and other file system events |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | Creation and modification of registry entries |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | Sign-ins and other authentication events |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | DLL loading events |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Office 365 email events, including email delivery and blocking events |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Information about files attached to Office 365 emails |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Information about URLs on Office 365 emails |

## Related topics
- [Proactively hunt for threats](advanced-hunting.md)
- [Learn the query language](advanced-hunting-language-overview.md)
- [Use shared queries](advanced-hunting-shared-queries.md)
- [Hunt for threats across devices and emails](advanced-hunting-query-emails-devices.md)
- [Find miscellaneous events](advanced-hunting-misc-events.md)
- [Apply query best practices](advanced-hunting-best-practices.md)
