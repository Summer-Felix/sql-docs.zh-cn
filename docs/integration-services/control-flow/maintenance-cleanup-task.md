---
title: "“清除维护”任务 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.maintenancecleanuptask.f1"
helpviewer_keywords: 
  - "删除文件"
  - "删除文件"
  - "“清除维护”任务"
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
caps.latest.revision: 25
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 25
---
# “清除维护”任务
  “清除维护”任务将删除与维护计划相关的文件，包括维护计划所创建的数据库备份文件和报表。 有关详细信息，请参阅[维护计划](../../relational-databases/maintenance-plans/maintenance-plans.md)和 [SQL Server 数据库的备份和还原](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)。  
  
 通过使用“清除维护”任务，包可以删除在指定服务器上的备份文件或维护计划报表。 “清除维护”任务包括的一个选项可以删除特定文件或删除文件夹中的一组文件。 可以指定要删除的文件的扩展名（可选）。  
  
 当您配置清除维护任务以删除备份文件时，默认的文件扩展名为 BAK。 对于报表文件，默认文件扩展名为 TXT。 您可以根据需要更新扩展名，唯一的限制是扩展名的长度必须少于 256 个字符。  
  
 通常，需要删除不再需要的旧文件，并且可以将“清除维护”任务配置为删除已达到指定时限的文件。 例如，可以将任务配置为删除时限超过四周的文件。 可以使用日、周、月或年来指定要删除的文件的时限。 如果不指定要删除的文件的最小时限，则删除所有指定类型的文件。  
  
 与更早版本的“清除维护”任务相比，该任务的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本不自动删除指定目录的子目录中的文件。 此约束减少了可能利用“清除维护”任务的功能来恶意删除文件的任何攻击的可攻击面。 若要删除一级子文件夹，必须通过选中“清除维护任务”对话框的“包括一级子文件夹”选项来显式选择执行此操作。  
  
## “维护清除”任务的配置  
 可以通过 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器来设置属性。 此任务位于 **设计器中** “工具箱” **的** “维护计划中的任务” [!INCLUDE[ssIS](../../includes/ssis-md.md)] 部分。  
  
 有关可在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置的属性的详细信息，请单击以下主题：  
  
-   [“清除维护”任务（维护计划）](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## 相关任务  
 有关如何在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置这些属性的信息，请参阅[设置任务或容器的属性](../Topic/Set%20the%20Properties%20of%20a%20Task%20or%20Container.md)。  
  
## 另请参阅  
 [Integration Services 任务](../../integration-services/control-flow/integration-services-tasks.md)   
 [控制流](../../integration-services/control-flow/control-flow.md)  
  
  