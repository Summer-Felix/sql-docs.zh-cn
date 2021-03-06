---
title: "VARCHAR 列大小 （适用于 Oracle 的 ODBC 驱动程序） |Microsoft 文档"
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
- data types [ODBC], ODBC driver for Oracle
- varchar column size [ODBC]
- ODBC driver for Oracle [ODBC], data types
ms.assetid: eb4cb410-3d00-4251-8c5e-a06f36c4dac7
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6002a906b2796cbc2f9f50519c11e846455b3ce9
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="varchar-column-size-odbc-driver-for-oracle"></a>VARCHAR 列大小 （适用于 Oracle 的 ODBC 驱动程序）
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 相反，使用提供的 Oracle 的 ODBC 驱动程序。  
  
 在 Oracle8，VARCHAR 列的最大大小已增加从 2000年到 4000 字节。 Oracle 7.3.x 版客户端软件就无法将绑定的参数值大于 2000 个字节。 因此，如果使用超过 2000 个字节的 VARCHAR 列创建表时，将无法执行参数化的插入、 更新、 删除和对其具有超过 2000年字节的限制的客户端软件的数据的查询。 用于 Oracle 的 ODBC 驱动程序和适用于 Oracle OLE DB 提供程序都使用参数化的插入、 更新、 删除和查询，因为它们将在此情况下报告 ORA 01026 错误。 在强制执行由 Oracle 客户端软件的限制内的数据起作用。 若要避免此 2000年字节的限制，你必须将客户端软件升级到 Oracle8 (8.0.4.1.1c 或更高版本)。
