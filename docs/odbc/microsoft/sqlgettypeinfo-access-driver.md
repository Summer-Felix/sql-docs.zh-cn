---
title: "SQLGetTypeInfo （Access 驱动程序） |Microsoft 文档"
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
- Access driver [ODBC], SQLGetTypeInfo
- SQLGetTypeInfo function [ODBC], Access Driver
ms.assetid: a28b16eb-ca36-4297-9297-ecd7c107a84e
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c9b9fba89b9752af4fbfb19bfcd1f858058733d3
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="sqlgettypeinfo-access-driver"></a>SQLGetTypeInfo （Access 驱动程序）
> [!NOTE]  
>  本主题提供访问特定于驱动程序信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 生成的表中返回的类型 (TYPE_NAME) 名称**SQLGetTypeInfo**将是最常使用的数据源的名称。  
  
 SQL_ALL_EXCEPT_LIKE 将返回可搜索的列中的字节，计数器、 双精度型、 单、 long 类型的值和短数据类型。 （如功能可以通过将值转换为使用 ODBC 规范的转换函数，然后执行比较的字符。）
