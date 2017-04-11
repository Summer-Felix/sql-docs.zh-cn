---
title: "客户端协议 - TCP/IP 属性（“协议”选项卡） | Microsoft Docs"
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
  - "TCP/IP [SQL Server], 客户端协议"
  - "客户端协议 [SQL Server]"
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
caps.latest.revision: 25
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 25
---
# 客户端协议 - TCP/IP 属性（“协议”选项卡）
  在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 配置管理器中，可使用“TCP/IP 属性”对话框的“协议”选项卡查看或指定下列选项。 若要连接到另一个端口，可以在 **“默认端口”** 框中键入端口号。 有关连接字符串的详细信息，请参阅[使用 TCP IP 创建有效的连接字符串](../../tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)。  
  
## 选项  
 **默认端口**  
 指定 TCP/IP Net-library 在尝试连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的目标实例时将使用的端口。 默认值端口为 1433。  
  
 连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的默认实例时，客户端将使用此值。 如果已经将默认实例配置为侦听另一个端口，则要将此值更改为该端口号。  
  
 连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的命名实例时，客户端将尝试从在服务器上运行的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser 服务获取端口号。 如果 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser 服务没有运行，则必须通过此设置或作为连接字符串的一部分提供端口号。  
  
 **已启用**  
 可能的值为“是”和“否”。  
  
 **Keep Alive**  
 此参数（毫秒）控制 TCP 通过发送 **KEEPALIVE** 包尝试验证空闲连接是否仍保持原样的频率。 默认值为 30000 毫秒。  
  
 **保持活动状态的间隔**  
 此参数（毫秒）确定重新传输 **KEEPALIVE** 直到接收到响应的间隔。 默认值为 1000 毫秒。  
  
## 另请参阅  
 [选择网络协议](../Topic/Choosing%20a%20Network%20Protocol.md)   
 [新建别名（“别名”选项卡）](../../tools/configuration-manager/new-alias-alias-tab.md)   
 [\<别名>属性（“别名”选项卡）](../../tools/configuration-manager/alias-properties-alias-tab.md)  
  
  