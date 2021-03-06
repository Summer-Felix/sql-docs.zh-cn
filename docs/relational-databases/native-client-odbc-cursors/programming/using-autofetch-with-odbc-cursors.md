---
title: "使用 ODBC 游标自动提取 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-cursors
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9b0dd154b1f8a4dd791dfc111dacaa750a66da96
ms.sourcegitcommit: a0aa5e611a0e6ebb74ac1e2f613e8916dc7a7617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2018
---
# <a name="using-autofetch-with-odbc-cursors"></a>通过 ODBC 游标使用自动提取
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  连接到的实例时[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序支持自动提取选项，当使用任何服务器游标类型。 自动提取， **SQLExecute**或**SQLExecDirect**打开游标的函数还具有一种隐式[SQLFetchScroll](../../../relational-databases/native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) 函数。 组成第一个行集的行将作为语句执行的一部分返回给绑定应用程序变量，并通过网络将另一个往返保存到服务器。 [SQLGetData](../../../relational-databases/native-client-odbc-api/sqlgetdata.md)时不支持自动提取选项启用的; 结果集中的列必须绑定到程序变量。  
  
 应用程序通过对 SQL_CO_AF 设置特定于驱动程序的 SQL_SOPT_SS_CURSOR_OPTIONS 语句属性请求自动提取。  
  
## <a name="see-also"></a>另请参阅  
 [光标编程的详细信息 &#40; ODBC &#41;](../../../relational-databases/native-client-odbc-cursors/programming/cursor-programming-details-odbc.md)  
  
  
