---
title: "订阅，分发服务器到订阅服务器的历史记录（快照订阅） | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.rep.monitor.subscription.pubtodist.snapshot.f1"
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
caps.latest.revision: 20
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 20
---
# 订阅，分发服务器到订阅服务器的历史记录（快照订阅）
  **“分发服务器到订阅服务器的历史记录”** 选项卡显示有关分发代理的详细信息，包括状态、历史记录、信息性消息和所有错误消息。  
  
## 选项  
 从 **“视图”** 菜单中选择要查看哪些分发代理会话，然后在标记为 **“分发代理的会话”**的网格中选择特定的会话。 有关此会话的详细信息显示在标记为 **“所选会话中的操作”**的网格中。 如果所选会话由于出错而结束，则还将显示一个标记为 **“所选会话的错误详细信息或消息”** 的文本区域。  
  
 **视图**  
 选择要查看哪些分发代理会话。  
  
 **状态**  
 分发代理的状态。 下面列出了可能的状态值：  
  
-   错误  
  
-   已完成  
  
-   正在重试  
  
-   正在运行  
  
 **Start Time**  
 会话的开始时间。  
  
 **结束时间**  
 会话的结束时间。 如果代理尚未停止，此字段为空。  
  
 **Duration**  
 分发代理已在此会话中运行的时间。 如果代理当前正在运行，该时间表示已用时间；如果代理会话已经结束，则该时间表示会话的总时间。  
  
 **错误消息**  
 如果会话由于出错而结束，此字段将显示分发代理记录的上一条错误消息。 如果某会话未因出错而结束，此字段为空白。  
  
 **操作消息**  
 分发代理在所选会话过程中记录的所有信息性消息和错误消息。  
  
 **操作时间**  
 操作中描述的时间 **操作消息** 列已执行。  
  
 **所选会话的错误详细信息或消息**  
 仅当所选的会话显示的值时，才显示 **错误** 中 **状态** 列。 此文本区域显示详细错误信息以及出错时尝试执行的命令。 另外，还包括指向与该错误相关的其他内容的链接。  
  
## 另请参阅  
 [启动复制监视器](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [查看信息并执行与订阅 & #40; 关联的代理任务复制监视器 & #41;](../../relational-databases/replication/monitor/view information and perform tasks for subscription agents.md)   
 [监视复制](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [复制代理概述](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  