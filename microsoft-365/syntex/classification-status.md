---
title: View the status of a file being processed by Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
ms.date: 06/01/2023
audience: admin
ms.topic: conceptual
ms.service: microsoft-syntex
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority:  medium
ROBOTS: NOINDEX, NOFOLLOW
description: Learn how to use the classification status column in a SharePoint document library with Microsoft Syntex.
---

# View the status of a file being processed by Microsoft Syntex

<sup>**Applies to:**  &ensp; &#10003; All custom models &ensp; | &ensp; &#10003; All prebuilt models</sup>

In a document library, the **Classification status** column lets you know the status of a file that is being processed by a model in Microsoft Syntex.

The status shows you whether the processing of a file is in progress, completed, or wasn’t done due to an error with the file or the job. This helps you know whether a file needs to be queued again for processing or if additional investigation is required.  

When a model is applied to a library, the **Classification status** column is added. The column won't be automatically added to libraries where a model has already been applied. You'll need to apply the model again to add the column.

| Classification status | Description |
| ------- | ------- 
| In progress | File has been queued for processing. |
| Finished | File has been processed. |
| Not supported | File has been queued, but can't be processed (for example, the file type extension is not supported). |
| Error | File can't be queued for processing (for example, the file is not supported at all). |
| [Empty] | No models have been applied to the library. |