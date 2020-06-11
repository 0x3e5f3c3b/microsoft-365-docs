---
title: New Microsoft Edge app
description:  
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
---

# New Microsoft Edge app

The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse. Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.

## Initial deployment

To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal. We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours. To pause the deployment, file another ticket asking Operations to hold.

## Updates to Microsoft Edge

Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks. Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers. The Microsoft Edge Beta channel is not currently available.

To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).

## Settings managed by Microsoft Managed Desktop

Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser. The default browser settings are as follows:

### Microsoft Edge extensions

The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users. To enable and deploy extensions in your environment, see Settings you manage. 

#### Extension installation blocklist
**Default value:** All

Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints. There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices. 

#### Allow user-level native messaging hosts (installed without admin permissions)

**Default value:** Disabled

By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level. Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.  

### Secure Sockets Layer (SSL)

#### Minimum SSL version

**Default value:** Minimum TLS 1.2 supported

If you want to use the less secure TLS 1.1, you can request this.

#### Allows users to proceed from the SSL warning page

**Default value:** Disabled

We don't recommend enabling this setting since it allows users to visit sites with SSL errors.

### Microsoft Defender Smart Screen

#### Configure Microsoft Defender SmartScreen

**Default value:** Enabled

Enabled by default to help protect end users.

#### Microsoft Defender SmartScreen prompts for sites

**Default value:** Enabled

We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.

#### Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads

**Default value:** Enabled

We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.

### Adobe Flash

#### Default Adobe Flash setting

**Default value:** Disabled

We don't recommend using Flash because of associated security risks. If you still have processes which depend on Flash, set the **PluginsAllowedForUrls** policy to enable Flash for sites which need it. If can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.

### Password manager

#### Enable saving passwords to the password manager

**Default value:** Disabled

We do not recommend allowing end users to save passwords on their device.

### Other settings

#### Enable site isolation for every site

**Default value:** Enabled

When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.

#### Supported authentication schemes

**Default value:** NTLM, Negotiate

Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.

#### Automatically import another browser's data and settings at first run

**Default value:** Automatically import all supported datatypes and settings from the default browser 

With this policy applied, the First Run Experience will skip the import section, minimizing user interaction. The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting. 


## Settings you manage