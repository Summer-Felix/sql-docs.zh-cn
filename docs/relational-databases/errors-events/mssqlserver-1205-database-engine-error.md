---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: afbc0f15e52f470d88514a4e3cf865447a4a64fd
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver1205"></a>MSSQLSERVER_1205
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|1205|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|LK_VICTIM|  
|消息正文|事务(进程 ID %d)与另一个进程被死锁在 %.*ls 资源上，并且已被选作死锁牺牲品。 重新运行该事务。|  
  
## <a name="explanation"></a>解释  
在不同事务中访问资源的顺序冲突，从而导致死锁。 例如：  
  
-   Transaction1 更新 **Table1.Row1**，而 Transaction2 更新 **Table2.Row2**。  
  
-   Transaction1 尝试更新 **Table2.Row2**，但因 Transaction2 尚未提交而被阻止。  
  
-   Transaction2 现在尝试更新 **Table1.Row1**，但因 Transaction1 尚未提交而被阻止。  
  
-   之所以出现死锁，是因为 Transaction1 在等待 Transaction2 完成，但 Transaction2 在等待 Transaction1 完成。  
  
系统将检测到此死锁，并将所涉及的事务之一选作“牺牲品”，然后发出此消息，回滚牺牲品的事务。  
  
## <a name="user-action"></a>用户操作  
重新执行事务。 您还可以修订应用程序以避免死锁。 可以重试被选作牺牲品的事务，而且很可能成功，具体取决于同时执行的操作。  
  
为防止或避免出现死锁，请考虑让所有的事务按相同顺序（先访问 **Table1**，然后访问 **Table2**）访问行；这样，虽然可能会出现阻止，但不会出现死锁。  
  
