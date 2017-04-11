---
title: "Broker:Corrupted Message 事件类 | Microsoft Docs"
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
  - "Broker:Corrupted Message 事件类"
ms.assetid: 084bf198-2138-438e-bdc7-4ff1e04300f7
caps.latest.revision: 23
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 23
---
# Broker:Corrupted Message 事件类
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将创建一个 **Broker:Corrupted Message** 事件。  
  
## Broker:Corrupted Message 事件类的数据列  
  
|数据列|类型|说明|列号|可筛选|  
|-----------------|----------|-----------------|-------------------|----------------|  
|**ApplicationName**|**nvarchar**|客户端应用程序的名称，该客户端应用程序创建了指向 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]实例的连接。 此列由应用程序传递的值填充，而不是由所显示的程序名填充。|10|是|  
|**BigintData1**|**bigint**|此消息的序列号。|52|是|  
|**BinaryData**|**图像**|消息的正文。|2|是|  
|**ClientProcessID**|**int**|由主机分配给正在运行客户端应用程序的进程的 ID。 如果客户端提供了客户端进程 ID，则填充此数据列。|9|是|  
|**DatabaseID**|**int**|由 USE *database* 语句指定的数据库的 ID；如果未对给定实例发出 USE *database* 语句，则为默认数据库的 ID。 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 数据列而且服务器可用，则 **ServerName** 将显示数据库名。 可使用 DB_ID 函数来确定数据库的值。|3|是|  
|**错误**|**int**|事件中文本的 **sys.messages** 的消息 ID 号。|31|是|  
|**EventClass**|**int**|捕获的事件类的类型。 对于 **Broker:Corrupted Message** ，始终是 **161**。|27|是|  
|**EventSequence**|**int**|此事件的序列号。|51|是|  
|**FileName**|**nvarchar**|远程端点的网络地址。|36|是|  
|**GUID**|**uniqueidentifier**|损坏的消息所属会话的会话 ID。 此标识符将作为消息的一部分进行传输，并在会话双方之间共享。|54|是|  
|**Host Name**|**nvarchar**|正在运行客户端程序的计算机的名称。 如果客户端提供了主机名，则填充此数据列。 若要确定主机名，请使用 HOST_NAME 函数。|8|是|  
|**IntegerData**|**int**|此消息的片段数。|25|是|  
|**IsSystem**|**int**|指示事件是发生在系统进程中还是发生在用户进程中。 1 = 系统，0 = 用户。|60|是|  
|**LoginSid**|**图像**|已登录用户的安全标识号 (SID)。 服务器中的每个登录名都具有唯一的 SID。|41|是|  
|**NTDomainName**|**nvarchar**|用户所属的 Windows 域。|7|是|  
|**NTUserName**|**nvarchar**|拥有生成此事件的连接的用户的名称。|6|是|  
|**ObjectName**|**nvarchar**|会话另一方的服务名称和远程数据库用来连接至此数据库的连接字符串。|34|是|  
|**RoleName**|**nvarchar**|接收此消息的端点的角色。 取下列值之一。<br /><br /> **initiator**：接收端点为会话的发起方。<br /><br /> **target**：接收端点为会话的目标。|38|是|  
|**ServerName**|**nvarchar**|所跟踪的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的名称。|26|是|  
|**Severity**|**int**|导致 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 删除消息的错误的严重性。|29|是|  
|**SPID**|**int**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 为客户端所关联的进程分配的服务器进程 ID。|12|是|  
|**StartTime**|**datetime**|事件（如果有）的开始时间。|14|是|  
|**State**|**int**|指示 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 源代码中生成该事件的位置。 可能生成此事件的每个位置都有不同的状态代码。 Microsoft 支持工程师可使用此状态代码查找生成该事件的位置。|30|是|  
|**TextData**|**ntext**|检测到的损坏说明。|1|是|  
|**Transaction ID**|**bigint**|系统为事务分配的 ID。|4|是|  
  
 此事件的 **TextData** 列包含一条描述消息问题的消息。  
  
  