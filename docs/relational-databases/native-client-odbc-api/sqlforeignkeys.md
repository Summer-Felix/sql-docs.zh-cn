---
title: SQLForeignKeys | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c8d6259b3d7325d3b0ebfb133a918e6fb64a5d7c
ms.sourcegitcommit: a0aa5e611a0e6ebb74ac1e2f613e8916dc7a7617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2018
---
# <a name="sqlforeignkeys"></a>SQLForeignKeys
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 通过外键约束机制支持级联更新和删除操作。 如果在 FOREIGN KEY 约束的 ON UPDATE 和/或 ON DELETE 子句中指定 CASCADE 选项，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 将为 UPDATE_RULE 和/或 DELETE_RULE 列返回 SQL_CASCADE。 如果未在 FOREIGN KEY 约束的 ON UPDATE 和/或 ON DELETE 子句中指定 NO ACTION 选项，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 则为 UPDATE_RULE 和/或 DELETE_RULE 列返回 SQL_NO_ACTION。  
  
 在任何中存在无效的值时**SQLForeignKeys**参数， **SQLForeignKeys**返回 SQL_SUCCESS 上执行。 **SQLFetch**返回 SQL_NO_DATA，在这些参数中使用了无效值。  
  
 **SQLForeignKeys**可以执行对静态服务器游标。 尝试执行**SQLForeignKeys**返回的可更新的 （动态或键集） 游标中的 SQL_SUCCESS_WITH_INFO 指示游标类型已更改。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序支持为链接服务器上的表报表信息由接受的两部分名称*FKCatalogName*和*PKCatalogName*参数： *Linked_Server_Name.Catalog_Name*。  
  
## <a name="see-also"></a>另请参阅  
 [SQLForeignKeys 函数](http://go.microsoft.com/fwlink/?LinkId=59344)   
 [ODBC API 实现详细信息](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
