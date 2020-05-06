---
title: "Apply a sensitivity label to content automatically"
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 
localization_priority: Priority
ms.collection: 
- M365-security-compliance
ms.topic: article
search.appverid: 
- MOE150
- MET150
description: "When you create a sensitivity label, you can automatically assign a label to a document or email, or you can prompt users to select the label that you recommend."
---

# Apply a sensitivity label to content automatically

>*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*

When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.

The ability to apply sensitivity labels to content automatically is important because:

- You don't need to train your users when to use each of your classifications.

- You don't need to rely on users to classify all content correctly.

- Users no longer need to know about your policies—they can instead focus on their work.

There are two different methods for automatically applying a sensitivity label:

- **Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook). 
    
    This method supports recommending a label to users, as well as automatically applying a label. But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content. This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved. However, not all client apps support auto-labeling. This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps). 
    
    For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.

- **Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview. 
    
    > [!NOTE]
    > See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).
    
    This method is referred to as auto classification with sensitivity labels. You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange). For Exchange, it doesn't include emails at rest (mailboxes). 
    
    Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version. As a result, this capability is immediately available throughout your organization and suitable for labeling at scale. Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process. Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.
    
    For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.
    
    Specific to auto-labeling for SharePoint and OneDrive:
    - Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day
    - Maximum of 10 sites collections across all policies
    - Maximum of 10 policies across your tenant

    Specific to auto-labeling for Exchange:
    - Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy. When there is a match, the email is labeled but not the attachment.
    - If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied. If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored. However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.
    - Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.
    - Incoming email is labeled when there is a match with your auto-labeling conditions. However, if the label is configured for encryption, that encryption isn't applied.
    

## Compare auto-labeling for Office apps with auto-labeling policies

Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:

|Feature or behavior|Label setting: Auto-labeling for Office apps |Policy: Auto-labeling|
|:-----|:-----|:-----|:-----|
|App dependency|[Yes](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |No |
|Restrict by location|No |Yes |
|Conditions: Trainable classifiers|Yes |No |
|Conditions: Sharing options and additional options for email|No |Yes |
|Recommendations, policy tooltip, and user overrides|Yes |No |
|Simulation mode|No |Yes |
|Exchange attachments checked for conditions|No | Yes|
|Apply visual markings |Yes |Yes (email only) |
|Override IRM encryption applied without a label|Yes if the user has the minimum usage right of Export |Yes (email only) |
|Label incoming email|No |Yes (encryption not applied) |

> [!NOTE]
> When content has been manually labeled, that label will never be replaced by automatic labeling. However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.

## How multiple conditions are evaluated when they apply to more than one label

The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).

## Don't configure a parent label to be applied automatically or recommended

Remember, you can't apply a parent label (a label with sublabels) to content. Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy. If you do, the parent label won't be applied to content.

To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.

For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).

## How to configure auto-labeling for Office apps

Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client. For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):

![Auto labeling options for sensitivity labels](../media/sensitivity-labels-auto-labeling-options.png)

You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. Choose from a list of sensitive info types or trainable classifiers:

![Label conditions for auto-labeling in Office apps](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> The option for **Trainable classifiers** is currently rolling out to tenants in public preview. If you don't see this option, try again a few days..

When this sensitivity label is automatically applied, the user sees a notification in their Office app. For example:

![Notification that a document had a label applied automatically](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### Configuring sensitive info types for a label

When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:

![Sensitive info types for auto-labeling in Office apps](../media/sensitivity-labels-sensitive-info-types.png)

After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy. For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Further, you can choose whether a condition must detect all sensitive information types, or just one of them. And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups. For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).

![Options for instance count and match accuracy](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### Configuring trainable classifiers for a label

When you select the **Trainable classifiers** option, select one or more of the built-in trainable classifiers:

![Options for trainable classifiers and sensitivity labels](../media/sensitivity-labels-classifers.png)

For more information about these trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).

During the preview period, the following apps support trainable classifiers for sensitivity labels:

- Microsoft 365 Apps for enterprise for Windows, from [Office Insider](https://office.com/insider):
    - Word
    - Excel
    - PowerPoint

- Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):
    - Word
    - Excel
    - PowerPoint
    - Outlook

### Recommend that the user applies a sensitivity label

If you prefer, you can recommend to your users that they apply the label. With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.

![Option for recommending a sensitivity label to users](../media/Sensitivity-labels-Recommended-label-option.png)

Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.

![Prompt to apply a recommended label](../media/Sensitivity-label-Prompt-for-required-label.png)

### When automatic or recommended labels are applied

The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client. In both cases, however:

- You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity. Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).

- You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity. When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.

Specific to built-in labeling:

- Not all Office apps support automatic (and recommended) labeling. For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

- For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.

- For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).

Specific to the Azure Information Protection unified labeling client:

-  Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.

- For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).

- Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.

## How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange
> [!NOTE]
> Auto-labeling policies are in public preview and subject to change.

### Prerequisites for auto-labeling policies

- Auditing for Microsoft 365 must be turned on for simulation mode. If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).

- To auto-label files in SharePoint and OneDrive:
    - You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).
    - At the time the auto-labeling policy runs, the file mustn't be open by another process or user.

- If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types: 
    - Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved. 
    - To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.

- One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies. For these labels:
    - It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction. 
    - If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.
    - If the labels apply encryption, they must be configured for the **Assign permissions now** setting.

### Learn about simulation mode

Simulation mode is unique to auto-labeling policies and woven into the workflow. You can't automatically label documents and emails until your policy has run at least one simulation.

Workflow for an auto-labeling policy:

1. Create and configure an auto-labeling policy

2. Run the policy in simulation mode and wait at least 24 hours

3. Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours

4. Repeat step 3 as needed

5. Deploy in production

The simulated deployment runs like the WhatIf parameter for PowerShell. You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined. You can then refine your rules for accuracy if needed, and rerun the simulation. However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.

Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment. For example, you might start with a single location, such as a SharePoint site, with a single document library. Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.

Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.

### Creating an auto-labeling policy

1. In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:
    
    - **Solutions** > **Information protection**
    
    If you don't immediately see this option, first select **Show all**.

2. Select the **Auto-labeling (preview)** tab:
    
    ![Auto-labeling (preview) tab](../media/auto-labeling-tab.png)
    

3. Select **+ Create policy**.

4. For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**. You can refine your search by using the **Show options for** dropdown. Or, select **Custom policy** if the templates don't meet your requirements. Select **Next**.

5. For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.

6. For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive. Then select **Next**.

7. For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations. If you need different rules per location, select **Advanced settings**. Then select **Next**.
    
    The rules use conditions that include sensitive information types and sharing options:
    - For sensitive information types, you can select both built-in and custom sensitive information types.
    - For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.
    
    If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:
    - Sender IP address is
    - Recipient domain is
    - Recipient is
    - Attachment's file extension is
    - Attachment is password protected
    - Any email attachment's content could not be scanned
    - Any email attachment's content didn't complete scanning

8. For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.

9. On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.
    
    The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps. If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).

10. Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step. When you have defined all the rules you need, and confirmed their status is on, select **Next**.

11. For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.

12. For the **Decide if you want to run policy simulation now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode. Otherwise, select **Leave policy turned off**. Select **Next**. 

13. For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.
    
    Unlike auto-labeling for Office apps, there's no separate publish option. However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.

Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not. Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**). For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.

You can modify your policy directly from this interface:

- For a policy in the **Off** section, select the **Edit policy** button.

- For policy in the **Simulation** section, select the **Edit** option at the top of the page, from either tab:
    
    ![Edit auto-labeling policy option](../media/auto-labeling-edit.png)
    
    When you're ready to run the policy without simulation, select the **Turn on policy** option.

You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):
- **Content Explorer List viewer** lets you see a file's label but not the file's contents.
- **Content Explorer Content viewer** lets you see the file's contents.

> [!TIP]
> You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information. Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.

