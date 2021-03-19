---
title: "Pre-work for the migration from Microsoft Cloud Deutschland"
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: 
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: "Summary: Pre-work when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region."
---

# Pre-work for the migration from Microsoft Cloud Deutschland

Use these links to get to the pre-work steps relevant to your organization:

- For **all customers** using Office 365 in Microsoft Cloud Deutschland, do [these steps](#General-tenant-migration-considerations).
- For **DNS changes**, do [this step](#dns).
- If you're using **Active Directory Federation Services** on premeises, do [these steps](#Active-Directory-Federation-Services-(AD-FS)).
- If you're using **SharePoint Online**, do [this step](#sharepoint-online).
- If you're using **Exchange Online** or **Exchange hybrid**, do [this step](#exchange-online).
- If you 're using **Skype for Business Online**, do [this stpe](#Skype-for-Business-Online)
- If you're using a third-party mobile device management (MDM) solution, do [this step](#mobile-device-management).
- If you're using **third-party services** or **line-of-business (LOB) apps** that are integrated with Office 365, do [this step](#line-of-business-apps).
- If you're also using **Dynamics 365**, do [this step](#dynamics365).
- If you're also using **Power BI**, do [this step](#power-bi).
- If you're also using **Azure services** with your Office 365 subscription, do [this step](#microsoft-azure).

## General tenant migration considerations

**Applies to:** All customers using Office 365 in the Microsoft Deutschland Cloud instance

Office 365 tenant and user identifiers are preserved during migration. Azure AD service calls are redirected from Microsoft Cloud Deutschland to Office 365 Global services and are transparent to Office 365 services.

- General Data Protection Regulation (GDPR) Data Subject Requests (DSRs) are executed from the Azure Admin portal for future requests. Any legacy or non-customer diagnostic data that is resident in Microsoft Cloud Deutschland is deleted at or before 30 days elapse.
- Multi-factor authentication (MFA) requests that use Microsoft Authenticator display as the user ObjectID (a GUID) while the tenant is copied to Office 365 services. MFA requests will perform as expected despite this display behavior.  Microsoft Authenticator accounts that were activated by using Office 365 services endpoints will display the user principal name (UPN).  Accounts added by using Microsoft Cloud Deutschland endpoints will display the user ObjectID but will work with both Microsoft Cloud Deutschland and Office 365 services endpoints.

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Prepare to notify users about restarting and signing in to and out of their clients after migration. | Office client licensing will transition from Microsoft Cloud Deutschland to Office 365 services in the migration. Clients pick up a new valid license after signing out of and in to Office clients. |	Users' Office products need to refresh licenses from Office 365 services. If licenses aren't refreshed, Office products may experience license validation errors. |
| Ensure network connectivity to [Office 365 services URLs and IP addresses](https://aka.ms/o365urls). | All clients and services hosted by the customer that are used to access Office 365 service must be able to access the Office 365 Global services endpoints. <br>In case you or your collaboration partners have firewall rules in place that would prevent accessing the URLs and IP addresses listed in [Office 365 services URLs and IP addresses](https://aka.ms/o365urls) must change the firewall rules to permit access to the Office 365 Global service endpoints| Failures of the service or client software can occur if this is not done before Phase 4  |
| Cancel any trial subscriptions. | Trial subscriptions will not be migrated and will block transfer of paid subscriptions. | Trial services are expired and non-functioning if accessed by users after cancellation. |
| Analyze differences in license features between Microsoft Cloud Deutschland and the Office 365 Global Services. | Office 365 services include additional features and services not available in the current Microsoft Cloud Deutschland. During subscription transfer, new features will be available to users. | <ul><li> Analyze the different features provided by the licenses for Microsoft Cloud Deutschland and Office 365 Global Services. Start with the [Office 365 platform Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Determine if any new features of Office 365 services should be initially disabled to limit effects on users or on user change management, and alter user license assignments as needed. </li><li>Prepare users and help desk staff for new services and features provided by Office 365 services. |
| Create organization-wide [retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention) to protect from inadvertent deletion of content during migration.  |<ul><li>To ensure that content isn't inadvertently deleted by end users during the migration, customers may choose to enable an organization-wide retention policy. </li><li>Although retention isn't required, since holds placed at anytime during the migration should work as expected, having a retention policy is a back-up safety mechanism. At the same time, a retention policy might not be used by all customers, especially those who are concerned about over preservation.</li></ul>| Apply retention policy as described in [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). Failures of the service or client software can occur if this is not done before Phase 4 of 9. </li></ul>|
|||||

## DNS

<!-- before phase 9 -->

**Applies to**: Customers who set a custom _msoid_ CNAME in their own DNS domain

If configured, the _msoid_ CNAME affects only customers using Office Desktop client (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

In case you have set a DNS CNAME called _msoid_ in one or many DNS namespaces that you own, you have to remove the CNAME until the end of phase 8 at the latest. You can remove the CNAME _msoid_ any time before the end of phase 8.

To verify if you have set a CNAME in your DNS namespace, follow the steps below and replace _contoso.com_ with your own domain name:

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

If the command line returns a DNS record, remove the _msoid_ CNAME from your domain.

## Active Directory Federation Services (AD FS)

<!-- before phase 4 -->

**Applies to**: Customers using AD FS on premises to authenticate users connecting to Microsoft Office 365<br>
**When applied**: Any time before phase 4 starts

Read and apply the [ADFS Migration steps](ms-cloud-germany-transition-add-adfs)

## SharePoint Online

<!-- before phase 4 -->

**Applies to**: Customers using SharePoint 2013 on-premises<br>
**When applied**: Any time before phase 4 starts

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Limit SharePoint 2013 workflows, use during the SharePoint Online migration. | Reduce SharePoint 2013 workflows and complete in-flight workflows before transitions. | Inaction may result in user confusion and help desk calls. |
||||

## Exchange Online

<!-- before phase 5 -->

**Applies to**: Exchange Online customers who have enabled sharing calendar and availability address space<br>
**When applied**: Any time before end of phase 9

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Notify external partners of the upcoming transition to Office 365 services. | Availability address space configurations allow sharing of free/busy information with Office 365. | Failure to do so may result in service or client failure at a later phase of customer migration. |
||||

### Exchange Online Hybrid configuration

**Applies to:** All customers using an active Exchange Hybrid Configuration with Exchange servers on-premises<br>
**When applied**: Any time before phase 5 starts

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Update to the latest version of the Hybrid Configuration Wizard (HCW) anytime before your tenant is entering migration stage 5. You may start this activity immediately after receiving the message center notification that your Office 365 tenant migration has begun (phase 1).<br>Your Exchange administrator must uninstall previous versions of the HCW, and then install and execute the latest version (17.0.5378.0 or higher) from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard). |<ul><li>The latest version of the HCW includes necessary updates to support the Exchange Online migration from the Microsoft Cloud Deutschland instance to Office 365 Global Services.</li><li> Updates include changes to on-premises certificate settings for the _Send connector_ and the _Receive connector_.</li><li>When executing the HCW before phase 5, select "Office 365 Germany" on the 2nd page of the HCW under _Office 365 Exchange Online_ in the listbox below  _My Office 365 organization is hosted by_</li><li>**NOTE**: Upon completion of your Office 365 tenant  migration after phase 9, you will remove and re-install the HCW again, this time using "Office 365 Worldwide" settings on the 2nd page of the HCW to complete your Hybrid setup with the Exchange Online global service.</li></ul>|Failure to run the HCW before Phase 5 (Exchange migration) may result in service or client failure. |
| Establish AuthServer on-premises pointing to global Security Token Service (STS) for authentication | This ensures that authentication requests for Exchange availability requests from users in migration state that target the hybrid on-premises environment are authenticated to access the on-premises service. Similarly, this will ensure authentication of requests from on-premises to Office 365 Global services endpoints. | After Azure AD migration (phase 2) is complete, the administrator of the on-premises Exchange (hybrid) topology must add a new authentication service endpoint for the Office 365 Global services. With this command from Exchange PowerShell, replace `<TenantID>` with your organization's tenant ID found in the Azure portal on Azure Active Directory.<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> Failing to complete this task may result in hybrid free-busy requests failing to provide information for mailbox users who have been migrated from Microsoft Cloud Deutschland to Office 365 services.  |
||||

## Skype for Business Online

<!-- before phase 7 -->

**Applies to**:  Skype For Business Online customers<br>
**When applied**: Any time before phase 7 starts

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Deploy Teams desktop client for users who access Skype for Business in Germany. | Migration moves Skype for Business users to Microsoft Teams for collaboration, calling, and chat. Either, deploy the Microsoft Teams desktop client or ensure that a supported browser is available. | Inaction will result in unavailability of Microsoft Teams collaboration services. |
| Review and prepare for migration-related DNS changes. | Customer-owned DNS zone changes for Skype for Business Online. |<ul><li>We recommend that you update the Time-to-Live (TTL) for any  customer-owned domain DNS records to 5 minutes to expedite the refreshing of DNS records. However, the Microsoft-managed cutover associated with this DNS change may occur anytime within the provided 24-hour change window. </li><li>Disruption of service is possible in the future. Users won't be able to log into Skype for Business and will be redirected to the migrated Teams experience in the Office 365 services. </li></ul>|
| Prepare End User and Administration training and readiness for the transition to Microsoft Teams. | Be successful in your transition from Skype to Teams by planning user communication and readiness. | <ul><li>Clients need to be aware of the new services and how to use once their services are transitioned to the Office 365 services. </li><li>After DNS changes are made for both the customer vanity domains and the initial domain, users would sign into Skype for Business and see that they now are migrated to Teams. This would also download the desktop client for Teams in the background. </li></ul>|
||||

## Mobile Device Management

<!-- before phase 5 -->
**Applys to:** Customers using a third-party mobile device management (MDM) solution<br>
**When applied**: Any time before phase 5 starts

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| Prepare end-user and administration training about users removing and re-adding their account to Microsoft Outlook for iOS and Android. | Microsoft Outlook for iOS and Android accounts configured with mailboxes in Microsoft Cloud Deutschland may have to be removed and added again to Outlook in order to properly synchronize the new Office 365 services configuration. | Microsoft Outlook for iOS and Android customers | Outlook mailboxes previously configured for Microsoft Cloud Deutschland may not pick up the new Office 365 Services configuration, leading to errors and degraded performance of other user experiences. IT admins are encouraged to provide documentation that proactively instructs users to remove and re-add their accounts to Microsoft Outlook for iOS and Android if issues with signing in or synchronizing mail occur after migration. |
| Determine if any reconfiguration is required after migration. | Mobile Device Management (MDM) solutions may target `outlook.de` endpoints. In this transition to Office 365 Services, client profiles should update to the Office 365 services URL, `outlook.office365.com`. | Exchange Online and MDM customers | Clients may continue to function while the `outlook.de` endpoint is accessible, but they'll fail if Microsoft Cloud Deutschland endpoints are no longer available. |
|||||

## Line-of-business apps

**Applies to:** Customers using line-of-business (LOB) apps with endpoints provided by Microsoft Cloud Deutschland<br>
**When applied**: After completion of phase 2 and before end of phase 9

If you're using a third-party service or line-of-business (LOB) apps that are integrated with Office 365, you must resolve any dependencies on endpoints provided by the Microsoft Cloud Deutschland instance. For example, if your LOB apps are connecting to `https://graph.microsoft.de/`, you must change the endpoint to `https://graph.microsoft.com/`. The endpoints of the Microsoft Office 365 Global service become available to your tenant after phase 2.

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Determine if any reconfiguration is required after migration. | Third-party services and applications that integrate with Office 365 may be coded to expect Microsoft Cloud Deutschland IP addresses and URLs. | Required action. Inaction may result in failures of the service or client software. |
||||

## Dynamics	365

**Applies to**: Customers using Microsoft Dynamics 365

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| For Dynamics 365 sandbox subscriptions, be sure to download the production environment of the Dynamics SQL instance from your Dynamics 365 subscription in Microsoft Cloud Deutschland. The latest production backup should be restored to the sandbox before sandbox migration. | Migration of Dynamics 365 requires customers to ensure that the Sandbox environment is refreshed with the latest production database. | The FastTrack team will assist customers in performing dry runs to validate the version upgrade from 8.x to 9.1.x. |
||||

## Power BI

**Applies to**: Customers using Power BI

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Removal of objects from Power BI subscriptions that won't be migrated from Power BI Microsoft Cloud Deutschland to Office 365 services. | Migration of Power BI services will require customer action to delete certain artifacts, such as datasets and dashboards. | <ul><li>Admins may have to remove the following items from their subscription: </li><li>Real-Time datasets (for example, streaming or push datasets) </li><li>Power BI on-premises Data Gateway configuration and data source </li></ul>|
||||

## Microsoft Azure

If you are using the same Azure Active Directory identity partition for Office 365 and Microsoft Azure in the Microsoft Cloud Deutschland instance, make sure that you are preparing for the customer driven migration of Microsoft Azure services.

> [!NOTE]
> The migration of your Microsoft Azure services must not be started before your Office 365 tenant has reached migration phase 3 and must be completed before migration phase 8 has been completed.

Customers who use Office 365 and Azure resources (for example, networking, compute, and storage) will perform the migration of resources to the Office 365 services instance. This migration is the customer's responsibility. Message Center posts will signal the start. Migration must be completed before finalization of the Azure AD organization in the Office 365 services environment. For Azure migrations, see the Azure migration playbook, [Overview of migration guidance for Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main).

| Step(s) | Description | Impact |
|:-------|:-------|:-------|
| Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main). |<ul><li>Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. </li><li> Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.</li></ul>|<ul><li>Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. </li><li> Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event. </li><li>Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss. </li><li> A Message center notification will signal the point at which customer-led migration can begin. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## More information

Getting started:

- [Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland Migration Assistance](https://aka.ms/germanymigrateassist)
- [How to opt-in for migration](ms-cloud-germany-migration-opt-in.md)
- [Customer experience during the migration](ms-cloud-germany-transition-experience.md)

Moving through the transition:

- [Migration phases actions and impacts](ms-cloud-germany-transition-phases.md)
- [Additional pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud apps:

- [Dynamics 365 migration program information](https://aka.ms/d365ceoptin)
- [Power BI migration program information](https://aka.ms/pbioptin)
- [Getting started with your Microsoft Teams upgrade](https://aka.ms/SkypeToTeams-Home)
