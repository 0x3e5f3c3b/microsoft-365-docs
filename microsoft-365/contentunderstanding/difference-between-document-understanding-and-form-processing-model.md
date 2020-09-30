---
title: "Difference between document understanding and form processing models"
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: 
localization_priority: Priority
description: "Describes key difference between document understanding and form processing models"
---

# Difference between document understanding and form processing models 


Content understanding in Microsoft SharePoint Syntex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.  For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view. Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view. 

Content understanding lets you create *models* to identify and extract the information you need. Models have value in helping to resolve business issues for search, business processes, compliance, and many others.

There are two model types that you can use:

- [Document understanding models](document-understanding-overview.md)
- [Form processing models](form-processing-overview.md)

While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.



## Structured versus unstructured and semi-structured content

Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document. For example, an unstructured document could be a contract renewal letter that can be written in different ways. However, information exists consistently in the body of each contract renewal document, such as the text string *Service start date of* followed by an actual date.   

Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices. Form processing models are trained to understand the layout of your form from example documents, and learn to look for the data you need to extract from  similar locations, since forms have a more structured layout where entities are in the same location (for example, a social security number in a tax form). 

> [!NOTE]
> You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library. 


## Where they are created

Document understanding models are created and managed in a SharePoint content center site. 

> [!NOTE]
> For more information about input documents, see [Form processing model requirements and limitations](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library. Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings. Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.

When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery. Or you can use existing content types to define your model if needed.

Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library. Form processing model creation needs to be enabled on your document library for a user to create a form processing model for it. Or an admin can do this in the content understanding admin settings. Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.

Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.

## Where they can be applied

You can apply document understanding models to SharePoint document libraries that you have access to. Use the content center to create a document understanding model, and apply it to different document libraries. The content center gives you a more central control for how document understanding models are used and where they are applied. Note this information must also roll up to a content center.

Form processing models can currently only be applied to the SharePoint document library from which you created them. This allows licensed users with access to the site to be able to create a form processing model. Note that your admin needs to enable form processing on a SharePoint document library for it to be available to licensed users.

 ## See Also
[Training: Improve business performance with AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)

[Create a classifier](create-a-classifier.md)

[Create an extractor](create-an-extractor.md)

[Apply a document understanding model](apply-a-model.md)

[Create a form processing model](create-a-form-processing-model.md)
