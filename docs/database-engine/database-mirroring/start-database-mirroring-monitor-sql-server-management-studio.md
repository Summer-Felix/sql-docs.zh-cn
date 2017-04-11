---
title: "启动数据库镜像监视器 (SQL Server Management Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "监视数据库镜像 [SQL Server]"
  - "数据库镜像监视器 [SQL Server], 启动"
  - "数据库镜像 [SQL Server], 监视"
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
caps.latest.revision: 20
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 20
---
# 启动数据库镜像监视器 (SQL Server Management Studio)
  数据库镜像监视器是通过 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 启动的 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]监视器的一部分。  
  
> [!NOTE]  
>  不是在 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 有关 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 各版本支持的功能列表，请参阅 [SQL Server 2016 各个版本支持的功能](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md)。  
  
### 启动数据库镜像监视器  
  
1.  连接到主体服务器实例之后，在对象资源管理器中，单击服务器名称以展开服务器树。  
  
2.  展开 **“数据库”**，再选择要监视的数据库。  
  
3.  右键单击数据库，选择“任务”，再单击“启动数据库镜像监视器”。  
  
4.  在 **“数据库镜像监视器”** 对话框中，单击 **“注册镜像数据库”** 以注册一个或多个镜像数据库。  
  
    > [!NOTE]  
    >  在一个伙伴上注册数据库时，会自动在另一个伙伴上注册此数据库。 如果监视器已具有另一个伙伴实例的连接凭据，则可以使用这些凭据进行连接。 否则，监视器尝试使用 Windows 身份验证进行连接。 如果要更改用于连接到任一服务器实例的凭据，则单击 **“当单击‘确定’后，显示‘管理服务器连接’对话框”**。  
  
 有关数据库镜像监视器的详细信息，请参阅[数据库镜像监视器概述](../../database-engine/database-mirroring/database-mirroring-monitor-overview.md)。  
  
## 另请参阅  
 [数据库镜像 (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [使用 Windows 身份验证建立数据库镜像会话 (SQL Server Management Studio)](../../database-engine/database-mirroring/establish database mirroring session - windows authentication.md)  
  
  