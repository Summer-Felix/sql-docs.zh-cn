---
title: "到 c： 日期 SQL |Microsoft 文档"
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
- converting data from SQL to C types [ODBC], date
- date data type [ODBC]
- data conversions from SQL to C types [ODBC], date
ms.assetid: 703c7960-9cf4-4d7a-9920-53b29c184f97
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 87a62501d4d03073d8c43b2f791ceffeec9b0b30
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="sql-to-c-date"></a>到 c： 日期的 SQL
日期 ODBC SQL 数据类型的标识符是：  
  
 SQL_TYPE_DATE  
  
 下表显示 ODBC C 日期 SQL 数据可能转换到的目标的数据类型。 列和表中的条款的说明，请参阅[转换数据从 SQL C 数据类型到](../../../odbc/reference/appendixes/converting-data-from-sql-to-c-data-types.md)。  
  
|C 类型标识符|测试|**TargetValuePtr*|**StrLen_or_IndPtr*|SQLSTATE|  
|-----------------------|----------|------------------------|----------------------------|--------------|  
|SQL_C_CHAR|*BufferLength* > 字符字节长度<br /><br /> 11 < = *BufferLength* < = 字符字节长度<br /><br /> *BufferLength* < 11|data<br /><br /> 截断的数据<br /><br /> 未定义|10<br /><br /> 以字节为单位的数据的长度<br /><br /> 未定义|不适用<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_WCHAR|*BufferLength* > 字符长度<br /><br /> 11 < = *BufferLength* < = 字符长度<br /><br /> *BufferLength* < 11|data<br /><br /> 截断的数据<br /><br /> 未定义|10<br /><br /> 以字符为单位的数据的长度<br /><br /> 未定义|不适用<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_BINARY|数据的字节长度 < = *BufferLength*<br /><br /> 数据的字节长度 > *BufferLength*|data<br /><br /> 未定义|以字节为单位的数据的长度<br /><br /> 未定义|不适用<br /><br /> 22003|  
|SQL_C_TYPE_DATE|无 [a]|data|6 [c]|不适用|  
|SQL_C_TYPE_TIMESTAMP|无 [a]|数据 [b]|16 [c]|不适用|  
  
 [a] 的值*BufferLength*忽略此转换。 该驱动程序假定的大小 **TargetValuePtr*是 C 数据类型的大小。  
  
 [时间戳结构 b] 上，时间字段设置为零。  
  
 [c] 这是对应的 C 数据类型的大小。  
  
 当日期 SQL 数据转换为字符 C 数据时，生成的字符串是在"*yyyy*-*mm*-*dd*"格式。 此格式不受 Windows® 国家/地区设置。
