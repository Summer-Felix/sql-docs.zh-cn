---
title: "可用性数据库的数据同步状态不正常 | Microsoft Docs"
ms.custom: ""
ms.date: "05/17/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.agdashboard.arp3datasynchealthy.issues.f1"
helpviewer_keywords: 
  - "可用性组 [SQL Server], 策略"
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
caps.latest.revision: 15
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "erikre"
caps.handback.revision: 15
---
# 可用性数据库的数据同步状态不正常
    
## 简介  
  
|||  
|-|-|  
|**策略名称**|可用性数据库数据同步状态|  
|**问题**|可用性数据库的数据同步状态不正常。|  
|**类别**|**警告**|  
|**方面**|可用性数据库|  
  
## 说明  
 此策略汇总可用性副本中所有可用性数据库（也称为“数据库副本”）的数据同步状态。 当有数据库副本不处于要求的数据同步状态时，此策略处于不正常状态。 否则，该策略处于正常状态。  
  
> [!NOTE]  
>  对于此版本的 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]，与可能原因和解决方法有关的信息位于 TechNet Wiki 上的[一些可用性数据库的数据同步状态不正常](http://go.microsoft.com/fwlink/p/?LinkId=220858)中。  
  
## 可能的原因  
 此可用性数据库的数据同步状态不正常。 在异步-提交可用性副本上，每个可用性数据库都应该处于“正在同步”状态。 在同步提交副本上，每个可用性数据库必须处于 SYNCHRONIZED 状态。  
  
## 可能的解决方法  
 使用数据库副本策略查找具有不正常数据同步状态的数据库副本，然后解决该数据库副本上的问题。  
  
## 另请参阅  
 [AlwaysOn 可用性组概述 (SQL Server)](../Topic/Overview%20of%20Always On%20Availability%20Groups%20\(SQL%20Server\).md)   
 [使用 AlwaysOn 面板 (SQL Server Management Studio)](../Topic/Use%20the%20Always On%20Dashboard%20\(SQL%20Server%20Management%20Studio\).md)  
  
  