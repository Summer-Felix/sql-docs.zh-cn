---
title: "SMO 连接管理器 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "连接 [Integration Services], SMO"
  - "SMO 连接管理器"
  - "连接管理器 [Integration Services], SMO"
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
caps.latest.revision: 21
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 21
---
# SMO 连接管理器
  SMO 连接管理器使得包能够连接到 SQL 管理对象 (SMO) 服务器。  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 包括的传输任务使用 SMO 连接管理器。 例如，传输 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名的传输登录任务使用 SMO 连接管理器。  
  
 将 SMO 连接管理器添加到包时，[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 会创建将在运行时决定 SMO 连接的连接管理器，设置该连接管理器的属性，并将该连接管理器添加到包上的“连接”集合。 该连接管理器的 **ConnectionManagerType** 属性设置为 **SMOServer**。  
  
 可以按下列方式配置 SMO 连接管理器：  
  
-   指定安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的服务器的名称。  
  
-   为连接到服务器选择身份验证模式。  
  
## SMO 连接管理器的配置  
 可以通过 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器或以编程方式来设置属性。  
  
 有关可以在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置的属性的详细信息，请参阅 [SMO 连接管理器编辑器](../../integration-services/connection-manager/smo-connection-manager-editor.md)。  
  
 有关以编程方式配置连接管理器的信息，请参阅 <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> 和[以编程方式添加连接](../../integration-services/building-packages-programmatically/adding-connections-programmatically.md)。  
  
## 另请参阅  
 [Integration Services (SSIS) 连接](../../integration-services/connection-manager/integration-services-ssis-connections.md)  
  
  