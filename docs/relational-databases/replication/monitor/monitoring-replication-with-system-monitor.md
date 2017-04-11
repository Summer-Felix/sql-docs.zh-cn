---
title: "使用系统监视器监视复制 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "监视性能 [SQL Server 复制], 系统监视器"
  - "系统监视器 [SQL Server], 复制"
  - "性能计数器 [SQL Server 复制]"
ms.assetid: 8cd3a270-0328-4bfd-bf23-b1d759cc120c
caps.latest.revision: 30
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 30
---
# 使用系统监视器监视复制
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 系统监视器可以使用图形、 图表和报告来衡量您的计算机的效率和识别和解决可能出现的问题 （如资源使用不平衡、 硬件不足或程序设计），并规划其他硬件需求。 有关详细信息，请参阅 [监视资源使用情况和 #40;系统监视器 & #41;](../../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)。  
  
 系统监视器使用性能对象和计数器，它们提供各种进程的性能信息。 您可以通过与复制代理相关联的计数器来测量复制的性能：  
  
|代理|性能对象|计数器|说明|  
|-----------|------------------------|-------------|-----------------|  
|所有代理|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Agents|正在运行|当前正在运行的复制代理数。|  
|快照代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Snapshot|Snapshot: Delivered Cmds/sec|每秒传递到分发服务器的命令数。|  
|快照代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Snapshot|Snapshot: Delivered Trans/sec|每秒传递到分发服务器的事务数。|  
|日志读取器代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Logreader|Logreader: Delivered Cmds/sec|每秒传递到分发服务器的命令数。|  
|日志读取器代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Logreader|Logreader: Delivered Trans/sec|每秒传递到分发服务器的事务数。|  
|日志读取器代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Logreader|Logreader: Delivery Latency|从事务应用于发布服务器起，到传递给分发服务器为止所经过的时间（以毫秒为单位）。|  
|分发代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Dist.|Dist: Delivered Cmds/sec|每秒传递到订阅服务器的命令数。|  
|分发代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Dist.|Dist: Delivered Trans/sec|每秒传递到订阅服务器的事务数。|  
|分发代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Dist.|Dist: Delivery Latency|从事务传递给分发服务器起，到应用于订阅服务器为止所经过的时间（以毫秒为单位）。|  
|合并代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Merge|Conflicts/sec|在合并过程中每秒出现的冲突数。|  
|合并代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Merge|Downloaded Changes/sec|每秒从发布服务器复制到订阅服务器的行数。|  
|合并代理|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: Replication Merge|Uploaded Changes/sec|每秒从订阅服务器复制到发布服务器的行数。|  
  
## 另请参阅  
 [监视和 #40;复制和 #41;](../../../relational-databases/replication/monitor/monitoring-replication.md)  
  
  