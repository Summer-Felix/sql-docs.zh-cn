---
title: "诊断 |Microsoft 文档"
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
- diagnostic information [ODBC]
- functions [ODBC], diagnostic information
- diagnostic information [ODBC], about diagnostic information
ms.assetid: 450abd88-90a1-4fbc-b417-8efbdd8e1dea
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: efbc34be3dc532b329863a98305952d90adcc9f5
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostics"></a>诊断
ODBC 中的函数返回了两种方式的诊断信息。 返回代码指示的总体成功或失败的函数，诊断记录提供有关函数的详细的信息。 至少一个诊断记录-标头记录 — 即使如果函数成功，则返回。  
  
 诊断信息用于在开发期间捕获硬编码的 SQL 语句中的编程错误，如无效的句柄和语法错误。 它用于在运行时中捕获用户输入的 SQL 语句中的运行时错误和警告，如数据截断、 访问冲突和语法错误。  
  
 本部分包含以下主题。  
  
-   [返回代码](../../../odbc/reference/develop-app/return-codes-odbc.md)  
  
-   [诊断记录](../../../odbc/reference/develop-app/diagnostic-records.md)  
  
-   [使用 SQLGetDiagRec 和 SQLGetDiagField](../../../odbc/reference/develop-app/using-sqlgetdiagrec-and-sqlgetdiagfield.md)  
  
-   [实现 SQLGetDiagRec 和 SQLGetDiagField](../../../odbc/reference/develop-app/implementing-sqlgetdiagrec-and-sqlgetdiagfield.md)  
  
-   [诊断处理示例](../../../odbc/reference/develop-app/diagnostic-handling-examples.md)
