---
title: "SQLSetEnvAttr 和光标库 |Microsoft 文档"
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
helpviewer_keywords: SQLSetEnvAttr function [ODBC], Cursor Library
ms.assetid: 59cc8eae-09ae-4796-869a-c5806488ae83
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0ba91a55e578cfdadd012dcd786633b95387f42c
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="sqlsetenvattr-and-the-cursor-library"></a>SQLSetEnvAttr 和游标库
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 避免在新的开发工作中使用此功能，并计划修改当前使用此功能的应用程序。 Microsoft 建议使用驱动程序的游标功能。  
  
 本主题讨论使用**SQLSetEnvAttr**具有的是光标库函数。 有关常规信息**SQLSetEnvAttr**，请参阅[SQLSetEnvAttr 函数](../../../odbc/reference/syntax/sqlsetenvattr-function.md)。  
  
 游标库不受 SQL_ATTR_ODBC_VERSION 环境属性，而不考虑应用程序版本或驱动程序版本的设置。
