---
title: "子包的实现 | Microsoft Docs"
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
  - "子包"
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
caps.latest.revision: 40
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 40
---
# 子包的实现
  使用 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]来实现负载平衡时，子包将安装在其他服务器上，以利用可用的 CPU 或服务器时间。 若要创建和运行子包，需要执行以下步骤：  
  
-   设计子包。  
  
-   将包移动到远程服务器。  
  
-   在包含运行子包步骤的远程服务器上创建 SQL Server 代理作业。  
  
-   测试并调试 SQL Server 代理作业和子包。  
  
 设计子包时，包的设计不受限制，并且可以添加任何希望的功能。 但是，如果包要访问数据，则必须确保运行包的服务器能够访问该数据。  
  
 若要标识执行子包的父包，请在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 的“解决方案资源管理器”中右键单击该包，然后单击“入口点包”。  
  
 设计完子包之后，下一个步骤是将它们部署在远程服务器上。  
  
## 将子包移动到远程实例  
 将包移动到其他服务器的方式有多个。 两个推荐的方法是：  
  
-   通过使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]将包导出。  
  
-   先为包含要部署的包的项目生成部署实用工具，然后运行包安装向导将包安装到文件系统或 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]实例，从而达到部署包的目的。 有关详细信息，请参阅[早期包部署 (SSIS)](../../integration-services/packages/legacy-package-deployment-ssis.md)。  
  
 必须重复部署到希望使用的每个远程服务器。  
  
## 创建 SQL Server 代理作业  
 子包已经部署到多个服务器之后，请在包含子包的每个服务器上创建 SQL Server 代理作业。 SQL Server 代理作业包含调用作业代理时运行子包的步骤。 SQL Server 代理作业不是已调度作业；它们只在父包调用它们时才会运行子包。 返回到父包的作业成功或失败的通知反映 SQL Server 代理作业成功或失败，以及是否成功调用了代理作业，而不是反映子包的成功或失败或它是否已执行。  
  
## 调试 SQL Server 代理作业和子包  
 通过使用下列方法之一，可以测试 SQL Server 代理作业及其子包：  
  
-   通过单击“调试”/“开始执行(不调试)”在 SSIS 设计器中运行每个子包。  
  
-   通过使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]在远程计算机上运行单个 SQL Server 代理作业，以确保包运行。  
  
 有关如何对从 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理作业运行的包进行故障排除的信息，请参阅 [支持知识库中的](http://support.microsoft.com/kb/918760) An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step [!INCLUDE[msCoName](../../includes/msconame-md.md)] （从 SQL Server 代理作业步骤调用 SSIS 包时 SSIS 包不运行）。  
  
 SQL Server 代理检查代理的子系统访问权，并在每次运行作业步骤时将访问权授予代理。  
  
 可以在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中创建代理。  
  
## 相关任务  
  
-   [使用 SQL Server Management Studio 在 SSIS 服务器上运行包](../../integration-services/packages/run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  