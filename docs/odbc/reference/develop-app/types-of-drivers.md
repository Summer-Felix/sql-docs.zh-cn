---
title: "类型的驱动程序 |Microsoft 文档"
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
- driver compatibility issues [ODBC]
- ODBC drivers [ODBC], backward compatibility
- backward compatibility [ODBC], application and driver compatibility
- compatibility [ODBC], application and driver compatibility
ms.assetid: 864c53c1-b68a-48b6-b6bc-5ecb520bb9dc
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c2068bb92d1aaa00debc46277c117d4134091666
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-drivers"></a>类型的驱动程序
ODBC 驱动程序可以进行分类，如下所示：  
  
-   **32 位 ODBC 2。**  
     ***x*驱动程序**的 32 位驱动程序的：  
  
    -   导出仅 ODBC 2*.x*函数。  
  
    -   出现 ODBC 2。*x*行为的行为更改。  
  
-   **ISO 和打开组符合驱动程序**的 32 位驱动程序的：  
  
    -   导出 Open Group 或 ISO CLI 文档中记录的所有函数。 这将 ODBC 中包括一些函数已弃用。  
  
    -   演示 ODBC 3.0 行为的行为更改。  
  
    -   不一定会通过 ODBC 3.0 驱动程序管理器。  
  
-   **ODBC 3.0 驱动程序**的 32 位驱动程序的：  
  
    -   导出仅函数中减去 ODBC 3.0 弃用函数。  
  
    -   它能够暴露 ODBC 2。*x*行为或 ODBC 3.0 相关的行为时会行为的变化，基于 SQL_ATTR_APP_ODBC_VERSION 环境属性。  
  
-   **ODBC 3.5 （或更高版本） ANSI 驱动程序**的 32 位驱动程序的：  
  
    -   导出仅函数中减去 ODBC 3.5 过时的函数。  
  
    -   它能够暴露 ODBC 2。*x*行为或 ODBC 3.0 行为或与行为的变化，有关 ODBC 3.5 行为基于 SQL_ATTR_APP_ODBC_VERSION 环境属性。  
  
-   **ODBC 3.5 （或更高版本） Unicode 驱动程序**的 32 位驱动程序的：  
  
    -   支持 ODBC 3.5 ANSI 驱动程序的所有的功能。  
  
    -   将导出的所有 ODBC 字符串 Api 的 Unicode 版本。  
  
    -   可以存储和处理数据源上的 Unicode 数据。  
  
> [!NOTE]  
>  16 位 ODBC 驱动程序不会直接使用 ODBC 3。*x*驱动程序管理器。 但是，很可能使用 2.0 ODBC 驱动程序管理器，它随后 thunk 最多 3 个 16 位驱动程序。*x*驱动程序管理器。
