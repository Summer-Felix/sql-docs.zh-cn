---
title: "“锁定事件”类别 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 06427f8e-89bb-4710-a0c1-dc5e42b7e95e
caps.latest.revision: 6
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 6
---
# “锁定事件”类别
  “锁定事件”事件类别具有下表中说明的各事件类。  
  
|Event Class|事件 ID|Description|  
|-----------------|--------------|-----------------|  
|死锁|50|收集跟踪开始后的所有元数据锁死锁事件。|  
|锁超时|51|收集跟踪开始后的所有元数据锁超时事件。|  
|已获取锁|52|收集自开始跟踪后与已获取的锁有关的信息。|  
|已释放锁|53|收集自开始跟踪后与已释放的锁有关的信息。|  
|正在等待的锁|54|收集自开始跟踪后与处于等待状态的锁有关的信息。|  
  
 有关与每个锁事件类关联的列的信息，请参阅 [Lock Events Data Columns](../../analysis-services/trace-events/lock-events-data-columns.md)。  
  
## 另请参阅  
 [Analysis Services 跟踪事件](../../analysis-services/trace-events/analysis-services-trace-events.md)  
  
  