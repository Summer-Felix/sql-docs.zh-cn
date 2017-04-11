---
title: "数据库邮件外部程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "外部程序 [数据库邮件]"
  - "DatabaseMail90.exe"
  - "数据库邮件 [SQL Server], 外部程序"
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
caps.latest.revision: 40
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 40
---
# 数据库邮件外部程序
  数据库邮件外部可执行程序是 **DatabaseMail.exe**，该程序位于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装的 **MSSQL\Binn directory** 目录中。 当有电子邮件要处理时，数据库邮件使用 Service Broker 激活来启动该外部程序。 数据库邮件启动该外部程序的一个实例。 该外部程序在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]的服务帐户的安全上下文中运行。  
  
 **本主题内容：**  
  
-   [数据库邮件外部程序概念](#ComponentsAndConcepts)  
  
-   [与配置数据库邮件外部程序相关的任务](#RelatedTasks)  
  
##  <a name="ComponentsAndConcepts"></a> 数据库邮件外部程序概念  
 该外部程序启动后，使用 Windows 身份验证连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 并开始处理电子邮件。 如果达到指定的超时期限时没有邮件要发送，该程序将退出。 可以使用数据库邮件配置向导或数据库邮件存储过程配置该程序退出前等待的时间。 有关详细信息，请参阅 [sysmail_configure_sp (Transact SQL)](../../relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql.md)。  
  
 外部程序将信息存储在 **msdb** 数据库的系统表中。 如果该外部程序无法与 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]通信，就将错误记录在 Microsoft Windows 应用程序事件日志中。 如果在 **数据库邮件配置向导** 的 **“配置系统参数”** 对话框中将日志记录级别设置为 **“详细”**，则还会记录其他消息。  
  
 请注意，为了提高效率，该外部程序会缓存帐户和配置文件信息。 因此，对帐户和配置文件所做的配置更改在几分钟内可能不会反映在该外部程序中。  
  
##  <a name="RelatedTasks"></a> 与配置数据库邮件外部程序相关的任务  
  
|配置任务|主题链接|  
|------------------------|----------------|  
|指定外部程序在退出前的时间。|[sysmail_configure_sp (Transact-SQL)](../../relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql.md)|  
  
## 另请参阅  
 [SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md)   
 [数据库邮件日志和审核](../../relational-databases/database-mail/database-mail-log-and-audits.md)   
 [数据库邮件](../../relational-databases/database-mail/database-mail.md)  
  
  