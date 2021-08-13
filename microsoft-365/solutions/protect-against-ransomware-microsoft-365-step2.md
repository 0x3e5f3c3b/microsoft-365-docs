---
title: "Step 2: Minimize privileged access and prevent credential escalation"
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: 
description: Step through protecting your Microsoft 365 resources from ransomware attacks.
---

# Step 2: Minimize privileged access and prevent credential escalation

The best ways to minimize privileged access and prevent credential escalation are through:

- Executing a privileged access strategy
- Detecting and responding to a credential escalation

High-privilege accounts are those for IT admins or priority users with access to ransomable resources.

## Privileged access strategy

### Prevent: Attacker can’t obtain privileged access

Ways to prevent escalation to a high-privilege account:

- Change authentication requirements

   - New and strong password

   - Multi-factor authentication

   - Use Conditional Access policies to lock down access requirements for high-privilege accounts

- Use governance to determine which high-privilege accounts can be removed

### Mitigate: Attacker has privileged access, but can’t use it easily

Ways to keep an attacker from using an admin account:

- Secure admin workstations for all Microsoft 365 admin procedures
- Use Azure AD Privileged Identity Management

   Requires and enrollment and approval process before the admin account becomes usable.

- Privileged access management (PAM)

   Requires a request for just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.

## Detection and response of credential escalation

Ways to determine whether an attacker has escalated their privileges to a high-privilege account:

- Azure AD Identity Protection

   Monitor for password spray attacks.

- Microsoft 365 Defender and Microsoft Defender for Identity

Once you discover a compromised high-privilege account, remove it.

## Next step

[![Step 3 for ransomware protection with Microsoft 365](../media/protect-against-ransomware-microsoft-365/protect-against-ransomware-step3.png)](protect-against-ransomware-microsoft-365-step3.md)

[Step 3: Prevent attacker access](protect-against-ransomware-microsoft-365-step3.md)
