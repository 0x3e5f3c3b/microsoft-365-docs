---
title: "Microsoft Compliance Score (preview) FAQ"
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: 
- MOE150
- MET150
description: "Find answers to frequently asked questions about Microsoft Compliance Score, which helps organizations simplify and automate risk assessments."
---

# Compliance Score (preview) frequently asked questions

## What is Compliance Score?

Microsoft Compliance Score is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you understand your organization's compliance posture. It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards. Compliance Score provides built-in control mapping that helps connect common controls among key regulations and standards, so you can take one action to satisfy multiple requirements at the same time and better scale your compliance program.

## What's new in the preview version of Compliance Score?

Visit the [Compliance Score release notes](compliance-score-release-notes.md) to learn about feature updates and known issues.

## How do I access Compliance Score?

Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with a Microsoft 365 global admin, compliance admin, or compliance data admin role. Select **Compliance Score** on the left navigation pane. You should then see your [Compliance Score dashboard with your score](compliance-score-setup.md#understand-the-compliance-score-dashboard). If you don't have appropriate role access, the global admin for your organization can grant you permission.

## What roles or permissions are needed to use Compliance Score?

Compliance Score uses a role-based access control (RBAC) permission model, and the actions you can perform depend on the type of role assigned to you. Your organization's Microsoft 365 global admin is the person who can perform the setup functions and administer roles in Compliance Score. At a minimum, users need the **Azure AD global reader** role to read data in Compliance Score. Learn more about permissions, roles, and setup procedures at [Compliance Score setup](compliance-score-setup.md).

## What is the difference between Compliance Score and Compliance Manager?

Compliance Score and Compliance Manager share the same backend, but they are in two different locations. Compliance Score is in the Microsoft 365 compliance center, and Compliance Manager is in the Microsoft Service Trust Portal. Think of Compliance Score as a simplified version of Compliance Manager, giving you a more complete view of your organization's current compliance posture and the steps you can take to improve it. While you can take many actions directly within Compliance Score, some functionality lives in Compliance Manager for now. Read more about the [relationship between Compliance Score and Compliance Manager](compliance-score.md#relationship-to-compliance-manager).

Access [Compliance Manager in the Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ComplianceManager/V3). Be sure to **select Compliance Manager** from the top navigation drop-down menu, which has the most current features, and *not Compliance Manager (classic)*, which contains early-release features.

## Should I use Compliance Score or Compliance Manager?

Compliance Score is useful for everyone in your organization who plays a role in compliance. With Compliance Score, you don't need to be familiar with regulations and standards to help improve your organization's data protection. Compliance Score is the optimal starting place for all users. From here, you can see your compliance score, learn which recommended actions can help minimize risks, and, manage your assessments.

For now, Compliance Manager is the place where you can create custom templates to build assessments. Learn more about [which actions are supported only by Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) during public preview.

## If I have a high score, does it mean I'm fully compliant?

No. Your compliance score measures your progress in completing recommended actions that help reduce risks around data protection and regulatory standards. It does not express an absolute measure of organizational compliance with any particular standard or regulation. Compliance Score should not be interpreted as a guarantee in any way.

## What regulations and standards does Compliance Score monitor?

Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline, which is a set of controls that includes common industry regulations and standards. This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).

Organizations can create and add custom assessments that are more relevant to their organization. Use one of Compliance Score's ready to use [templates](compliance-score-templates.md), customize a Microsoft template with your own controls and actions, or create your own template. Read details about [working with assessments and templates](compliance-score-assessments.md).

## How does Compliance Score continuously assess my environment?

Compliance Score automatically scans your environment and uses Secure Score to detect system settings. Learn more about [continuous assessment](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls).

## What is the difference between Compliance Score and Secure Score?

Compliance Score provides a broad view of your organization's data protection and compliance posture. Compliance Score also provides built-in workflow tools; it lets organizations assign work to users, track the control implementation and test status, and upload evidence and create audit reports.

Microsoft Secure Score is a security analytics tool for helping with understanding your security posture. [Learn more about Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).

## Which cloud services are covered by Compliance Score?

Compliance Score currently provides assessments for Office 365 and Intune. Expanded coverage is expected in future releases, and will be noted in the [Compliance Score release notes](compliance-score-release-notes.md).

## Can I use Compliance Score for non-Microsoft products?

While Compliance Score provides continuous monitoring and recommended actions only for Microsoft cloud services, you can add custom assessments in Compliance Manager for your on-premises, third-party services. In this way, you can use Microsoft Compliance Score as a SaaS compliance management tool to help you manage all the controls across your digital assets.

You can use one of Compliance Score's ready to use [templates](compliance-score-templates.md) to create assessments for particular standards, or [create your own template](working-with-compliance-manager.md#create-a-template), which you'll need to do in Compliance Manager.

## How do I delete a template or assessment I no longer need?

To delete an assessment, open the assessment you wish to delete and select **Delete assessment**. Note that deleting an assessment is permanent. View additional details about [deleting assessments](compliance-score-assessments.md#delete-an-assessment). Deleting an assessment does not delete its template. Templates can’t be deleted, but can be hidden from view. Review [instructions for hiding templates](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## What test procedures does Microsoft follow for controls?

Microsoft participates in annual audits for controls. You can review the audit reports from our auditors, which are available for download from the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3).

## Why are some controls tested annually, and others tested every three years?

The FedRAMP assessment is an example of why this might be the case. It is conducted every year and tests a cross-section of controls among major control families. FedRAMP classifies controls as **core** when they're important enough to require annual testing. Controls designated as non-core are tested every three years. A subset of controls that span all the major control families are tested annually. In this way, each annual audit looks at scenarios across the board to ensure the solution is robust. Read more about the [FedRAMP annual assessment process](https://www.fedramp.gov/annual-assessment-guidance/).
