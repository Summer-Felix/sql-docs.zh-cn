---
title: "存储过程参数限制 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stored procedures [ODBC], ODBC driver for Oracle
- ODBC driver for Oracle [ODBC], stored procedures
ms.assetid: 8b804bcf-4cce-4e6f-aa45-00bab9ef9921
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9755f10bd5eb1bf88549bb2fd417049d45b59c6a
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="stored-procedure-parameter-limitations"></a>存储的过程参数限制
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 相反，使用提供的 Oracle 的 ODBC 驱动程序。  
  
 当运行 Oracle 存储利用 10 的过程或多个输出参数时，存储的过程调用将失败，从而导致访问冲突或 ActiveX 数据对象 (ADO) 错误。 这可以使用 Microsoft ODBC Driver for Oracle 具有发生版本 8.0.4.0.0 和 8.0.4.0.4 Oracle 客户端软件。  
  
 若要解决此问题，Oracle 客户端软件必须是升级到版本 8.0.4.2.0 或更高版本。 有关详细信息的联系人 Oracle Corporation[修补程序](../../odbc/microsoft/oracle-software-patches.md)。  
  
> [!NOTE]  
>  Oracle 客户端软件版本 8.0.3.0.0 的早期版本时不会出现此问题。
