---
title: "SQL Server 复制中不推荐使用的功能 | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "不推荐使用的功能 [SQL Server 复制]"
ms.assetid: 46bd3edd-d6de-40a6-a015-21cce8321feb
caps.latest.revision: 67
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 67
---
# SQL Server 复制中不推荐使用的功能
  本主题介绍 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]中仍然可用但不推荐使用的复制功能。 按照计划， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]未来版本将不再具有这些功能。 在新的应用程序中不应使用这些不推荐使用的功能。  
  
## 中不推荐使用的项 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]  
  
|功能|说明|  
|-------------|-----------------|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|如果每个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 端点都处于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]的当前版本的两个主版本内，则支持复制。 因此， [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 不支持面向或源自 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 或 [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]的复制。|  
|[!INCLUDE[ssEW](../../includes/ssew-md.md)]|如果每个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 端点都处于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]的当前版本的两个主版本内，则支持复制。 因此， [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 不支持面向或源自 [!INCLUDE[ssEW](../../includes/ssew-md.md)]的复制。|  
  
## 另请参阅  
 [复制的向后兼容性](../../relational-databases/replication/replication-backward-compatibility.md)  
  
  