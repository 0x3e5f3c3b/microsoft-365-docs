---
title: Create a model in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority:  medium
description: Learn how to create a model with SharePoint Syntex.
---

# Create a model in Microsoft SharePoint Syntex

<sup>**Applies to:**  &ensp; &#10003; All custom models &ensp; | &ensp; &#10003; All trained models</sup>

Whether you want to create a custom model or use a trained model, you start in the **Models** library. For information about the different model types, see [Overview of model types in SharePoint Syntex](model-types-overview.md).

## Create a model

Follow these steps to create a model in SharePoint Syntex.

1. From the **Models** page, select **Create a model**.

2. On the **View options for classification and extraction** page, there are two sections:

    - **Build a custom model**
    - **Use a trained model**

### To build a custom model

1. In the **Build a custom model** section, select the type of custom model you want to learn more about or you want to start creating. 

    - **Classify and extract by text pattern** – Best for Office files and automatic classification of files

    - **Extract by layout** – Best for non-English languages and files with tables

    - **Extract by text pattern and layout** – Best for a mix of both text and layout needs

#### Classify and extract by text pattern

1. On the **Classify and extract by text pattern** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

2. On the **Create model to classify and extract by text pattern** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.
    
3. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. Under **Sensitivity labels**, select the sensitivity label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

4. When you are ready to create the model, select **Create**.

5. You are now ready to begin training the model:

    - [Upload six example files](create-a-classifier#add-your-example-files).
    - [Train the model to classify](create-a-classifier.md).
    - [Add explanations of text patterns](explanation-types-overview.md).
    - [Train extractors](create-an-extractor.md) (optional).
    - [Test model](create-a-classifier#test-your-model) (optional).

#### Extract by layout

#### Extract by text pattern and layout

### To use a trained model

1. In the **Use a trained model** section, select the type of trained model you want to learn more about or to start using. 

    - **Receipts** – Save time processing receipts for expenses. Automatically extract key info specific to expenses.

    - **Invoices** – Save time processing invoices. Automatically extract key info specific to invoices.

#### Receipts

1. On the **Receipts** page, you'll find more information about the model. If you want to proceed with using the model, select **Next**.

2. On the **Create a model to process receipts** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Office expenses*.

    - **Description** – Enter information about how this model will be used.
    
3. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a retention label has been already applied to the library where the file is stored, it will be selected. 

4. When you are ready to create the model, select **Create**.

5. To complete the model:

    - [Upload an example file](create-a-classifier#add-your-example-files).
    - [Select extractors](create-an-extractor.md).
    - [Apply model to library](apply-a-model.md).

#### Invoices

