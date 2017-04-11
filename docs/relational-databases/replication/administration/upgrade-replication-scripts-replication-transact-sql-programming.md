---
title: "升级复制脚本（复制 Transact-SQL 编程） | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "脚本 [SQL Server 复制], 升级"
  - "升级 SQL Server, 复制数据库"
  - "升级复制应用程序"
  - "复制 [SQL Server], 脚本编写"
  - "复制 [SQL Server], 升级"
  - "升级复制数据库"
ms.assetid: 0b8720bd-f339-4842-bc8f-b35a46f6d3ee
caps.latest.revision: 41
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 41
---
# 升级复制脚本（复制 Transact-SQL 编程）
  [!INCLUDE[tsql](../../../includes/tsql-md.md)] 脚本文件可用于以编程方式配置复制拓扑。 有关详细信息，请参阅 [复制系统存储过程概念](../../../relational-databases/replication/concepts/replication-system-stored-procedures-concepts.md)。  
  
> [!IMPORTANT]  
>  虽然不需要升级由 **sysadmin** 角色的成员执行的脚本，我们仍建议您按照本主题中的说明修改现有脚本。 按照 [Replication Agent Security Model](../../../relational-databases/replication/security/replication-agent-security-model.md)主题的“代理所需权限”部分的说明为每个复制代理指定一个具有最低权限的帐户。  
  
 这些安全改进允许您显式指定用于执行复制代理作业的 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 帐户，从而可对权限进行更多控制，这些安全改进会影响现有脚本中的以下存储过程：  
  
-   **sp_addpublication_snapshot**:  
  
     现在应提供 Windows 凭据作为 **@job_login** 和 **@job_password** 在执行时 [sp_addpublication_snapshot & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md) 若要创建快照代理在分发服务器在其下运行的作业。  
  
-   **sp_addpushsubscription_agent**:  
  
     现在应执行 [sp_addpushsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql.md) 若要显式添加作业，并提供 Windows 凭据 (**@job_login** 和 **@job_password**) 用于运行分发代理作业在分发服务器。 在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之前的 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]版本中，当创建推送订阅时会自动执行此操作。  
  
-   **sp_addmergepushsubscription_agent**:  
  
     现在应执行 [sp_addmergepushsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql.md) 若要显式添加作业，并提供 Windows 凭据 (**@job_login** 和 **@job_password**) 用于运行合并代理作业在分发服务器。 在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之前的 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]版本中，当创建推送订阅时会自动执行此操作。  
  
-   **sp_addpullsubscription_agent**:  
  
     现在应提供 Windows 凭据作为 **@job_login** 和 **@job_password** 在执行时 [sp_addpullsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql.md) 若要创建用于分发代理在订阅服务器上运行的作业。  
  
-   **sp_addmergepullsubscription_agent**:  
  
     现在应提供 Windows 凭据作为 **@job_login** 和 **@job_password** 在执行时 [sp_addmergepullsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql.md) 若要创建在其下运行合并代理在订阅服务器上的作业。  
  
-   **sp_addlogreader_agent**:  
  
     现在应执行 [sp_addlogreader_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql.md) 若要手动添加作业，并提供日志读取器代理在分发服务器在其下运行的 Windows 凭据。 在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之前的 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]版本中，当创建事务发布时会自动执行此操作。  
  
-   **sp_addqreader_agent**:  
  
     现在应执行 [sp_addqreader_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql.md) 若要手动添加作业，并提供队列读取器代理在分发服务器在其下运行的 Windows 凭据。 在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之前的 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]版本中，当创建支持排队更新的事务发布时会自动执行此操作。  
  
 在安全模型中引入 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], ，复制代理程序始终对计算机进行连接的本地实例 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 使用 Windows 身份验证使用在提供的凭据 **@job_name** 和 **@job_password**。 有关运行复制代理作业时所使用的 Windows 帐户的要求，请参阅 [Replication Agent Security Model](../../../relational-databases/replication/security/replication-agent-security-model.md)。  
  
> [!IMPORTANT]  
>  如果可能，请在运行时提示用户输入安全凭据。 如果将凭据保存在脚本文件中，请确保该文件本身受到安全保护。  
  
### 升级用于配置快照发布或事务发布的脚本  
  
1.  在现有的脚本中之前, [sp_addpublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md), ，执行 [sp_addlogreader_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql.md) 在发布数据库上的发布服务器。 指定在其下的日志读取器代理运行的 Windows 凭据 **@job_name** 和 **@job_password**。 如果代理将使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 身份验证连接到发布服务器时，您还必须指定的值为 **0** 为 **@publisher_security_mode** 和 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 登录信息 **@publisher_login** 和 **@publisher_password**。 这样，便为发布数据库创建了一个日志读取器代理作业。  
  
    > [!NOTE]  
    >  此步骤仅针对事务发布，无需对快照发布执行该步骤。  
  
2.  （可选）之前 [sp_addpublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md), ，执行 [sp_addqreader_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql.md) 在分发数据库上分发服务器上。 指定在其下运行的队列读取器代理的 Windows 凭据 **@job_name** 和 **@job_password**。 这样，便为分发服务器创建了一个队列读取器代理作业。  
  
    > [!NOTE]  
    >  仅需要对支持排队更新订阅服务器的事务发布执行此步骤。  
  
3.  （可选）更新的执行 [sp_addpublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md) 若要设置实现新复制功能的参数的任何非默认值。  
  
4.  之后 [sp_addpublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md), ，执行 [sp_addpublication_snapshot & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md) 在发布数据库上的发布服务器。 指定 **@publication** 和在其下的快照代理运行的 Windows 凭据 **@job_name** 和 **@job_password**。 如果代理将使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 身份验证连接到发布服务器时，您还必须指定的值为 **0** 为 **@publisher_security_mode** 和 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 登录信息 **@publisher_login** 和 **@publisher_password**。 此操作将为发布创建一个快照代理作业。  
  
5.  （可选）更新的执行 [sp_addarticle & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addarticle-transact-sql.md) 若要设置实现新复制功能的参数的任何非默认值。  
  
### 升级向快照发布或事务发布添加订阅的脚本  
  
1.  在执行用于创建订阅的存储过程之后，请确保执行用于创建分发代理作业的存储过程以同步订阅。 所用的存储过程将取决于订阅类型。  
  
    -   对于请求订阅，更新的执行 [sp_addpullsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql.md) 提供在其下运行分发代理在订阅服务器的 Windows 凭据 **@job_name** 和 **@job_password**。 这是执行后 [sp_addpullsubscription](../../../relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql.md)。 有关详细信息，请参阅 [Create a Pull Subscription](../../../relational-databases/replication/create-a-pull-subscription.md)。  
  
    -   对于推送订阅，执行 [sp_addpushsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql.md) 在发布服务器上。 指定 **@subscriber**, ，**@subscriber_db**, ，**@publication**, ，分发代理在分发服务器在其下运行的 Windows 凭据 **@job_name** 和 **@job_password**, ，和此代理作业的计划。 有关详细信息，请参阅 [Specify Synchronization Schedules](../../../relational-databases/replication/specify-synchronization-schedules.md)。 这是执行后 [sp_addsubscription](../../../relational-databases/system-stored-procedures/sp-addsubscription-transact-sql.md)。 有关详细信息，请参阅 [Create a Push Subscription](../../../relational-databases/replication/create-a-push-subscription.md)。  
  
### 升级用于配置合并发布的脚本  
  
1.  （可选）在现有的脚本中，更新的执行 [sp_addmergepublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql.md) 若要设置实现新复制功能的参数的任何非默认值。  
  
2.  之后 [sp_addmergepublication & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql.md), ，执行 [sp_addpublication_snapshot & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql.md) 在发布数据库上的发布服务器。 指定 **@publication** 和在其下的快照代理运行的 Windows 凭据 **@job_name** 和 **@job_password**。 如果代理将使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 身份验证连接到发布服务器时，您还必须指定的值为 **0** 为 **@publisher_security_mode** 和 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 登录信息 **@publisher_login** 和 **@publisher_password**。 此操作将为发布创建一个快照代理作业。  
  
3.  （可选）更新的执行 [sp_addmergearticle & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql.md) 若要设置实现新复制功能的参数的任何非默认值。  
  
### 升级向合并发布添加订阅的脚本  
  
1.  执行完用于创建订阅的存储过程后，请确保执行用于创建合并代理作业的存储过程以同步订阅。 所用的存储过程将取决于订阅类型。  
  
    -   对于请求订阅，更新的执行 [sp_addmergepullsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql.md) 提供在其下运行合并代理在订阅服务器的 Windows 凭据 **@job_name** 和 **@job_password**。 这是执行后 [sp_addmergepullsubscription](../../../relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql.md)。 有关详细信息，请参阅 [Create a Pull Subscription](../../../relational-databases/replication/create-a-pull-subscription.md)。  
  
    -   对于推送订阅，执行 [sp_addmergepushsubscription_agent & #40;Transact SQL & #41;](../../../relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql.md) 在发布服务器上。 指定 **@subscriber**, ，**@subscriber_db**, ，**@publication**, ，合并代理在分发服务器上运行的 Windows 凭据 **@job_name** 和 **@job_password**, ，和此代理作业的计划。 有关详细信息，请参阅 [Specify Synchronization Schedules](../../../relational-databases/replication/specify-synchronization-schedules.md)。 这是执行后 [sp_addmergesubscription](../../../relational-databases/system-stored-procedures/sp-addmergesubscription-transact-sql.md)。 有关详细信息，请参阅 [Create a Push Subscription](../../../relational-databases/replication/create-a-push-subscription.md)。  
  
## 示例  
 下面是一个用于创建 Product 表的事务发布的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 此发布支持以排队更新作为故障转移的立即更新。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createtranpub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_1.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建事务发布的脚本进行更新，从而可以在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 此发布支持以排队更新作为故障转移的立即更新。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createtranpub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_2.sql)]  
  
## 示例  
 下面是一个可创建 Customers 表的合并发布的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createmergepub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_3.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建合并发布的脚本进行升级，从而可以在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createmergepub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_4.sql)]  
  
## 示例  
 下面是一个可创建对事务发布的推送订阅的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createtranpushsub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_5.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建对事务发布的推送订阅的脚本进行升级，从而可在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createtranpushsub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_6.sql)]  
  
## 示例  
 下面是一个可创建对合并发布的推送订阅的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createmergepushsub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_7.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建对合并发布的推送订阅的脚本进行升级，从而可在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createmergepushsub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_8.sql)]  
  
## 示例  
 下面是一个可创建事务发布的请求订阅的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createmergepushsub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_7.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建对事务发布的请求订阅的脚本进行升级，从而可在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createtranpullsub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_9.sql)]  
  
## 示例  
 下面是一个可创建对合并发布的请求订阅的 [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] 脚本示例。 为了方便阅读，删除了默认参数。  
  
 [!code-sql[HowTo#sp_createmergepullsub_NWpreupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_10.sql)]  
  
## 示例  
 下面的示例将对上一个用于创建对合并发布的请求订阅的脚本进行升级，从而可在 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 和更高版本中成功运行。 在此示例中显式声明了新参数的默认值。  
  
> [!NOTE]  
>  在运行时使用提供 Windows 凭据 **sqlcmd** 脚本变量。  
  
 [!code-sql[HowTo#sp_createmergepullsub_NWpostupgrade](../../../relational-databases/replication/codesnippet/tsql/upgrade-replication-scri_11.sql)]  
  
## 另请参阅  
 [创建发布](../../../relational-databases/replication/publish/create-a-publication.md)   
 [创建推送订阅](../../../relational-databases/replication/create-a-push-subscription.md)   
 [创建请求订阅](../../../relational-databases/replication/create-a-pull-subscription.md)   
 [查看和修改复制安全设置](../../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)   
 [MSSQL_ENG021797](../../../relational-databases/replication/mssql-eng021797.md)   
 [MSSQL_ENG021798](../../../relational-databases/replication/mssql-eng021798.md)   
 [复制系统存储过程概念](../../../relational-databases/replication/concepts/replication-system-stored-procedures-concepts.md)   
 [升级复制数据库](../../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
  