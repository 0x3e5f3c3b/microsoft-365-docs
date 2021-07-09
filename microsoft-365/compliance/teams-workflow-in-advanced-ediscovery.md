---
title: "Teams workflow in Advanced eDiscovery"
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: 
- MET150
ms.collection: M365-security-compliance
description: "Learn how to preserve, collect, review, and export content from Microsoft Teams in Advanced eDiscovery."
---

# Advanced eDiscovery workflow for content in Microsoft Teams

This article provides a comprehensive set of procedures, guidelines, and best practices for using Advanced eDiscovery to preserve, collect, review, and export content from Microsoft Teams. The goal of this article is to help you optimize your eDiscovery workflow for Teams content.

There are four categories of Teams content that you can collect and process using Advanced eDiscovery:

- **Teams 1:1 chats**. Chat messages, posts, and attachments shared in a Teams conversation between two people.  Teams 1:1 chats are also called *conversations*.

- **Teams group chats**. Chat messages, posts, and attachments shared in a Teams conversation between three or more people. Also called *1:N* chats or *group conversations*.

- **Teams channels**. Chat messages, posts, replies, and attachments shared in a Teams channel.

- **Private Teams channels**. Message posts, replies, and attachments shared in a private Teams channel.

## Where Teams content is stored

A prerequisite to managing Teams content in Advanced eDiscovery is to understand the type Teams content that you can collect, process and review in Advanced eDiscovery and where that content is stored in Microsoft 365. The following table lists Teams content type and where each are stored.

||Location of chat messages and posts  |Location of files and attachments |
|:---------|:---------|:---------|
|Teams 1:1 chats     |Messages in 1:1 chats are stored in the Exchange Online mailbox of all chat participants. |Files shared in a 1:1 chat are stored in the OneDrive for Business account of the person who shared the file. |
|Teams group chats     |Messages in group chats are stored in the Exchange Online mailbox of all chat participants. |Files shared in group chats chat are stored in the OneDrive for Business account of the person who shared the file. |
|Teams channels     |All channel messages and posts are stored in the Exchange Online mailbox associated with the team.|Files shared in a channel are stored in the SharePoint Online site associated with the team.           |
|Private Teams channels     |Messages sent in a private channel are stored in the Exchange Online mailboxes of all members of the private channel.|Files shared in a private Channel are stored in a dedicated SharePoint Online site associated with the private channel.|
||||

## Create a case for Teams content

The first step to managing Teams content in Advanced eDiscovery is to create a case using the large case format that's optimized for managing Teams content. Here's the benefits of using the large case format for Teams content:

- Conversation threading, in which additional messages in the same conversation that include responsive items are are automatically collected and added to review sets.

- Teams chat conversations (that include the original post and all replies) are automatically added to review sets as an HTML transcript file.

- Collections up to 1 TB can be added to reviews sets, which enables you to collect and amounts large amounts of Teams content in a case.

To 

## Add Teams data sources and preserve Teams content  

## Collect Teams content 

## Review Teams content 



Understand grouping, threading, and extraction behavior for Teams messages to optimize review of Teams content.  

 

### Grouping 

After Teams content is collected into a review set, Team chat messages are grouped by family or by conversation.  

Transcript  


| Teams content type|Group by family  |Group by conversation  |
|:---------|:---------|:---------|
|Teams 1:1 and group chats   | A transcript and its attachments/extracted items will share the same FamilyId        |ll transcripts and their family items within the same conversation/thread would share the same ConversationId. For Teams 1-1 chat, transcripts of different time windows, but same conversation thread would be grouped together.           |
|Teams channel and private channels    | A transcript and its attachments/extracted items will share the same FamilyId. Each post and all its replies would be its own transcript.        |Each post has its unique conversationId. If there are recent replies for a post that weren’t collected initially, these replies will continue to be grouped via ConversationId with the originally collect post.           |
||||


### Conversation threading

Transcript HTML Threading 

- **Teams 1:1 chats and group chats**. All messages that were posted within a 24-hour time window are grouped in a single transcript.  

- **Teams channel messages and private channel messages**. Each post and all its corresponding replies are grouped in a single transcript.



## Export Teams content 