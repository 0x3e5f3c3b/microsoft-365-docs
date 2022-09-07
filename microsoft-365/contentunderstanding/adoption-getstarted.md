---
title: Get started driving adoption of Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.date: 
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection: 
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: 
ms.localizationpriority:  medium
description: Learn how to use and implement SharePoint Syntex in your organization to help streamline your business processes.
---

# Get started driving adoption of Microsoft SharePoint Syntex

Think of the intelligent content services available in SharePoint Syntex as having three parts:

- **Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse. Learn more about [content understanding](document-understanding-overview.md).
- **Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate. Learn more about [content processing](form-processing-overview.md).
- **Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Purview Information Protection.

With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex. For  custom model types, there are three different ways of understanding your content. The custom model type you use is based on file format and use case.

| Classify and extract by text pattern | Extract by layout | Extract by text pattern and layout |
| ------- | ------- | ------- |
| Created in the content center, part of SharePoint Syntex. | Created from document library. | Created from document library. |
| Model created in native interface. | Model created in AI builder. | Model created in AI builder. |
| Used for semi-structured or unstructured file formats. | Used for structured or semi-structured file formats. | Used for unstructured or free-form file formats. |
| Trainable classifier with optional extractors. | Settable classifier. | Settable classifier. |
| Can be applied to multiple libraries. | Restricted to a single library. | Restricted to a single library. |
| Train on 5-10 PDF, Office, or email files, including negative examples. | Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Train on PDF, JPG, PNG format, total 50 MB/500 pp. |

For a more complete comparison of the custom capabilities, see [Compare custom models in SharePoint Syntex](difference-between-document-understanding-and-form-processing-model.md).

If you don't need to build a custom model, you can use a [trained model](prebuilt-overview.md) that has already been trained for specific structured documents.

## Identify pilot business scenarios to optimize

To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful. The "why" helps determine what model will be needed, and how to structure your organization based on where the model will be applied. Here are a few scenarios where custom models can help your organization:

- **Content processing**: Process contracts, statements of work, and other form-like documents. Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.

- **Invoice analysis**: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.

Think about ways that SharePoint Syntex can help your organization:

- Automate business processes
- Improve search accuracy
- Manage compliance risk

When thinking about which business scenarios to consider, ask yourself the following questions:

- Does it solve a real problem?
- Will it be widely used or have broad impact?
- Is it obtainable?
- Can you measure success?

Prioritize scenarios based on impact and ease of implementation. Make your initial focus area higher impact scenarios that can also be easily implemented. De-prioritize lower impact scenarios that are hard to implement.

Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.

## Identify roles and responsibilities

Determine who in your organization will build and manage the models. The following roles might be involved.

| SharePoint/Knowledge admin | Power Platform admin | Knowledge manager | Model owner |
|:-------|:-------|:-------|:-------|
| AAD role| AAD role | AAD role | Champions |
| Configure **Extract by layout** and **Extract by text pattern and layout** models | Configure Dataverse environment | Gather use cases | Gather business use cases |
| Manage content centers and permissions| Purchase and allocate AIB credits | Establish best practices and review model analytics | Create and apply models |

Knowledge manager, business process owner, and content model owner create sample models and champion adoption in the organization. Others who might be involved the compliance admin and taxonomy managers.

Where will they build and apply the models? Are there existing processes or repositories that could be enhanced?

- **Classify and extract by text pattern**: You can create multiple content centers for different business areas.
- **Extract by layout** or **Extract by text pattern and layout**: Decide which sites will get this action.

## Strategic positioning

Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex. Research and provide the following resources to help with this positioning:

- Business outcomes:
  - Potential fiscal outcomes
  - Potential agility outcomes
  - Business outcome template
- Stakeholders/Exec sponsor buy-in/alignment
  - Business case decks
  - Financial models
  - Company readiness - culture

## Identify stakeholders

Identify the stakeholders for your project.

|Role |Responsibilities |Department |
|:-------|:-------|:--------|
| Executive sponsor   | Communicate high-level vision and values to the company   |  Executive leadership   |
| Project lead | Oversee the entire launch execution and rollout process | Project management |
| Knowledge administrators| Create and manage the content centers | IT or other department|
| Content managers and model owners| Gather use cases and create and apply models | Any department|
| Champions | Help evangelize and manage objection handling | Any department (staff) |
| Tenant administrator | Configure tenant-level settings | IT department|
| Power Platform administrator| Configure Dataverse environment | IT department|

> [!NOTE]
> Though we recommend having each of these roles fulfilled throughout your rollout, you might find that you don't require them all to get started with your identified solution.

## Readiness checklist

To get ready for implementing SharePoint Syntex, you need to:

![Readiness for content understanding.](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Plan the end state
    - Models are the means, not the end.
    - Plan for harnessing the value of extracted metadata with:
      - Search
      - Filtering and view formatting
      - Compliance
      - Automation
2. Identify
    - Understand existing information architecture and content management feature use.
    - Are any existing content types good candidates for models?
    - What existing processes would be improved by metadata?
3. Design
    - Design your approach to information architecture, managed metadata, and content types.
    - Design the process for definition, creation, and management.

## Engage your organization

1. Identify stake holders, confirm scenarios, and develop a project plan.
2. Configure settings and apply licenses.
3. Begin awareness and training – recruit champions.
4. Roll out in stages.  
5. Gather feedback and iterate.
6. As usage grows plan for any AI Builder credits as needed.

## See also

[SharePoint Syntex adoption center](https://adoption.microsoft.com/en-us/sharepoint-syntex/adoption/)

[Scenarios and use cases for SharePoint Syntex](adoption-scenarios.md)

[Overview of model types in SharePoint Syntex](syntex-overview.md)
