---
title: "Microsoft 365 admin center Teams usage activity reports"
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: "Learn how to get the Microsoft Teams usage activity report and gain insights into the Teams activity in your organization."
---

# Microsoft 365 Reports in the admin center - Microsoft Teams usage activity

The Microsoft 365 Reports dashboard shows you the activity overview across the products in your organization. It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product. Check out [the Reports overview topic](activity-reports.md). <br/>

The brand-new **Teams usage report** gives you an overview of the usage activity in Teams, including the number of active users, channels and messages so you can quickly see how many users across your organization are using Teams to communicate and collaborate.  It also includes other Teams specific activities, such as the number of active guests, meetings, and messages. 

<br/>![Microsoft 365 reports - Microsoft Teams activity report.](../../media/teams-usage.png)


## How to get to the Microsoft Teams usage activity report

1. In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.
2. From the dashboard homepage, click on the **View more** button on the **Microsoft Teams activity** card.<br/>
<br/>![Microsoft 365 reports - Microsoft Teams activity card.](../../media/teams-usage-card.png)

## Interpret the Microsoft Teams usage activity report

You can view the user activity in the Teams report by choosing the **Teams Usage** tab. This will display the following charts:

- Channel usage: Tracks the number of channel uses, by activity type, over time.
  <br/> ![Teams usage activity report - channel usage.](../../media/teams-usage-channel.png)<br/>

- Team usage: Tracks the number of teams, by type and activity, over time.
  <br/> ![Teams usage activity report - team usage.](../../media/teams-usage-usage.png)<br/>

Additionally, a table shows usage details for individual teams, such as last activity date, active users, active channels, and other data.

<br/>![Microsoft 365 reports - Microsoft Teams usage activity table.](../../media/teams-usage-table.png)

In the table, select **Choose columns** to add or remove columns from the report. <br/>  <br/> 
![Teams usage activity report - choose columns.](../../media/teams-usage-columns.png)

You can also export the report data into an Excel .csv file by selecting the **Export** link. This exports data of all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data. The exported format for **audio time**, **video time**, and **screen share time** follows ISO8601 duration format.

The **Microsoft Teams usage activity** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you select a particular day in the report, the table will show data for up to 28 days from the current date (not the date the report was generated).

To ensure data quality, we perform daily data validation checks for the past three days and will be filling any gaps detected. You may notice differences in historical data during the process.

> [!Important]
> Data for a given day will show up within 48 hours. For example, data for January 10th should show up in the report by January 12th.


### Channel usage metrics

The Channel usage chart shows data on the following metrics.

|Item|Description|
|:-----|:-----|
|**Metric**|**Definition**|
|Active channel users  <br/> |This is the total of internal active users, active guests, and external active users.  <br/><br/> **Internal active users** - Users that have at least one panel action in the specified time period. This excludes guests.   <br/> **Active guests** - Guests that have at least one panel action in the specified time period. A guest is a person from outside your organization who accesses shared resources by signing in to a guest account in my directory.  <br/> **External active user** - External users that have at least one panel action in the specified time period. An external user is a person from outside your organization who is participating in a resource – such as a shared channel – using their own identity and not a guest account in your directory.  <br/>|  
|Active channels   <br/> |Valid channels in active teams that have at least one active user in the specified time period. This includes public, private, or shared channels.   <br/> |
|Channel messages    <br/> |The number of unique messages that the user posted in a private chat during the specified time period.  <br/> |
|||

### Team usage metrics

The Teams usage chart shows data on the following metrics.

|Item|Description|
|:-----|:-----|
|**Metric**|**Definition**|
|Team ID  <br/> |Team GUID <br/>|  
|Internal active users   <br/> |Users that have at least one panel action in the specified time period including guests. <br/> <br/> Internal users and guests that reside in the same tenant. Internal users exclude guests.   |
|Active guests     <br/> |Guests that have at least one panel action in the specified time period. <br/> <br/> A guest is defined as persons from outside your organization who accesses shared resources by signing in to a guest account in my directory.   |
|External active users   <br/> |External users that have at least one panel action in the specified time period.<br/><br/> An external user is defined as a person from outside your organization who is participating in a resource – such as a shared channel – using their own identity and not a guest account in your directory.   |  
|Active channels    <br/> |Valid channels in active teams that have at least one active user in the specified time period. This includes public, private, or shared channels. <br/>  |
|Active shared channels      <br/> |Valid shared channels in active teams that have at least one active user in the specified time. <br/> <br/>A shared channel is defined as a Teams channel that can be shared with people outside the team. These people can be inside your organization or from other Azure AD organizations.   |
|Total organized meetings   <br/> |The sum of one-time scheduled, recurring, ad hoc and unclassified meetings a user organized during the specified time period.  <br/>|  
|Posts    <br/> |Count of all the post messages in channels in the specified time period.  |
|Replies     <br/> |Count of all the reply messages in channels in the specified time period.  |
|Mentions  <br/> |Count of all mentions made in the specified time period. <br/>|  
|Reactions    <br/> |Number of reactions an active user made in the specified time period. |
|Urgent messages      <br/> |Count of urgent messages in the specified time period.  |
|Channel messages   <br/> |The number of unique messages that the user posted in a team chat during the specified time period. <br/>|  
|Last activity date    <br/> |The latest date that any member of the team has committed an action. |
|||


### Teams details

Data for following metrics are available for individual teams.

 |Item|Description|
|:-----|:-----|
|**Metric**|**Definition**|
|Posts    <br/> |Count of all the post messages in channels in the specified time period.  |
|Replies     <br/> |Count of all the reply messages in channels in the specified time period.  |
|Urgent messages      <br/> |Count of urgent messages in the specified time period.  |
|Tenant name      <br/> |Tenant name of this user’s origin.   |
|Host tenant name      <br/> |Tenant names of this user all involved shared channel origin.   |
|||










