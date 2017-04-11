---
title: "分发代理安全性 | Microsoft Docs"
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
  - "sql13.rep.security.DA.f1"
helpviewer_keywords: 
  - "“分发代理安全性”对话框"
ms.assetid: de40cc21-2e58-4464-9be7-b5b90c925e9b
caps.latest.revision: 25
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 25
---
# 分发代理安全性
  使用 **“分发代理安全性”** 对话框可以指定用于运行分发代理的 Windows 帐户。 对于推送订阅，分发代理在分发服务器上运行；对于请求订阅，分发代理在订阅服务器上运行。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 帐户也称为“进程帐户 ”，因为代理进程是在此帐户下运行。 该对话框中可用的其他选项取决于访问对话框的方式：  
  
-   如果从新建订阅向导访问该对话框，您还可以指定分发代理在建立与订阅服务器（对于推送订阅）或分发服务器（对于请求订阅）的连接时所使用的上下文。 可以通过模拟 Windows 帐户，或在指定的 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户的上下文中建立连接。  
  
-   如果对话框中访问从 **订阅属性** 对话框框中，指定在其下分发代理建立连接通过单击属性按钮的上下文 (**...**) 中 **订阅服务器连接** 或 **分发服务器连接** 该对话框中的一行。 有关访问 **订阅属性** 对话框中，请参阅 [查看和修改推送订阅属性](../../relational-databases/replication/view-and-modify-push-subscription-properties.md) 和操作方法︰ [查看和修改请求订阅属性](../../relational-databases/replication/view-and-modify-pull-subscription-properties.md)。  
  
 所有帐户必须是有效的，并且为每个帐户指定了正确的密码。 在运行代理之前不会对帐户和密码进行验证。  
  
## 选项  
 **进程帐户**  
 输入运行分发代理所使用的 Windows 帐户：  
  
-   对于推送订阅，该帐户必须：  
  
    -   至少是属于 **db_owner** 分发数据库中的固定的数据库角色。  
  
    -   是发布访问列表 (PAL) 的成员。  
  
    -   对快照共享拥有读取权限。  
  
    -   如果是对非 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器的订阅，必须对订阅服务器的 OLE DB 访问接口的安装路径具有读取权限。  
  
-   对于请求订阅，该帐户必须至少是成员的 **db_owner** 订阅数据库中的固定的数据库角色。  
  
 如果在建立连接时模拟进程帐户，则还需要其他权限。 请参阅下面的 **“连接到分发服务器”** 和 **“连接到订阅服务器”** 部分。  
  
 **进程帐户** 对请求订阅，不能指定 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], ，这是因为分发代理不运行的实例上 [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]。  
  
 **密码** 和 **确认密码**  
 输入 Windows 帐户的密码。  
  
 **连接到分发服务器**  
 对于推送订阅，连接到分发服务器始终通过模拟中指定的帐户建立 **进程帐户** 文本框。  
  
 对于请求订阅，请选择分发代理是通过模拟在 **“进程帐户”** 文本框中指定的帐户，还是通过使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户来建立与分发服务器的连接。 如果选择使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户，请输入 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名和密码。  
  
> [!NOTE]  
>  建议您选择模拟 Windows 帐户，而不要使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户。  
  
 连接所用的 Windows 帐户或 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户必须：  
  
-   是 PAL 的成员。  
  
-   对快照共享拥有读取权限。  
  
 **连接到订阅服务器**  
 对于请求订阅，订阅服务器上的连接始终通过模拟中指定的帐户建立 **进程帐户** 文本框。  
  
 对于推送订阅，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器和非 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器的选项是不同的：  
  
-   对于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器：请选择分发代理是通过模拟在 **“进程帐户”** 文本框中指定的帐户，还是通过使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户来建立与订阅服务器的连接。 如果选择使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户，请输入 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名和密码。  
  
    > [!NOTE]  
    >  建议您选择模拟 Windows 帐户，而不要使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 帐户。  
  
     Windows 帐户或 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 用于连接到订阅服务器上的帐户必须至少是属于 **db_owner** 订阅数据库中的固定的数据库角色。  
  
-   对于非 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器，请在订阅服务器上指定当分发代理连接到订阅服务器时所使用的数据库登录名。 该登录名应具有足够的权限以在订阅数据库中创建对象。 有关配置非[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器，请参阅 [为非 SQL Server 订阅服务器创建订阅](../../relational-databases/replication/create-a-subscription-for-a-non-sql-server-subscriber.md)。  
  
 **其他连接选项**  
 仅限非 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 订阅服务器。 以连接字符串的形式为订阅服务器指定所有连接选项（Oracle 不需要指定附加选项）。 应使用分号分隔每个选项。 下面是 IBM DB2 连接字符串的示例（使用分行符是为了提高可读性）：  
  
```  
Provider=DB2OLEDB;Initial Catalog=MY_SUBSCRIBER_DB;Network Transport Library=TCP;Host CCSID=1252;  
PC Code Page=1252;Network Address=MY_SUBSCRIBER;Network Port=50000;Package Collection=MY_PKGCOL;  
Default Schema=MY_SCHEMA;Process Binary as Character=False;Units of Work=RUW;DBMS Platform=DB2/NT;  
Persist Security Info=False;Connection Pooling=True;  
```  
  
 字符串中的大多数选项都特定于正在配置的 DB2 服务器，但是应始终将“将二进制数作为字符处理”  选项设置为 **False**。 需要为“初始目录”  选项指定一个值以标识订阅数据库。 有关详细信息，请参阅 [IBM DB2 Subscribers](../../relational-databases/replication/non-sql/ibm-db2-subscribers.md)。  
  
## 另请参阅  
 [管理复制中的登录名和密码](../../relational-databases/replication/security/manage-logins-and-passwords-in-replication.md)   
 [复制代理安全性模式](../../relational-databases/replication/security/replication-agent-security-model.md)   
 [复制代理概述](../../relational-databases/replication/agents/replication-agents-overview.md)   
 [复制安全最佳实践](../../relational-databases/replication/security/replication-security-best-practices.md)   
 [订阅发布](../../relational-databases/replication/subscribe-to-publications.md)  
  
  