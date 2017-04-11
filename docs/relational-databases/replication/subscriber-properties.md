---
title: "订阅服务器属性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.rep.configdistwizard.subscribers.f1"
helpviewer_keywords: 
  - "“订阅服务器属性”对话框"
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
caps.latest.revision: 22
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 22
---
# 订阅服务器属性
   **订阅服务器属性** 对话框中包含与订阅服务器上运行的版本相关的信息 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 之前 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]。  
  
## 选项  
 **到订阅服务器的代理连接**  
 分发代理和合并代理从分发服务器连接到订阅服务器时所处的上下文。此选项只适用于 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 以前的版本。  
  
 选择 **“模拟代理进程帐户”** ，可以使用分发服务器上 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理帐户的上下文连接到订阅服务器；也可以指定 **“SQL Server 身份验证”**，再输入 **“登录名”** 和 **“密码”**的值。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 建议您选择 **“模拟代理进程帐户”**。  
  
 对于 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 及更高版本，可以在新建订阅向导中为每个订阅指定连接信息，并可以在 **“订阅属性”** 对话框中更改连接信息。  
  
 **默认代理计划**  
 在新建订阅向导中用于运行的版本的订阅服务器的默认计划 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 之前 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]。  
  
 **杂项**  
 包含有关订阅服务器和订阅服务器类型的信息。  
  
## 另请参阅  
 [查看和修改分发服务器和发布服务器属性](../../relational-databases/replication/view-and-modify-distributor-and-publisher-properties.md)   
 [& #40; 属性引用复制和 #41;](../../relational-databases/replication/properties-reference-replication.md)   
 [订阅发布](../../relational-databases/replication/subscribe-to-publications.md)  
  
  