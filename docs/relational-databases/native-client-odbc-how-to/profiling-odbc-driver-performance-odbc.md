---
title: "分析 ODBC 驱动程序性能操作指南主题 (ODBC) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-how-to
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e6d7aed-28d2-419e-be6a-f60d3729bfd0
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0a55cfa991c0639539049e5d0cbbaa4f75c30944
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="profiling-odbc-driver-performance-odbc"></a>分析 ODBC 驱动程序性能 (ODBC)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC 驱动程序有两个特定于驱动程序的选项，用于对驱动程序的性能进行事件探查。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC 驱动程序可以在文件中记录性能统计信息。 日志文件是以制表符分隔的文件，它可以在支持以制表符分隔的文件（比如 Microsoft Excel）的任何电子表格中进行分析。  
  
 驱动程序也可以记录长时间运行的查询（在指定长度的时间内未从服务器获得响应的查询）。 这些查询可以随后由程序员和数据库管理员进行分析。  
  
## <a name="in-this-section"></a>本節內容  
  
-   [配置文件驱动程序的性能数据 &#40; ODBC &#41;](../../relational-databases/native-client-odbc-how-to/profiling-odbc-driver-performance-data.md)  
  
-   [记录运行时间较长查询 &#40; ODBC &#41;](../../relational-databases/native-client-odbc-how-to/profiling-odbc-driver-performance-data-log-long-running-queries.md)  
  
## <a name="see-also"></a>另请参阅  
 [ODBC 操作指南主题](../../relational-databases/native-client-odbc-how-to/odbc-how-to-topics.md)  
  
  
