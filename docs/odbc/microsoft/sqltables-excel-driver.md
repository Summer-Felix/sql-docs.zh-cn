---
title: "SQLTables （Excel 驱动程序） |Microsoft 文档"
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
- Excel driver [ODBC], SQLTables
- SQLTables function [ODBC], Excel Driver
ms.assetid: 9410b686-4b5b-4b51-b5ef-f9d2e7a48faa
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 083f0813418dc366f14acc11be79c9eb68f5550d
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="sqltables-excel-driver"></a>SQLTables （Excel 驱动程序）
> [!NOTE]  
>  本主题提供 Excel 驱动程序相关的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
|参数|注释|  
|--------------|--------------|  
|*szTableOwner*|唯一有效参数*szTableOwner*是 NULL，因为无驱动程序支持所有者名称。 与*szTableOwner*设置为 NULL，返回所有表。 TABLE_OWNER 列中返回 NULL。|  
|*szTableQualifier*|Microsoft Excel 3.0 或 4.0 驱动程序使用时，如果调用**SQLTables**值*szTableQualifier* ，不是现有表的名称，该驱动程序将创建具有该名称的表。<br /><br /> 在 TABLE_QUALIFIER 列中， **SQLTables**将返回目录的路径。|  
|*SzTableType*|Microsoft Excel 3.0 或 4.0，对于"表"是唯一支持的表类型。<br /><br /> 对于更高版本的 Microsoft Excel 文件中，表名称 （表与端上的"$"），则返回"系统表"并为工作表中的表返回"TABLE"。|
