---
title: "维护计划（服务器） | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.maint.servers.f1"
  - "sql13.swb.maint.maintplanproperties.server.f1"
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# 维护计划（服务器）
  使用 **“服务器”** 对话框可以选择要在其上运行维护计划的服务器。  
  
 必须配置包含一台主服务器和一台或多台目标服务器的多服务器环境，才能创建多服务器维护计划。 在多服务器维护计划中，应将本地服务器配置为主服务器。 在多服务器环境中，此对话框显示 **(local)** 主服务器和所有相应的目标服务器。 将为本地服务器创建一个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理作业。 此功能是处于启用还是禁用状态，取决于你是否选择了 **(local)** 服务器。 如果选择了目标服务器，将创建一个多服务器作业，并且该作业将下载到每个选定的目标服务器上。 如果未选择任何目标服务器，则会删除该多服务器作业。  
  
## 另请参阅  
 [维护计划](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [创建多服务器环境](../../ssms/agent/create-a-multiserver-environment.md)   
 [设置主服务器](../../ssms/agent/make-a-master-server.md)   
 [设置目标服务器](../../ssms/agent/make-a-target-server.md)  
  
  